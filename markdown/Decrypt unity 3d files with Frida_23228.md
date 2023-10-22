## Post #1
- Username: Joschka
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2020-12-27T16:01:24+00:00
- Post Title: Decrypt unity 3d files with Frida

If you have a unity game that you can't figure out the encryption for you can use this method to have the game decrypt the files for you.
Things you will need.
1. rooted android phone.
2. install python on your pc and then install Frida-tools (pip install frida-tools)
3. Frida server on your android phone.
4. Ida pro or ghidra to find the functions you want.

[https://frida.re/docs/android/](https://frida.re/docs/android/)

Step1.
load your unity games libil2cpp.so file into your disassembler of choice and then apply names to the functions using Il2CppDumper.
[https://github.com/Perfare/Il2CppDumper](https://github.com/Perfare/Il2CppDumper)
just load it into ida or ghidra and after it is finished analyzing it run the script that Il2CppDumper gave you.

Step2.
Find the function that is doing the decryption.
This can be found in unity games by looking at the LoadAssetBundle functions.
Lets look at this example.
com.tencent.hlfish
[https://www100.zippyshare.com/v/XBTE3aAV/file.html](https://www100.zippyshare.com/v/XBTE3aAV/file.html)
So if I search for LoadAssetBundleSync in the function window I get 1 result

and if i look at the pseudo code generated i see this function.

HLArcade_HLUtils__CreateABFromEncryptFile
Now we go into this function we will notice 2 important things.

The first thing is the load from memory function.
UnityEngine_AssetBundle__LoadFromMemory_20449300
All unity games decrypt their files into memory then load them from memory so we can see its taking in v7.
And if we go up a little bit we see v7 being created from HLArcade_HLFileCryptNew__DecryptFileNew
So lets hop into this function.

looks like its taking a string (file path) and then decrypting it for us so lets see what it does when it runs.
you can see in the bottom left the function offset 00683014
so we are going to use Frida to see what its doing

Step3.
Install the apk onto your phone.
now use adb to setup frida server (Magisk can do this part as a plugin for you if you have it installed).
[https://github.com/frida/frida/releases](https://github.com/frida/frida/releases) frida-server-14.2.2-android-arm64.xz (extract this with 7z)
adb push c:\frida-server-14.2.2-android-arm64 /data/local/tmp/frida-server
now do adb shell
then type su to change to root mode
now change to the directory /data/local/tmp
cd /data/local/tmp
and make Frida server executable
chmod 777 ./frida-server
now run Frida server
./frida-server

Step4 
test and make sure you can see your device in Frida
(Frida installs itself into the scripts directory in your python install)
frida-ps.exe -U
and you should see the running programs on your phone.


Step5
lets launch or game and attach to it with Frida.
frida.exe -U -f com.tencent.hlfish
and it should show a black screen on your phone and 'your command prompt should look like this.

if you typed %resume the game would start up like normal with Frida attached but we want o write our monitor code first.

```
var nativeFuncAddr = 0x00683014; //
 
Interceptor.attach(Module.findExportByName(null, "dlopen"), {
    onEnter: function(args) {
        this.lib = Memory.readUtf8String(args[0]);
        console.log("dlopen called with: " + this.lib);
    },
    onLeave: function(retval) {
        if (this.lib.endsWith(moduleName)) {
            console.log("ret: " + retval);
            var baseAddr = Module.findBaseAddress(moduleName);
            Interceptor.attach(baseAddr.add(nativeFuncAddr), {
                onEnter: function(args) {
                    console.log("[-] hook invoked");
                    //var keyDump = Memory.readByteArray(args[0], 0x300);
                    //var keyDump2 = Memory.readByteArray(args[1], 0x300);
                    //console.log(hexdump(keyDump));
                    //console.log(hexdump(keyDump2));
                    console.log(JSON.stringify({
                        a0: args[0],
                        a1: args[1],
                        a2: args[2]
                    }, null, '\t'));
                },
        onLeave: function (retval) {
        console.log(retval);
        //var keyDump2 = Memory.readByteArray(retval, 0x300);
        //console.log(hexdump(keyDump2));
        }
            });
        }
    }
});

```

if you paste this in it should look like this

if you see any red text you did something wrong and check your commands again.
This code is hooking when libil2cpp.so is loaded then hooking the function at address 0x00683014 in that .so and printing its arguments and return value.
so lets type %resume and see if we get a hit.

We found the module loading.

and we hooked the function.
so the parameters passed to the function are.
        "a0": "0x0",
        "a1": "0xb1a845f0",
        "a2": "0xc62c3b84"
so the first parameter is 0
the 2nd is a pointer to the file name
and the 3rd is a pointer to the file size that this function writes there.
and the return value is a pointer to the decrypted asset bundle in memory.
we can look at these using this command
Memory.readByteArray(new NativePointer(0xb1a845f0),0x100);
hey look the first file it decrypts

and if we look at the next part
its just all 0's where it wants to write the size to.
and if we look at the return address.

bingo a unity header

so now we just need a function to create our string for us for the file we want to decrypt.
if we search for CreateString it comes right up.
System_String_o *__cdecl System_String__CreateString(System_String_o *this, int8_t *value, const MethodInfo *method)


so lets try creating a string.
You will get an error if you do this outside the hook code but it will still work

```
var moduleBase = Module.findBaseAddress(moduleName);
var careate_str = ptr(parseInt(moduleBase) +   0x00FCA590 ) 
var careate_str_f = new NativeFunction(careate_str, 'pointer' , [ 'pointer' , 'pointer' ]); 
var root = '/storage/emulated/0/Android/data/com.tencent.hlfish/files/AssetBundles/'
var path = 'kernel' 
var path_str_utf8 = Memory.allocUtf8String(root + path) 
var path_str = careate_str_f(new NativePointer(path_str_utf8), path_str_utf8);

Memory.readByteArray(new NativePointer(path_str), 0x100);

```


so lets try decrypting that file.
So restart the game with Frida and just type %resume till you are at the logon page.
now lets decrypt this file

we see the file is 0x14F2AC in size so les dump it

```
var moduleName = "libil2cpp.so";
var moduleBase = Module.findBaseAddress(moduleName);
var careate_str = ptr(parseInt(moduleBase) +   0x00FCA590 )
var careate_str_f = new NativeFunction(careate_str, 'pointer' , [ 'pointer' , 'pointer' ]);
var root = '/storage/emulated/0/Android/data/com.tencent.hlfish/files/AssetBundles/'
var path = 'kernel'
var path_str_utf8 = Memory.allocUtf8String(root + path)
var path_str = careate_str_f(new NativePointer(path_str_utf8), path_str_utf8);

Memory.readByteArray(new NativePointer(path_str), 0x100);

//Construction parameter 3
var arg3_ptr = Memory.alloc( 0x4 )
Memory.writeInt(arg3_ptr, 0x0 )


//decrypt
var decrypt = parseInt(moduleBase) +  0x00683014;
var decrypt_f = new NativeFunction(ptr(decrypt), 'pointer', ['int','pointer', 'pointer']);
var retval = decrypt_f(0,path_str, arg3_ptr)
var file_bgein = retval.add(0x10)

//dump
var dump = Memory.readByteArray(new NativePointer(file_bgein), 0x14F2AC);
var file = new File("/storage/emulated/0/Android/data/com.tencent.hlfish/files/AssetBundles/kernel.unity3d","w"); 
file.write(dump);
file.close();

```


now lets grab our dumped file
now I have all the games logic lua files.
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-12-29T05:11:57+00:00
- Post Title: Decrypt unity 3d files with Frida

Thanks to chrrox, a very kind tutorial!
This is clearly the best commentary ever. It's more polite about frida than any site or doc, and the test scripts are very effective.
It will be possible to output key and iv by adjusting arg and changing the export of the file to a string.

But unfortunately, frida doesn't currently support the Android emulator, so you need a real device.
[https://github.com/frida/frida/issues/1191](https://github.com/frida/frida/issues/1191)
I actually tried it and succeeded in executing frida-server.
However, as mentioned in the issue above, the injection doesn't work because you have to go through a library that doesn't work on the emulator.

The chrrox tutorials are so polite that if you have a rooted device, you can try it out right away.
When installing frida-server, if it doesn't work, you may succeed by running su in the shell to get permissions,
or by run "setenforce 0" in SELinux state to put it in permissive mode.
## Post #3
- Username: brewslee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 05, 2020 7:07 pm
- Post datetime: 2021-03-31T12:35:56+00:00
- Post Title: Decrypt unity 3d files with Frida

First off, thanks for this tutorial. I learnt a lot from it and came to a similar conclusion with my project. 

I am trying to decrypt unity assetbundle files and, like you, have found the function/method responsible for decrypting the files. But the issue I am having now is I want to automate the process with a list of assetbundle paths and I can't do this without scripting the reading of the UnityFS file size in the header. As you are aware, the file size is an int64 little endian but Frida's .readS64() reads in big endian. Do you have any suggestions for automating the reading of the assetbundle file size?
## Post #4
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2021-04-21T06:35:20+00:00
- Post Title: Decrypt unity 3d files with Frida

Could you please to tell me where did you find adress 0xaf698000? Sorry I'm noob and it's really make me loss there. Thank you
## Post #5
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2021-05-03T18:08:15+00:00
- Post Title: Decrypt unity 3d files with Frida

> Reply from vuphanus ↑Wed Apr 21, 2021 2:35 pm at Wed Apr 21, 2021 2:35 pm
>
> 
Could you please to tell me where did you find adress 0xaf698000? Sorry I'm noob and it's really make me loss there. Thank you

Seem author ignore me. This is just a up post. Hope someone here will point me out. Thank you
## Post #6
- Username: UuPhan
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-05-03T22:51:38+00:00
- Post Title: Decrypt unity 3d files with Frida

it says right in the tutorial its the return address from the called function.
## Post #7
- Username: Temperature Index
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 04, 2021 2:31 pm
- Post datetime: 2021-05-04T06:39:50+00:00
- Post Title: Decrypt unity 3d files with Frida

Hi. I'm...interested in being able to decrypt a certain game's files. But this method is...well, honestly, it's a bit over my head, and also not something I can pull off very easily.

I don't have access to a rooted phone, because my phone is a secure device and can't be rooted with any known method.

Because of these things is there any way I can confirm this method would work on a specific game? Specifically...A Certain Magical Index - Imaginary Fest? Thank you for the reply in advance, and sorry for the trouble.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-05-04T21:46:40+00:00
- Post Title: Decrypt unity 3d files with Frida

Just try it in an emulator with root enabled.
If it runs this method will work.
Then buy a cheap phone off ebay to root with.
## Post #9
- Username: TakeAaron
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 08, 2019 4:23 pm
- Post datetime: 2021-06-09T02:33:37+00:00
- Post Title: Decrypt unity 3d files with Frida

why I can't search LoadAssetBundle this function in function
