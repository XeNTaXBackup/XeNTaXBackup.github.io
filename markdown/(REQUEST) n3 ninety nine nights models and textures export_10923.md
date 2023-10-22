## Post #1
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2013-11-02T16:52:58+00:00
- Post Title: (REQUEST) n3: ninety nine nights models and textures export

Hi I m extract the Ninety-Nine Nights (2006) iso use by 360 extractor

I can't find character mesh file where is it.. 
And texture&img file looks like in 36t file. But 99Nights_Dot36T_exporter.exe file link that can turn it all seemed lost.

Here's some sample
[http://pan.baidu.com/s/168ZqF](http://pan.baidu.com/s/168ZqF)
[http://pan.baidu.com/s/1ACNl6](http://pan.baidu.com/s/1ACNl6)

Help for export method..
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-11-02T17:29:13+00:00
- Post Title: (REQUEST) n3: ninety nine nights models and textures export

> Reply from systembest
>
> Hi I m extract the Ninety-Nine Nights (2006) iso use by 360 extractor

I can't find character mesh file where is it.. 
And texture&img file looks like in 36t file. But 99Nights_Dot36T_exporter.exe file link that can turn it all seemed lost.

Here's some sample
http://pan.baidu.com/s/168ZqF
http://pan.baidu.com/s/1ACNl6

Help for export method..

Blender importer with the texture extractor packed:

[https://skydrive.live.com/#cid=FFBE4E57 ... 49FCBE!177](https://skydrive.live.com/#cid=FFBE4E570949FCBE&id=FFBE4E570949FCBE!177)
## Post #3
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2013-11-02T17:56:08+00:00
- Post Title: (REQUEST) n3: ninety nine nights models and textures export

Thx and how can i export mesh data? 
I use offzip for pak files and extract 00000800 dat file
But bms script doesn't work. Report error message..

I'm used this bms script. 

# Game: Ninety-Nine Nights (XBox360)
# by fatduck     Aug09
# script for QuickBMS [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)

endian big
get CSIZE asize
math CSIZE -= 0x800
get USIZE long
clog MEMORY_FILE 0x800 CSIZE USIZE

get NUMRES long MEMORY_FILE
for i = 0 < NUMRES
    getdstring RESNAME 260 MEMORY_FILE
    get OFSRES long MEMORY_FILE
    get RESLENGTH long MEMORY_FILE
    log RESNAME OFSRES RESLENGTH MEMORY_FILE
next i
## Post #4
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-11-02T23:03:29+00:00
- Post Title: (REQUEST) n3: ninety nine nights models and textures export

> Reply from systembest
>
> Thx and how can i export mesh data? 
I use offzip for pak files and extract 00000800 dat file
But bms script doesn't work. Report error message..

I'm used this bms script. 

# Game: Ninety-Nine Nights (XBox360)
# by fatduck     Aug09
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
get CSIZE asize
math CSIZE -= 0x800
get USIZE long
clog MEMORY_FILE 0x800 CSIZE USIZE

get NUMRES long MEMORY_FILE
for i = 0 < NUMRES
    getdstring RESNAME 260 MEMORY_FILE
    get OFSRES long MEMORY_FILE
    get RESLENGTH long MEMORY_FILE
    log RESNAME OFSRES RESLENGTH MEMORY_FILE
next i

I Don't know, but this is what I have:

```
# by fatduck     Aug09
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
get CSIZE asize
math CSIZE -= 0x800
get USIZE long
clog MEMORY_FILE 0x800 CSIZE USIZE

get NUMRES long MEMORY_FILE
for i = 0 < NUMRES
    getdstring RESNAME 260 MEMORY_FILE
    get OFSRES long MEMORY_FILE
    get RESLENGTH long MEMORY_FILE
    log RESNAME OFSRES RESLENGTH MEMORY_FILE
next i
```


It's the same crap. 2 things come to my mind: update your quickbms by downloading the latest exe version or your rip is corrupted. If you want some files, PM.
## Post #5
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2013-11-04T04:50:49+00:00
- Post Title: (REQUEST) n3: ninety nine nights models and textures export

This is when i run quickbms report error message.


And how to use 99Nights_Dot36T_exporter & import-n3-2011-03-27.blend file? 
I just drag 36t file. and  put in 99Nights_Dot36T_exporter.exe than appcrash. Am i use wrong?
