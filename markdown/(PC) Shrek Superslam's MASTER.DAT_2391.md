## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-01-13T07:55:15+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

A sorta recent game. This is Shrek Superslam for the PC. I have no idea why it has not been looked over yet but I have. Apparently it uses dds textures. Other than that I do not know.

[http://www.megaupload.com/?d=P8MQA4MA](http://www.megaupload.com/?d=P8MQA4MA)

In this are 2 files. MASTER.DAT which is the archive and MASTER.DIR which tells where the files and directories are in the archive. It might be somthing interesting, I'm not sure exactly how data is handled but I recognized some files it may contain. Though I'm not sure if any utilities could be used for it or not but it has been untouched.
## Post #2
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2007-07-15T18:01:11+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

I want to translate this game in to my language. Could someone make a plugin to MEC, please? I need to unpack and edit this game archive.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-15T18:27:15+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

The file has been deleted by megaupload.
## Post #4
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2007-07-16T08:18:26+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

I can´t upload it, because I have slow internet. (This 2 files has 212 MB, whole game has 661MB). It can be downloaded from torrent: 
```
LINK REMOVED
```


We do not accept links to warez. Period. Don't do it again. 
Mr.Mouse
## Post #5
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2007-07-16T08:48:25+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

> Reply from kramla
>
> I can´t upload it, because I have slow internet. (This 2 files has 212 MB, whole game has 661MB). It can be downloaded from torrent: Code: Select allLINK REMOVED

We do not accept links to warez. Period. Don't do it again. 
Mr.Mouse
I´m sorry for that. I´m new here.
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-16T08:52:09+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

Well, Warez is typically prohibited on any public forums as it brings trouble. It would be difficult for me to reupload the files. It's been quite a while ago and my current computer can no longer run it.
## Post #7
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2007-07-17T08:30:09+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

I find out that the files after compressing with winrar have only 80 Mb and I decided to upload it. It take very long time. I only hope that it wasn´t unavailing.

```
http://www.megaupload.com/?d=U78EY562
```
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-17T11:13:55+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

Ok here's the british localization file, but it is compressed. Could be some LZ* but can't say for sure. Its uncompressed size is 3429 bytes.
Here's my 010 Editor binary template for MASTER.DIR:

```

struct Entry {
	uint	offset;
	int	size;
	uint	sizecompressed;
	string filename;
	if(FTell() % 4 != 0)
		char	padding[4- FTell() % 4];
} entries[1935]<optimize=false>;

```

[british.dat.rar](https://xentaxbackup.github.io/file/1271_british.dat.rar)
## Post #9
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2007-07-17T11:46:49+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

> Reply from Rheini
>
> Ok here's the british localization file, but it is compressed. Could be some LZ* but can't say for sure. Its uncompressed size is 3429 bytes.
Here's my 010 Editor binary template for MASTER.DIR:
Code: Select alluint uk[1936];

struct Entry {
	uint	offset;
	int	size;
	uint	sizecompressed;
	string filename;
	if(FTell() % 4 != 0)
		char	padding[4- FTell() % 4];
} entries[1935]<optimize=false>;

I dont know what to do with this. I´m only beginner. It would be better to make for me some program or plugin.
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-17T11:53:44+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

It doesn't make any sense to create a tool if we can't identify the compression technique.
So please be patient
## Post #11
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2007-07-17T11:58:27+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

> Reply from Rheini
>
> It doesn't make any sense to create a tool if we can't identify the compression technique.
So please be patient

OK. I appreciate your prey
## Post #12
- Username: kramla
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Jul 15, 2007 11:27 pm
- Post datetime: 2007-07-23T15:47:40+00:00
- Post Title: (PC) Shrek Superslam's MASTER.DAT

I locate something with hexaeditor in the Master.dat and in my saves. It looks similarly. The first file is my save and second is cutting from master.dat. 

```
http://www.megaupload.com/?d=31BVHPQL
```
