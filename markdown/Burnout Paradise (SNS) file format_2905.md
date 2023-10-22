## Post #1
- Username: benten
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 14, 2008 7:36 pm
- Post datetime: 2008-01-24T16:56:18+00:00
- Post Title: Burnout Paradise (SNS) file format?

Hello there.

Could anyone please look into this format for me.
File format is SNS from the x360 game Burnout Paradise.

Expect it hopefully to be music as located in the Streams folder (original file is 12.7mb

Thank you.
[ROCKRIDGECLIFFS.SNS.zip](https://xentaxbackup.github.io/file/1432_ROCKRIDGECLIFFS.SNS.zip)
## Post #2
- Username: misioslaw
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 18, 2009 2:19 am
- Post datetime: 2009-05-17T20:51:01+00:00
- Post Title: Burnout Paradise (SNS) file format?

SNS audio are EALayer3 compressed
Headers of streams are packed separately in file STREAMHEADERS.BUNDLE
Burnout Paradise (PC) .BUNDLE files are archive files with data packed with ZLIB (compress method)
All headers of files (textures,streams,etc..) are packed separately.
In many cases first unpacked file in archive are contents index.
## Post #3
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-30T11:04:11+00:00
- Post Title: Burnout Paradise (SNS) file format?

I'm also looking for this..
## Post #4
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2009-12-17T19:51:40+00:00
- Post Title: Burnout Paradise (SNS) file format?

I'm also interested in the music. Has there been any progress in extracting/converting the audio files?:)

Edit: Are there some other file examples needed? I could provide them I think.
## Post #5
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2009-12-20T16:05:05+00:00
- Post Title: Burnout Paradise (SNS) file format?

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T16:20:18+00:00
- Post Title: Burnout Paradise (SNS) file format?

I don't know what's the job of the bundle/bnd2 files anyway for who is interested the following is a a simple quickbms script, maybe someone will find a meaning in the extracted data:

```
goto 0x10
get FILES long
get DUMMY long
get OFFSET long
goto 0x30
for i = 0 < FILES
    getdstring DUMMY 16
    get SIZE long
    get DUMMY long
    get DUMMY long
    get ZSIZE long
    getdstring DUMMY 32
    math SIZE &= 0xffffff #???
    clog "" OFFSET ZSIZE SIZE
    math OFFSET += ZSIZE
    math OFFSET += 15
    math OFFSET &= 0xfffffff0
next i
```
## Post #7
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2009-12-20T16:27:38+00:00
- Post Title: Burnout Paradise (SNS) file format?

Does the info misioslaw gave not help? 

Here's his post again:

> SNS audio are EALayer3 compressed
>
> Headers of streams are packed separately in file STREAMHEADERS.BUNDLE
>
> Burnout Paradise (PC) .BUNDLE files are archive files with data packed with ZLIB (compress method)
>
> All headers of files (textures,streams,etc..) are packed separately.
>
> In many cases first unpacked file in archive are contents index.

So according to his post those files inside should be the headers or so.

But yeah, I'm way too unexperienced to help more than just to deliver file examples.
## Post #8
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2009-12-28T17:11:34+00:00
- Post Title: Burnout Paradise (SNS) file format?

Sorry for the double post, but is there no way to use misioslaw's information about the headers together with aluigi's QuickBMS script to assemble and extract/convert the music?
## Post #9
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-01-17T21:02:17+00:00
- Post Title: Burnout Paradise (SNS) file format?

Still no one who can use misioslaw's and aluigi's information to get working audio files?
