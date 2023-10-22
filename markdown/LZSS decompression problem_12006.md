## Post #1
- Username: Papipone
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 03, 2014 8:39 am
- Post datetime: 2014-09-25T04:04:45+00:00
- Post Title: LZSS decompression problem

Hi, 

I am a fan of Sega's Yakuza games. Unfortunately, Ryu Ga Gotoku 5 is not translated. I would like, if possible, start a translation project over internet. Consequently, I have to decompress every packed files.

So, I decided to write a GUI tool, using C++, that handle decompression and "compression" (importation). 
I started to work on and I discovered that a "parc" script was made for quickbms (thanks to luigi), but for learning purpose, I chose to continue the work done so far.

Here is the things done (*.par):
-the offset of the number of repertories is known.
-the offset of the number of files is known.
-the offsets of the name of files or repertories have been retrieved.
-the offsets of every files in archive have been retrieved.
-the offset of compressed size of every files is known.
-the offset of uncompressed size of every files is known.

Next, I moved to the offset of the first compressed file in the archives where I am stuck. I searched for LZSS compression on internet but I did not find anything relevant. 

Here is an extract of one of the archives : 

```
0037 0D0A 3030 3030 006C 6973 742E 7478              .7..0000.list.tx
7400 0D0A 3264 5F79 6B5F 0074 6974 6C65              t...2d_yk_.title
5F6C 6F00 676F 5F74 6D2E 6464 9073 8B01              _lo.go._tm.dd.s<.
3030 3F01 6261 63E0 6B7F 0173 015F 0170              00?.bacàk..s._.p
7265 73F8 736F 0162 012F 03D6 0805 06                resoso.b./.Ö...
```


This is a text file which list the 7 textures of the archive. The data begin to be garbled at the end of the 4th line (After 9073). A byte is added every 7 or 8 bytes before 9073 (00). There must be an operation to do on 90 (end  of line 4) in order to be redirected to an offset that correspond to the correct datas because this value does not appear in the decompressed file.

I am a newcomers in the world of Data's compression/encryption. As a result, I really have poor knowledge about that   . 
Can someone help me to uncompress this thing please ?

thanks in advance.

Edit : here is the full file with a text file containing information about several offset.


 file.zip
(198.16 KiB) Downloaded 49 times


The text file has been written with notepad. It may be unreadable with notepad (line moved).
## Post #2
- Username: RikuKH3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 26, 2012 7:37 am
- Post datetime: 2014-09-25T21:37:39+00:00
- Post Title: LZSS decompression problem

[https://github.com/Grumbel/rfactortools ... unyakuza.h](https://github.com/Grumbel/rfactortools/blob/master/other/quickbms/src/compression/unyakuza.h)

And you simply can extract it using exciting script and just rebuild without compression, just in case.
## Post #3
- Username: Papipone
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 03, 2014 8:39 am
- Post datetime: 2014-09-26T01:04:21+00:00
- Post Title: LZSS decompression problem

Hi, 

Thanks for your response. 

> And you simply can extract it using exciting script and just rebuild without compression, just in case.
Yes, I know but I already started to code. All the boring stuff has been done (get every infos from files contained in the archive). 
The only thing to do known is to find a way to decompress files. Once done, it will be easiest to repack (I hope  ).   

```
int unyakuza(unsigned char *in, int insz, unsigned char *out, int outsz, int check_head)
```
 
Do you know what the "unsigned char* out" argument of the function is symbolizing   ? (It is from the unyakuza.h file provided with quickbms). 

Thanks
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-26T02:41:20+00:00
- Post Title: LZSS decompression problem

Keep up the good work
## Post #5
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-26T11:17:30+00:00
- Post Title: LZSS decompression problem

> Reply from Papipone
>
> Code: Select allint unyakuza(unsigned char *in, int insz, unsigned char *out, int outsz, int check_head) 
Do you know what the "unsigned char* out" argument of the function is symbolizing   ? (It is from the unyakuza.h file provided with quickbms).Isn't it just a pointer to the output buffer?
## Post #6
- Username: Papipone
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 03, 2014 8:39 am
- Post datetime: 2014-10-02T19:40:59+00:00
- Post Title: LZSS decompression problem

Hi, 

With the help of the work done by luigi auriemma I have been able to decompress datas. Now, I just need to code a recompression tool.

thanks for your help !!
## Post #7
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-10-03T19:34:50+00:00
- Post Title: LZSS decompression problem

> Reply from Papipone
>
> 

Hi, 

With the help of the work done by luigi auriemma I have been able to decompress datas. Now, I just need to code a recompression tool.

thanks for your help !!

It looked like earlier they said you don't need to re-compress the data to get it working (just need to have it it one constant file), just what I read.
## Post #8
- Username: Papipone
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 03, 2014 8:39 am
- Post datetime: 2014-10-30T00:43:30+00:00
- Post Title: LZSS decompression problem

Hi,

I am still on it. The decompression algorithm has been fully integrated to the GUI app. The compression algorithm is still in development an will allow to compress any files using an LZSS algorithm.

Here is an overview :



Ryu screen1.png (72.69 KiB) Viewed 213 times



I need to figure out to what the last bytes (5067 A02D, 4DF1 767F, ...) of these enumerations mean. Does anyone have an idea please?

```

00000280  8000 0000 0000 00B7 0000 005F 0000 0800  €......·..._....
00000290  0000 0020 0000 0000 0000 0000 5067 A02D  ... ........Pg -
000002A0  8000 0000 0000 0280 0000 0084 0000 085F  €......€...„..._
000002B0  0000 0020 0000 0000 0000 0000 4DF1 767F  ... ........Mñv.
000002C0  8000 0000 0002 0080 0001 6D2C 0000 1000  €......€..m,....
000002D0  0000 0020 0000 0000 0000 0000 5049 9BFE  ... ........PI›þ

```


thanks.
## Post #9
- Username: caoyang131
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 06, 2014 10:48 pm
- Post datetime: 2014-11-06T14:57:28+00:00
- Post Title: LZSS decompression problem

> Reply from Papipone
>
> Hi,

I am still on it. The decompression algorithm has been fully integrated to the GUI app. The compression algorithm is still in development an will allow to compress any files using an LZSS algorithm.

Here is an overview :
Ryu screen1.png

I need to figure out to what the last bytes (5067 A02D, 4DF1 767F, ...) of these enumerations mean. Does anyone have an idea please?
Code: Select allOffset(h)   00    02    04    06    08     0A    0C    0E

00000280  8000 0000 0000 00B7 0000 005F 0000 0800  €......·..._....
00000290  0000 0020 0000 0000 0000 0000 5067 A02D  ... ........Pg -
000002A0  8000 0000 0000 0280 0000 0084 0000 085F  €......€...„..._
000002B0  0000 0020 0000 0000 0000 0000 4DF1 767F  ... ........Mñv.
000002C0  8000 0000 0002 0080 0001 6D2C 0000 1000  €......€..m,....
000002D0  0000 0020 0000 0000 0000 0000 5049 9BFE  ... ........PI›þ


thanks.

I think the last bytes is the checksum of filename in the parc pack,you don`t need to calculate them.
## Post #10
- Username: bobcan
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 26, 2007 11:12 am
- Post datetime: 2017-08-12T02:37:50+00:00
- Post Title: LZSS decompression problem

> Reply from RikuKH3
>
> https://github.com/Grumbel/rfactortools ... unyakuza.h

And you simply can extract it using exciting script and just rebuild without compression, just in case.

Sorry

How To Open unyakuza.h File Types In quickbms ??
