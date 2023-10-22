## Post #1
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2012-06-27T06:42:53+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

[http://www.youtube.com/watch?v=uZKxCUXxB0Y](http://www.youtube.com/watch?v=uZKxCUXxB0Y)






This game cute 3d chararter come out
Ill more information and add data later on
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-27T13:12:09+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

it's not out yet is it?
## Post #3
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-06-27T14:20:28+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

> Reply from howfie
>
> it's not out yet is it?

The demo should have been out 2 weeks ago in the Japanese store of xbox live. Right now I don't have my 360 (RROD lol). I'm gonna see if I can download it if you're interested in it.

See ya.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-27T14:59:39+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

LOL that sucks dude. I would be pissed.
## Post #5
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2012-06-27T17:11:58+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

Hi guys

my uploaded 437mb file of model.dat
[http://bitshare.com/files/rd9e8ezk/model.7z.html](http://bitshare.com/files/rd9e8ezk/model.7z.html)
[http://bitshare.com/files/e5m3muf9/model.7z.html](http://bitshare.com/files/e5m3muf9/model.7z.html)
[http://rapidgator.net/file/21495782/model.7z.html](http://rapidgator.net/file/21495782/model.7z.html)
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-27T19:34:35+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

data is compressed, anyone recognize the compression?
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-27T20:54:54+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

0F F5 12 EE
is the clasic xmem compress
use xb decompress from the sdk to extract the data.
the archive format is simple

```
get baseoff long
for
get offset long
get size long
math offset * 0x800
math offset + baseoff
math size * 0x400
log "" offset size
if size == 0
cleanexit
endif
next

```


the resulting mdl files contain several xmem files i am not sure if quickbms handles these or not but the sdk does no problem.
i would automate the mdl extraction part if i knew what to feed into quickbms.

mdl extraction

```
get files long
get arcsize long
get null long
get base basename
for i = 0 < files
set name base
string name + _
string name + i
get type byte
if type == 0
string name + .mdl.xcomp
elif type == 1
string name + .1.xcomp
elif type == 2
string name + .dds.xcomp
elif type == 3
string name + .3.xcomp
elif type == 4
string name + .4.xcomp
elif type == 5
string name + .5.xcomp
elif type == 6
string name + .6.xcomp
elif type == 7
string name + .7.xcomp
elif type == 8
string name + .anm.xcomp
elif type == 9
string name + .tex.xcomp
endif
getdstring null 11
get offset long
get blocksize long
get size long
math offset * 0x800
log name offset size
next i

```
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-30T00:51:58+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

run this with the mdl bat file

```
c:\quickbms\quickbms.exe -d -F "*.mdl" C:\Character\mdl.bms C:\Character\mdl G:\WEBZEN\Character\ext
```


then run this bat file in the root of the folder you extracted these to.

```
xbdecompress.exe "%%f" "%%~pnf"
del "%%f"
)

```


and here is the bms to convert the character .tex files into dds files.

```
get files long
get unk long
get base basename
set offset files
math offset * 4
math offset + 12
for i = 0 < files
set name base
string name + _
string name + i
string name + .dds
get size long
log name offset size
math offset + size
next i

```
## Post #9
- Username: youngmark
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-30T16:40:57+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

here is the basic noesis script.
done
1.verts
2.uv's
3.normals
4.faces
not done
-bones / weights
-materials

[fmt_robotics_mdl_v1.rar](https://xentaxbackup.github.io/file/5526_fmt_robotics_mdl_v1.rar)
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-01T18:08:24+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

these nice models will definitely make good anime references . kinda looks toaru majutsu no index style.
## Post #11
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-01T18:17:11+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

ok chroxx i follow yor steps but iam stuck in the part of

"run this with the mdl bat file"  with the code below that
its said "Error the input folder its empty" so what i did
wrong ?
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-06T07:53:55+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

are the bones/weights/materials for this game hard to figure out? gonna finish this one up?
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-06T09:30:03+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

the bones / wieghts are not to hard
for materials i think ill have to edit the extraction script to count the texture number rather then the file number in the archive.
but yeah if i don't finish it this weekend feel free or if you want to anyway go for it.
## Post #14
- Username: meda
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 16, 2012 9:14 pm
- Post datetime: 2013-01-19T18:37:06+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

Can somebody finish this up and add the bones?
## Post #15
- Username: b9502032
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Apr 21, 2014 3:52 am
- Post datetime: 2014-05-04T13:44:59+00:00
- Post Title: [XBOX360]ROBOTICS;NOTES

Hi sorry to reup this thread but i really dont know what is xb decompress is 
I extract the iso file and got the model.dat and what is the next step to do
please help me , appriciate
## Post #16
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2016-11-26T00:20:58+00:00
- Post Title: Re: [XBOX360]ROBOTICS;NOTES

I can't open .mdl file while using chrrox plugin on noesis
File not be prieveiwed error message displayed
