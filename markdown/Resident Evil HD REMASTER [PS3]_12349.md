## Post #1
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-12-08T08:18:41+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

Help extract the files from the archive of the ARC, the head 16 bytes SFH, corrupted files are extracted.
[http://rghost.ru/59485530](http://rghost.ru/59485530)
## Post #2
- Username: nameless32
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 17, 2010 2:51 am
- Post datetime: 2014-12-08T13:44:02+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from Kaltan
>
> Help extract the files from the archive of the ARC, the head 16 bytes SFH, corrupted files are extracted.
http://rghost.ru/59485530
[http://www.tzarsectus.com/tools/ARCtool.rar](http://www.tzarsectus.com/tools/ARCtool.rar)

can extract, but no reimport/repack yet...
## Post #3
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-12-08T15:49:37+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

My tool doesn't correctly extract REmaster PS3 files. I thought I got it working, but most files end up corrupt. The ARC format is the same as in previous MT Framework games, but they've added this SFH header. The header lists the full size of the ARC file at 0x08, but there seems to be padding/data between certain files within the ARC container. I haven't been able to figure out the pattern of how it works.
## Post #4
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-12-08T15:51:22+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from nameless32
>
> Kaltan wrote:Help extract the files from the archive of the ARC, the head 16 bytes SFH, corrupted files are extracted.
http://rghost.ru/59485530
http://www.tzarsectus.com/tools/ARCtool.rar

can extract, but no reimport/repack yet...

Retrieves, but at the end of halyards damaged and texture TEX. Incomprehensible SFH 16-byte header + 16 bytes at the end.
## Post #5
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-12-08T16:07:43+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from Sectus
>
> My tool doesn't correctly extract REmaster PS3 files. I thought I got it working, but most files end up corrupt. The ARC format is the same as in previous MT Framework games, but they've added this SFH header. The header lists the full size of the ARC file at 0x08, but there seems to be padding/data between certain files within the ARC container. I haven't been able to figure out the pattern of how it works.
If you look in the hex editor, then the offset and size of the compressed file is correct, then at + 16 bytes for each file.
## Post #6
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-12-08T17:09:20+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from Kaltan
>
> If you look in the hex editor, then the offset and size of the compressed file is correct, then at + 16 bytes for each file.
It's not that simple. For instance, pl00_hairall_NM.tex in pl00.arc is offset by an additional 80 bytes.
## Post #7
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-12-08T17:25:38+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from Sectus
>
> Kaltan wrote:If you look in the hex editor, then the offset and size of the compressed file is correct, then at + 16 bytes for each file.
It's not that simple. For instance, pl00_hairall_NM.tex in pl00.arc is offset by an additional 80 bytes.
Whether it is possible to come up with the realties in Resident Evil Code: Veronica and RE5 also SFH.
## Post #8
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-12-08T17:37:11+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

I updated ARCtool with a small change. SFH support still doesn't work, but I fixed a bug related to it (wouldn't correctly skip SFH header sometimes) and added error handling for when it fails zlib decompression.

> Reply from Kaltan
>
> Whether it is possible to come up with the realties in Resident Evil Code: Veronica and RE5 also SFH.
Code Veronica and RE5 also use SFH headers on PS3?
## Post #9
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-12-08T17:40:38+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from Sectus
>
> I updated ARCtool with a small change. SFH support still doesn't work, but I fixed a bug related to it (wouldn't correctly skip SFH header sometimes) and added error handling for when it fails zlib decompression.
Kaltan wrote:Whether it is possible to come up with the realties in Resident Evil Code: Veronica and RE5 also SFH.
Code Veronica and RE5 also use SFH headers on PS3?
Yes, games that go into PSN, PKG archives head SFH
## Post #10
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-12-08T17:51:45+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

Your program works fine with ARCtool Code Veronica, Resident Evil HD REMASTER with Bat RE revelatens XBOX 360, but not on PS3
## Post #11
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2014-12-08T18:03:00+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

So I guess a disc version of REmaster does not use SFH headers and thus would work just fine with my tool?
## Post #12
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-12-08T18:07:34+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from Sectus
>
> So I guess a disc version of REmaster does not use SFH headers and thus would work just fine with my tool?
Uses))) It is as if PSN. That's what I wanted)))
## Post #13
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2014-12-11T15:43:01+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from Kaltan
>
> Sectus wrote:So I guess a disc version of REmaster does not use SFH headers and thus would work just fine with my tool?
Uses))) It is as if PSN. That's what I wanted)))

Chestnut, and his hands did not try to unpack, or you know how to Use only a software, and then sell the  translation?))))))
## Post #14
- Username: Kashtan23
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 14, 2014 3:00 am
- Post datetime: 2014-12-11T17:58:27+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from vadim
>
> Kaltan wrote:Sectus wrote:So I guess a disc version of REmaster does not use SFH headers and thus would work just fine with my tool?
Uses))) It is as if PSN. That's what I wanted)))

Chestnut, and his hands did not try to unpack, or you know how to Use only a software, and then sell the  translation?))))))
??? That thou beguiled.
## Post #15
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-12-15T08:39:34+00:00
- Post Title: Resident Evil HD REMASTER [PS3]

> Reply from Sectus
>
> So I guess a disc version of REmaster does not use SFH headers and thus would work just fine with my tool?
Can you share source code of the tool?
## Post #16
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2014-12-23T08:50:40+00:00
- Post Title: Re: Resident Evil HD REMASTER [PS3]

Here are text and font from this game: [https://www.dropbox.com/s/7mmh6f7x5kd95 ... 3.rar?dl=0](https://www.dropbox.com/s/7mmh6f7x5kd95sl/Resident%20Evil%20Remaster%20PS3.rar?dl=0)
Hope anyone can take and look! Thanks for any help!
