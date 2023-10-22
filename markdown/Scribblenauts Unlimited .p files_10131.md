## Post #1
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-02-11T10:14:02+00:00
- Post Title: Scribblenauts Unlimited *.p files

Hello. I need help with unpacking archives in this game. could u try to extract them?? thanks
[index.zip](https://xentaxbackup.github.io/file/6184_index.zip)
## Post #2
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-02-11T10:19:35+00:00
- Post Title: Scribblenauts Unlimited *.p files

add audio.p files
[audio.p.zip](https://xentaxbackup.github.io/file/6185_audio.p.zip)
## Post #3
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2013-03-10T04:22:25+00:00
- Post Title: Scribblenauts Unlimited *.p files

I signed up for the forums (donated) to also voice interest in this request.
## Post #4
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2013-03-11T18:29:09+00:00
- Post Title: Scribblenauts Unlimited *.p files

Sorry for the double-post.

If you look at index.bin and set your hex editor to 14 bytes per row, it seems the data is organized in this pattern.  I am not very experienced with hex editing or disassembly, but after spending the whole morning messing with this file in a hex editor, I have made some observations that may be useful:

First, delete the first 4 bytes to properly align the rows.

Columns 00-01: appears to be the value to designate which bigfile.p is being referenced
Columns 02-05: byte offset in bigfile.p for current entry
Columns 06-09: byte size of the current entry
Columns 0A-0D: unknown; this seems to be byte size -1 for all entries in objects.p

Byte values are stored little-endian.

0000E-1AB8B: 0000 (objects.p)
1AB8C-53F73: 0106 (1.p)
54302-5771F: 0300/0306 (audio.p)
53F74-54301, 57720-5CFE1, 5F91E-65AF3, 66750-69D73: 0206 (2.p)
58440-5844D, 5CFE2-5F91D, 65AF4-6674F: 0406 (ui.p)

I think we basically just need a script to parse the index.bin file this way.  Could someone help us out?
## Post #5
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-03-11T20:04:50+00:00
- Post Title: Scribblenauts Unlimited *.p files

Files in the archives seem to be looked up with just the index.
## Post #6
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2013-03-11T20:35:10+00:00
- Post Title: Scribblenauts Unlimited *.p files

The index definitely seems to be pointing to the right locations, the individual headers are lining up exactly.  Unfortunately they seem to be encrypted or compressed with an unknown format.

All of the large files indexed in audio.p have a similar header and start with "1FCB" and what appears to be some encoded text.

```

00000000  31 46 43 42 02 02 44 AC E0 6B 1A 00 6C 07 00 00  1FCB..D¬àk..l...
00000010  F0 F1 12 00 86 03 01 00 30 05 D4 06 E0 06 90 06  ðñ..†...0.Ô.à...
00000020  C8 06 90 06 8C 06 94 06 C8 06 58 06 B0 04 28 04  È...Œ.”.È.X.°.(.
00000030  44 05 34 06 80 06 88 06 7C 06 68 06 6C 05 74 06  D.4.€.ˆ.|.h.l.t.
00000040  84 06 10 05 40 06 A4 06 B8 05 40 04 0C 04 30 04  „...@.¤.¸.@...0.
00000050  B4 05 88 06 80 06 A8 04 20 04 1C 04 7C 05 18 05  ´.ˆ.€.¨. ...|...
00000060  74 05 A8 05 60 06 B0 06 E0 06 A0 06 D8 06 1C 07  t.¨.`.°.à. .Ø...
00000070  FC 05 B8 06 D8 06 70 06 0C 06 04 05 C8 05 20 07  ü.¸.Ø.p.....È. .
00000080  F8 06 14 07 5C 07 48 07 20 07 40 07 F0 06 90 04  ø...\.H. .@.ð...
00000090  C8 04 1C 04 58 05 98 06 90 06 CC 06 AC 06 B0 06  È...X.˜...Ì.¬.°.
000000A0  04 06 A4 06 38 05 7C 04 40 06 D0 06 00 07 04 05  ..¤.8.|.@.Ð.....
000000B0  6C 04 58 04 E8 05 B4 06 1C 06 60 06 BC 06 28 07  l.X.è.´...`.¼.(.
000000C0  C0 06 84 06 E8 05 D0 05 CC 06 E4 06 D4 06 04 07  À.„.è.Ð.Ì.ä.Ô...
000000D0  40 07 4C 06 68 06 28 07 3C 07 4C 06 F4 06 AC 06  @.L.h.(.<.L.ô.¬.
000000E0  10 06 28 07 24 07 48 07 14 07 24 07 5C 07 2C 07  ..(.$.H...$.\.,.
000000F0  30 07 04 06 D4 04 28 04 80 05 DC 06 FC 06 1C 07  0...Ô.(.€.Ü.ü...
00000100  24 07 1C 07 C0 05 30 06 34 06 98 05 BC 06 20 07  $...À.0.4.˜.¼. .
```
## Post #7
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2013-03-13T19:05:53+00:00
- Post Title: Scribblenauts Unlimited *.p files

I believe someone at the Scribblenauts Wiki knows somethign about it, as they have apparently extracted some character images from it. MAXinsanity I think the name was, but I'm not sure if they'd be willing to help. I would love to see if someone can properly unpack these files and get the resources from them so I can make my wallpapers and such.
## Post #8
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2013-05-17T12:38:07+00:00
- Post Title: Scribblenauts Unlimited *.p files

Sorry to bump this 2-month old topic.

I've found, after disassembly using IDA, that mss32.dll (the Miles Sound System) is responsible for handling audio playback and decoding audio files.

The "WAV" files that have a header starting with 1FCB are actually Bink Audio (.binka) files; it is handled by binkawin.asi (a DLL) in the game root directory. This file is probably also present in many other games using the MSS. If anyone has the ability to do so, they may wish to further analyse binkawin.asi and write a decoder for Bink Audio.

mss32.dll happens to have several utility functions, including one that can decode any file and return a PCM .wav file (a proper WAV). So by abusing the functions present in the DLL, the "WAV" files can be decoded into playable .wav files.

Following code is written in C#. 

```
using System.IO;
using System.Runtime.InteropServices;

namespace BinkA2WAV
{
    internal unsafe class Program
    {
        private static void Main(string[] args)
        {
            byte[] inData = File.ReadAllBytes(args[0]);
            IntPtr resultPtr;
            uint resultSize = 0;
            AIL_set_redist_directory(".");
            AIL_startup();
            if (AIL_decompress_ASI(inData, (uint) inData.Length, ".binka", &resultPtr, &resultSize, 0) == 0)
            {
                Console.WriteLine("Native call returned 0: failure; it reports \"{0}\"",
                                  Marshal.PtrToStringAnsi(AIL_last_error()));
                return;
            }
            var result = new byte[resultSize];
            Marshal.Copy(resultPtr, result, 0, result.Length);
            AIL_mem_free_lock(resultPtr);
            AIL_shutdown();
            File.WriteAllBytes(args.Length > 1 ? args[1] : args[0], result);
        }

        [DllImport("mss32.dll", EntryPoint = "_AIL_decompress_ASI@24")]
        private static extern int AIL_decompress_ASI([MarshalAs(UnmanagedType.LPArray)] byte[] indata, uint insize,
                                                     [MarshalAs(UnmanagedType.LPStr)] String ext, IntPtr* result,
                                                     uint* resultsize, uint zero);

        [DllImport("mss32.dll", EntryPoint = "_AIL_last_error@0")]
        private static extern IntPtr AIL_last_error();

        [DllImport("mss32.dll", EntryPoint = "_AIL_set_redist_directory@4")]
        private static extern IntPtr AIL_set_redist_directory([MarshalAs(UnmanagedType.LPStr)] string redistDir);

        [DllImport("mss32.dll", EntryPoint = "_AIL_mem_free_lock@4")]
        private static extern void AIL_mem_free_lock(IntPtr ptr);

        [DllImport("mss32.dll", EntryPoint = "_AIL_startup@0")]
        private static extern int AIL_startup();

        [DllImport("mss32.dll", EntryPoint = "_AIL_shutdown@0")]
        private static extern int AIL_shutdown();
    }
}
```

[This](http://code.google.com/p/vgce/source/browse/trunk/#trunk%2FScribbleExtract%2FScribbleExtract) is the utility I used to extract the *.p files; it is not written by me.
## Post #9
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2013-05-19T19:57:08+00:00
- Post Title: Scribblenauts Unlimited *.p files

This is really awesome!  Can someone compile these to win32 binaries?

EDIT:
Grabbed VS2012 and I'm going to try to give this a go myself.  If I'm not mistaken both ScribbleExtract and the code AngelSL posted should compile with it, right?  Hopefully I can figure it out  

EDIT #2:
Nice, I got ScribbleExtract compiled and it works perfectly!  I will include this for anyone else who wants to use it.  Just put it in the main install directory of Scribblenauts Unlimited and it will make an "extracted" folder.

I can't seem to get the code AngelSL posted working yet.  If anyone can provide some insight, it would be greatly appreciated.
[ScribbleExtract.7z](https://xentaxbackup.github.io/file/6412_ScribbleExtract.7z)
## Post #10
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2013-05-20T07:51:23+00:00
- Post Title: Scribblenauts Unlimited *.p files

> Reply from kooz
>
> This is really awesome!  Can someone compile these to win32 binaries?

EDIT:
Grabbed VS2012 and I'm going to try to give this a go myself.  If I'm not mistaken both ScribbleExtract and the code AngelSL posted should compile with it, right?  Hopefully I can figure it out  

EDIT #2:
Nice, I got ScribbleExtract compiled and it works perfectly!  I will include this for anyone else who wants to use it.  Just put it in the main install directory of Scribblenauts Unlimited and it will make an "extracted" folder.

I can't seem to get the code AngelSL posted working yet.  If anyone can provide some insight, it would be greatly appreciated.

What issue are you having? It's C#, by the way, not C++, so you'll have to compile it as that. And be sure to either change the relative path to mss32.dll to an absolute path, or you'll have to use it in the same directory where mss32.dll and binkawin.asi are located (same as ScribbleExtract).
## Post #11
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2013-05-20T10:11:40+00:00
- Post Title: Scribblenauts Unlimited *.p files

> Reply from AngelSL
>
> What issue are you having?

Mostly it's a complete unfamiliarity with the language and, in general, compiling native code.  I managed to get past the /unsafe flag and some other issues with VS2012 but I'm sure I was doing something wrong.  I pasted the code into a new "C# console application" and eventually got an exe compiled.

I tried Mono this morning while at work and managed to get it compiled via command line, seemingly without errors, but I am still getting an error when running it:

```
 Volume in drive C has no label.
 Volume Serial Number is 460C-7EAC

 Directory of C:\Users\Administrator\Desktop\binka2wav

05/20/2013  06:00 AM    <DIR>          .
05/20/2013  06:00 AM    <DIR>          ..
05/20/2013  05:42 AM             2,069 BinkA2WAV
11/21/2012  04:38 PM            55,296 binkawin.asi
11/21/2012  04:38 PM           424,448 mss32.dll
05/19/2013  06:11 PM         1,241,584 SCRIB.WAV
               4 File(s)      1,723,397 bytes
               2 Dir(s)  73,667,923,968 bytes free

C:\Users\Administrator\Desktop\binka2wav>mcs BinkA2WAV
BinkA2WAV(7,14): error CS0227: Unsafe code requires the `unsafe' command line option to be specified
Compilation failed: 1 error(s), 0 warnings

C:\Users\Administrator\Desktop\binka2wav>mcs BinkA2WAV /unsafe

C:\Users\Administrator\Desktop\binka2wav>BinkA2WAV SCRIB.WAV

Unhandled Exception: System.BadImageFormatException: An attempt was made to load a program with an incorrect format. 
(Exception from HRESULT: 0x8007000B)
   at BinkA2WAV.Program.AIL_set_redist_directory(String redistDir)
   at BinkA2WAV.Program.Main(String[] args)

C:\Users\Administrator\Desktop\binka2wav>
```


I will try the cmd line VS2012 compiler when I get home.
## Post #12
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2013-05-20T11:23:21+00:00
- Post Title: Scribblenauts Unlimited *.p files

> Reply from kooz
>
> AngelSL wrote:What issue are you having?

Mostly it's a complete unfamiliarity with the language and, in general, compiling native code.  I managed to get past the /unsafe flag and some other issues with VS2012 but I'm sure I was doing something wrong.  I pasted the code into a new "C# console application" and eventually got an exe compiled.

I tried Mono this morning while at work and managed to get it compiled via command line, seemingly without errors, but I am still getting an error when running it:
Code: Select allC:\Users\Administrator\Desktop\binka2wav>dir
 Volume in drive C has no label.
 Volume Serial Number is 460C-7EAC

 Directory of C:\Users\Administrator\Desktop\binka2wav

05/20/2013  06:00 AM    <DIR>          .
05/20/2013  06:00 AM    <DIR>          ..
05/20/2013  05:42 AM             2,069 BinkA2WAV
11/21/2012  04:38 PM            55,296 binkawin.asi
11/21/2012  04:38 PM           424,448 mss32.dll
05/19/2013  06:11 PM         1,241,584 SCRIB.WAV
               4 File(s)      1,723,397 bytes
               2 Dir(s)  73,667,923,968 bytes free

C:\Users\Administrator\Desktop\binka2wav>mcs BinkA2WAV
BinkA2WAV(7,14): error CS0227: Unsafe code requires the `unsafe' command line option to be specified
Compilation failed: 1 error(s), 0 warnings

C:\Users\Administrator\Desktop\binka2wav>mcs BinkA2WAV /unsafe

C:\Users\Administrator\Desktop\binka2wav>BinkA2WAV SCRIB.WAV

Unhandled Exception: System.BadImageFormatException: An attempt was made to load a program with an incorrect format. 
(Exception from HRESULT: 0x8007000B)
   at BinkA2WAV.Program.AIL_set_redist_directory(String redistDir)
   at BinkA2WAV.Program.Main(String[] args)

C:\Users\Administrator\Desktop\binka2wav>

I will try the cmd line VS2012 compiler when I get home.

C# compiles to MSIL. It's a managed language.

You need to target 32-bit when compiling, because mss32.dll is a 32-bit DLL. If not, BinkA2WAV will launch in 64-bit mode and it'll not be able to P/Invoke mss32.dll.

I've attached a working compile; make sure mss32.dll and binkawin.asi are in the same directory as it.

When time permits, I'll try and disassemble binkawin.asi and write a proper decoder.
[BinkA2WAV.zip](https://xentaxbackup.github.io/file/6417_BinkA2WAV.zip)
## Post #13
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2013-05-20T12:37:20+00:00
- Post Title: Scribblenauts Unlimited *.p files

> Reply from AngelSL
>
> You need to target 32-bit when compiling, because mss32.dll is a 32-bit DLL. If not, BinkA2WAV will launch in 64-bit mode and it'll not be able to P/Invoke mss32.dll.
Okay, that makes sense; I didn't even consider the compiler might default to x64.   I made another attempt at it with that in mind, but I'm still missing something:

```
Microsoft (R) Visual C# Compiler version 4.0.30319.17929
for Microsoft (R) .NET Framework 4.5
Copyright (C) Microsoft Corporation. All rights reserved.


D:\scribb>BinkA2WAV TITLE.WAV

Unhandled Exception: System.IndexOutOfRangeException: Index was outside the bounds of the array.
   at BinkA2WAV.Program.Main(String[] args)

D:\scribb>
```

I have a lot to learn, obviously, and I appreciate you taking the time to explain things.  


> Reply from AngelSL
>
> I've attached a working compile; make sure mss32.dll and binkawin.asi are in the same directory as it.
It works beautifully, thank you so much!  


> Reply from AngelSL
>
> When time permits, I'll try and disassemble binkawin.asi and write a proper decoder.
That would be awesome.  I'm sure there are/will be plenty of games that would benefit from it (like Defiance).  Perhaps it could even be added to vgmstream.


Anyway, thanks again.
## Post #14
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2013-05-20T13:27:18+00:00
- Post Title: Scribblenauts Unlimited *.p files

> Reply from kooz
>
> AngelSL wrote:You need to target 32-bit when compiling, because mss32.dll is a 32-bit DLL. If not, BinkA2WAV will launch in 64-bit mode and it'll not be able to P/Invoke mss32.dll.
Okay, that makes sense; I didn't even consider the compiler might default to x64.   I made another attempt at it with that in mind, but I'm still missing something:
Code: Select allD:\scribb>"C:\Windows\Microsoft.NET\Framework\v4.0.30319\csc.exe" BinkA2WAV.cs /unsafe /platform:x86
Microsoft (R) Visual C# Compiler version 4.0.30319.17929
for Microsoft (R) .NET Framework 4.5
Copyright (C) Microsoft Corporation. All rights reserved.


D:\scribb>BinkA2WAV TITLE.WAV

Unhandled Exception: System.IndexOutOfRangeException: Index was outside the bounds of the array.
   at BinkA2WAV.Program.Main(String[] args)

D:\scribb>

I've changed one LoC up there so it defaults to overwriting the original file if a new output filename is not provided (I already did this in my local copy but that was after I posted the source here).

Your compiled version should now work the same as mine.

Have fun!
## Post #15
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2013-09-25T06:42:23+00:00
- Post Title: Scribblenauts Unlimited *.p files

Hey guys, I just grabbed the newly released Scribblenauts Unmasked and figured I would have a go at ripping the music before I even dive into the game.  I ran into some trouble, so I thought I'd share my findings.

Unfortunately, ScribbleExtract (in its current state) is not working for Unmasked.  Despite similar resource and index file structures, the file containing file/pathname strings is formatted in a new XML format, which I assume ScribbleExtract cannot understand.

The good news is, the bigfile containing audio is still set up with the same structure (and is in fact, still named audio.p).  As before, the individual BinkA files contained within are simply concatenated, and are easily identified by their "1FCB" header.

Now, I'm sure many members here know exactly how to use QuickBMS or some other tool to make splitting this file easy... however, I do not.  After pages of mostly Linux/Unix solutions from Google, and getting further confused/sidetracked with an app by the name of PowerGREP, I suddenly remembered seeing some type of file splitting function in VGMToolbox...

As it turns out, this functionality of VGMToolbox works exactly as I had hoped.  The "1FCB" headers serve as a perfect delimiter to allow this tool to do the hard work.  The only drawback is, of course, the resulting filenames are completely generic, but the files themselves are all prepped and ready to be converted using AngelSL's brilliant BinkA2WAV.

I've included a screenshot of the settings I used to achieve this, though honestly it's pretty self-explanatory (obviously, if even I can figure it out  ).



vgmtoolbox.png (57.65 KiB) Viewed 237 times



...Sadly, after all that effort, it turns out I don't really care for the majority of the new music, haha.
## Post #16
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-09-26T15:18:05+00:00
- Post Title: Re: Scribblenauts Unlimited *.p files

Any chance for the new version? "Scribblenauts Unmasked A DC Comics Adventure" 
Thanks.
## Post #17
- Username: kooz
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 09, 2013 2:08 am
- Post datetime: 2013-09-30T17:55:20+00:00
- Post Title: Re: Scribblenauts Unlimited *.p files

> Reply from Savage
>
> Any chance for the new version? "Scribblenauts Unmasked A DC Comics Adventure" 
Thanks.
My previous post describes how to get the music/sounds (audio.p) extracted, albeit without any original filenames.  As far as the other resources go, it looks like an update to [ScribbleExtract](https://code.google.com/p/vgce/source/list) is going to be necessary.  I'm not sure if the author, [Adam Heinermann](https://code.google.com/u/117834403524165760048/), is on Xentax, but it looks like you could contact him through Google Plus or email.
## Post #18
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-10-29T13:35:40+00:00
- Post Title: Re: Scribblenauts Unlimited *.p files

Unfortunately, the decoder replaces the fcb files with the decoded streams.

If you want to preserve the original data, use the attached batch file. 

```
copy *.fcb dec
copy binka2wav.exe dec
copy binkawin.asi dec
copy mss32.dll dec
cd dec
ren *.fcb *.wav
for %%i in (*.wav) do binka2wav.exe %%i
move *.wav ..
del /q /s *.*
cd..
rd dec
```

[decode fcb.zip](https://xentaxbackup.github.io/file/6738_decode fcb.zip)
## Post #19
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-11-19T00:02:45+00:00
- Post Title: Re: Scribblenauts Unlimited *.p files

I finally got the game when it was in the Humble WB Games Bundle. It was quite a deal. In any case, I've written a new unpacker for it considering the one listed earlier in this thread is sort of borked. Find it [here](http://forum.xentax.com/viewtopic.php?f=32&t=10970). Also on that page is a modified BinkA2Wav that processes files recursively and doesn't overwrite the source file.
