## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-09T22:58:10+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

Educational Doom clone by the people responsible for CD-Zelda. I'm trying to rip and convert the graphics to a viewable format (png or bmp) as well as the textures for use in a few projects. Sounds are easy as they are WAV. Graphics are hard because they are *.CMP and some are *.PCX so ripping them is a problem, ripping them doesn't quite work since they have no "magic bytes". Well, please help me crack this format.

They seem to be a headerless data file that starts off by indexing and naming each entry.
[IMMEeenLAB.rar](https://xentaxbackup.github.io/file/2020_IMMEeenLAB.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-09T23:20:12+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-10T01:00:30+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

```
set OFFSET long 0
set SIZE long 0
get TOTAL_SIZE asize
get NEW_OFFSET asize
for
    getdstring NEW_NAME 12
    get NEW_OFFSET long

    if NEW_NAME == ""
        set NEW_OFFSET long TOTAL_SIZE
    endif

    if NAME != ""
        set SIZE long NEW_OFFSET
        math SIZE -= OFFSET
        log NAME OFFSET SIZE
    endif

    set NAME string NEW_NAME
    set OFFSET long NEW_OFFSET

    if NAME == ""
        cleanexit
    endif
next
```
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-10T01:12:03+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

Is this a MEX Script? Hm... this is odd, my MultiEX is giving me weird problems, a division by zero. Huh...
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-10T01:35:32+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

it is a quickbms script
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-10T01:44:01+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

Thank you, now to get MultiEx working again. Maybe the old regkey is outdated or was lost. I hope Mr. Mouse comes on soon. O_o;;
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-10T01:54:17+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

it's a [QuickBMS](http://aluigi.org/papers.htm#quickbms) script, sorry I forgot to specify it
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-10T02:14:26+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

Wow, thanks! Works like a charm! I've dumped the content of a few LAB files and they extract perfectly.

Now for the second archive format that contains images.

Are these IMG files also a kind of container?
[IMGs.rar](https://xentaxbackup.github.io/file/2021_IMGs.rar)
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-10T10:37:18+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

the only thing that I can notice at a first look is that the data probably starts from offset 0x1000 (probably uncompressed at 8 bit), but I have no experience with graphic formats
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-10T17:44:54+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

Alright, thanks. I'll see if somebody can get a means to convert the graphics to a usable format.
## Post #11
- Username: YoshiOG1
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 16, 2011 2:30 am
- Post datetime: 2011-11-20T18:29:19+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

Is there a BMS script to compile multiple files into one LAB file?
You know, so that we can hack something in a level.

What I'd like to do is take one of the extracted files (one of the WAV sounds, for instance), change it, and then put the files back together as a LAB file.  If such a script has not yet been made, then could someone please make a script to compile files into one LAB file?

Thanks in advance.  
----------------------------
P.S. Here's the link to an example of what I've done with WAV files in I.M. Meen's main directory:
[http://www.youtube.com/watch?v=MxgXHzP7-_c](http://www.youtube.com/watch?v=MxgXHzP7-_c)
It's quite funny, actually.  And if I could just do something like this within the LAB files, that would be pretty nice!
## Post #12
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-11-21T07:14:35+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

I always knew that you'd end up hacking the game for YTPs.
## Post #13
- Username: YoshiOG1
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 16, 2011 2:30 am
- Post datetime: 2011-11-23T00:26:09+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

> Reply from Darkfox
>
> ... Graphics are hard because they are *.CMP and some are *.PCX so ripping them is a problem, ...
You can open *.PCX files with a program called IrfanView.  I'm not sure about *.CMP, though.
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-11-23T02:54:08+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

That isn't a problem anymore, was just for ripping them at the time. Unpacking LAB files fixed that. CMPs are the uncracked image format and Version 2 IMG files (Chill Manor)
## Post #15
- Username: YoshiOG1
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 16, 2011 2:30 am
- Post datetime: 2011-11-23T17:56:29+00:00
- Post Title: I.M.Meen (1995 PC/DOS) LAB files [complete]

> Reply from Darkfox
>
> That isn't a problem anymore, was just for ripping them at the time. Unpacking LAB files fixed that. CMPs are the uncracked image format and Version 2 IMG files (Chill Manor)

Ok.
But would you know how to put LAB files back together?
Like compressing multiple files into one LAB file?
## Post #16
- Username: YoshiOG1
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 16, 2011 2:30 am
- Post datetime: 2011-11-24T21:43:26+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) LAB files [complete]

*bump*

Anyone?  I need to know if I can reassemble a LAB file!  (I would like to inject multiple files into an empty LAB file for a hack.)
## Post #17
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-11-25T11:35:57+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) LAB files [complete]

> Reply from YoshiOG1
>
> 
Ok.
But would you know how to put LAB files back together?
Like compressing multiple files into one LAB file?

I would not, but since there is no compression or special routines, it'd be relatively simple to make. Maybe somebody will, would be nice. =D
## Post #18
- Username: YoshiOG1
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 16, 2011 2:30 am
- Post datetime: 2011-12-03T19:29:46+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) LAB files [complete]

> Reply from Darkfox
>
> YoshiOG1 wrote:
Ok.
But would you know how to put LAB files back together?
Like compressing multiple files into one LAB file?

I would not, but since there is no compression or special routines, it'd be relatively simple to make. Maybe somebody will, would be nice. =D

I've figured it out!

Here's how to do it:
1) Make sure you have a newer version of QuickBMS that can re-import files.
2) Modify the files that you want to modify.  If you're going to change the WAV files, make sure that the new sound file is 22.050 kHz, 8-bit, and mono.  If you're gonna change the OBJECTS.DEF file, make sure that the edited version has the same number of characters as the original (it has to be the same size, in bytes).
3) Make a desktop shortcut to QuickBMS with arguments -r and -w by going to the shortcut's properties and adding the arguments to the Target field (e.g. "C:\QuickBMS\quickbms.exe" -r -w).
4) Run QuickBMS from the desktop shortcut, and do what you would normally do when extracting the files from the LAB file.  Just make sure that you choose the LAB file before choosing the folder containing the modified files.
5) QuickBMS should reimport the files back into the LAB file, as long as the DEF files aren't bigger than before, and the WAV files are PCM 22.050 kHz 8-bit Mono.

Have fun!!
