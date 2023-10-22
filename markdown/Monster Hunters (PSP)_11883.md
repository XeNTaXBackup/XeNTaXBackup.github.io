## Post #1
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2014-09-02T19:14:48+00:00
- Post Title: Monster Hunters (PSP)

I've read around and for what I found they're some tools for extract models from those games (1,2,Unite,3rd). I read often they're tools for extract stuff from the Data.BIN of the game, even found tools for extract them, but no matter what I do I cannot make them work.

I've found tools here:

[https://github.com/codestation/mhtools](https://github.com/codestation/mhtools)

[https://github.com/svanheulen/mhff](https://github.com/svanheulen/mhff)

I've found one that are .Py tools, but I don't know how made work those .Py, neither with CMD, .Bat or even double click it

If someone know a way to actually extract model of the PSP version, I would appreciate that it guide me on the good way.

I'm more interesting on extract one model of the Monster Hunter Freedom Unite, one that its a DLC, But that the game has it on his data (I've use cheat in the game and the model comes as "Dummy" Named).


Sorry if my own English its broken.
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-09-03T21:20:13+00:00
- Post Title: Monster Hunters (PSP)

From the [mhff ReadMe](https://github.com/svanheulen/mhff/blob/master/README): All of these scripts require Python 3.x

You'll need a Java Development Toolkit (JDK) to compile the source code of the [mhtools](https://github.com/codestation/mhtools).
Or try this one: [mhtools.jar](http://www.mediafire.com/download/tz3d1d4i7n4ete6/mhtools.jar) (please reply if it works - since I don't own the game, I can't test it)
## Post #3
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2014-09-04T05:59:33+00:00
- Post Title: Monster Hunters (PSP)

> Reply from herbert3000
>
> From the mhff ReadMe: All of these scripts require Python 3.x

You'll need a Java Development Toolkit (JDK) to compile the source code of the mhtools.
Or try this one: mhtools.jar (please reply if it works - since I don't own the game, I can't test it)

I gonna try with that one, thanks. And I wasn't aware one need another program for make .jar, no matter how I search around on Goggle, but it never say how.

I cannot test it asap, for don't have the enough time, but if work or not, I gonna let you know.

I do know it need the Python 3.x, but I did install the 3.1 or sort like that, but it just open it and close it, neither on CMD way or doing a bat.

But, I gonna try to search more.
For now, thanks buddy
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-04T12:51:45+00:00
- Post Title: Monster Hunters (PSP)

> Reply from Darkhowlings
>
> I do know it need the Python 3.x, but I did install the 3.1 or sort like that, but it just open it and close it, neither on CMD way or doing a bat.started the pmo.py in blender 2.69 -> CTD, strange.

But I got it working by this hack:

```
    parser = argparse.ArgumentParser(description='Converts a Monster Hunter PMO file to Wavefront OBJ format')
    parser.add_argument('pmofile', help='PMO input file')
    parser.add_argument('mtlfile', help='MTL input file')
    parser.add_argument('outputfile', help='OBJ output file')
    #args = parser.parse_args()
    #convert_pmo(args.pmofile, args.mtlfile, args.outputfile)
    convert_pmo("D:\\000_data.pmo", "test.mtl", "D:\\test.obj")
```




000_data_pmo_.JPG (63.22 KiB) Viewed 492 times
## Post #5
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2014-10-03T06:29:39+00:00
- Post Title: Monster Hunters (PSP)

Sorry for don’t respond early, but here goes what I found out:

> Reply from herbert3000
>
> From the mhff ReadMe: All of these scripts require Python 3.x

You'll need a Java Development Toolkit (JDK) to compile the source code of the mhtools.
Or try this one: mhtools.jar (please reply if it works - since I don't own the game, I can't test it)

Actually it works! The Java only ran as command, it was able to extract all the data from the Data.BIN, from the .PAK models to even the music/effect that were on .WAV

> Reply from shakotay2
>
> Darkhowlings wrote:I do know it need the Python 3.x, but I did install the 3.1 or sort like that, but it just open it and close it, neither on CMD way or doing a bat.started the pmo.py in blender 2.69 -> CTD, strange.

But I got it working by this hack:
Code: Select allif __name__ == '__main__':
    parser = argparse.ArgumentParser(description='Converts a Monster Hunter PMO file to Wavefront OBJ format')
    parser.add_argument('pmofile', help='PMO input file')
    parser.add_argument('mtlfile', help='MTL input file')
    parser.add_argument('outputfile', help='OBJ output file')
    #args = parser.parse_args()
    #convert_pmo(args.pmofile, args.mtlfile, args.outputfile)
    convert_pmo("D:\\000_data.pmo", "test.mtl", "D:\\test.obj")

After some try and edit, it actually works, but… I don’t know if something it’s going on my PC, or it’s the Python who’s giving problem, but I was only able to extract a .OBJ, but without UV and neither form, I mean it was a “Cube” in simple words.

I gonna try to get the last Python and try again, because I was trying with the 2,7, because every time I try with the 3,0.1 I’ve it keep showing the sentence

> File "C:\Python30\pmo.py", line 238
>
>     with open(pmo_file, 'rb') as pmo, open(obj_file, 'w') as obj:
>
>                                     ^
>
> SyntaxError: invalid syntax

While the 2,7 didn’t give a problem, but once again, maybe its Python.

And to really know how you made it work on Blender! But maybe it’s because I never get along fine with Blender, let’s just say he hates me heh


*Just for add something odd around about the formats:
The game models are named the same with the ones of the Kingdom Hearts Birth by Sleep (.PMO) yet, they’re not the same ones or Noesis would open it. But once again, its not the first time two model formats with same name are not exactly the same

When it fully work and all, I gonna try to resume all, so they gonna be a way for extract model from those game (and even music/effect).
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-03-19T05:11:32+00:00
- Post Title: Monster Hunters (PSP)

sorry for dump old topic, but somebody got some information? when I try decrypt file I got it :S
## Post #7
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-07-11T18:47:38+00:00
- Post Title: Monster Hunters (PSP)

> Reply from shakotay2 ↑Thu Sep 04, 2014 8:51 pm at Thu Sep 04, 2014 8:51 pm
>
> 
Darkhowlings wrote:I do know it need the Python 3.x, but I did install the 3.1 or sort like that, but it just open it and close it, neither on CMD way or doing a bat.started the pmo.py in blender 2.69 -> CTD, strange.

But I got it working by this hack:
Code: Select allif __name__ == '__main__':
    parser = argparse.ArgumentParser(description='Converts a Monster Hunter PMO file to Wavefront OBJ format')
    parser.add_argument('pmofile', help='PMO input file')
    parser.add_argument('mtlfile', help='MTL input file')
    parser.add_argument('outputfile', help='OBJ output file')
    #args = parser.parse_args()
    #convert_pmo(args.pmofile, args.mtlfile, args.outputfile)
    convert_pmo("D:\\000_data.pmo", "test.mtl", "D:\\test.obj")

000_data_pmo_.JPG

Sorry for bumping such an old post, but I have tried your solution and it did not work.

It said: "Python script fail. Check console for now..."
I tried checking the console but there wasn't anything there.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-11T20:50:41+00:00
- Post Title: Monster Hunters (PSP)

Tried it again with blender 2.75 and works for me (menu Windows\\Toggle System Console):
.

```
\config\userpref.blend
AL lib: (EE) UpdateDeviceParams: Failed to set 44100hz, got 48000hz instead
found bundled python: D:\blender-2.75a\2.75\python
b'pmo\x00'
b'102\x00'
mtllib
pmo to obj
ready

-------------------------------------

importing obj 'D:\\test.obj'
        parsing obj file...
0.0360 sec
        loading materials and images...
        Material not found MTL: b'D:\\test.mtl'
0.0010 sec
        building geometry...
        verts:577 faces:750 materials: 1 smoothgroups:0 ...
finished importing: b'D:\\test.obj' in 0.0590 sec.

```
You have to adjust the path to 000_data.pmo in pmo.py.
.



000_data.pmo.png (86.24 KiB) Viewed 263 times
## Post #9
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-07-13T11:27:56+00:00
- Post Title: Monster Hunters (PSP)

I did adjust the path though, it just didn't work :\
## Post #10
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-07-21T22:36:47+00:00
- Post Title: Monster Hunters (PSP)

> Reply from shakotay2 ↑Fri Jul 12, 2019 4:50 am at Fri Jul 12, 2019 4:50 am
>
> 
Tried it again with blender 2.75 and works for me (menu Windows\\Toggle System Console):
.
Code: Select allRead new prefs: C:\Users\unk\AppData\Roaming\Blender Foundation\Blender\2.75
\config\userpref.blend
AL lib: (EE) UpdateDeviceParams: Failed to set 44100hz, got 48000hz instead
found bundled python: D:\blender-2.75a\2.75\python
b'pmo\x00'
b'102\x00'
mtllib
pmo to obj
ready

-------------------------------------

importing obj 'D:\\test.obj'
        parsing obj file...
0.0360 sec
        loading materials and images...
        Material not found MTL: b'D:\\test.mtl'
0.0010 sec
        building geometry...
        verts:577 faces:750 materials: 1 smoothgroups:0 ...
finished importing: b'D:\\test.obj' in 0.0590 sec.
You have to adjust the path to 000_data.pmo in pmo.py.
.
000_data.pmo.png

Do you know what could be causing it? I cannot get it to run.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-25T23:05:37+00:00
- Post Title: Monster Hunters (PSP)

> Reply from Portugalotaku ↑Mon Jul 22, 2019 6:36 am at Mon Jul 22, 2019 6:36 am
>
> 
shakotay2 wrote: ↑Fri Jul 12, 2019 4:50 am
Tried it again with blender 2.75 and works for me (menu Windows\\Toggle System Console):
.
Code: Select allRead new prefs: C:\Users\unk\AppData\Roaming\Blender Foundation\Blender\2.75
\config\userpref.blend
AL lib: (EE) UpdateDeviceParams: Failed to set 44100hz, got 48000hz instead
found bundled python: D:\blender-2.75a\2.75\python
b'pmo\x00'
b'102\x00'
mtllib
pmo to obj
ready

-------------------------------------

importing obj 'D:\\test.obj'
        parsing obj file...
0.0360 sec
        loading materials and images...
        Material not found MTL: b'D:\\test.mtl'
0.0010 sec
        building geometry...
        verts:577 faces:750 materials: 1 smoothgroups:0 ...
finished importing: b'D:\\test.obj' in 0.0590 sec.
You have to adjust the path to 000_data.pmo in pmo.py.
.
000_data.pmo.png


Do you know what could be causing it? I cannot get it to run.Dozens of reasons - depends on your OS, your skills, whatever.

If the message you're getting is still:
"Python script fail. Check console for now..."
then there should be more info in the blender console. (I'd be surprised if not.)

Check your python installation. Usually the patched script works with the bundled python which comes with blender 2.75 and higher.
## Post #12
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-07-29T23:55:26+00:00
- Post Title: Monster Hunters (PSP)

> Reply from shakotay2 ↑Fri Jul 26, 2019 7:05 am at Fri Jul 26, 2019 7:05 am
>
> 

I tried checking the console before, nothing appears. The only thing I know for certain is that the problem lies in this line:

    with open(pmo_file, 'rb') as pmo, open(obj_file, 'w') as obj:

This is the error that python itself gives:

Traceback (most recent call last):
  File "F:\MHFF\mhff-master\psp\pmo.py", line 272, in <module>
    convert_pmo("F:\MHFF\00\0078\000_data.pmo", "000_data.mtl", "F:\MHFF\00\0078\000_data.obj")
  File "F:\MHFF\mhff-master\psp\pmo.py", line 249, in convert_pmo
    with open(pmo_file, 'rb') as pmo, open(obj_file, 'w') as obj:
TypeError: file() argument 1 must be encoded string without NULL bytes, not str
>>> 

Though I can try reinstalling blender 2.75 and see if that adds the correct python version.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-31T06:56:59+00:00
- Post Title: Monster Hunters (PSP)

The script has been updated since 2014 (surprise  ) and I won't dig into this again because the problem with the pmo was solved by patching the old script from 2014.
So guess you're lost for now.
## Post #14
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-08-01T23:51:42+00:00
- Post Title: Monster Hunters (PSP)

:\

I guess I can try getting the 2014 script and then patching that.
## Post #15
- Username: cptforce123
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 14, 2020 5:34 am
- Post datetime: 2020-03-18T15:08:22+00:00
- Post Title: Monster Hunters (PSP)

how to use this program to extract all mhp3rd audio file?
