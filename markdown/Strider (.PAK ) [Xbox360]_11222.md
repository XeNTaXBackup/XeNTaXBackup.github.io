## Post #1
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-02-19T17:21:14+00:00
- Post Title: Strider (.PAK ) [Xbox360]

Who can help with unpacking the game files?

sample - [https://cloud.mail.ru/public/75be43c867cc/SHELL.PAK](https://cloud.mail.ru/public/75be43c867cc/SHELL.PAK)
## Post #2
- Username: jbeckman
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-19T23:01:03+00:00
- Post Title: Strider (.PAK ) [Xbox360]

I would need a 2nd file to know the format 100% but you can just run.
c:\offzip.exe -1 -a c:\file.pak c:\extract-folder 0
and this will give you the uncompressed pak file.
## Post #3
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2014-02-20T09:42:21+00:00
- Post Title: Strider (.PAK ) [Xbox360]

Would be nice to know what's in those archives, particularly the full global.pak and shell.pak, I'll send a PM with the smaller archives since I believe you still can't post the files directly due to the issue with copyright content.

However those are from the PC version so they will likely not match the X360 format.
(Big Endian or what it was, something like that.)


EDIT: Oh and the Offzip tip above worked, unfortunately they still can't be opened but they are no longer compressed.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-02-22T13:00:15+00:00
- Post Title: Strider (.PAK ) [Xbox360]

[http://aluigi.org/papers/bms/others/strider.bms](http://aluigi.org/papers/bms/others/strider.bms)
## Post #5
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-02-23T18:10:39+00:00
- Post Title: Strider (.PAK ) [Xbox360]

> Reply from aluigi
>
> http://aluigi.org/papers/bms/others/strider.bms

Thank script opens fine, but ... does not open large main required archive GLOBAL.PACK ( 1.14GB )
If you choose the regular version of the program (quickbms.exe) , it takes such a mistake

If you choose quickbms_4gb_files.exe version, it takes such a mistake

I can upload any file sharing Global.pak you to look into the problem. Tell me, how do you download more convenient?
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-24T10:33:25+00:00
- Post Title: Strider (.PAK ) [Xbox360]

> Reply from TimonS
>
> aluigi wrote:http://aluigi.org/papers/bms/others/strider.bms

Thank script opens fine, but ... does not open large main required archive GLOBAL.PACK ( 1.14GB )
If you choose the regular version of the program (quickbms.exe) , it takes such a mistake

If you choose quickbms_4gb_files.exe version, it takes such a mistake

I can upload any file sharing Global.pak you to look into the problem. Tell me, how do you download more convenient?
Download latest version of QuickBMS > [http://aluigi.altervista.org/papers/quickbms.zip](http://aluigi.altervista.org/papers/quickbms.zip)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-02-24T11:46:12+00:00
- Post Title: Strider (.PAK ) [Xbox360]

unfortunately the problem in this case was a longlong that was set as long (fixed in the current script) and the need of allocating lot of memory for unpacking the archive.
Basically the whole archive is packed as an unique compressed stream so the memory-to-memory feature of quickbms requires to allocate memory for the compressed data and for the uncompressed data which result in a lot of memory.
If you don't have many gb of RAM the only solution is unpacking the archive with offzip (which works as file-to-file) and then modifying the script to not use the MEMORY_FILE and load directly the unpacked file on the disk:

```
open FDSE "offzip_dump.dat" 1
...
    #log "" OFFSET SIZE MEMORY_FILE
    log "" OFFSET SIZE 1
```
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-02-24T15:47:43+00:00
- Post Title: Strider (.PAK ) [Xbox360]

I have updated the script with the suggestions of swuforce because the names are embedded in the first file (that it's not a real file), current version is 0.2a that supports also the xbox files
## Post #9
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-02-24T18:05:41+00:00
- Post Title: Strider (.PAK ) [Xbox360]

Tragically, I have all the same it did not work. And the updated version of the program, and downloaded a new version of the script, nothing helped. How to use

```
open FDSE "offzip_dump.dat" 1
...
    #log "" OFFSET SIZE MEMORY_FILE
    log "" OFFSET SIZE 1
```
[/quote]
too, constantly fails. Computer RAM - 6GB/ how can miss as much memory on such a file, it is not clear.

I upload file - [https://cloud.mail.ru/public/051f2ab6901c/GLOBAL.PAK](https://cloud.mail.ru/public/051f2ab6901c/GLOBAL.PAK)

still just wanted to ask if you can order from your script to convert textures? If yes, what is the approximate price?
.TEX to .dds and .dds to .TEX ( xbox360 ) whit swizling
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-02-26T09:32:55+00:00
- Post Title: Strider (.PAK ) [Xbox360]

the modification I suggested in the previous post is no longer valid because the script has been deeply modified.
If you unpacked the archive with offzip then replace all the "MEMORY_FILE" with "1" and replace the following:

```
clog MEMORY_FILE OFFSET PAK_SIZE PAK_XSIZE 
```
with:

```
open FDSE "00000014.pak" 1
```
## Post #11
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-02-26T14:27:47+00:00
- Post Title: Strider (.PAK ) [Xbox360]

> Reply from aluigi
>
> the modification I suggested in the previous post is no longer valid because the script has been deeply modified.
If you unpacked the archive with offzip then replace all the "MEMORY_FILE" with "1" and replace the following:
Code: Select allclog MEMORY_FILE OFFSET PAK_SIZE PAK_XSIZE with:
Code: Select allopen FDSE "00000014.pak" 1

I tried to unzip and I offzip again gives some mistake today ... try a few more options. If I did not get unpacked, could you give me pull out files with text and fonts? Willing to pay, if needed. Want to translate the game into Russian, and then we have 80% of the players simply do not understand the story
## Post #12
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2014-03-14T11:19:57+00:00
- Post Title: Strider (.PAK ) [Xbox360]

@TimonS -  if you decompress GLOBAL.PAK, you will have text, just open in hex editor.
I'm working on PC version, beginning of text file is looking like ?strings table?, English file \xF304 - 1267, the same number of string entries, there is even offset to beginning of strings.

I will probably need some coffee  

Info: PC version read uncompressed data.

Update: Yep, it's table, each string entry have unique id, probably depends on other sources and number, where last string ended.

Update 2: Got it: [https://www.dropbox.com/s/u23fm9t8yff8w97/STRIDER2.png](https://www.dropbox.com/s/u23fm9t8yff8w97/STRIDER2.png)
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-20T16:25:39+00:00
- Post Title: Strider (.PAK ) [Xbox360]

Hi guys! Any news with extracting main, big global.pak file? I'm trying to write maxscript for this game, but there's only a few models available in smaller .paks (player models are in global.pak too I guess). 

[](http://piccy.info/view3/6099024/1f501918f7b1775043ad308743035fa0/orig/)[](http://i.piccy.info/a3c/2014-03-20-16-25/i9-6099024/744x574-r)
## Post #14
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-22T15:04:39+00:00
- Post Title: Strider (.PAK ) [Xbox360]

TimonS have you managed somehow extract global.pak?
## Post #15
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-03-25T15:15:57+00:00
- Post Title: Strider (.PAK ) [Xbox360]

> Reply from zaramot
>
> TimonS have you managed somehow extract global.pak?
I meet same problem, I can't unpack Global.pak!
## Post #16
- Username: huyixiong
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 14, 2014 5:10 pm
- Post datetime: 2014-10-15T11:15:32+00:00
- Post Title: Re: Strider (.PAK ) [Xbox360]

@zaramot 
could you share your maxscript,i extract the PAK file,and i think there will be some models in the level folder
but the file doesn't have file extention,and i can't use the or identify the model,so can you tell me how to extract the mod package and how to import in the max? 
thank you
