## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-01-21T11:21:37+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006)

Hello, everyone! I came here today wondering how can I extract the files from this awesome game! The formats are .lin from what I can see. I uploaded an [archive](https://www.dropbox.com/s/7o4d8r17pvzn5xf/Files.rar?dl=0) with some samples. Any ideas?
I tried using Umodel and DecUbi, but to no avail..
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-22T09:31:54+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006)

this bms script will at least decompress the lin file  

```

get ARC_SZ asize
get NAME basename
get EXT extension
string NAME + _decomp.
string NAME + EXT
do
	get SIZE long
	get ZSIZE long
	savepos OFFSET
	append
	clog NAME OFFSET ZSIZE SIZE
	append
	math OFFSET + ZSIZE
	goto OFFSET
while OFFSET != ARC_SZ 

```


i have not looked at the decompressed file close enough yet to split the contained files,
i will come back to it later unless someone else gets to it first.
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-01-22T21:15:43+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006)

wow, this is great, I wanna dig level files
is it xbox or 360?
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-01-25T21:25:13+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006)

> Reply from AceWell
>
> this bms script will at least decompress the lin file  
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

get ARC_SZ asize
get NAME basename
get EXT extension
string NAME + _decomp.
string NAME + EXT
do
	get SIZE long
	get ZSIZE long
	savepos OFFSET
	append
	clog NAME OFFSET ZSIZE SIZE
	append
	math OFFSET + ZSIZE
	goto OFFSET
while OFFSET != ARC_SZ 


i have not looked at the decompressed file close enough yet to split the contained files,
i will come back to it later unless someone else gets to it first.

Thank you so much! I hope we can port the models from it asap!
## Post #5
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-01-25T21:25:35+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006)

> Reply from Tosyk
>
> wow, this is great, I wanna dig level files
is it xbox or 360?

This is from the original Xbox version, can't wait to work more on ripping stuff from it!
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-02-05T16:59:19+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006)

*bump* Anything new?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-17T08:28:20+00:00
- Post Title: Splinter Cell: Double Agent (Xbox Version 2006)

if this thread were in "Game Archives" it would likely receive proper attention   
i can not go further with these files, too chaotic for me.   
maybe aluigi can figure them out easier than me.
