## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-12-20T09:27:18+00:00
- Post Title: A Static Hook Technique for Android Game Resources Dumping

It’s not rare to encounter circumstances for Android games where the asset files are encrypted. If it’ll take too much work to reverse engineering the algorithm from the .so library, while we only need certain files to be decrypted, a relatively easier way is to hook the call of a function of which the arguments contain the data we need, and dump the data to local files directly.

Unlike known methods, in this article we'll modify the assembly code in the .so library file directly, hence avoiding the routines of writing additional hooking program, which however brings some restrictions to the applicability of this method:

1. the standard library functions we need must have been imported by the .so library already. Since dumping mostly involves fundamental functions like malloc, free, fopen, fwrite, etc., it’s not difficult to meet this condition;

2. there must be enough room to place the assembly code of our dump routine. We need to write our code in the .text section which inevitably will occupy and break existing sub-routine. Therefore, we need to find a "victim" sub-routine which is long enough to accommodate all of our assembly code, while destroying it won't damage the game's logic and crash it. A second choice is to adapt the part of code of a sub-routine which handles an exception that is unlikely to happen in actual run-time. A last choice would be locating a sub-routine that is called only after the function to be hooked has been called, so that you can get the data dumped before the game crashes. But you might only be able to dump one asset this way.

Apart from dumping assets, this method might also be used for debugging purpose such as revealing the actual address of a dynamically calculated function call, if the game has used anti-debugging techniques.

To demonstrate this trick, I'll show you how to dump the manifest list of Asphalt 9: Legends. Here're a few facts about this game that you need to know:
1. the game packages use hashes for asset names, while for earlier versions of the game they came with an unencrypted manifest file called "__manifest_NX_100__", which contains the mapping info of the original names to the hashes. This manifest file has been encrypted in later versions of the game.
2. the game uses split apk packages and each package comes with a corresponding encrypted manifest file.

The benefits of using this technique for the task would be that we don't need to care for the complicated decryption routine, and that we can dump each manifest to the same file in append mode to get the complete list, assuming the function is called by a single thread. 

The applications and knowledge required for the task are:
1. an Android emulator. For this demonstration it's Nox.
2. a Disassembler with the ability to patch assembly code. For this demonstration it's IDA Pro;
3. basic knowledge about ARM assembly. Here's a good tutorial to start with for the basics (credit to @azeria_labs): [https://azeria-labs.com/writing-arm-assembly-part-1/](https://azeria-labs.com/writing-arm-assembly-part-1/) .
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-12-20T09:33:10+00:00
- Post Title: A Static Hook Technique for Android Game Resources Dumping

Now let's begin. Install the game in the emulator and get the main .so library named " libAsphalt9.so". You can pull it from the emulator after installation or just unpack the corresponding split apk to get it. 

Once we have the library file, we can load it in IDA, and wait for the analyze process to complete. When it's done, navigate to the menu "View", "Open subviews", "Strings", and wait for the generation of string list to complete. When that's finished, search for the string "manifest" in the Strings View, as shown below:


Double-click on the string "__manifest_{}_{}__" and press the "X" key when the cursor is on the variable to reveal where it's been referenced, as shown below:


As you can see, it's been referenced once only by a sub-routine. Double-click on the entry to jump to its address, where it's like:


Press the "F5" key to decompile the assembly into pseudo code:


Here in the "do ... while" loop beginning from line 72, it constructs the manifest name and iteratively check if the file exists. Collapse parts of the code and it'll reveal some overall logics of this sub-routine:


We notice that at line 97 and line 112, it called the same function with an error message string as one of the arguments, so we can just assume that function merely inform the game of an error message. Basically we can draw some conclusions:
1. if the condition at line 95 meet, the manifest file is not found;
2. if the condition at line 110 meet, it means the "manifest key is not valid".

Base on that we can tell that the function will load the file after line 123. Scroll down and we can see:


We can tell that the codes between line 128 and line 132 are possibly in charge of reading the manifest file. Especially the function call at line 131, where the address of the variable v63 is passed into the function while it's also been used in the following condition. But we don't need to care for the details of that. What we need is to find the variable that holds the decrypted manifest data. Keep scrolling down from line 159:



It seems that the manifest is parsed in this piece of code. We noticed that at line 187 the variable v61 and a linefeed character is passed into the sub-routine, and at line 217, v61 is fed into the std::string destructor. That means v61 is a pointer to a std::string object. Let's dive into the function at line 187:


We see that the pointer to the character and a local variable of its length is passed into the sub-routine at line 6, as the 2nd and the 3rd arguments, while a1 is still the first argument. Look into the function at line 6:


It's not hard to understand what it's doing here. It checks the length of the string and if it's larger than 0xB (11 in decimal), it'll allocate a piece of memory to hold the string, and the size of the buffer is aligned to 0x10 bytes. In this case, the layout of the class std::string is as:

```
{
	long	bufferSize; // or capacity, value = (actual bufferSize) | 1
	long	stringLength;
	char*	stringBuffer;
}

```

And if the string length is smaller than 11, the string is store on the stack, and the layout of the class std::string would be:

```
{
	byte	stringLength; // value = (actual stringLength) * 2
	char	stringBuffer[11];
}

```

Either way, the size of the struct std::string is 12 bytes fixed. The trick to determine which layout it belongs to, is to check the zero bit of the first byte, and if it's zero, then the string is stored on the stack, otherwise it's stored on the heap.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-12-20T09:43:22+00:00
- Post Title: A Static Hook Technique for Android Game Resources Dumping

Back to the routine where this string constructor is called, it seems the codes below are splitting the manifest string by the linefeed and processing each line accordingly:


And at line 195 in the above screenshot, the variable v56, and the linefeed string, and an index of the loop is passed into the function. Then at line 196 it checks the return value and break the loop if it's -1. Naturally we can tell that the function at line 195 must be looking for the i-th occurrence of the linefeed character in the manifest string buffer. So, we know that v56 should be the string object that hold the manifest data.
Scroll down to the end of the pseudo code and base on line 237 we can confirm that the data type of v56 is also a std::string.


Place the cursor at line 237, then switch to the IDA View, right-click and navigate to the "Synchronize with" entry, and select the corresponding pseudo code view:


Then we'll be directed to the assembly code where the string destructor is called:


The function call at address 0x02715570 is what we're going to hook. We'll change this instruction and make it call our dump routine instead, and we can place this original call in our dump routine to avoid memory leak if necessary.
The pseudo code of the dump routine is simple, we just open a file and save the data to it, and destroy the string at the end. Since we know that the string for the manifest definitely contains more than 11 characters, we can just simplify the routine and skip the check of whether it's stored on heap or on stack.
The overall pseudo code is as following:

```
{
	fp = fopen("filepath", "ab");
	if (fp != NULL)
	{
		fwrite(str->stringBuffer, str->stringLength, 1, fp);
		fclose(fp);
	}
	std::string::~string(str);
}

```

Now let's translate it into assembly:

```
ADD     R11, SP, #0 ; backup current stack pointer
SUB     SP, SP, #0x80 ; allocate some space on the stack, though no local variables are used here
MOV     R4, R0 ; backup the string * pointer

ADR     R1, .+0x44 ; mode, "ab", which is 0x44 bytes below current address
ADR     R0, .+0x44 ; filename, which is 0x44 bytes below current address
BL      fopen ; call fopen

CMP     R0, #0 ; check if the return FILE * pointer is null
BEQ     .+36 ; jump to dump_open_failed if failed open file

MOV     R5, R0 ; backup FILE * pointer
MOV     R3, R0 ; FILE *
MOV     R2, #1 ; count
LDR     R1, [R4,#4] ; size
LDR     R0, [R4,#8] ; buffer

BL      fwrite ; fwrite(buffer, size, 1, fp)

MOV     R0, R5 ; FILE *
BL      fclose ; close the file

; label dump_open_failed
MOV     R0, R4 ; string *
BL      _ZNSt6__ndk112basic_stringIcNS_11char_traitsIcEENS_9allocatorIcEEED1Ev ; original call of std::string::~string()
SUB     SP, R11, #0 ; restore current stack pointer
POP    {R4,R5,R11,PC} ; restore registers and return to the call

mode DCB "ab\0\0" ; mode
filename DCB "/data/data/com.gameloft.android.ANMP.GloftA9HM/manifest.dump\0" ; filename

```

The output filename I used is "/data/data/com.gameloft.android.ANMP.GloftA9HM/manifest.dump", the path "/data/data/com.gameloft.android.ANMP.GloftA9HM/" is created once the game is installed so the path existed and the game has the write permission to this path. You can choose a filename as you like as long as there's enough room to hold the string. If there's no enough room even for a shortest path, then you'll have to pick an existing string that's long enough and which is referenced as is, i.e., it must not be served as a format string. Then you place a pointer to this string, at the end of the dump routine, and reference it like:

```
ADD     R1, PC, R1 ; get the absolute address of the string. value in R1 is the address of the string relative to PC

```

The complete assembly code is as following:

```
ADD     R11, SP, #0 ; backup current stack pointer
SUB     SP, SP, #0x80 ; allocate some space on the stack, though no local variables are used here
MOV     R4, R0 ; backup the string * pointer

LDR     R1, [PC, #0x44] ; mode, "ab"
ADD     R1, PC, R1
LDR     R0, [PC, #0x40] ; filename
ADD     R0, PC, R0
BL      fopen ; call fopen

CMP     R0, #0 ; check if the return FILE * pointer is null
BEQ     .+36 ; jump to dump_open_failed if failed open file

MOV     R5, R0 ; backup FILE * pointer
MOV     R3, R0 ; FILE *
MOV     R2, #1 ; count
LDR     R1, [R4,#4] ; size
LDR     R0, [R4,#8] ; buffer

BL      fwrite ; fwrite(buffer, size, 1, fp)

MOV     R0, R5 ; FILE *
BL      fclose ; close the file

; label dump_open_failed
MOV     R0, R4 ; string *
BL      _ZNSt6__ndk112basic_stringIcNS_11char_traitsIcEENS_9allocatorIcEEED1Ev ; original call of std::string::~string()
SUB     SP, R11, #0 ; restore current stack pointer
POP    {R4,R5,R11,PC} ; restore registers and return to the call

; mode
00 00 00 00 ; =( (address of mode string) - (value of the PC register when it's is dereferenced) )
; filename
00 00 00 00 ; =( (address of filename string) - (value of the PC register when it's is dereferenced) )

```
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-12-20T09:53:05+00:00
- Post Title: A Static Hook Technique for Android Game Resources Dumping

Now we need to find our "victim" function to place the code. I found one by looking for the reference of the string " /system/app/Superuser.apk":



We can tell from the pseudo code that this function merely checks whether the "su" command is available and return the result as a Boolean value. The result is stored in a global variable and accessed directly for later calls. It's surely long enough to hold our codes.

Switch to the IDA View, and place the cursor at the symbol of this function, then navigate to the "Edit" menu, then select "Functions", "Delete function". Then right-click to use the Assemble tool, or the Patcher utility of the Keypatch tool, to modify the 2nd and the 3rd instructions, and NOP the rest of the instructions like this:




Then place the cursor at the label "loc_3CA551C", and press the "P" key to create a function as below:


Press F5 on the code and we can see the pseudo code like this:


Now we can write our code on the NOP area:






We can adjust the form of the constants to make it look closer to our original code.

Place the cursor at the first remaining NOP instruction, then switch to the Hex View, and "Synchronize with" the IDA view, as shown below:


Press F2 when the cursor is placed on the data, then we can modify the binary directly. On the left side you can only type in hex value while on the right side it allows input of characters. Modified the hex data like this:


Note that I merely fill the rest of the space with the same character to reveal that there're more room we can use. You don't have to do that as long as your string terminates with a null character. Press F2 again to apply the changes.

Now switch back to the IDA View and undefine the two symbols at 0x3CA557C and 0x3CA5580, then re-define them as constant char arrays:




Now go to the beginning of this function and press "P" to create a function in IDA:


The adjusted codes are as following:


Now let's press the F5 key and see how the pseudo code look like:


The mode string "ab" doesn't show as a literal string as it's shorter than 4 characters. Not really a problem though.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-12-20T09:55:36+00:00
- Post Title: A Static Hook Technique for Android Game Resources Dumping

Finally, we can now hook the function call. Place the cursor at the call of the string destructor in pseudo code view, and "Synchronize with" it under the IDA view:




Then patch the BL instruction to call our dump routine like this:




As a final step, navigate to the "Edit" menu, select "Patch program", then "Apply patches to...", and save the patched .so file to an individual path.
Now we can examine if this will work. Launch the Nox emulator, open a cmd window from where it's installed, and use the adb tool to connect to the emulator. 
Then we need to push the modified .so to the game's lib path. For this game it's "/data/app/com.gameloft.android.ANMP.GloftA9HM-1/lib/arm/":


When it's done, run the game in the emulator, and check if the dump file has been generated:


Make sure to check if the file size stop growing so that we get a complete manifest list.

Check the first 5 lines of the file and we can confirm that it worked as expected:


Pull the dump file from the emulator and we can do some further procession with it.
