## Post #1
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-12-17T12:57:09+00:00
- Post Title: The Saboteur .PCK files

Saboteur.pck
English(US).pck
It is possible to unpack this files?

Here is first 20mb of 600mb from file Saboteur.pck
[http://multi-up.com/187686](http://multi-up.com/187686)
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-12-17T23:27:08+00:00
- Post Title: The Saboteur .PCK files

```
{
	char magic[4]; // "1KCP"
	uint unknown;
	uint numDirs;
	PCKDirectoryEntry dirs[numDirs];
}

struct PCKDirectoryEntry
{
	uint numFiles;
	uint offsetToFileEntries;
}

struct PCKFileEntry
{
	uint unknown;
	uint size;
	uint offset;
}
```
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-18T00:00:42+00:00
- Post Title: The Saboteur .PCK files

translation of the format showed by GameZelda in a quickbms script:

```
get unknown long
get numDirs long
for i = 0 < numDirs
    get numFiles long
    get offsetToFileEntries long
    savepos TMP
    goto offsetToFileEntries
    for j = 0 < numFiles
        get unknown long
        get size long
        get offset long
        log "" offset size
    next j
    goto TMP
next i
```
note that the extracted files are archives (BKHD)
## Post #4
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-12-18T06:37:57+00:00
- Post Title: The Saboteur .PCK files

@ GameZelda & aluigi
Thanks, but what to do with these BKHD files?
I see inside of them RIFF headers.
ps: It's looks like PCK files have similar structure as in Assassin Creed 2 archives.
## Post #5
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-12-18T08:21:03+00:00
- Post Title: The Saboteur .PCK files

Yep its WWise RIFF too - looks like this codec will be more common in games. 
Creed2 X360; Divinity2 and now The Saboteur.
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-12-18T22:56:59+00:00
- Post Title: The Saboteur .PCK files

HMM these riff should convert with the eve converter right?
## Post #7
- Username: shearerc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 05, 2010 10:09 pm
- Post datetime: 2010-02-06T14:02:11+00:00
- Post Title: The Saboteur .PCK files

> Reply from OrangeC
>
> HMM these riff should convert with the eve converter right?
You probably already figured by now, but ww2ogg 0.8 by hcs can convert those pesky RIFFs to a "proper" OGG vorbis file.
## Post #8
- Username: DarkBolo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 23, 2010 3:00 am
- Post datetime: 2010-11-23T07:56:15+00:00
- Post Title: The Saboteur .PCK files

Hi guys
I know this topic is a bit old, but I'll give it a try.
I have extracted those .BKH files from .PCK (Saboteur).
Now I have .BKH files and some wave files.
When I'm trying to convert those wave with ww2ogg09
I am getting .OGG files, but they weight only 1KB each
and when I am playing them nothing happens.
What am I doing wrong? Please help!
I love Saboteur and I want to have full OST.
## Post #9
- Username: wulk0r
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 25, 2011 12:11 am
- Post datetime: 2011-01-24T16:27:55+00:00
- Post Title: The Saboteur .PCK files

is there something missing? i tried to extract the files from saboteur.pck with quickbms. i used the script from above after it was asked for. but what i got after extracting was a lot of .dat files O_o no .wav or other files nor even the .bkh. do i miss a step of doing something? shouldn't be there some wav or the bkh files? please help

cheers
