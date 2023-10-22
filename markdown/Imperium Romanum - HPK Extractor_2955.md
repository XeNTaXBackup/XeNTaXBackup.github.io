## Post #1
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-01T12:39:25+00:00
- Post Title: Imperium Romanum - HPK Extractor

Hi there!

I made a archive extractor for Imperium Romanum,this game using a HPK archives (I didnt seen this in any game yet).

Into to archive:
Archive structure is pretty complex,its not encrypted but its using a few tricks how to fool hackers 

Most of files are compressed with ZLIB(like Textures and XML) but every file may be splitted into  32KB chunks (offsets are in ZLIB Header),few files have "ZLIB" tag,but they are not compressed,usually because of small input buffer (for example chunk with 24 bytes is not compressed,but directly saved into file).You can also find a relative or absolute offsets of files  or directories,which are also incorrect.

Game using also in few files a LZSS compression which is not supported in this Extractor ( I cannot find a correct library which will decompress LZSS files(I know structure of "LZSS" filles)).

USAGE:
HPKExtractor.exe [options] -hpk "YourFile.hpk"
Options are: "-zlib" - This will decompress all ZLIB files.

Game with work with compressed and decompressed files too,but if you will using decompressed files then you may notice a slight decrease of game performance.

Game will work with extracted archives,only one thing is need to be done to work:
Move all HPK archives from subfolders into main folder (where is exe located) then extract all archives,delete all hpk archives and folders Local and Packs.
Thats all.

Request: 
1. I'm looking for decompiler for a LUA files (5.1)
2. I'm looking for a LZSS library which will be able to decompress "LZSS" files
Any help will be appreciated 

Thank you for any help.
[HPKExtractor.rar](https://xentaxbackup.github.io/file/1464_HPKExtractor.rar)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-01T13:31:43+00:00
- Post Title: Imperium Romanum - HPK Extractor

> Reply from Demander
>
> Request: 
1. I'm looking for decompiler for a LUA files (5.1)
[http://luadec.luaforge.net/](http://luadec.luaforge.net/)
(though this one targets lua 5.02, it might be of help)

> 2. I'm looking for a LZSS library which will be able to decompress "LZSS" files
Some LZSS decompression code can be found here: [viewtopic.php?p=17531#p17531](http://forum.xentax.com/viewtopic.php?p=17531#p17531)
But of course this might be a variation of LZSS, so you still have to figure out the correct parameters.
## Post #3
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-01T14:18:42+00:00
- Post Title: Imperium Romanum - HPK Extractor

Thank you for your reply  
1. LUADec works only for 5.0 not 5.1  I tried it sooner and it wont works.

2. I'll look at that,I found in main exe a procedure which will decompress a LZSS,its pretty long procedure but there is no calls in another parts in exe (there is only byte operations),so I ripped that procedure from exe to my app,I know a parameters to this procedure but I'm unable to add them into correct registers (I dont know asm well,so I need to help with that).

LZSS procedure looks like same as ZLIB,but I dont know last parameter.

procedure LZSSDecode (const InBuffer:Pointer;const InSize:Integer;out OutBuffer:Pointer;out OutSize:Integer;Unknown:Integer);
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-01T14:55:01+00:00
- Post Title: Imperium Romanum - HPK Extractor

zlib actually uses LZSS combined with Huffman entropy coding.
you might post a text file containing the code you ripped if you want help with it.

btw Antivir detects the trojan horse TR/Dldr.Delf.T.3 in HPKExtractor.exe
## Post #5
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-01T15:16:38+00:00
- Post Title: Imperium Romanum - HPK Extractor

I dont known,if its legal to releaseng parts of code from PE  probably not...

But I can post here a LZSS file,which is created by game but its not in game included:
UserConfig.dat

Header:

Magic: 4 Bytes
Original FileSize: 4 Bytes
Chunk Size: 4 Bytes
Unknown: 2 Bytes - Probably parameters to LZSS decompression algo
ChunkOffset: 4 Bytes - Offset to first chunk

Next bytes are compressed data.

There are uncompressed data,LF is linefeed,Tab is tab key .. everything should be without commas in uncompressed file 

```
ASCII "userconfig.id_old_rect =",LF,"{",LF,TAB,"idTabletDlg = false;",LF,TAB,"idEconomyOverviewDlg = box(point(197, 173), point(826, 595));",LF,TAB,"idSettlementOverviewDlg = box(point(197, 173), point(826, 595));",LF,"};",LF,"userconfig.GameKe"...
```
## Post #6
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-01T15:20:51+00:00
- Post Title: Imperium Romanum - HPK Extractor

> Reply from Rheini
>
> zlib actually uses LZSS combined with Huffman entropy coding.
you might post a text file containing the code you ripped if you want help with it.

btw Antivir detects the trojan horse TR/Dldr.Delf.T.3 in HPKExtractor.exe

Really ? it works for me normally,it may be because of used packer,I already uploaded it again with different PE compressor.
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-01T15:51:54+00:00
- Post Title: Imperium Romanum - HPK Extractor

Still detects that trojan horse. What packer do you use?
btw which programming language do you use for your tool?
## Post #8
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-01T15:59:30+00:00
- Post Title: Imperium Romanum - HPK Extractor

Maybe its because of your Antivirus program,I'm using latest AVG antivirus,and I dont have any reports because of viruses.
and I'm writing in Object Pascal (delphi)
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-01T16:15:23+00:00
- Post Title: Imperium Romanum - HPK Extractor

Maybe you could just use upx or MEW?
## Post #10
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-01T16:29:15+00:00
- Post Title: Imperium Romanum - HPK Extractor

> Reply from Rheini
>
> Maybe you could just use upx or MEW?

Okey I packed it for last time  If it will report you any virus or horse then you have really bad antivirus
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-01T22:19:52+00:00
- Post Title: Imperium Romanum - HPK Extractor

Thank you for your patience  It works now.

> Reply from Demander
>
> I dont known,if its legal to releaseng parts of code from PE  probably not...
But you might tell us the function VA (Virtual Address)

> Reply from Demander
>
> Into to archive:
Archive structure is pretty complex,its not encrypted but its using a few tricks how to fool hackers
Care to share your knowledge?
## Post #12
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-02T11:11:14+00:00
- Post Title: Imperium Romanum - HPK Extractor

Hi again 

1) I can tell you where that procedure begins  But better will be a offset where is function called,to see what parameters going to this procedure.

Go to "0066B1C0",this is procedure where is called a procedure of LZSS decompression 
(0066A160).
(I'm using patch 1.1)

Maybe somebody can rewrite that procedure to asm block,it doesnt matter which language you are using,so it can be universal to all languages.

But probably,it will be better to new function (because of legal issues)....

2) I'll write a HPK structure later,I still dont know few bytes (most of them are same in every hpk archive,but its better to know them because of archive rebuilding)

3) I found that game using a next compression algo  I think its used only for savegame files (*.sav),strange thing is that "magic" is "LZIS",I dont know if its any kind of compression algo or its just LZS.

EDIT:
"LZIS" structure is similar as "ZLIB" and "LZSS":
4 Bytes - magic
4 Bytes - original filesize (yeah original saved games has over 13MB per each)
4 Bytes - chunk size
2 Bytes - unknown (probably parameters to decompression algo)

Next bytes are offsets to chunks,every chunk can be smaller than chunk size,but probably should not be larger.

I made a screenshot of compressed file,selected bytes are beginning of compressed chunk,maybe somebody will recognize a compression algo (beginning of every compressed chunk seems to be same).

[http://img150.imageshack.us/img150/1323/86403044id5.png](http://img150.imageshack.us/img150/1323/86403044id5.png)
## Post #13
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-02T12:31:20+00:00
- Post Title: Imperium Romanum - HPK Extractor

> Reply from Demander
>
> I made a screenshot of compressed file,selected bytes are beginning of compressed chunk,maybe somebody will recognize a compression algo (beginning of every compressed chunk seems to be same).

http://img150.imageshack.us/img150/1323/86403044id5.png
As I already said before, there's too much redundancy in the first part (all those 0x6666 and 0x0000 for example)
That part can't be compressed. Did you try to compress it again (e.g. with WinRAR or 7zip)? This way you can get a hint if the data is already compressed.
## Post #14
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-02T12:42:53+00:00
- Post Title: Imperium Romanum - HPK Extractor

Its compressed  I know it from header... original filesize is saved here  (I'm 100% sure)

I splitted one chunk from saved game,maybe it will help to find a compression algo.
[Alexandria_auto.rar](https://xentaxbackup.github.io/file/1466_Alexandria_auto.rar)
## Post #15
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-04T12:31:24+00:00
- Post Title: Imperium Romanum - HPK Extractor

Nobody to help ?:P Please its important or I cant finish extractor.
I just need somebody who knows assembler language,for function calling explanation...
## Post #16
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-04T12:45:07+00:00
- Post Title: Re: Imperium Romanum - HPK Extractor

You need to pass the correct arguments to the function by pushing them in reverse order. Something along the lines of

```
   {
      pusha
      push arg2
      push arg1
      call function
      popa
   }
```
## Post #17
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-04T13:25:34+00:00
- Post Title: Re: Imperium Romanum - HPK Extractor

This is what I already know  but problem is somewhere else. I'm callin that function in normall way,not in asm code.

This is my procedure which including that asm code:

```

```


In game exe file,that function is called:

```
 push ecx // Unknown
 mov ecx,dword ptr ss:[esp+01ch] // I dont know
 push edx // OutBuffer Size
 mov edx,dword ptr ss:[esp+01ch] / I dont know again
 push eax //OutBuffer pointer
 push ecx // InBuffer Size
 push edx // InBuffer pointer
 call function // call LZSS decompression

Some of registers are used more times,so how that function obtains that values ? From stack ?

```

So If I want to call that function in normal way then I need to move a parameters from my procedure to correct registers

So it should be something like:

```
asm
// added
        mov ebx,InBuffer
        mov edi,InSize
        mov eax,OutBuffer
//begin of original function
...

```


I posted a offsets if that before,if you dont own that game,you can download only patch,it includes a game exe file.

Thanks for any help.
## Post #18
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-04T13:42:49+00:00
- Post Title: Re: Imperium Romanum - HPK Extractor

I haven't tried to embed a function like that yet, but I think this isn't so easy because of the stack and so on.
Why don't you translate it back into C?
## Post #19
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-04T13:56:46+00:00
- Post Title: Re: Imperium Romanum - HPK Extractor

> Reply from Rheini
>
> I haven't tried to embed a function like that yet, but I think this isn't so easy because of the stack and so on.
Why don't you translate it back into C?

I know much better Object Pascal (for years) than C or C++ (for months),anyway translating it to Object Pascal will be hard too (because of knowledge of asm) but not too as in C++,so I want  to use game code in my app only for debugging that function,rewriting will be much easier.

I think that it will be pretty easy,function needs only 5 params,which I ,except 1, know them all.
That function doesnt work with another data,or buffers... its standalone.
## Post #20
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-04T15:17:34+00:00
- Post Title: Re: Imperium Romanum - HPK Extractor

Had a look at it in the demo exe.
At least the calling function seems to be a class member function. ecx contains the this pointer for the object.

```
mov     byte ptr [esp+10h+var_10], al
mov     ecx, [esp+10h+var_10]
push    ecx
```

It probably gets some private member of the class, saves it into a local variable and pushes it to the function (where it is more or less used as an index into an array).

It's not so important that the registers hold the right values cause the function gets the arguments from the stack.
Ensure that your LZSSDecode function uses the stdcall calling convention and the compiler doesn't setup a stack frame.
In D there is a command named "naked" to do that:
> naked
>
> 
>
> Causes the compiler to not generate the function prolog and epilog sequences. This means such is the responsibility of inline assembly programmer, and is normally used when the entire function is to be written in assembler.
## Post #21
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-03-04T15:51:22+00:00
- Post Title: Re: Imperium Romanum - HPK Extractor

Thanks for your answer,but I may not understood at all 

So What I need to do is to PUSH that arguments into correct stacks ?

Maybe you can send me PM with example ?:) or if you are using a any kind of messanger (msn,icq or so on) maybe you'll be able to help me more  (also its more faster)

Thank you
## Post #22
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-04T16:50:18+00:00
- Post Title: Re: Imperium Romanum - HPK Extractor

Simply make your LZSSDecode function use the stdcall convention, in C this works by using the __stdcall modifier, in D this works by using extern(Windows) cause most Windows Api functions use stdcall.
Then you just put the asm code in your LZSSDecode function and make sure the stack frame is created properly. Either use that "naked" way I described (if something like that exists in Delphi) or you got to remove the prolog and epilog instructions (like mov ebp,esp and so on)
Then you have to deal with the data used at 66A18E (demo v 1.01.118).
I mean that array at 66AACC and that offset array at 66AA8C.
You got to figure out what they do.

EDIT: Seems to be some compiler optimization for that big switch at 66A18E
It seems to have 36 cases, where 20 lead to the error case (function return)
## Post #23
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-08T23:58:21+00:00
- Post Title: Re: Imperium Romanum - HPK Extractor

> Reply from Demander
>
> Request: 
1. I'm looking for decompiler for a LUA files (5.1)
Well, no decompiler, but at least recently a Lua 5.1 disassembler has come up: http://luaforge.net/projects/chunkspy/
