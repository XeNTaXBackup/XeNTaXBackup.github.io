## Post #1
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-10-26T08:12:50+00:00
- Post Title: Netease game: datangwushuang unpacking format WDF for help

Netease game: datangwushuang unpacking format WDF for help
I want to unpack it, but I don't have experience in this field. Can anyone help me?
[http://dtws.163.com/](http://dtws.163.com/)

Smallest link：

[https://mega.nz/#!mzRjXAjB!5_523hA0H-Yr ... pMN91AiNFs](https://mega.nz/#!mzRjXAjB!5_523hA0H-YrCGNDbpXmzmJc4g7TvoJCJpMN91AiNFs)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-26T16:42:31+00:00
- Post Title: Netease game: datangwushuang unpacking format WDF for help

BMS script to unpack the sample:

```
get Skip long
get Count long
get EntryOffset long
goto EntryOffset
get ArcName basename
for i = 0 < Count
	get Hash long
	get Offset long
	get Size long
	get Skip long
	string Name p "%s/%08d." ArcName i
	log Name Offset Size
next i

```
## Post #3
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-10-27T07:55:01+00:00
- Post Title: Netease game: datangwushuang unpacking format WDF for help

Thank you. I unpacked the files through your script, but I found that their file names have no relation, and the format is encrypted unconventional model map format. Can you help me again? I upload one file of all types.
[https://mega.nz/#!6rIzRKCa!Ebn6c-jiEDVN ... t6UyHLJfeY](https://mega.nz/#!6rIzRKCa!Ebn6c-jiEDVNsunN_bylxZKdNj8QC4ttAt6UyHLJfeY)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-10-27T13:53:34+00:00
- Post Title: Netease game: datangwushuang unpacking format WDF for help

Texture is in BC3 format:



00000044.tex.jpg (7.61 KiB) Viewed 110 times



No luck with the model. Seem the vertices are encoded as 8-bit integers.
## Post #5
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-10-28T10:56:27+00:00
- Post Title: Netease game: datangwushuang unpacking format WDF for help

> Reply from Bigchillghost ↑Sun Oct 27, 2019 9:53 pm at Sun Oct 27, 2019 9:53 pm
>
> 
Texture is in BC3 format:
00000044.tex.jpg

No luck with the model. Seem the vertices are encoded as 8-bit integers.

Well, thank you for your help. Does tex have a batch conversion script?
