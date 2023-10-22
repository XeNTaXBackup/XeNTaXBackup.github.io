## Post #1
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2013-05-19T04:10:40+00:00
- Post Title: Question about QuickBMS commands

Hello im writing a batch script to make it easier for me to access bms scripts and I have a problem with 2 things.

1. I can take archives in a specific folder and output them in their own folders all in a "./OUTPUT" folder but I notice that if I have a archive in an "./INPUT" folder that is also in another folder, it will output into the root of the "./OUTPUT" folder. An example of what I have is

```
"./quickbms.exe" -d -F "*.FILETYPE" "./SCRIPT.BMS" "./INPUT" "./OUTPUT"
```

All archives will output in their own folders "whatever the Archive name was" in the root of the "./OUTPUT" folder but wont recreate whatever folder they were in originally.

Another explanation using example above is, say I have a archive in the root of "./INPUT" folder and another archive in another folder inside "./INPUT" folder and want it to output to the "./OUTPUT" folder with the same folders and their names instead of all archives being decompressed to the root, how would I be able to do this? I basically want it to recreate folder names inside the "./OUTPUT" folder with wherever the archives are located in "./INPUT" folder.


2. I have a problem with multiple archive types being in the same folder, specifically; I have a BMS script that handles multiple file types under the same compression but I also have file types that aren't compressed the same in the same folder and it tries to access those files, when it does it errors out. Is there a way I can check the first 4 bytes of a file before the script accesses it to check if this file can be decompressed? I cant just specify the file type because there are some that are in the same folder that is compressed differently. If I were able to detect the first 4 bytes of a file before the script is called, I can skip files that aren't compatible.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-05-21T18:17:14+00:00
- Post Title: Question about QuickBMS commands

1)
I guess you refer to a situation like having the archives folder\subfolder1\myarchive.arc and folder\subfolder2\myarchive.arc.
Currently quickbms creates an output folder based on the name of the archive, the next week I will check if it's possible to take also the subfolder.

2)
quickbms has only a check for the extension or multiple extensions -f "*.mp3,*.ogg,*.txt"
Maybe next week I can check if it's possible to add an option to avoid the termination of the tool if the script calls cleanexit or idstring fails, it seems a good option for batch processes.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-21T22:56:19+00:00
- Post Title: Question about QuickBMS commands

i noticed quickbms does not like to work on files in a folder with the .dat extension.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-05-22T04:54:43+00:00
- Post Title: Question about QuickBMS commands

I have created a folder containing 2 files named asdf.dat and 00000000.dat and then I launched "quickbms script.bms that_folder" without having problems.

do you have a way to replicate that problem?
## Post #5
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2013-05-23T10:53:31+00:00
- Post Title: Question about QuickBMS commands

> Reply from aluigi
>
> 1)
I guess you refer to a situation like having the archives folder\subfolder1\myarchive.arc and folder\subfolder2\myarchive.arc.
Currently quickbms creates an output folder based on the name of the archive, the next week I will check if it's possible to take also the subfolder.

2)
quickbms has only a check for the extension or multiple extensions -f "*.mp3,*.ogg,*.txt"
Maybe next week I can check if it's possible to add an option to avoid the termination of the tool if the script calls cleanexit or idstring fails, it seems a good option for batch processes.
1. Exactly what I need, sounds good.
2. Also sounds like a good fix, one of the main problems I had is that I constantly re compress file types and put them in folders but sometimes I just want to decompress the entire folder without having to search for ones that are compressed, that sounds like it would fix my problem.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-23T12:48:52+00:00
- Post Title: Question about QuickBMS commands

I used this script

```
get size asize
get name basename
if magic == 0x4F4D4123
string name + .amo
log name offset size
elseif magic == 0x4544D4123
string name + .amt
log name offset size
endif

```

on files with .dat using the -d -F command ant it said no files existed.
i renamed them to any other extension then ran the same command worked no problem.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-05-24T15:15:41+00:00
- Post Title: Question about QuickBMS commands

@chrrox
do you have the same problem if you use {} instead of * in your filter?
## Post #8
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2013-05-29T08:20:37+00:00
- Post Title: Question about QuickBMS commands

aluigi THANKS for the fix. "I checked out the update already". Its great. I just have 2 small requests for you that I think is missing from QuickBMS which I feel is a much needed feature. I think there should be a extra modifier for -d command that wont make folders for individual files. "Keep -d the way it is but maybe make something like "-d n" n standing for nofolder creation from file name.
-d works good for archives but I also want to decompress individual files that aren't archives and keep them in the same folder without making individual folders for them.

"example of this, Say I have a folder named whatever in the ./INPUT folder that has FILENAME.ARCHIVE, and FILENAME.FILE.
I want both files to be generated in whatever folder they were named in the ./INPUT folder. FILENAME.ARCHIVE is an archive so -d works flawless with it "ESPECIALLY after the last update" but FILENAME.FILE isn't an archive so if I use the -d command it will make a folder for the file BUT if I don't use -d that file will be generated to the root of the ./OUTPUT folder and not in the original folder in the ./INPUT folder which is confusing for large compressing and decompressing projects with lots of files and folders."

secondly Id like to see a command that can ignore specific file types and names, kinda like the way -F works but instead of it finding the file type you specify in the "*.*" field afterwards, the script just ignores it.


What im doing personally is that im working with batch scripts and im kinda fusing 2 different scripts in one that handles different file types with their own command lines. With the suggestions I stated above I would be able to make my QuickBMS based de-compiler(s) MUCH easier to use.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-06-02T12:37:18+00:00
- Post Title: Question about QuickBMS commands

cool idea the negative filter, I have just added it to quickbms 0.5.21a:

-f "!{}.txt" will extract all the files except the txt ones
-f "{}.mp*;!{}.mp3" all the mp* files (like mpg or mpeg) except the mp3 files

why I use {} instead of *?
because windows is so stupid that even if you place your filter string within quotes it continues to handle the wildcards inside so in case of problems use {} instead of any * char and everything will work correctly!

I have not fully understood what you mean with that alternative -d anyway I have added also the -D option that doesn't create the folder with the same name of the file, so just the same relative path.
## Post #10
- Username: Controller
- Rank: n00b
- Number of posts: 11
- Joined date: Mon May 25, 2009 8:44 am
- Post datetime: 2013-06-02T16:37:04+00:00
- Post Title: Question about QuickBMS commands

I'd like to batch extract files to a subfolder each.
tried using the -d option, but fails (asks for output directory)

when manually specifying a directory, there's the problem it cannot be automatically created.
quickbms asks if the directory should be created (not so good for batching), and fails doing so.

If i create the directory manually, it works, but brings "Press RETURN to quit" and waits for input.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-06-02T16:52:19+00:00
- Post Title: Question about QuickBMS commands

try placing echo y in pipe before quickbms:

```
echo y | quickbms YOUR_OPTIONS
```
## Post #12
- Username: Controller
- Rank: n00b
- Number of posts: 11
- Joined date: Mon May 25, 2009 8:44 am
- Post datetime: 2013-06-03T10:53:27+00:00
- Post Title: Question about QuickBMS commands

echo y | ... works to confirm directory creating question. However, not supported by my batch tool. I'd appreciate adding an -y option or something alike.

The actual problem when creating directories is:
Instead of creating 
D:\GameMusicRip\2013\TR2013\bigfile.000_unpack\default\pc-w\audio\streams\music\ziggurat\_01_chasmzig_120_v01
it creates subfolders relative to the current directory, and multiple times, e.g.
D:\DEV\Software\Tools\ctConvF\helpers\GameMusicRip\2013\TR2013\bigfile.000_unpack\default\pc-w\audio\streams\music\ziggurat\_01_chasmzig_120_v01\GameMusicRip\2013\TR2013\bigfile.000_unpack\default\pc-w\audio\streams\music\ziggurat
or
D:\GameMusicRip\2013\TR2013\bigfile.000_unpack\default\pc-w\audio\streams\music\ziggurat\GameMusicRip\2013\TR2013\bigfile.000_unpack\default\pc-w\audio\streams\music\ziggurat\_01_chasmzig_120_v01\GameMusicRip\2013\TR2013\bigfile.000_unpack\default
( current directory \ specified path \ specified path ... )
guess it simply repeats creating subfolders until limit is reached
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-06-09T14:42:29+00:00
- Post Title: Question about QuickBMS commands

Do you have an example command to replicate the problem?

Here I have tried using -D with absolute and relative folders, from the input folder, from the output folder, using same input and output folder and so on but in my minimal tests I did there was nothing wrong.

I used just a simple script like the following for creating 2 files with different name:

```
get NAME basename
log NAME 0 SIZE
string NAME += ".blah"
log NAME 0 SIZE
```
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-06-09T14:53:42+00:00
- Post Title: Question about QuickBMS commands

I guess I have found a problem that may be related to this, I'm checking it
## Post #15
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-06-30T08:04:07+00:00
- Post Title: Question about QuickBMS commands

Hi. Simple question.
If i have filename in unicode, for example 

and use this command

getdstring name 0x4c
......
log name blablabla

i get file with name 00000000.dat
What i need to do? Something i did not think
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-06-30T10:20:09+00:00
- Post Title: Re: Question about QuickBMS commands

```
set name unicode name
```

remember to use the latest version of QuickBMS that I have released yesterday, it has a better support for unicode strings

note that the handling of utf16 endianess depepends by the current endian status (I tell you in case you get strange chars), the one of that string is little endian.
## Post #17
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-06-30T10:39:20+00:00
- Post Title: Re: Question about QuickBMS commands

Thanks. Now all is good.
I find this command in quickbms readme, but not correctly understand it and use new var - set nameascii unicode name or set name unicode nameascii
## Post #18
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-08-08T03:25:25+00:00
- Post Title: Re: Question about QuickBMS commands

Another one silly question 
It's possible use in quickbms double condition or triple and so on 
for example i need this condition if a != 0x0d or 0x5b or 0x58
if it's possible how i must write this condition, i try some variation but with no luck
## Post #19
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-08T09:37:53+00:00
- Post Title: Re: Question about QuickBMS commands

yes

if a == x

elif b == y

else c == z

endif
## Post #20
- Username: Roan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 16, 2019 5:52 pm
- Post datetime: 2019-05-18T09:27:32+00:00
- Post Title: Re: Question about QuickBMS commands

How to extract multiple .pak files at a time?
