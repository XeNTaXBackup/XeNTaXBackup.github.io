## Post #1
- Username: atomic
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 16, 2008 12:14 pm
- Post datetime: 2008-02-18T08:38:37+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-18T09:44:34+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

> Reply from atomic
>
> Typical external directory based storage idx stores filenames data in eea file, both attached.
So, what do you already have?
## Post #3
- Username: atomic
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 16, 2008 12:14 pm
- Post datetime: 2008-02-18T09:54:09+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

Nothing, i cannot seem to match the offsets, i just need to know if anyone else is able too.
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-02-18T18:21:24+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

Very simple format.

In idx,...

16 byte filename, dword (4 byte) end of file data in .eea file.

Calculate size of file using previous file end of data.

In eea,...

First file seems to have no data.

Image format inside archive (named .bmp, but not really bmp)

short width, height, unk1, unk2

followed by width * height * 4 data

untested
## Post #5
- Username: atomic
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 16, 2008 12:14 pm
- Post datetime: 2008-02-18T21:02:55+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

Thanks Rick,

Now i know why the files are strange, each block is compressed with LZ77/LZSS. Im glad i was able to discover the compression used, but does anyone know how i can decompress them?
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-18T21:32:22+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

[viewtopic.php?p=19052#p19052](http://forum.xentax.com/viewtopic.php?p=19052#p19052)
## Post #7
- Username: atomic
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 16, 2008 12:14 pm
- Post datetime: 2008-02-18T21:38:15+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

Thanks Rheini, tried DeLZSS_2 but it crashes, also tried DeLZSS1 did not decompress, may be something funny in the params.

Also if someone could confirm compression just to put my mind at ease
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-18T22:02:44+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

No the data is not compressed, They just use custom formats.
## Post #9
- Username: atomic
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 16, 2008 12:14 pm
- Post datetime: 2008-02-18T22:11:38+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

Any thoughts on how to read the files?
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-18T22:19:33+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

> Reply from Rick
>
> Image format inside archive (named .bmp, but not really bmp)

short width, height, unk1, unk2

followed by width * height * 4 data

untested
## Post #11
- Username: atomic
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 16, 2008 12:14 pm
- Post datetime: 2008-02-18T22:41:01+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

> Reply from Rheini
>
> Rick wrote:Image format inside archive (named .bmp, but not really bmp)

short width, height, unk1, unk2

followed by width * height * 4 data

untested

I have no problem admitting i have no idea what this means!!!
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-18T22:53:40+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

I'd "translate" this info into the following 010 binary template:

```
short height;
short uk1;
short uk2;
struct RGBA {
	byte r;
	byte g;
	byte b;
	byte a;
} data[width*height];

```
## Post #13
- Username: atomic
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 16, 2008 12:14 pm
- Post datetime: 2008-02-18T23:28:23+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

> Reply from Rheini
>
> I'd "translate" this info into the following 010 binary template:
Code: Select allshort width;
short height;
short uk1;
short uk2;
struct RGBA {
	byte r;
	byte g;
	byte b;
	byte a;
} data[width*height];

At the risk of being flamed, im not very experienced with binary templates. I see you did a tut for them back in December, but i cannot find a valid link. Is the tut still applicable?
## Post #14
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-19T09:48:24+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

I always provide my information as a binary template, not only because you can use it with 010 Editor but also cause it is imho very easy to read and to understand (at least if you know a little bit C)
[http://www.cplusplus.com/doc/tutorial/structures.html](http://www.cplusplus.com/doc/tutorial/structures.html)

Here's the tutorial (should be version 4):
[http://xlice.net/file/3537d0356727ef35a ... 4.rar.html](http://xlice.net/file/3537d0356727ef35a8512bcef91dbc29/tutv4.rar.html)
## Post #15
- Username: atomic
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 16, 2008 12:14 pm
- Post datetime: 2008-02-20T15:02:15+00:00
- Post Title: Simfarm (Dos Version) .idx and .eea

Still having problems - im not too good at this   

Is anybody able to view the files in picture form?
## Post #16
- Username: atomic
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Feb 16, 2008 12:14 pm
- Post datetime: 2008-02-21T04:55:19+00:00
- Post Title: Re: Simfarm (Dos Version) .idx and .eea

Ok...progress has been made!!!

I have managed to correct the issues i have been having, but need some hints on opening the extracted images. I have confirmed that the data is readable and can be imported raw into photoshop, however, the images dont appear correct.

When opening raw i get 2/3 small sections of the same image, black and white, i also dont seem to be able to open them as 4 bit data, only 8 which could be my problem.


Any ideas guys?
