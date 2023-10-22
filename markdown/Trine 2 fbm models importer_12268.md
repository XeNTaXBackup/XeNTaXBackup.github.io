## Post #1
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2014-11-24T20:39:25+00:00
- Post Title: Trine 2 fbm models importer

I created maxscript for import of Trine 2 fbm files in 3D Studio Max. (Tested with game version: Trine 2 Gobline Menace DLC and Trine 2 Complete Story). 


 trine2-CS.rar
trine2-CS.ms (3.04 KiB) Downloaded 70 times

 

Works with static meshes only. The bone system is decoded, except that the vertex weights. (Maybe someone will help with this   but its realy not important. The game has a small group of characters)

About fbi files - just rename *.fbi to *.dss
(About the Normal map: 
 Gobline Menace - swap red channel with alpha; Complete Story - change the levels to 127-255)

You can unpack fbq files with this bms script get from: [viewtopic.php?f=10&t=7621](http://forum.xentax.com/viewtopic.php?f=10&t=7621)

```
# script for QuickBMS http://quickbms.aluigi.org

comtype lzf
get DUMMY long
get FILES long
get BASE_OFF long
math BASE_OFF += 0xc
for i = 0 < FILES
    get NAME string
    get OFFSET long
    get NOZIP byte
    get SIZE long
    get ZSIZE long
    get CRC long
    math OFFSET += BASE_OFF
    if NOZIP == 0
        clog NAME OFFSET ZSIZE SIZE
    else
        log NAME OFFSET SIZE
    endif
next i

```


Sorry about my bad english
## Post #2
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2014-11-29T10:02:02+00:00
- Post Title: Trine 2 fbm models importer

The script works fine! Is there any way of create a batch process?
## Post #3
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2014-11-30T16:57:27+00:00
- Post Title: Trine 2 fbm models importer

> Reply from jmgg
>
> The script works fine! Is there any way of create a batch process?

The batch is easy. Here is an example:


 trine2-CS-batch.rar
(3.51 KiB) Downloaded 42 times



You have to set up some settings like this:

```
mdir = @"k:\games\Trine 2 Complete Story\Trine 2 Gobline Menace DLC\rip\data\root\instance_base\entity\object\"
sdir = @"d:\3D\game-models\trine2\zzz2\"
```


where 
tdir is texture root folder
mdir is fbm root folder
sdir is for converted max files root folder

The script works with up to 95 % of models, but there is some bugs and I will try to fix them now.
The fbm files are several different versions and that makes some difficulties.
For example, the models are in cubic form in the array of vertices (with values between -1 and 1). After that there is some kind of transform matrix and not works fine with some models
## Post #4
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-03T11:39:42+00:00
- Post Title: Trine 2 fbm models importer

> Reply from vallex
>
> jmgg wrote:The script works fine! Is there any way of create a batch process?

The batch is easy. Here is an example:
The attachment trine2-CS-batch.rar is no longer available

You have to set up some settings like this:
Code: Select alltdir = @"d:\3D\materials\_trine2\"
mdir = @"k:\games\Trine 2 Complete Story\Trine 2 Gobline Menace DLC\rip\data\root\instance_base\entity\object\"
sdir = @"d:\3D\game-models\trine2\zzz2\"

where 
tdir is texture root folder
mdir is fbm root folder
sdir is for converted max files root folder

The script works with up to 95 % of models, but there is some bugs and I will try to fix them now.
The fbm files are several different versions and that makes some difficulties.
For example, the models are in cubic form in the array of vertices (with values between -1 and 1). After that there is some kind of transform matrix and not works fine with some modelsHello my friend, thank you for your great work, I tested the latest scripts, but I do not know how to set the path. I decrypted content folder not found 

```
mdir = @"k:\games\Trine 2 Complete Story\Trine 2 Gobline Menace DLC\rip\data\root\instance_base\entity\object\"
sdir = @"d:\3D\game-models\trine2\zzz2\"
```

[BaiduShurufa_2014-12-3_19-25-42.png](https://xentaxbackup.github.io/file/8185_BaiduShurufa_2014-12-3_19-25-42.png)
## Post #5
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2014-12-03T21:03:24+00:00
- Post Title: Trine 2 fbm models importer

The paths in your case are somethink like this:

```
mdir = { game folder } 
sdir = { where you want to save the max files}

```
## Post #6
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-09T19:21:03+00:00
- Post Title: Trine 2 fbm models importer

> Reply from vallex
>
> The paths in your case are somethink like this:
Code: Select alltdir = { game folder } 
mdir = { game folder } 
sdir = { where you want to save the max files}Hello, my friends, thank you for your reply. I will now test
## Post #7
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-09T19:41:52+00:00
- Post Title: Trine 2 fbm models importer

> Reply from raykingnihong
>
> vallex wrote:The paths in your case are somethink like this:
Code: Select alltdir = { game folder } 
mdir = { game folder } 
sdir = { where you want to save the max files}
Hello, my friends, thank you for your reply. I will now testHello, my friends, thank you for your reply. Please also forgive me for my stupidity, I set the path, run the script error, ask for help
[BaiduShurufa_2014-12-10_3-32-4.png](https://xentaxbackup.github.io/file/8230_BaiduShurufa_2014-12-10_3-32-4.png)
## Post #8
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-01-02T22:07:28+00:00
- Post Title: Trine 2 fbm models importer

just set vraymat = false
