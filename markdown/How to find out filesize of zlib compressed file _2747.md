## Post #1
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-08-12T18:37:37+00:00
- Post Title: How to find out filesize of zlib compressed file ???

Hello guys 

I have ONE simple question for which I havent found an anwer.

How I can detect filesize of zlibed files ??? Is there any specification of zlib header ???
Because I want load into buffer only exact size from file.

I have many zlibed files merged into one file,without any information in it.

Thank you in advance
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-08-12T20:09:35+00:00
- Post Title: How to find out filesize of zlib compressed file ???

Interesting question. I too have not (bothered) to find out. And just assumed a maximum possible size (like....duhhhhhhh...10 times the compressed size).   Call me pragmatic .... and you'd be right!!!!!
## Post #3
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-08-12T21:40:37+00:00
- Post Title: How to find out filesize of zlib compressed file ???

I"m working on World in Conflict unpacker,and in SDF archives isnt all files compressed,for example mp3 is uncompressed.

I figured out that informations about files are written in chunks which are zlibed,but when I unzlibed that chunk,I didnt found any important information about read files in archive.


[img][http://img224.imageshack.us/img224/8972/untitlediw7.jpg](http://img224.imageshack.us/img224/8972/untitlediw7.jpg)
[/img]

PS: Jaeder Naub is able to detect length of zlibed files but I think that its always wrong count
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-12T22:18:39+00:00
- Post Title: How to find out filesize of zlib compressed file ???

The reason of this is that MP3 and OGG are are an already compressed format of audio and there is little one can do to further compress them (often trying this is counter-productive). Plus they are easier to load as-is.

You seem already familiar with coding, yes? And just need a bit of info how to uncompress ZLIB properly? I will say there is not just one type of ZLIB out there as I recall.
## Post #5
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-08-12T23:09:18+00:00
- Post Title: How to find out filesize of zlib compressed file ???

Darkfox: Thank you  Yep,I programming in Object Pascal for 4 years  I made splitter for that zlibed archives,it works but need to solve "buffer error" when decompressing files (rare error,maybe I loaded into buffer smaller file than was expected).

There are more variants of zlib ??? but they are compatible between,true ?.

When I searched for version of zlib,I found out this:

```
<zipimporter object "%.300s">...<zipimporter object "%.300s%c%.150s">
```


ZipImporter is probably class,based on zlib ???
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-12T23:18:55+00:00
- Post Title: How to find out filesize of zlib compressed file ???

I'm not exactly sure if what I said was true but it's a common compression used. I'm only just now getting into a programming course in college. But what I get from what your saying is that you think the problem is that you don't know how to detect the length of the uncompressed file?
## Post #7
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-08-12T23:25:18+00:00
- Post Title: How to find out filesize of zlib compressed file ???

Nope  I"m not able to detect filesize of compressed file  I need to know it because of loading data into decompression buffer,if length will be shorter then zlib raises exception ("buffer error");

I"m going to sleep right now  If you are not americana,then good night
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-12T23:54:46+00:00
- Post Title: How to find out filesize of zlib compressed file ???

Alright, hope somebody can help you. And by the way, I am American, yes. I make it too obvious don't I?

Well, hope somebody can help you with your problem, until then good luck.
## Post #9
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-08-14T16:10:01+00:00
- Post Title: How to find out filesize of zlib compressed file ???

Hmm,still nobody know ??? I still searching for the anwer
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-14T21:09:40+00:00
- Post Title: How to find out filesize of zlib compressed file ???

The answer is no.
Just read the specification: [http://www.ietf.org/rfc/rfc1950.txt](http://www.ietf.org/rfc/rfc1950.txt)
## Post #11
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-10-07T09:09:44+00:00
- Post Title: How to find out filesize of zlib compressed file ???

> I"m working on World in Conflict unpacker,and in SDF archives isnt all files compressed,for example mp3 is uncompressed.
Great! i examined this game and tried few experiments.

The mp3's are a bit packed, if you unpack a sdf without precomp, just extracting the mp3 files you get big mp3 files

But! if you use precomp and extract the mp3 files you get more than 2000 mp3 files, can we touch this? No

Anyway i'm expecting if somebody can make a unpacker for this...

Thanks!
## Post #12
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-10-08T11:09:26+00:00
- Post Title: How to find out filesize of zlib compressed file ???

Hi there, since there's no update from Demander I made a Sdf unpacker myself.

You can download it from [http://www.xentax.com/uploads/author/johndoe/unsdf.zip](http://www.xentax.com/uploads/author/johndoe/unsdf.zip)
It's a pretty basic command-line tool. Just give it the name of the sdf file as parameter, it will create a subdirectory in the current directory and extract all files/directories there.

The source code can be downloaded from [http://www.xentax.com/uploads/author/jo ... df-src.zip](http://www.xentax.com/uploads/author/johndoe/unsdf-src.zip)

I have no time to add the tool or the format to the Wiki, maybe someone else volunteers?
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-10-08T18:44:37+00:00
- Post Title: How to find out filesize of zlib compressed file ???

Thanks !!!
## Post #14
- Username: Csokis
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 09, 2007 1:54 am
- Post datetime: 2007-10-08T20:12:31+00:00
- Post Title: How to find out filesize of zlib compressed file ???

> Reply from john_doe
>
> Hi there, since there's no update from Demander I made a Sdf unpacker myself.

Wow, thanks! 
Please, make SDF Packer!
