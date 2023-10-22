## Post #1
- Username: ekardon
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 27, 2015 10:32 am
- Post datetime: 2017-02-26T15:43:34+00:00
- Post Title: [Solved] I cannot open .dpk files with anything

Hi,

I was looking for the source files of this game, and came across with this file extension. I looked through the froum, but there doesn't seem to be anything that works. MultiEX Commander's latest version is unable to extract the files inside, only thing I get is Content.bin.

Also in [this thread](http://forum.xentax.com/viewtopic.php?t=573&highlight=starmageddon), there are two bms scripts, which doesn't work as well. File sizes differ from 1MB to 85MBs. I can upload all of them if anyone asks for them. I am giving a 5MB file for now.

I hope someone will find a solution. Thanks in advance.

Here is the file [bgm.dpk](https://mega.nz/#!hcNGRDpI!QE349mQ9xg3SBkeeE5laktAYOyzpmWCQ4H8o4WHk4ns) (5.0MB)
## Post #2
- Username: ekardon
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 27, 2015 10:32 am
- Post datetime: 2017-03-14T21:10:05+00:00
- Post Title: [Solved] I cannot open .dpk files with anything

Up. 
Any info is welcomed. Thank you.
## Post #3
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2017-03-16T07:17:22+00:00
- Post Title: [Solved] I cannot open .dpk files with anything

This is Quick BMS script for bgm.dpk file, which you provided. May not work with other dpk files, so do tests. For it dont uncomment a last "If-Else-Endif" construction, then files doesn't extract, and see what will writing. If something will wrong, report here and provide problem files.
[dpk_test.zip](https://xentaxbackup.github.io/file/12629_dpk_test.zip)
## Post #4
- Username: ekardon
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 27, 2015 10:32 am
- Post datetime: 2017-03-17T14:18:34+00:00
- Post Title: [Solved] I cannot open .dpk files with anything

> Reply from devmode
>
> This is Quick BMS script for bgm.dpk file, which you provided. May not work with other dpk files, so do tests. For it dont uncomment a last "If-Else-Endif" construction, then files doesn't extract, and see what will writing. If something will wrong, report here and provide problem files.
Wow, it works perfect with all the dpk files from this game. I did delete the comment marks from the code, and it was able to extract all the data. Just one question though, it dows not reach to %100, is this the normal behaviour? And one suggestion, it creates too many folders inside of each other, few folders could make it easy to browse. 

Also I wonder that, could it be possible to import to this archive?

Great script man, thanks
## Post #5
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2017-03-17T18:09:32+00:00
- Post Title: [Solved] I cannot open .dpk files with anything

> Reply from ekardon
>
> Just one question though, it dows not reach to %100, is this the normal behaviour?
Likely yes. Just it is significative percent of file read. 

> Reply from ekardon
>
> And one suggestion, it creates too many folders inside of each other, few folders could make it easy to browse
Extracted resources have paths how indicated inside original file. 
So more correctly, but it can be edited how prefer.

> Reply from ekardon
>
> Also I wonder that, could it be possible to import to this archive?
Theoretically, yes, format is simple. But some info is unknown, and I don't have ideas what is that can be and how it is important.
## Post #6
- Username: ekardon
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 27, 2015 10:32 am
- Post datetime: 2017-03-17T20:52:09+00:00
- Post Title: [Solved] I cannot open .dpk files with anything

> Reply from devmode
>
> Likely yes. Just it is significative percent read.Ok, then we have no problem here.

> Reply from devmode
>
> Extracted resources have paths how indicated inside original file. 
So more correctly, but it can be edited how prefer.Not big deal really, so it is fine. However I would like to learn how to tweak the path if you don't mind.

> Reply from devmode
>
> Theoretically, yes, format is simple. But some info is unknown, and I don't have ideas what is that can be and how it is important.It is not really that important. The game is a trivia game, so it asks questions, and audio files were packed inside of this dpk files. Unless someone has another language's audio files, because I don't, it will be useless (I would only use it fun purposes). 

I was just wondering if it was easy or not, because if it is and you can create something, it will be complete utility for this archive.

Again, great script. It was big help, thank you.

P.S: I have some other files that I don't know of. I don't have any idea about them. I think I will open up another thread. Would you like to take a look at them? File extensions are: mdl, txd, wld. File sizes doesn't exceed 10mb for txd, and 1mb for others. The folder says Questions, so I think they should hold some text data, but I have no idea.
## Post #7
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2017-03-18T20:32:48+00:00
- Post Title: [Solved] I cannot open .dpk files with anything

> Reply from ekardon
>
>  However I would like to learn how to tweak the path if you don't mind.

Ok, in attach little modified script
Set 'UseShortNames' to '1' and files will extracting to destination folder without long pathes. 

Well, I'm also wrote a more or less functional script for packaging.

[dpkPack_v1.zip](http://www.mediafire.com/file/l4k2kqhj0yff9c5/dpkPack_v1.zip)

Usage:

> * Place script to the quickbms folder.
>
> * Place folders with files what need to packing to same folder, and create *.CFG file with text e.g.:
>
> 
>
> #;----------------------------------------------
>
> 3
>
> \rw\Graphics\game\friends\AUDIO\bgm\OGG\Apt1.ogg
>
> \rw\Graphics\game\friends\AUDIO\bgm\OGG\Apt2.ogg
>
> \rw\Graphics\game\friends\AUDIO\bgm\OGG\apt3.ogg
>
> #;----------------------------------------------
>
> 
>
> * Run quickbms and select CFG file as input.
>
> 
>
> '3' <-- Thats count of files, what should packed. Shouldn't be biggest then count of lines plased bottom.
>
> All pathes should be relatives. 
>
> DPK file will be created in destination folder with CFG file name.

Possible to pack any files, but i don't know how game will do with them) Should works right with OGG files. In order to game found replaced sounds, obvious what they should having original names. 
Reconstruction of original pathes doesn't important. Likely game doesn't use them, but who knows.
[dpk_v1.zip](https://xentaxbackup.github.io/file/12654_dpk_v1.zip)
## Post #8
- Username: ekardon
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 27, 2015 10:32 am
- Post datetime: 2017-03-20T11:11:21+00:00
- Post Title: [Solved] I cannot open .dpk files with anything

> Reply from devmode
>
> 
Ok, in attach little modified script
Set 'UseShortNames' to '1' and files will extracting to destination folder without long pathes.This works quite nicely thanks 

> Reply from devmode
>
> 
Well, I'm also wrote a more or less functional script for packaging.

dpkPack_test.zipI can confirm that this is actually working without a problem. Only thing is I wasn't able to use it with full paths. So, I did use only filenames, and put CFG file and OGG files together in a folder. It works.

> Reply from devmode
>
> 
Possible to pack any files, but i don't know how game will do with them) Should works right with OGG files. In order to game found replaced sounds, obvious what they should having original names. 
Reconstruction of original pathes doesn't important. Likely game doesn't use them, but who knows.Game does quite good with them. I changed the intro music with a longer and bigger OGG file and packed it. The result was fantastic. It works without any problems. And as I said, I didn't used full paths. It seems devs of this game didn't really tried to make things hard.

Thank you for your hard work! You made a complete toolset for this archive type. Thanks.
