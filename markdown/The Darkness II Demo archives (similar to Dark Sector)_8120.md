## Post #1
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2012-01-25T01:11:57+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

Hi all, I'm currently trying to extract the music from this demo (PC version). So I looked around and low and behold the structure of these archives seems similar to that of Dark Sector, probably because they have the same developer. The thing that seems to be different is the compression of the .cache files and the inclusion of .toc files (idk if those were in Dark Sector too). I'll upload some example files now.

H.Misc.cache:
[http://www.mediafire.com/download.php?jd35zag9fsax315](http://www.mediafire.com/download.php?jd35zag9fsax315)

H.Misc.toc:
[http://www.mediafire.com/download.php?9v39gw7x5e6w8xl](http://www.mediafire.com/download.php?9v39gw7x5e6w8xl)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-01-26T19:51:45+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

yes seconded.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-27T15:41:52+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

download QuickBMS 0.5.6 (the new algorithm is available from this version) and try this script:

```
#   the folders structure is incomplete, I save only the last one so type 'r' when requested
# script for QuickBMS http://quickbms.aluigi.org

open FDDE "toc"
open FDDE "cache" 1

comtype COMPRLIB_RLE3
set PATH string ""
get DUMMY long
get DUMMY long
get FILES asize
math FILES -= 8
math FILES /= 0x60
for i = 0 < FILES
    get OFFSET longlong
    get TSTAMP longlong
    get ZSIZE long
    get SIZE long
    get DUMMY long
    get ID long
    getdstring NAME 0x40

    if OFFSET == -1
        set PATH string NAME
        string PATH += /
    else
        set FNAME string PATH
        string FNAME += NAME
        if SIZE == ZSIZE
            log FNAME OFFSET SIZE 1
        else
            math OFFSET += 4
            math ZSIZE  -= 4
            clog FNAME OFFSET ZSIZE SIZE 1
        endif
    endif
next i
```
the only problem is that the folders structure is not complete at the moment so you must select the 'r' option for continuing the extraction
## Post #4
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-01-30T01:54:04+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

Will reimport feature work for this game/files?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-30T10:48:25+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

no, I have not added the recompression algorithm because it comes from a "not widely known" library so I doubt about its usage in more games.
## Post #6
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-31T17:09:56+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

what are the file dialogs english?
## Post #7
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-01-31T20:19:47+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

> Reply from quattro65
>
> what are the file dialogs english?
H.misc.cache> language.cl (root folder after extraction)

@aluigi
Anyway to write a reimport script without compression?

In Dark Sector game (diferent compression method) we were able to repack the .cache 
files without any compression, and the game read it. Just the file size increase, but no problem.
## Post #8
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-01-31T21:33:55+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

> Reply from Herdell
>
> quattro65 wrote:what are the file dialogs english?  
H.misc.cache> language.cl (root folder after extraction)

@aluigi
Anyway to write a reimport script without compression?

In Dark Sector game (diferent compression method) we were able to repack the .cache 
files without any compression, and the game read it. Just the file size increase, but no problem.
tnx 
Herdell next problem open file .cl
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-01T11:16:54+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

> Reply from Herdell
>
> Anyway to write a reimport script without compression?
the reimport feature works only with native recompressions.
I may add it to the next quickbms version but sincerely I don't know because only this game uses it
## Post #10
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-02-01T17:19:41+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

> Reply from aluigi
>
> 
the reimport feature works only with native recompressions.
I may add it to the next quickbms version but sincerely I don't know because only this game uses it
Would be great if you do it. I'm interested in game localization.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-01T18:18:35+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

I have found the solution, using the "EXECUTE" feature I implemented in the latest quickbms.
in short for reimporting would be enough to replace:

```
comtype COMPRLIB_RLE3
```
with
```
comtype EXECUTE "codrle3 #INPUT# #OUTPUT#"
```

there is only a little obstacle at the moment, I must fix a little thing in quickbms to do it because I forgot to allow the EXECUTE mode enabled also during reimporting (oh well errors happen).

in attachment there is the precompiled version of the code you can find here:
[http://library.thinkquest.org/C008719/f ... /CODRLE3.C](http://library.thinkquest.org/C008719/frames/algorithms/rle/third/CODRLE3.C)
[CODRLE3.zip](https://xentaxbackup.github.io/file/5026_CODRLE3.zip)
## Post #12
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-02-01T23:26:53+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

Sorry, but what I need to do?
Wait for the compiled version?

I'm a n00b.
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-02T00:05:01+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

yes wait the new version I will release probably tomorrow
## Post #14
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-02-04T01:17:51+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

Any news?
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-04T01:27:47+00:00
- Post Title: The Darkness II Demo archives (similar to Dark Sector)

eh eh eh looks like you don't follow my website :)
## Post #16
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-02-04T13:23:19+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

I do, but these days I really didn't it.

Thank you man!
## Post #17
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2012-02-10T13:36:19+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

I've got extracted files from H.misc.cache but I don't know how to repack them into H.misc.cache back... please tell me 

Thank you!!
## Post #18
- Username: quattro65
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Jan 21, 2012 11:23 pm
- Post datetime: 2012-02-10T14:56:58+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

> Reply from phill05
>
> I've got extracted files from H.misc.cache but I don't know how to repack them into H.misc.cache back... please tell me 

Thank you!!
use reimport quickbms file  language.cl script  as shown above
how to edit the file language.cl? have tried?
## Post #19
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2012-02-11T09:08:41+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

There are several .png files inside of F.Texture.cache but unfortunately they cannot be opened. It seems like the files are corrupted or encrypted. Also the same thing for audio files.
## Post #20
- Username: Renzo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 25, 2011 7:19 pm
- Post datetime: 2012-02-17T20:21:15+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

So we have languages.cl extracted now. But the text seems encrypted or something. Is there any chance of someone trying to decrypt or extract the text from the file?
## Post #21
- Username: Shadowfied
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 01, 2012 2:53 pm
- Post datetime: 2012-04-01T08:42:17+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

Any news on this? Like someone said earlier, the .png files does not open, nor does the .fbx files or audio files. Is there anything we can do?
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-05-04T03:42:57+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

it's not simple png it's headerless dds
## Post #23
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2012-10-01T16:37:35+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

any news about this now?
## Post #24
- Username: hotgoblin
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Apr 15, 2012 1:52 am
- Post datetime: 2012-12-22T23:09:07+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

Okay QuickBMS export all files!

I've  FBX, OBJ files but I can't import them in a 3D program (tested with Cinema 4D and Maya).
The WAV files can't I open too.

I think they are encrypted or something like this
## Post #25
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2012-12-24T02:37:02+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

yeah, and .png files don't open too :/
i really wanna open the models and the .wav files from this game... 


> Reply from hotgoblin
>
> Okay QuickBMS export all files!

I've  FBX, OBJ files but I can't import them in a 3D program (tested with Cinema 4D and Maya).
The WAV files can't I open too.

I think they are encrypted or something like this

Oh, and where did you find the .obj files?
## Post #26
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-12-24T02:51:05+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

So how am I supposed to work this? I  saved it as a .bat and it doesn't work.
## Post #27
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2012-12-25T01:42:37+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

you need to download quickbms, save the script as .txt and load in quickbms.
## Post #28
- Username: hotgoblin
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Apr 15, 2012 1:52 am
- Post datetime: 2012-12-26T00:24:32+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

> Reply from manbox74
>
> yeah, and .png files don't open too :/
i really wanna open the models and the .wav files from this game... 

hotgoblin wrote:Okay QuickBMS export all files!

I've  FBX, OBJ files but I can't import them in a 3D program (tested with Cinema 4D and Maya).
The WAV files can't I open too.

I think they are encrypted or something like this 

Oh, and where did you find the .obj files?

Very small files just 10 kb or something like this. I think all 3D models
are in .FBX

All formats (wav, fbx, png) are encrypted
## Post #29
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2012-12-26T01:51:26+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

I just found the skeletons (for example : JackieFull_skel.fbx), not the models. Do you know in which file you found them?idk why but i wanna take a look (even though I don't know nothing about "programming"...)


can someone help to open those .fbx files, please??
## Post #30
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2012-12-27T22:27:19+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

Hey, good news
You can use Ninja Ripper to rip the models (they come in T-POSE)  


here's Jackie
## Post #31
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2012-12-28T18:23:07+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

I don't remember him to be black
## Post #32
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2013-01-05T21:02:35+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

Yeah xD but I already fixed this!
## Post #33
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-14T19:02:17+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

i have extracted wav but he look like missing riff what's the tool i must use for get it readable
use revorb for see but no result

any idea plz
## Post #34
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-24T15:46:23+00:00
- Post Title: Re: The Darkness II Demo archives (similar to Dark Sector)

up
