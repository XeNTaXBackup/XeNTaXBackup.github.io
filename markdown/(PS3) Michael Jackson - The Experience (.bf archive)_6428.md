## Post #1
- Username: 0johntheripper0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 15, 2011 12:11 am
- Post datetime: 2011-04-14T16:20:31+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

Hey board!
Long time lurker, first time poster.

Been attempting to open Ubisoft's latest game's files, and have tried a variety of BFExtractors, with no luck (crashing, invalid file type etc.)  I want to lighten the proverbial load on the ~14GB file to speed loading times.  Trying to further compress BGM, Vocals, SFX, Videos and some music.

I was wondering if you could have a look?

Unfortunately the filesize is quite large (114mb), but the smallest of the three archives that I could find.

```
http://www.mediafire.com/?l93fbqbd3jxbeyp
```


Thanks guys!!!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-14T17:50:24+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

can you upload also the first 10 megabytes of a non-wav bf file?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-17T17:25:54+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

hello?
I have already created the script, I need a non-wav sample only to tune the extraction because each file acts also as a container
## Post #4
- Username: stevie101x
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 18, 2011 2:16 am
- Post datetime: 2011-04-20T11:04:17+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

Hi iam also looking for a way to extract the large .bf archive in (PS3) Michael Jackson the experience. I noticed that nothing has been posted on this thread for a couple of days, I can post a link to another .bf file for you to work with but apart from the wav file that you already have the only other files that I have are quite large 532 MB and 17.3 GB. If this is any good I will supply a link for the smaller of the two files, any help with this would be greatly appreciated.
## Post #5
- Username: 0johntheripper0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 15, 2011 12:11 am
- Post datetime: 2011-04-20T15:08:37+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

> Reply from aluigi
>
> hello?
I have already created the script, I need a non-wav sample only to tune the extraction because each file acts also as a container

My apologies, I've been out of the state for a few days with my wife.  Anyhow, what is the best way to grab the first 10MB of a file?  I'm extremely noobish when it comes to the science behind archiving.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T15:52:37+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

you can use one of the following tool suggested in the rules of the forum:
[blog/wp-content/uploads/2010/02/filecutter1_0_1.zip](http://forum.xentax.com/blog/wp-content/uploads/2010/02/filecutter1_0_1.zip)
[http://www.xentax.com/downloads/tools/filecutter.zip](http://www.xentax.com/downloads/tools/filecutter.zip)
## Post #7
- Username: 0johntheripper0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 15, 2011 12:11 am
- Post datetime: 2011-04-20T16:11:23+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

heres the first ~3MB of the smaller of the two files.  I can't seem to cut the other file.  Its giving me a (from what I understand) overflow error (14GB file).

```
http://www.mediafire.com/?ij8o25b9e57j17f
```
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T18:48:07+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

the script is the following but I don't understand why some compressed files are invalid so if you get a "compression" error while using quickbms I don't know how to solve it at the moment:

```
idstring "ABE\0"
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get OFFSET long
get DUMMY long
get SIZE long
get DUMMY long
get DUMMY long
get FILES long
get DUMMY long

goto OFFSET
get DUMMY long
get DUMMY long
get DUMMY long

for i = 0 < FILES
    getdstring NAME 0x50
    get DUMMY long
    get DUMMY long
    get ZSIZE long
    get DUMMY longlong
    get DUMMY long
    get DUMMY long
    get OFFSET longlong
    get SIZE long
    getdstring DUMMY 0x50

    math ZIP = 0
    if ZSIZE < SIZE
        math ZIP = 1
    endif

    savepos TMP
    goto OFFSET
    get ZSIZE long
    get SIZE long
    goto TMP
    math OFFSET += 0x20
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
*updated*
## Post #9
- Username: 0johntheripper0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 15, 2011 12:11 am
- Post datetime: 2011-04-20T19:22:08+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

Well, it works!! Somewhat anyways...   


On the first file (~500MB):
It dies after about 50 files, giving me these errors: 

the compressed LZO input is wrong or incomplete (-6)

there is an error with the decompression
the returned output size is negative (-1)

On the second file (~14GB):
It seems to extract the files appropriately, but stops around 4.3GB (A file size limitation of quickbms?)

Nevertheless, I'm impressed!
Thanks!
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T19:37:58+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

as already said, for the lzo problem I don't have idea.

while the second one don't worry, I have updated the script posted before (just a one-line fix) and you must use quickbms64_test.exe to extract the files.
now it should be ok.
## Post #11
- Username: 0johntheripper0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 15, 2011 12:11 am
- Post datetime: 2011-04-20T19:55:41+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

Hmmmm,

Now i'm getting 

incomplete input file number 0, can't read 4 bytes.
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T20:00:30+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

uhmm do you receive that message immediately?
at the moment I don't have other ideas, maybe I will return on it tomorrow.

if you want to make a quick try replace the first "get OFFSET longlong" you see in the script (there are 2 of it) with:
get OFFSET long
get DUMMY long

maybe it's the same but try
## Post #13
- Username: 0johntheripper0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 15, 2011 12:11 am
- Post datetime: 2011-04-20T20:10:14+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

Ok, implemented the change, got these results.

On the first (~500MB) file, It no longer extracts all of the content, only extracts 14 files then stops with the same incomplete input file number 0, cant read 4 bytes.

For the second (~14GB) file, it does not extract any files, and immediately returns the same error.

This is compared to the first revision of your script which:
1) Extracted more files from the ~500MB file, but many were 0-2k in size, then stopped with an error
2) Extracted 4GB of data from the ~14GB file, then stopped.

I really appreciate all the effort you are putting into this.  Thanks again.

EDIT:  On a related note, one of the config files found after a partial extraction contained the word "EnjimeBF", not sure what it means, but looked like it has relevance to the .bf file format.
## Post #14
- Username: Omnitrix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 07, 2014 9:00 pm
- Post datetime: 2016-07-24T12:57:10+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

Scripts working (Tintin .bf too), but not all files were extracted and other files corrupted (PS3 version). Any suggestion please?
## Post #15
- Username: Omnitrix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 07, 2014 9:00 pm
- Post datetime: 2016-08-10T20:58:19+00:00
- Post Title: (PS3) Michael Jackson - The Experience (.bf archive)

Anyone help?
## Post #16
- Username: Omnitrix
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 07, 2014 9:00 pm
- Post datetime: 2020-12-21T03:11:44+00:00
- Post Title: Re: (PS3) Michael Jackson - The Experience (.bf archive)

Hello again  9 years have passed and I wanna try and return to this game. May be after 9 years someone will help to break this .bf extension to extract things from this game? I can provide any file if someone need it.
