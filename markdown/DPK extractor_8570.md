## Post #1
- Username: Tiberio
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 17, 2012 1:15 am
- Post datetime: 2012-03-16T18:40:25+00:00
- Post Title: DPK extractor

Hi.

I would like to know if anyone knows or have any tool to extract a DPK file. This file is from Darkeden game.

I used Watto FileCutter to get a part (256 Kb from 800 MB). Thanks.
[dklegend.dpk.rar](https://xentaxbackup.github.io/file/5195_dklegend.dpk.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-19T09:38:40+00:00
- Post Title: DPK extractor

very strange archive, maybe there is a file table at its end but obviously it's not available in the uploaded dump.
the following is a script for it but note that the zlib compression is incomplete in that archive for unknown reasons:

```
# script for QuickBMS http://quickbms.aluigi.org

comtype zlib_noerror
get DPK_SIZE asize
for OFFSET = 0x200 < DPK_SIZE
    goto OFFSET
    padding 0x200
    savepos OFFSET
    if OFFSET >= DPK_SIZE
        cleanexit
    endif
    get SIZE long
    get DUMMY byte
    get DUMMY byte
    get ZSIZE long
    get NO_ZIP byte
    savepos OFFSET
    if NO_ZIP != 0
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
    math OFFSET += ZSIZE
next
```
## Post #3
- Username: Tiberio
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 17, 2012 1:15 am
- Post datetime: 2012-03-19T11:57:59+00:00
- Post Title: DPK extractor

Can you generate a BMS script to extract this file?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-19T12:18:34+00:00
- Post Title: DPK extractor

and what is that thing I posted?
## Post #5
- Username: Tiberio
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 17, 2012 1:15 am
- Post datetime: 2012-03-19T12:39:23+00:00
- Post Title: DPK extractor

Sorry, i dont know about this tool. How do i create a BMS file? Just save a txt as BMS and copy this code?
## Post #6
- Username: Tiberio
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 17, 2012 1:15 am
- Post datetime: 2012-03-19T12:43:24+00:00
- Post Title: DPK extractor

Well, i did it.
He extract some .dat files. Other noob question   ... How can i open them?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-19T12:48:55+00:00
- Post Title: DPK extractor

the files are nameless and I didn't see normal files (like dds, txt and so on) so don't expect something easy to use.
## Post #8
- Username: Tiberio
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 17, 2012 1:15 am
- Post datetime: 2012-03-19T12:54:06+00:00
- Post Title: DPK extractor

I got 52 extracted files. They have 0 ~ 716 Kb and one big file with 815.104 Kb. I cant open them.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-19T18:55:42+00:00
- Post Title: DPK extractor

You got 52 files no larger than 1 MB from an archive that's 800 MB in size?
## Post #10
- Username: Tiberio
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 17, 2012 1:15 am
- Post datetime: 2012-03-19T20:33:26+00:00
- Post Title: DPK extractor

Yes. This file contains all images from Darkeden game. But i cant open them...
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-19T22:41:15+00:00
- Post Title: DPK extractor

Post some of those files up.

But I still think it's weird that you only got 52 files from an archive that's 800 MB?
## Post #12
- Username: Tiberio
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 17, 2012 1:15 am
- Post datetime: 2012-03-19T23:11:23+00:00
- Post Title: DPK extractor

I put the files on 4shared: [http://www.4shared.com/rar/vMn4SNEO/Extract.html](http://www.4shared.com/rar/vMn4SNEO/Extract.html)
## Post #13
- Username: Tiberio
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 17, 2012 1:15 am
- Post datetime: 2012-03-20T21:53:47+00:00
- Post Title: DPK extractor

Any ideas?
