## Post #1
- Username: kmthrong
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Oct 22, 2014 9:19 pm
- Post datetime: 2014-10-24T16:36:34+00:00
- Post Title: Help in XBG watch dogs format

Hi I wanna a 3ds max script that can import this format,
I download this script for blender but it didn't work [http://www.mediafire.com/download/hd1m3 ... -01%5D.zip](http://www.mediafire.com/download/hd1m3uu4pv35pf7/WatchDogs%5BPC%5D%5B2014-07-01%5D.zip)
plz help me to import not important just mesh is enough tnx.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-24T21:42:13+00:00
- Post Title: Help in XBG watch dogs format

I wouldn't waste my spare time to write a maxscript when there's a working blender python script, especially when it's from Mariusz.  

What's your problem with the script? Did u use blender 2.49?

Or got an error message such as:
ImportError: No module named newGameLib Then copy the
newGameLib folder into your blender folder (where blender.exe resides).

start blender, load Blender249-WatchDogsImporter-2014-07-01.blend,
in the left side text window press alt-p, navigate to the .xbg model file and load it.

works like a charm, console output:

d:\WatchDogs[PC][2014-07-01]\char01.xbg
--------------------------------------------------
--------------------------------------------------
meshCount: 15
meshCount: 15
0 36 230 388 230 12 1946 0
-------------------- add new mesh
1 32 618 984 618 11 4506 0
...
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-10-25T01:39:30+00:00
- Post Title: Help in XBG watch dogs format

Yeah still working on this
## Post #4
- Username: kmthrong
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Oct 22, 2014 9:19 pm
- Post datetime: 2014-10-25T12:35:56+00:00
- Post Title: Help in XBG watch dogs format

> Reply from shakotay2
>
> I wouldn't waste my spare time to write a maxscript when there's a working blender python script, especially when it's from Mariusz.  

What's your problem with the script? Did u use blender 2.49?

Or got an error message such as:
ImportError: No module named newGameLib Then copy the
newGameLib folder into your blender folder (where blender.exe resides).

start blender, load Blender249-WatchDogsImporter-2014-07-01.blend,
in the left side text window press alt-p, navigate to the .xbg model file and load it.

works like a charm, console output:

d:\WatchDogs[PC][2014-07-01]\char01.xbg
--------------------------------------------------
--------------------------------------------------
meshCount: 15
meshCount: 15
0 36 230 388 230 12 1946 0
-------------------- add new mesh
1 32 618 984 618 11 4506 0
...

So I have this problem when I press alt+p give me this error: [http://0up.ir/up8/guest/10-25-2014-5-22-40-AM.png](http://0up.ir/up8/guest/10-25-2014-5-22-40-AM.png)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-25T13:22:44+00:00
- Post Title: Help in XBG watch dogs format

well, "Bad Magic Number", another stupid error message.  

What "they" meant to express is that the compiled python file (.pyc) doesn't match your python version, I guess.

here the number is: 0xF2D1 = 62161, that means python version 2.6a1 will be required at least.

(I'm using python 2.6.2., sry for the inconvenience.)

btw: don't use the latest python version for blender 2.49, since with python 3.0 there's a new Python API, that won't work here.
## Post #6
- Username: kmthrong
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Oct 22, 2014 9:19 pm
- Post datetime: 2014-10-25T17:17:45+00:00
- Post Title: Help in XBG watch dogs format

well, "Bad Magic Number", another stupid error message.  
And do you know what is more crazy than this blender is just 10 mb but python-2.6.2 is 13.9 mb 

But this time it said:
Compiled with python versian 2.5.2
'import site' failed ; use -v for traceback
[http://0up.ir/up8/guest/10-25-2014-10-53-37-AM.png](http://0up.ir/up8/guest/10-25-2014-10-53-37-AM.png)
Plz help me.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-25T18:49:27+00:00
- Post Title: Help in XBG watch dogs format

hmm, I have several blender installations on different partitions (XP and Win7).

On Win7 I get this message on blender2.49b startup:

Compiled with Python version 2.6.2.
'import site' failed; use -v for traceback
Checking for installed Python... No installed Python found.
Only built-in modules are available.  Some scripts may not run.
Continuing happily.

The WatchDogs.py script is working though but it's blender 2.49b.
So you might give it a last try before you pxrge...  

Or u could try use 2.49 with a path set to your python 2.6.2 installation (new System Variable: PythonPath).

(I installed python 2.6.6 for blender 2.49b on XP 18 months ago but don't remember
 the reasons since 2.49b seems to come with a built in 2.6.2 python)
## Post #8
- Username: kmthrong
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Oct 22, 2014 9:19 pm
- Post datetime: 2014-10-26T11:48:49+00:00
- Post Title: Help in XBG watch dogs format

So how can I give it a new address of python from my computer in blender?  
tnx for your support.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-26T14:23:54+00:00
- Post Title: Help in XBG watch dogs format

not sure whether I got what you mean.
setting the Python Path?

[http://www.katsbits.com/tutorials/blend ... riable.php](http://www.katsbits.com/tutorials/blender/python-path-variable.php)
## Post #10
- Username: kmthrong
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Oct 22, 2014 9:19 pm
- Post datetime: 2014-10-26T14:58:54+00:00
- Post Title: Help in XBG watch dogs format

Tnx it's working.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-26T15:24:10+00:00
- Post Title: Help in XBG watch dogs format

hallelujah!
## Post #12
- Username: saidbou
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 24, 2019 6:48 am
- Post datetime: 2019-01-23T22:53:36+00:00
- Post Title: Help in XBG watch dogs format

Sorry if the post is not accurate to the topic, but I'm looking for the blender file for Saint Seiya Soldier's Soul game. 
I got blender 249 and python 2.6.. and the script... But when I load the script, I'm getting a script error... Don't understand why...
Is the "newGameLib" folder the same for all the games ?
