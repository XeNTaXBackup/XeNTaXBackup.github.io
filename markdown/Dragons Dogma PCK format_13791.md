## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-11T13:56:23+00:00
- Post Title: Dragons Dogma PCK format

Hi all,

There is a new format for text, im working on it now, but there is a few tricky parts, so if anyone interested, free to help me out, just need struct, not tools... 

```
https://mega.nz/#!6kYigRhJ!K5GLKkYRI0CvR610rdhtugHlmfLLUjq-buiEoaIOojE
```


Thx Mike
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-01-12T01:42:14+00:00
- Post Title: Dragons Dogma PCK format

```
{
	unsigned int m_fileHash;
	unsigned int m_fileOffset;
	unsigned int m_fileSize;
};

struct Pack
{
	unsigned int m_magic;
	unsigned int m_numFiles;
	PackEntry[m_numFiles];
};

```


I'm pretty familiar with the formats for Capcom's MT Framework Engine. This is just a packed file with multiple .gmd (localisation) files.
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-12T07:40:52+00:00
- Post Title: Dragons Dogma PCK format

thx allready have a tool, made last night
## Post #4
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-01-15T21:04:03+00:00
- Post Title: Dragons Dogma PCK format

Anyone have a tool for pck files?
## Post #5
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2016-01-16T00:47:24+00:00
- Post Title: Dragons Dogma PCK format

> Reply from aluigi
>
> Code: Select allget EXT extension

if EXT == "pck"

    get DUMMY long
    get FILES long
    for i = 0 < FILES
        get DUMMY long
        get OFFSET long
        get SIZE long
        log "" OFFSET SIZE
    next i

elif EXT == "gmd"

    idstring "GMD\0"
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get STRINGS long
    get DUMMY long
    get SIZE long
    get NAMESZ long
    getdstring NAME NAMESZ
    get NAME basename
    string NAME + ".txt"
    for i = 0 < STRINGS
        slog NAME -1 -1
    next i

endif
## Post #6
- Username: AcTiViSioN
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 17, 2016 4:56 am
- Post datetime: 2016-01-16T20:59:33+00:00
- Post Title: Dragons Dogma PCK format

Please tell me, will soon be ready utility for compilation .pck files? I did the translation, but I can not assemble back ...
## Post #7
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-01-17T07:48:42+00:00
- Post Title: Dragons Dogma PCK format

Repack is not possible at this time, aint ya?
## Post #8
- Username: xNegrao
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 14, 2014 4:14 am
- Post datetime: 2016-01-17T08:38:57+00:00
- Post Title: Dragons Dogma PCK format

There is a chinese site with name of text files, this helps in some way?

[http://projects.pujia8.com/project/DragonsDogma/?page=1](http://projects.pujia8.com/project/DragonsDogma/?page=1)
## Post #9
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-01-24T02:14:50+00:00
- Post Title: Dragons Dogma PCK format

UP!
## Post #10
- Username: brendan19
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-24T09:41:24+00:00
- Post Title: Dragons Dogma PCK format

repack is possible.. i will release repacker once we Finnish our localization, or ask me private...
## Post #11
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2016-01-27T01:10:33+00:00
- Post Title: Dragons Dogma PCK format

Hi, i made my own tool and it can be repacked very easily.
problem is that .pck file is not all of texts in the game.
I had unpacked all of .arc files in the nativePC\rom and looks like they had same .gmd files with message.pck

it's one of sample text that i can't find any gmd files in pck
サルド
早くヤツのいる居城に向かいましょう (i found it. but i can't find サルド. it's script from サルド)

anyone knows about it?
## Post #12
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2016-01-27T09:28:25+00:00
- Post Title: Dragons Dogma PCK format

> Reply from MiRiKan
>
> 
サルド
早くヤツのいる居城に向かいましょう (i found it. but i can't find サルド. it's script from サルド)

I found it. Npc names are placed in bbs_rpg.arc, called NpcList.nnl
But there are more texts to find out...
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-01-27T13:28:13+00:00
- Post Title: Dragons Dogma PCK format

> Reply from MiRiKan
>
> MiRiKan wrote:
サルド
早くヤツのいる居城に向かいましょう (i found it. but i can't find サルド. it's script from サルド)

I found it. Npc names are placed in bbs_rpg.arc, called NpcList.nnl
But there are more texts to find out...

As i said i have 1 click only solution for repack. But i can only share it after we are done with localization or very privately...
I can share list of all arc files where all text is... here you go:
[DD_TEXT_ALL.rar](https://xentaxbackup.github.io/file/10371_DD_TEXT_ALL.rar)
## Post #14
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2016-01-28T06:23:14+00:00
- Post Title: Dragons Dogma PCK format

> Reply from michalss
>
> I can share list of all arc files where all text is... here you go:

Thanks,
I've found almost files, but it also helpful. It's only what i need.
