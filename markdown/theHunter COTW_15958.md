## Post #1
- Username: spoodge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 07, 2017 11:26 am
- Post datetime: 2017-03-07T03:46:12+00:00
- Post Title: theHunter COTW

Hey guys, I'm not a coder by any stretch of the imagination, but I'm looking to see if it's possible to extract/compress files from this game.

I have no interest in the meshes or textures, my main aim is to try and customise and tweak the game settings, I've tried a few arc extractors but none of them work or they produce empty files and/or errors.

So in layman's terms and using a scale of 1 to 10 how possible is this ?

thanks to anyone with the time to look at this.

sample files:

[http://www21.zippyshare.com/v/ubvVRHRf/file.html](http://www21.zippyshare.com/v/ubvVRHRf/file.html)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-03-11T12:28:15+00:00
- Post Title: theHunter COTW

ARC:

```
uint16 UNK1
uint16 UNK2
uint16 UNK3
uint16 PADDING?
Entry entry


Entry structure:
uint32 UnknownFlags?
uint32 OffsetInDAT
uint32 FileSize
```

DAT:

```
uint32[3] PADDING
File file

```


Here you are:
[https://github.com/MaKiPL/TheHunter_COTW_extractor](https://github.com/MaKiPL/TheHunter_COTW_extractor)

Binary:
[https://github.com/MaKiPL/TheHunter_COT ... tag/1.0.0b](https://github.com/MaKiPL/TheHunter_COTW_extractor/releases/tag/1.0.0b)


The ARC archive you posted contain probably only FSB5 containers, but opening them with FSB Extractor produces non-playable OGGs (although metadatas, filesize and filestructure, everything is fine). I can't help you with this, I have zero knowledge on audio-files.
## Post #3
- Username: spoodge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 07, 2017 11:26 am
- Post datetime: 2017-03-12T13:44:09+00:00
- Post Title: theHunter COTW

Wow, many thanks for your efforts, what .dll package do I need to run this? I keep getting .dll missing and each time I get one it asks for another, vcruntime140d.dll, ucrtbased.dll, etc etc.
## Post #4
- Username: spoodge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 07, 2017 11:26 am
- Post datetime: 2017-03-12T16:29:58+00:00
- Post Title: theHunter COTW

Ok, I got it to run but comes up with an assertion failed message.



File path is C:\cotw\game22.arc

It makes a folder called game22ext but it stays empty.

I'm on win764, I have all the redistributables I can think of.

I'll keep trying, maybe I'm missing some VB dlls.
## Post #5
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-03-12T19:31:48+00:00
- Post Title: theHunter COTW

Oh, sorry. I posted the debug version of the application instead of release so it required additional developer-only librariers. My fault.

The error is code couldn't seek empty stream. This is caused probably by:
1. .TAB file not belong to the same folder and name as .ARC file (e.g. game22.arc and game22.tab are in the same folder)
2. The file is protected so you should run the software as administrator (this happens if the files are set to read-only or it belongs on system disk)
3. You are putting wrong path 

I compiled it as release this time and also put the checks if the streams are valid and if not, then it will display which file is bad:
[https://github.com/MaKiPL/TheHunter_COT ... tag/1.0.0c](https://github.com/MaKiPL/TheHunter_COTW_extractor/releases/tag/1.0.0c)

example working case:
## Post #6
- Username: spoodge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 07, 2017 11:26 am
- Post datetime: 2017-03-13T03:05:01+00:00
- Post Title: theHunter COTW

> Reply from MaKiPL
>
>  (e.g. game22.arc and game22.tab are in the same folder)

Arghh! facepalm

It was late, I was tired, totally forgot the .tab file.   

Umm, what do I do with all the bin files? 

thx
## Post #7
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-03-13T13:09:10+00:00
- Post Title: theHunter COTW

There are no filenames and/or files extensions written to either ARC or TAB file, that's why all you get is hash-like names and .BIN extension. 
Download Hex editor, whichever you like and open them one-by-one to locate the file you need. I don't have the game so I can't help you more, but by investigating the "game22" archive I can see it holds only sounds, so you should look in some other files. I wish you luck!
## Post #8
- Username: spoodge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 07, 2017 11:26 am
- Post datetime: 2017-03-13T13:15:47+00:00
- Post Title: theHunter COTW

Nah, this is way beyond enjoyment, I'm looking for a much easier automated way.

no biggie, thanks for your efforts so far, maybe someone else can make use of it.
## Post #9
- Username: FozeSt
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 26, 2015 4:20 pm
- Post datetime: 2017-03-26T06:06:07+00:00
- Post Title: theHunter COTW

How to extract textures from bin files?
## Post #10
- Username: spoodge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 07, 2017 11:26 am
- Post datetime: 2017-03-26T06:11:14+00:00
- Post Title: theHunter COTW

You can get meshes and textures using ninja ripper but UV maps are messed up.
