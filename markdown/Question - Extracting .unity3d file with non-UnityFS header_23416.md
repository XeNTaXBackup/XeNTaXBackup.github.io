## Post #1
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-08T09:39:53+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

I posted a similar inquiry elsewhere some time last month but was not provided any solutions. I noticed this forum had a lot of similar questions regarding accessing encrypted .unity3d files and was wondering if help could be provided on this. I already had a look at the [Decrypt unity 3d files with Frida](https://forum.xentax.com/viewtopic.php?f=29&t=23228) tutorial, but this does not seem to be applicable to my situation due to not having a libil2cpp.so file et al.. I can provide additional information as required.

---

Application: [KartRider Rush+](https://play.google.com/store/apps/details?id=com.nexon.kart)

Prior to a recent update for the game, the package files could be accessed and extracted through usual extraction tools. However, it seems like the developers have changed how the files are encoded, and now instead of all the files having a UnityFS header, they instead have an FBAU header. Attempting to access these files now simply results in no data returned.

I am wondering if there are any other means to accessing the files' contents, or if this is considered custom encryption and will thus not be supported. Thank you.

I have included some example files via Google Drive Links, which includes two .unity3d files pre and post update, along with a hex image example:

Pre-Update (Works with standard tools)
[Example of two .unity3d files from pre-update](https://drive.google.com/drive/folders/1L7dUOQrs--hf7dqi_rH3dO2mpdsO0GNq)

Post-Update (Does not work with standard tools/encrypted)
[Example of two .unity3d files from post-update](https://drive.google.com/drive/folders/1ygFtjj9aIaLmrKnh4yO3il0WFHuDaE61)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-08T11:06:08+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

The game has that file


It looks like the first 0x1C0 bytes are encrypted.
most likely xor
## Post #3
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-08T22:25:30+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

Thank you for the very prompt response and tips. I was looking at the wrong folders so I missed the libil2cpp.so.

Just to put in some of my progress while I continue to try and figure this out:

Continuing with your tutorial, I set up everything as requested prior to Step 1. Using Ghidra in this scenario since IDA Pro requires payment and the free version does not seem to support this use case.

 Attempting to run Analysis on libil2cpp.so in Ghidra seemed to be stuck at 0% progress even after 3 hours, so I just halted it. Not sure if it's supposed to work after a longer period of time.
 Feeding the base libil2cpp.so and global-metadata.dat files into Il2CppDumper results in the common error "ERROR: This file may be protected."

 Based on the repository's README, I downloaded GameGuardian on my rooted device, dumped the appropriate files, retrieved the correct .bin file based on what the com.nexon.kart-maps file listed, edited it so it only contained the libil2cpp.so data, then fed that file into Il2CppDumper instead, which successfully generated the scripts.json file among others.
The scripts.json file contained 0 instances of LoadAssetBundleSync, and 4 instances of LoadAssetBundle (1 which seems like the actual function:
Code: Select all    {
      "Address": 47298720,
      "Name": "ABLoadReq$$LoadAssetBundle",
      "Signature": "UnityEngine_AssetBundle_o* ABLoadReq__LoadAssetBundle (ABLoadReq_o* __this, System_String_o* abPath, const MethodInfo* method);"
    },

).
 I ran the ghidra.py script in Ghidra, which took around 10 minutes.
 This is the result for the LoadAssetBundle function:
Code: Select all/* WARNING: Globals starting with '_' overlap smaller symbols at the same address */

undefined4 ABLoadReq$$LoadAssetBundle(int param_1,undefined4 param_2)

{
  int iVar1;
  undefined4 uVar2;
  undefined4 uVar3;
  
  if (cRam084e9e5e == '\0') {
    thunk_FUN_0099be88(0x42);
    cRam084e9e5e = '\x01';
  }
  iVar1 = *(int *)(*(int *)(ABLoadReq_TypeInfo + 0x58) + 0x18);
  if (iVar1 != 0) {
    uVar2 = XLua.DelegateBridge$$__Gen_Delegate_Imp852(iVar1,param_1,param_2,0);
    return uVar2;
  }
  uVar2 = 0;
  iVar1 = System.String$$IsNullOrEmpty(param_2,0);
  if (iVar1 == 0) {
    iVar1 = ABLoadReq$$IsEncrypted(param_1,*(undefined4 *)(param_1 + 0x14));
    if (iVar1 == 0) {
      uVar2 = UnityEngine.AssetBundle$$LoadFromFile(param_2,0);
    }
    else {
      uVar2 = ABLoadReq$$LoadEncryptedAB(param_1,param_2);
    }
    if (((*(byte *)(UnityEngine.Object_TypeInfo + 0xb7) & 2) != 0) &&
       (*(int *)(UnityEngine.Object_TypeInfo + 0x6c) == 0)) {
                    /* WARNING: Subroutine does not return */
      thunk_FUN_009afb28();
    }
    iVar1 = UnityEngine.Object$$op_Equality(uVar2,0,0);
    if (iVar1 == 1) {
      if (((*(byte *)(SimpleStringBuilder_TypeInfo + 0xb7) & 2) != 0) &&
         (*(int *)(SimpleStringBuilder_TypeInfo + 0x6c) == 0)) {
                    /* WARNING: Subroutine does not return */
        thunk_FUN_009afb28();
      }
      uVar3 = SimpleStringBuilder$$Concat(_StringLiteral_10568,param_2,0);
      GameSystemBase$$Log(5,uVar3,0);
    }
  }
  return uVar2;
}

I notice a LoadEncryptedAB function which may be what is required? This is its contents:
Code: Select all
void ABLoadReq$$LoadEncryptedAB(undefined4 param_1,undefined4 param_2)

{
  int iVar1;
  undefined4 uVar2;
  
  if (cRam084e9e60 == '\0') {
    thunk_FUN_0099be88(0x43);
    cRam084e9e60 = '\x01';
  }
  iVar1 = *(int *)(*(int *)(ABLoadReq_TypeInfo + 0x58) + 0x20);
  if (iVar1 != 0) {
    XLua.DelegateBridge$$__Gen_Delegate_Imp852(iVar1,param_1,param_2,0);
    return;
  }
  if (((*(byte *)(Utils_TypeInfo + 0xb7) & 2) != 0) && (*(int *)(Utils_TypeInfo + 0x6c) == 0)) {
                    /* WARNING: Subroutine does not return */
    thunk_FUN_009afb28();
  }
  uVar2 = Utils$$ReadAllBytes(param_2,0);
  uVar2 = Utils$$TeaDecrypt(uVar2,0);
                    /* WARNING: Treating indirect jump as call */
  UnityEngine.AssetBundle$$LoadFromMemory(uVar2,0);
  return;
}

 Similar logic expects me to look at the TeaDecrypt function:
Code: Select allvoid Utils$$TeaDecrypt(undefined4 param_1)

{
  undefined4 uVar1;
  int iVar2;
  int iVar3;
  
  if (DAT_084e64aa == '\0') {
    FUN_0099be88(0xc0c2d6b6);
    DAT_084e64aa = '\x01';
  }
  if (((*(byte *)(Utils_TypeInfo + 0xb7) & 2) != 0) && (*(int *)(Utils_TypeInfo + 0x6c) == 0)) {
                    /* WARNING: Subroutine does not return */
    FUN_009afb28();
  }
  iVar2 = Utils_TypeInfo;
  if (*(int *)(*(int *)(Utils_TypeInfo + 0x58) + 0x1c) == 0) {
    uVar1 = FUN_009d8f5c(TxTEA_TypeInfo);
    TxTEA$$.ctor(uVar1,0);
    iVar2 = Utils_TypeInfo;
    if (((*(byte *)(Utils_TypeInfo + 0xb7) & 2) != 0) && (*(int *)(Utils_TypeInfo + 0x6c) == 0)){
                    /* WARNING: Subroutine does not return */
      FUN_009afb28();
    }
    *(undefined4 *)(*(int *)(Utils_TypeInfo + 0x58) + 0x1c) = uVar1;
  }
  if (((*(byte *)(iVar2 + 0xb7) & 2) != 0) && (*(int *)(iVar2 + 0x6c) == 0)) {
                    /* WARNING: Subroutine does not return */
    FUN_009afb28();
  }
  iVar3 = *(int *)(*(int *)(iVar2 + 0x58) + 0x1c);
  if (iVar3 == 0) {
                    /* WARNING: Subroutine does not return */
    FUN_009c8e34(0);
  }
  TxTEA$$decrypt(iVar3,param_1,*(undefined4 *)(*(int *)(iVar2 + 0x58) + 0x20),0);
  return;
}

 And an image of what the software looks like at this point in time: https://prnt.sc/yrhnav


Assuming your xor encryption hypothesis is correct, I presume I still need to go through this process in order to find out what the files are xor'd with. Will continue trying to work on this, but will also greatly appreciate any additional assistance if applicable. Thanks!
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-09T01:13:59+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

Good job so far.
yeah you can notice
UnityEngine.AssetBundle$$
```
LoadFromMemory
```

in your code that I mentioned in the tutorial.
looks like from the code you have hear its using tea or xtea encryption.
So you can hook that function and log the key then use normal programs to decrypt your files.
you can also hook the result of the load asset bundle function to dump a decrypted file for reference.

[https://www.codeproject.com/Articles/31 ... ade-Simple](https://www.codeproject.com/Articles/31602/TEA-Encryption-Decryption-Made-Simple)

you can compare code in 
```
TxTEA$$decrypt
```

to see what it is doing.
## Post #5
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-09T05:39:29+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

Reviewing some of the relevant functions and their corresponding addresses:

 undefined4 ABLoadReq$$LoadAssetBundle(int param_1,undefined4 param_2) - 02d2b8a0
 void ABLoadReq$$LoadEncryptedAB(undefined4 param_1,undefined4 param_2) - 02d2bcc4
 void Utils$$TeaDecrypt(undefined4 param_1) - 025baae0
 UnityEngine.AssetBundle$$LoadFromMemory(uVar2,0) - 068ba44c


Cannot actually check the pseudo-code for the LoadFromMemory function in Ghidra but I assume this is normal.

Going into Step 3 of the tutorial, I followed everything to the last step but ran into an error:

```
/system/bin/sh: ./frida-server: can't execute: Is a directory
```


I looked around a bit but it doesn't seem like there was a proper solution to this, so I ended up installing the [Frida Server](https://play.google.com/store/apps/details?id=me.shingle.fridaserver) app on the Play Store which seems to serve the same purpose.

Step 4 worked as normal.

Step 5 presents some issues on my end:

 frida.exe -U -f com.nexon.kart
 Replace the address in the Code: Select allvar nativeFuncAddr = 0x00683014; // line with the TeaDecrypt address (0x025baae0)
 %resume gets a hit for the libil2cpp.so file (the ret changes every time):
Code: Select all. . .
dlopen called with: /system/lib/hw/gralloc.msm8974.so
dlopen called with: libc.so
dlopen called with: libc.so
dlopen called with: /data/app/com.nexon.kart-1/lib/arm/libil2cpp.so
ret: 0xb57f0344
dlopen called with: /vendor/lib/egl/eglsubAndroid.so
dlopen called with: /vendor/lib/egl/libGLESv2_adreno.so
dlopen called with: /vendor/lib/egl/libGLESv2S3D_adreno.so
. . .

 However, no functions are being hooked. I have rerun the frida.exe line with 0x02d2b8a0 and 0x068ba44c for nativeFuncAddr as well, but there are still no functions being hooked; this is with letting the game run/load up to the login screen where it can't go any further. It seems like I cannot continue without getting the pointers. I also don't understand where the return address 0xaf698000 came from in the tutorial but one step at a time I suppose.


In the meantime, I tried to set up whatever I could ahead:

 Searching for CreateString returns 33 functions; I just took the first result:
Code: Select all
/* WARNING: Control flow encountered bad instruction data */
/* WARNING: Globals starting with '_' overlap smaller symbols at the same address */

undefined2 * System.String$$CreateString(undefined4 param_1,undefined2 param_2,int param_3)

{
  undefined2 *puVar1;
  int iVar2;
  undefined2 *puVar3;
  undefined4 uVar4;
  undefined2 *puVar5;
  
  if (cRam0845453f == '\0') {
    FUN_0099be88(0x1c101);
    cRam0845453f = '\x01';
  }
  if (param_3 < 0) {
    uVar4 = FUN_009d8f5c(System.ArgumentOutOfRangeException_TypeInfo);
    System.ArgumentOutOfRangeException$$.ctor(uVar4,StringLiteral_469,0);
    FUN_009c8d88(uVar4,0,_Method$System.String.CreateString());
                    /* WARNING: Bad instruction - Truncating control flow here */
    halt_baddata();
  }
  if (param_3 == 0) {
    puVar1 = (undefined2 *)**(uint **)(string_TypeInfo + 0x58);
  }
  else {
    puVar1 = (undefined2 *)FUN_009e37e8(param_3);
    puVar3 = puVar1;
    if (puVar1 != (undefined2 *)0x0) {
      iVar2 = System.Runtime.CompilerServices.RuntimeHelpers$$get_OffsetToStringData(0);
      puVar3 = (undefined2 *)(iVar2 + (int)puVar1);
    }
    puVar5 = puVar3 + param_3;
    while (puVar3 < puVar5) {
      *puVar3 = param_2;
      puVar3 = puVar3 + 1;
    }
  }
  return puVar1;
}

 Trying to run the code that is meant to create a string (replacing com.tencent.hlfish with com.nexon.kart) results in an Error: access violation accessing 0x0. I assume this is because /storage/emulated/0/Android/data/com.nexon.kart/files/AssetBundles/ doesn't actually exist; these are the available directories in the files folder:
Code: Select allChatVoice
DecodedBanks
Ifs
Log
SyncRecords
Unity
il2cpp
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-09T11:38:44+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

you need to use frida server as root.
copy frida-server for arm64 to your device /data/local/tmp
log into adb
type su
now your root
change to /data/local/tmp
chmod 777 ./frida-server
./frida-server

[https://frida.re/docs/android/](https://frida.re/docs/android/)
## Post #7
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-09T17:29:49+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

Alright, I had to change the steps around a little but I managed to do it without using the FridaServer app...sort of.

Unless I am heavily misreading, my interpretation of Step 3 is as such:

> Install the APK onto your phone
>
>  Get the latest release of Frida server at https://github.com/frida/frida/releases
>
> 
>
>  In this use case and time of writing, it will be for Android ARM 64, so frida-server-14.2.11-android-arm64.xz
>
> 
>
>  Extract this with 7z and put the file into C:\ or wherever is accessible
>
>  Run the following:
>
> Code: Select alladb push c:\frida-server-14.2.11-android-arm64 /data/local/tmp/frida-server
>
> adb shell
>
> su
>
> cd /data/local/tmp/frida-server
>
> chmod 777 ./frida-server-14.2.11-android-arm64
>
> ./frida-server-14.2.11-android-arm64

With that said however, that last step now gives me a "not executable: 64-bit ELF file" error. I assume this is due to the device I am using which is incompatible with that specific Frida server (Nexus 5, Android Version 6.0.1), so I downloaded [frida-server-14.2.11-android-arm.xz](https://github.com/frida/frida/releases/download/14.2.11/frida-server-14.2.11-android-arm.xz) instead which works for my device. I do not know if that invalidates the rest of the tutorial, and if I'd need to switch to an emulator instead.

Beyond that, I run into the same errors as I mentioned in my previous post concerning no function hooks or the lack of AssetBundles folder.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-09T22:46:55+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

You can run the 32 bit frida server.
the offset is most likely wrong from the way it was dumped would be my guess as to why your not hitting the function.
or its not calling that function at all you can try a different function to hook.
you can also try dumping with
[https://github.com/lasting-yang/frida_dump](https://github.com/lasting-yang/frida_dump)

you can test with the sample tutorial I did to make sure that hook is working on your device first.

using adb shell you can create any directory you want also.
## Post #9
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-10T07:35:53+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

As you suggested, it makes sense to try the tutorial's sample APK first.

Since the link you provided in the tutorial no longer works, I am using the APK found at [https://www.coolapk.com/game/com.tencent.hlfish](https://www.coolapk.com/game/com.tencent.hlfish) (腾讯欢乐捕鱼 Version 2.2.5).

Speeding through to the end of Step 2, I look at the HLArcade.HLFileCryptNew$$DecryptFileNew function in Ghidra:



Okay...so besides the fact that I can't see the pseudo-code of HLArcade.HLFileCryptNew$$DecryptFileNew for some reason (can only see UResource.UFileCrypt$$DecryptFileNew), the address looks to be different from the tutorial as well, being at 00c1eb94 instead of 00683014. Might be because of APK version differences and the libil2cpp.so being different between your writing and mine.

Going into Step 5, I tested the monitor code on com.tencent.hlfish with the following nativeFuncAddr:

 0x00683014 (from your tutorial)
 0x00c1eb94 (HLArcade.HLFileCryptNew$$DecryptFileNew function)
 0x0201c4b8 (UFileCrypt$$DecryptFileNew function)
 0x02026620 (UResource.UResourceManagerBase$$LoadAssetBundleSync function)
 0x00010000 (Random testing start of file)


All of those did not return a function hook...so somewhat on a whim, I decided to try 0x00C0EB94 (0x00c1eb94 - 0x00010000), and...



...Alright then...

From this point, I will continue using com.tencent.hlfish instead of com.nexon.kart, and only return to my own APK once I fully complete your tutorial just to make sure we're on the same page.

So as seen from the screenshot above, I have 0x8dcdc840 and 0x9cfe9b5c. Continuing with Step 5, I got results as such:

```
0000  0a 0e 13 04 11 04 05 0a 09 04 02 04 08 0a 05 03   ................
0010  03 07 06 03 05 07 0c 04 05 11 09 0c 0f 11 0d 0d   ................
0020  13 0e 0f 01 01 09 04 0b 03 08 06 0d 09 13 76 01   ..............v.
0030  18 09 07 11 06 08 03 06 03 0e 03 12 03 04 08 0e   ................
0040  07 02 12 0f 08 11 08 0c 09 09 0e 0c 0f 0b 0d 00   ................
0050  00 0b 03 0b 01 05 06 0d 0a 12 79 01 03 04 03 11   ..........y.....
0060  20 1a 00 37 08 01 01 08 01 02 0d 0c 03 01 03 06    ..7............
0070  0f 04 15 00 00 00 16 2a 00 0c 25 6f 0f 02 0e 00   .......*..%o....
0080  0d 03 0f 03 06 0d 01 00 00 0a 06 08 01 02 01 00   ................
0090  09 08 13 01 00 01 18 08 4c 02 03 0a 05 06 0e 05   ........L.......
00a0  00 07 00 04 ff e3 00 f8 00 d2 00 3c 00 55 00 70   ...........<.U.p
00b0  00 74 00 78 00 7c 00 80 00 40 40 3d 36 38 76 38   .t.x.|...@@=68v8
00c0  7a 38 7e 38 32 78 2e 7c 2a 80 15 07 0f 09 0b 09   z8~82x.|*.......
00d0  5b 59 0b 33 35 77 35 2f 31 7b 75 2b 2d 7f 79 27   [Y.35w5/1{u+-.y'
00e0  29 1d 7d 10 14 08 14 0c 0e 73 0e 61 6e 3f 3d 3f   ).}......s.an?=?
00f0  41 43 54 0c 71 73 71 12 00 2b 17 26 27 36 37 36   ACT.qsq..+.&'676

```


```
0000  d5 ff ff ff 80 b5 0c 48 0c 49 0d 4a 78 44 79 44   .......H.I.JxDyD
0010  7a 44 57 f3 df f8 0b 49 00 28 79 44 08 60 0a d0   zDW....I.(yD.`..
0020  01 21 00 22 56 f3 0a f8 01 46 07 48 78 44 bd e8   .!."V....F.HxD..
0030  80 40 56 f3 41 bc 80 bd 25 ec d5 00 b0 c7 d5 00   .@V.A...%.......
0040  b2 f0 d5 00 ce f1 f2 00 c0 f1 f2 00 03 49 00 22   .............I."
0050  03 48 79 44 78 44 0a 60 56 f3 b2 bc 96 f1 f2 00   .HyDxD.`V.......
0060  98 f1 f2 00 80 b5 60 f3 8f f9 05 49 05 4a 06 4b   ......`....I.J.K
0070  79 44 7a 44 7b 44 bd e8 80 40 60 f3 30 b9 00 bf   yDzD{D...@`.0...
0080  f4 28 d6 00 8f ff ff ff d5 ff ff ff 80 b5 0c 48   .(.............H
0090  0c 49 0d 4a 78 44 79 44 7a 44 57 f3 9b f8 0b 49   .I.JxDyDzDW....I
00a0  00 28 79 44 08 60 0a d0 04 21 00 22 55 f3 c6 ff   .(yD.`...!."U...
00b0  01 46 07 48 78 44 bd e8 80 40 56 f3 fd bb 80 bd   .F.HxD...@V.....
00c0  9d eb d5 00 28 c7 d5 00 35 f0 d5 00 72 f1 f2 00   ....(...5...r...
00d0  64 f1 f2 00 03 49 00 22 03 48 79 44 78 44 0a 60   d....I.".HyDxD.`
00e0  56 f3 6e bc 3a f1 f2 00 3c f1 f2 00 80 b5 60 f3   V.n.:...<.....`.
00f0  4b f9 05 49 05 4a 06 4b 79 44 7a 44 7b 44 bd e8   K..I.J.KyDzD{D..

```


The above two blocks change every time I rerun the application so this doesn't seem right. I also notice the function hook returns "a2": "0x0" so I even though I hooked into a function, it might still be the wrong one. I'll continue messing around a little but that's currently where things stand.

---

As an aside, I did try the frida_dump repo you linked, but the first script returns a "TypeError: cannot read property 'getApplicationContext' of null at <anonymous> (/dump_so.js:4)" error and the second script returns a "Failed to spawn: the 'argv' option is not supported when spawning Android apps" error so I probably won't be able to make use of it anyways.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-10T10:49:24+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

You need to let it finish analyzing the program it takes several hours to do.
Yo need to wait till it says idle on the bottom then run he scripts.
It will run a 2nd time with the scripts.
Then you can start looking at code.
it has to say idle on the bottom between each step.
## Post #11
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-11T06:09:17+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

I have been continuing to work with the com.tencent.hlfish example but haven't seen any signs of a UnityFS header.

Hooking to the int HLArcade.HLFileCryptNew$$DecryptFileNew(undefined4 param_1,int *param_2) function, I get the following hits:

```
{
        "a0": "0x8d6ac840",
        "a1": "0x9d12eb5c",
        "a2": "0x0",
}
Return Value: 0x87dd6000

```


Looking at 0x8d6ac840 (a0):

```
0000  40 22 ff 98 00 00 00 00 55 00 00 00 2f 00 73 00   @"......U.../.s.
0010  74 00 6f 00 72 00 61 00 67 00 65 00 2f 00 65 00   t.o.r.a.g.e./.e.
0020  6d 00 75 00 6c 00 61 00 74 00 65 00 64 00 2f 00   m.u.l.a.t.e.d./.
0030  30 00 2f 00 41 00 6e 00 64 00 72 00 6f 00 69 00   0./.A.n.d.r.o.i.
0040  64 00 2f 00 64 00 61 00 74 00 61 00 2f 00 63 00   d./.d.a.t.a./.c.
0050  6f 00 6d 00 2e 00 74 00 65 00 6e 00 63 00 65 00   o.m...t.e.n.c.e.
0060  6e 00 74 00 2e 00 68 00 6c 00 66 00 69 00 73 00   n.t...h.l.f.i.s.
0070  68 00 2f 00 66 00 69 00 6c 00 65 00 73 00 2f 00   h./.f.i.l.e.s./.
0080  41 00 73 00 73 00 65 00 74 00 42 00 75 00 6e 00   A.s.s.e.t.B.u.n.
0090  64 00 6c 00 65 00 73 00 2f 00 46 00 69 00 73 00   d.l.e.s./.F.i.s.
00a0  68 00 69 00 6e 00 67 00 2f 00 6b 00 65 00 72 00   h.i.n.g./.k.e.r.
00b0  6e 00 65 00 6c 00 00 00 00 00 00 00 00 00 00 00   n.e.l...........
00c0  40 22 ff 98 00 00 00 00 57 00 00 00 53 00 79 00   @"......W...S.y.
00d0  73 00 74 00 65 00 6d 00 2e 00 43 00 6f 00 6e 00   s.t.e.m...C.o.n.
00e0  66 00 69 00 67 00 75 00 72 00 61 00 74 00 69 00   f.i.g.u.r.a.t.i.
00f0  6f 00 6e 00 2c 00 20 00 56 00 65 00 72 00 73 00   o.n.,. .V.e.r.s.

```


Looking at 0x87dd6000 (the return address):

```
0000  d8 74 cb 8f 00 00 00 00 00 00 00 00 97 17 00 00   .t..............
0010  00 00 d9 3e 00 20 38 3f 00 00 d9 3e 00 40 d9 3e   ...>. 8?...>.@.>
0020  00 40 8a 3e 00 40 d9 3e 00 40 8a 3e 00 20 38 3f   .@.>.@.>.@.>. 8?
0030  00 00 d9 3e 00 20 38 3f 00 00 d9 3e 00 40 d9 3e   ...>. 8?...>.@.>
0040  00 40 8a 3e 00 40 d9 3e 00 40 8a 3e 00 20 38 3f   .@.>.@.>.@.>. 8?
0050  00 c0 51 3f 00 c0 8c 3e 00 00 38 3f 00 c0 8c 3e   ..Q?...>..8?...>
0060  00 00 38 3f 00 00 bb 3e 00 c0 51 3f 00 00 bb 3e   ..8?...>..Q?...>
0070  00 c0 51 3f 00 c0 8c 3e 00 00 38 3f 00 c0 8c 3e   ..Q?...>..8?...>
0080  00 00 38 3f 00 00 bb 3e 00 c0 51 3f 00 00 bb 3e   ..8?...>..Q?...>
0090  00 00 0f 3f 00 80 18 3f 00 00 0f 3f 00 00 be 3e   ...?...?...?...>
00a0  00 80 d9 3e 00 00 be 3e 00 80 d9 3e 00 80 18 3f   ...>...>...>...?
00b0  00 00 0f 3f 00 80 18 3f 00 00 0f 3f 00 00 be 3e   ...?...?...?...>
00c0  00 80 d9 3e 00 00 be 3e 00 80 d9 3e 00 80 18 3f   ...>...>...>...?
00d0  00 40 f5 3e 00 00 61 3f 00 80 3c 3e 00 00 61 3f   .@.>..a?..<>..a?
00e0  00 80 3c 3e 00 c0 7f 3f 00 40 f5 3e 00 c0 7f 3f   ..<>...?.@.>...?
00f0  00 00 2a 3f 00 c0 7f 3f 00 00 2a 3f 00 20 79 3f   ..*?...?..*?. y?

```


Based on the tutorial, I should be expecting to see a UnityFS header there but don't. At this point I've been blindly throwing around Memory.scanSync in hopes to find something familiar, but has largely been futile with all the access violation errors.
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-11T10:53:36+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

you should see it in the return part of it.
I am guessing your device has low ram so its not keeping anything in memory after its read.
so print the memory in this section.

```
        console.log(retval);
        var keyDump2 = Memory.readByteArray(retval, 0x300);
        console.log(hexdump(keyDump2));
        }

```


Does the file your trying to decrypt exist?
## Post #13
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-02-11T14:19:59+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

I just wonder, if Il2CppDumper works fine, it should also create dummy mono libraries (for exploration via dnSpy or something), where you can find decryption scheme in more convenient format - and though tea/xtea key may not be present directly, you can find RVA for the function there and try to trace it at runtime. Decrypting/grabbing assets directly from memory is cumbersome as you could notice.
## Post #14
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-11T17:18:56+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

> Reply from chrrox ↑Thu Feb 11, 2021 6:53 pm at Thu Feb 11, 2021 6:53 pm
>
> 
you should see it in the return part of it.
I am guessing your device has low ram so its not keeping anything in memory after its read.
so print the memory in this section.
Code: Select all        onLeave: function (retval) {
        console.log(retval);
        var keyDump2 = Memory.readByteArray(retval, 0x300);
        console.log(hexdump(keyDump2));
        }


Does the file your trying to decrypt exist?

Your assumption seems to be correct. Adding the hexdump portion to the monitor code presents this when running it:

```
           0  1  2  3  4  5  6  7  8  9  A  B  C  D  E  F  0123456789ABCDEF
00000000  98 d3 d3 8e 00 00 00 00 00 00 00 00 b2 22 20 00  ............." .
00000010  55 6e 69 74 79 46 53 00 00 00 00 06 35 2e 78 2e  UnityFS.....5.x.
00000020  78 00 32 30 31 39 2e 34 2e 38 66 31 00 00 00 00  x.2019.4.8f1....
. . .

```


Trying to access this address via Memory.readByteArray returns this:

```
0000  40 29 f4 8e 00 00 00 00 00 00 00 00 ad 61 00 00   @)...........a..
0010  01 00 00 00 02 00 00 00 03 00 00 00 01 00 00 00   ................
0020  03 00 00 00 00 00 00 00 05 00 00 00 06 00 00 00   ................
. . .

```


Now I assume this issue of the memory in RAM being immediately wiped after it's read is going to cause issues for the rest of the tutorial...I tried to continue anyways with the CreateString step. Searching for that function brings up...a few options.

```
System.Globalization.CodePageDataItem$$CreateString	00d7a52c	undefined System.Globalization.CodePageDataItem$$CreateString()	236
System.String$$CreateStringFromEncoding	01558198	undefined System.String$$CreateStringFromEncoding()	232
System.String$$CreateString	0155e9c8	undefined System.String$$CreateString()	164
System.String$$CreateString	0155ea78	undefined System.String$$CreateString(undefined param_1, undefined param_2, undefined param_3, undefined param_4, undefined4 param_5)	608
System.String$$CreateString	0155edcc	undefined System.String$$CreateString()	1
System.String$$CreateString	0155edec	thunk undefined System.String$$CreateString()	4
System.String$$CreateString	0155edf0	undefined System.String$$CreateString()	24
System.String$$CreateString	0155ee08	undefined System.String$$CreateString()	24
System.String$$CreateString	0155ee20	thunk undefined System.String$$CreateString()	4
System.String$$CreateString	0155ee24	undefined System.String$$CreateString()	240

```


The only function(s) from above that didn't result in an access violation were:

```
System.String$$CreateString	0155edec	thunk undefined System.String$$CreateString()	4

```


Taking the second option since that matches your tutorial better (actual address is 0154edec because of 0x00010000 offset).

Beyond that, subbing in the correct addresses for your next script involving the Construction parameter 2 path parameter/Construction parameter 3/decrypt portion, I am getting access violation errors again at the

```
var file_bgein = retval.add(0x10)
```


line, which I assume is the RAM issue.

---

> Reply from Spiritovod ↑Thu Feb 11, 2021 10:19 pm at Thu Feb 11, 2021 10:19 pm
>
> 
I just wonder, if Il2CppDumper works fine, it should also create dummy mono libraries (for exploration via dnSpy or something), where you can find decryption scheme in more convenient format - and though tea/xtea key may not be present directly, you can find RVA for the function there and try to trace it at runtime. Decrypting/grabbing assets directly from memory is cumbersome as you could notice.

In case they are of any relevance, here are Google Drive links to [DummyDll (com.nexon.kart)](https://drive.google.com/file/d/1A6BXEbeGi6iYHSct5MqjGOFiLTauSLBt/view) and [DummyDll (com.tencent.hlfish)](https://drive.google.com/file/d/1l9ghM9_khEwS3W5QKhNtGGwhi6zLjuQC/view)

My initial impression is that these files aren't really any more convenient to sift through than the current usage of Ghidra with the naming script, as I am still seeing the functions along with the RVAs. I could definitely (and maybe hopefully) be wrong and the DummyDlls would be a better option to look through, but very preliminary research suggests otherwise, at least involving my current use case of just wanting to extract assets without doing any modifications.
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-11T18:47:19+00:00
- Post Title: Question - Extracting .unity3d file with non-"UnityFS" header

The hook is hitting the string create as you showed in your example.
So use that function.
You should be able to paste in the hook function then call create string and it should automatically print it for you.
## Post #16
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-11T19:54:59+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

I had actually done that already (got stuck at the part right after it) but I didn't document it here in detail.

To review, this is the CreateString function (again, working in com.tencent.hlfish for now) located at 0x0154edec:

```
int System.String$$CreateString(undefined4 param_1,int param_2)

{
  int iVar1;
  int iVar2;
  int iVar3;
  
  if (DAT_0298d2d8 == '\0') {
    thunk_FUN_006b1bd0(0x8ae8);
    DAT_0298d2d8 = '\x01';
  }
  if ((param_2 == 0) || (iVar1 = System.String$$wcslen(param_2), iVar1 == 0)) {
    iVar2 = **(int **)(string_TypeInfo + 0x5c);
  }
  else {
    iVar2 = thunk_FUN_006ba618();
    iVar3 = iVar2;
    if (iVar2 != 0) {
      iVar3 = System.Runtime.CompilerServices.RuntimeHelpers$$get_OffsetToStringData(0);
      iVar3 = iVar3 + iVar2;
    }
    System.Buffer$$Memcpy(iVar3,param_2,iVar1 << 1,0);
  }
  return iVar2;
}

```


This is the create string code from your tutorial with the appropriate address change (from 0x00FCA590 to 0x0154edec), which is run after the game application reaches the login screen:

```
var moduleBase = Module.findBaseAddress(moduleName);
var careate_str = ptr(parseInt(moduleBase) + 0x0154edec) 
var careate_str_f = new NativeFunction(careate_str, 'pointer' , [ 'pointer' , 'pointer' ]); 
var root = '/storage/emulated/0/Android/data/com.tencent.hlfish/files/AssetBundles/'
var path = 'kernel' 
var path_str_utf8 = Memory.allocUtf8String(root + path) 
var path_str = careate_str_f(new NativePointer(path_str_utf8), path_str_utf8);

Memory.readByteArray(new NativePointer(path_str), 0x100);

```


Result:

```
0010  72 61 67 65 2f 65 6d 75 6c 61 74 65 64 2f 30 2f   rage/emulated/0/
0020  41 6e 64 72 6f 69 64 2f 64 61 74 61 2f 63 6f 6d   Android/data/com
0030  2e 74 65 6e 63 65 6e 74 2e 68 6c 66 69 73 68 2f   .tencent.hlfish/
0040  66 69 6c 65 73 2f 41 73 73 65 74 42 75 6e 64 6c   files/AssetBundl
0050  65 73 2f 6b 65 72 6e 65 6c 00 00 00 74 00 69 00   es/kernel...t.i.
0060  80 98 ce 98 00 00 00 00 25 00 00 00 41 00 70 00   ........%...A.p.
0070  6f 00 6c 00 6c 00 6f 00 2e 00 50 00 6c 00 75 00   o.l.l.o...P.l.u.
0080  67 00 69 00 6e 00 73 00 2e 00 4d 00 73 00 64 00   g.i.n.s...M.s.d.
0090  6b 00 2e 00 41 00 70 00 6f 00 6c 00 6c 00 6f 00   k...A.p.o.l.l.o.
00a0  53 00 65 00 72 00 76 00 69 00 63 00 65 00 54 00   S.e.r.v.i.c.e.T.
00b0  79 00 70 00 65 00 00 00 6c 00 65 00 73 00 5f 00   y.p.e...l.e.s._.
00c0  40 19 d3 8c 00 00 00 00 00 00 00 00 13 00 00 00   @...............
00d0  06 00 00 00 0e 00 00 00 00 00 00 00 00 00 00 00   ................
00e0  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00   ................
00f0  00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00   ................
[Nexus 5::com.tencent.hlfish]->

```


I don't actually get an error afterwards as the tutorial suggests. Now I am going to attempt to run the decrypt portion of your code one line at a time (your tutorial screenshot seems to show a bit of duplicate and out-of-order code but the general flow still makes sense):

Construction Parameter 3/Decyrpt portion of code (replace tutorial's 0x00683014 with 0x00c0eb94, which as a reminder is the DecryptFileNew function):

```
var arg3_ptr = Memory.alloc( 0x4 )
Memory.writeInt(arg3_ptr, 0x0 )

//decrypt
var decrypt = parseInt(moduleBase) +  0x00c0eb94;
var decrypt_f = new NativeFunction(ptr(decrypt), 'pointer', ['int','pointer', 'pointer']);
var retval = decrypt_f(0,path_str, arg3_ptr)
var file_bgein = retval.add(0x10)


```


Here is a screenshot of the result:
## Post #17
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-11T22:15:50+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

The address should never change.
Your creating a normal string instead of a Unicode string.
The address for the function can be seen in gidra when you click the start of the function.
## Post #18
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-11T22:55:35+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

Yes I know the address should never change...I am writing in context of the function addresses in my libil2cpp.so file in comparison to the function in addresses in the libil2cpp.so file that you used for the [sample tutorial](https://forum.xentax.com/viewtopic.php?f=29&t=23228), most likely because they are different versions; the CreateString function in your file was located at 0x00FCA590, but the CreateString function in my file is located in one of these addresses, as per my previous post:

```
System.Globalization.CodePageDataItem$$CreateString	00d7a52c	undefined System.Globalization.CodePageDataItem$$CreateString()	236
System.String$$CreateStringFromEncoding	01558198	undefined System.String$$CreateStringFromEncoding()	232
System.String$$CreateString	0155e9c8	undefined System.String$$CreateString()	164
System.String$$CreateString	0155ea78	undefined System.String$$CreateString(undefined param_1, undefined param_2, undefined param_3, undefined param_4, undefined4 param_5)	608
System.String$$CreateString	0155edcc	undefined System.String$$CreateString()	1
System.String$$CreateString	0155edec	thunk undefined System.String$$CreateString()	4
System.String$$CreateString	0155edf0	undefined System.String$$CreateString()	24
System.String$$CreateString	0155ee08	undefined System.String$$CreateString()	24
System.String$$CreateString	0155ee20	thunk undefined System.String$$CreateString()	4
System.String$$CreateString	0155ee24	undefined System.String$$CreateString()	240

```


Of those options, only two don't throw access violation errors (0x00d7a52c and 0x0155edec RVAs), and it looks like they both print normal strings instead of Unicode strings? Obviously I did try 0x00FCA590 anyways which didn't work.

For reference:

0x00d7a52c function:

```

{
  int iVar1;
  undefined4 uVar2;
  
  if (DAT_02988e23 == '\0') {
    thunk_FUN_006b1bd0(0x1c4c);
    DAT_02988e23 = '\x01';
  }
  if (param_1 == 0) {
                    /* WARNING: Subroutine does not return */
    thunk_FUN_006a9668();
  }
  iVar1 = System.String$$get_Chars(param_1,0,0);
  if (iVar1 == 0x7c) {
    if (((*(byte *)(System.Globalization.CodePageDataItem_TypeInfo + 0xbb) & 2) != 0) &&
       (*(int *)(System.Globalization.CodePageDataItem_TypeInfo + 0x74) == 0)) {
      thunk_FUN_006aae30();
    }
    if (param_1 == 0) {
                    /* WARNING: Subroutine does not return */
      thunk_FUN_006a9668();
    }
    iVar1 = System.String$$Split
                      (param_1,**(undefined4 **)
                                 (System.Globalization.CodePageDataItem_TypeInfo + 0x5c),1,0);
    if (iVar1 == 0) {
                    /* WARNING: Subroutine does not return */
      thunk_FUN_006a9668();
    }
    if (*(uint *)(iVar1 + 0xc) <= param_2) {
      uVar2 = thunk_FUN_006aa464();
      FUN_006f98a4(uVar2,0);
    }
    param_1 = *(int *)(iVar1 + param_2 * 4 + 0x10);
  }
  return param_1;
}

```


0x0155edec function:

```

{
  int iVar1;
  int iVar2;
  int iVar3;
  
  if (DAT_0298d2d8 == '\0') {
    thunk_FUN_006b1bd0(0x8ae8);
    DAT_0298d2d8 = '\x01';
  }
  if ((param_2 == 0) || (iVar1 = System.String$$wcslen(param_2), iVar1 == 0)) {
    iVar2 = **(int **)(string_TypeInfo + 0x5c);
  }
  else {
    iVar2 = thunk_FUN_006ba618();
    iVar3 = iVar2;
    if (iVar2 != 0) {
      iVar3 = System.Runtime.CompilerServices.RuntimeHelpers$$get_OffsetToStringData(0);
      iVar3 = iVar3 + iVar2;
    }
    System.Buffer$$Memcpy(iVar3,param_2,iVar1 << 1,0);
  }
  return iVar2;
}

```
## Post #19
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-11T23:48:42+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

I reuploaded that apk for you to use for the example.
[https://www100.zippyshare.com/v/XBTE3aAV/file.html](https://www100.zippyshare.com/v/XBTE3aAV/file.html)
## Post #20
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-12T05:15:41+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

Okay, testing with the APK that you linked, the tutorial works just fine with regards to creating the string and retrieving the decrypted file. I don't even seem to run into supposed RAM issues when scanning the memory, as I can see the UnityFS header just fine. Rather annoying how this doesn't seem as straightforward with the newer com.tencent.hlfish, not to mention my original intention of trying to decrypt com.nexon.kart.

While I try to work backwards now and try the newer com.tencent.hlfish again, does this method only allow decrypting of files that are picked up by the initial monitoring code? My particular use case for example has like 1,000+ .unity3d files, of which maybe like five are loaded before the login screen.
## Post #21
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2021-02-12T06:57:40+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

@AltiV do you get same
parameters like in the tut [viewtopic.php?f=29&t=23228](https://forum.xentax.com/viewtopic.php?f=29&t=23228) ?
 "a0": "0x0",
"a1": "0xb1a845f0",
"a2": "0xc62c3b84"

my change every time when i run frida
## Post #22
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-12T08:21:20+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

You are going to get different values every time. I assume because it is writing to RAM it will just try and find a location where space is available, which can change every run.
## Post #23
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-12T12:44:57+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

You can dump any file with the code.
You can hook the function and just play the game and it will dump the files as they load.
or manually supply the file list and tell the game to decrypt them by calling its function.
## Post #24
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2021-02-13T04:45:37+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

Can someone help me pls 
i use this [viewtopic.php?f=29&t=23228](https://forum.xentax.com/viewtopic.php?f=29&t=23228) tut
With the demo apk it works 
But when i use a other apk i cant find the decryption func 
i use ida pro
Here is the apk [https://www83.zippyshare.com/v/mDtnZpvE/file.html
](https://www83.zippyshare.com/v/mDtnZpvE/file.html)
## Post #25
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-13T13:18:03+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

Make a new topic for your game and show where you are stuck.
[https://www.tap.io/app/195056?region=us](https://www.tap.io/app/195056?region=us)
## Post #26
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2021-02-15T22:29:26+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

Whats when 

```
                onEnter: function(args) {
                    console.log("[-] hook invoked");
```


dont call?
## Post #27
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-16T10:45:13+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

If you don't see hook called then the game never called the function after you tried to hook it.
This is the latest version of the game I found.
## Post #28
- Username: rayleigh
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jul 09, 2015 3:58 am
- Post datetime: 2021-02-16T11:05:56+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

thx i found the bug was a bug with frida i restart my samsung s5 and reinstall frida server now it works very strange bug
## Post #29
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-16T19:14:40+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

I use the module in magisk for frida.
## Post #30
- Username: AltiV
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 08, 2021 5:16 pm
- Post datetime: 2021-02-23T00:49:38+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

I know there's been a bit of a gap between my previous post and now, but I am still hoping to find successful resolution with this task. If someone could just help me decrypt the files to begin with that would be preferable, but I understand that may be too greedy.

I've looked into com.nexon.kart some more (since the tutorial APK is more or less resolved, at least with the exact version covered and not the up-to-date version), and it seems like I still can't really follow the functions used.

To recap, some of the relevant functions that I talked about previous are as such:

 undefined4 ABLoadReq$$LoadAssetBundle(int param_1,undefined4 param_2) - 02d1b8a0
 void ABLoadReq$$LoadEncryptedAB(undefined4 param_1,undefined4 param_2) - 02d1bcc4
 void Utils$$TeaDecrypt(undefined4 param_1) - 025aaae0
 UnityEngine.AssetBundle$$LoadFromMemory(uVar2,0) - 068aa44c


From the above, you could say that the functions are nested within each other (second function is called in the first, third function is called in the second, etc.).

The LoadAssetBundle function seems to hook just fine, with the second address/parameter returning expected results:

```
0010  72 00 3a 00 66 00 69 00 6c 00 65 00 3a 00 2f 00   r.:.f.i.l.e.:./.
0020  2f 00 2f 00 73 00 74 00 6f 00 72 00 61 00 67 00   /./.s.t.o.r.a.g.
0030  65 00 2f 00 65 00 6d 00 75 00 6c 00 61 00 74 00   e./.e.m.u.l.a.t.
0040  65 00 64 00 2f 00 30 00 2f 00 41 00 6e 00 64 00   e.d./.0./.A.n.d.
0050  72 00 6f 00 69 00 64 00 2f 00 6f 00 62 00 62 00   r.o.i.d./.o.b.b.
0060  2f 00 63 00 6f 00 6d 00 2e 00 6e 00 65 00 78 00   /.c.o.m...n.e.x.
0070  6f 00 6e 00 2e 00 6b 00 61 00 72 00 74 00 2f 00   o.n...k.a.r.t./.
0080  70 00 61 00 74 00 63 00 68 00 2e 00 31 00 30 00   p.a.t.c.h...1.0.
0090  31 00 30 00 39 00 30 00 2e 00 63 00 6f 00 6d 00   1.0.9.0...c.o.m.
00a0  2e 00 6e 00 65 00 78 00 6f 00 6e 00 2e 00 6b 00   ..n.e.x.o.n...k.
00b0  61 00 72 00 74 00 2e 00 6f 00 62 00 62 00 21 00   a.r.t...o.b.b.!.
00c0  2f 00 61 00 73 00 73 00 65 00 74 00 73 00 2f 00   /.a.s.s.e.t.s./.
00d0  50 00 6c 00 61 00 74 00 66 00 6f 00 72 00 6d 00   P.l.a.t.f.o.r.m.
00e0  41 00 73 00 73 00 65 00 74 00 73 00 2f 00 41 00   A.s.s.e.t.s./.A.
00f0  6e 00 64 00 72 00 6f 00 69 00 64 00 2f 00 61 00   n.d.r.o.i.d./.a.

```

However, the LoadEncryptedAB function never hooks onto anything, at least up to the log in screen of the game (I cannot go any further than this anyways because the game crashes afterwards). I assume that, based on the conditional required to hit this function (checking if the file is encrypted in the first place), none of the files are labelled as encrypted for whatever reason, although they clearly cannot be de-compiled by standard tools. This already deviates from the tutorial pretty heavily since I can't go any farther when looking for UnityFS strings.

Instead of the LoadEncryptedAB function, the other side of the conditional instead calls a UnityEngine.AssetBundle$$LoadFromFile function. However, not much is delved from this either since this also receives the file similar to the LoadAssetBundle function, and returns "gibberish". I have looked around for any other functions of relevance, but since LoadEncryptedAB is never hit, none of the subsequent functions are ever reached as well.
## Post #31
- Username: Driftdslash
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 22, 2021 7:22 am
- Post datetime: 2021-07-21T23:26:44+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

but i got only unity3d files using nox player. how does that related with that files?
## Post #32
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2023-05-13T18:23:34+00:00
- Post Title: Re: Question - Extracting .unity3d file with non-"UnityFS" header

i'm sorry for asking this, but has there been any progress made, the game now has a dino season so i think bumping a 2-year thread is bad
