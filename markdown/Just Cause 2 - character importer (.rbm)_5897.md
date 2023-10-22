## Post #1
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-01-24T14:21:08+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

The contents of this post was deleted because of possible forum rules violation.






Blender 249 importer for Just Cause 2
Update:2014-09-14
-unpack tab archiva (only parts with 'SARC' chunk) for skinned meshes
-import skeleton from bsk file
-import skinned meshes from rbm file

How use:
- install Blender249 and Python 26
- unpack importer
- click Blender249.blend
- in Text Window press alt+p
- select: bsk or tab or rbm type file
[Blender249[JustCause2][PC][rbm][bsk][2014-09-14].zip](https://xentaxbackup.github.io/file/7814_Blender249[JustCause2][PC][rbm][bsk][2014-09-14].zip)
## Post #2
- Username: BeeswaX
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Aug 30, 2006 5:46 am
- Post datetime: 2011-01-25T22:42:57+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

awesome, any chance of a exporter aswell ?
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-29T06:44:18+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-01-29T09:00:33+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

Most models in this game use the same file for creating skeleton.
i found they are:biped.bsk,civilian_biped.bsk,parachute.bsk .
Which file  is at the end of .cdoll file (edit in hexeditor) .
Importer don't read .cdoll files.
For reading another .bsk file please correct manual line 323.

Mayby this help you for weigting data:
For rigged model you must parenting meshes to armature :
 - select meshes - in 3d window menu -Select =>Select all by type =>mesh
 - select armature - shift + right button mouse
 - parenting - ctrl+p =>make parent to =>armature = >create vertex groups ? =>don't create groups 
 - select armature
 - go to pose editor - ctrl + tab - select bone RMB => g - for translate, r - for rotate , rr - for local rotate ,s - for scale bone.

For checking if model have vertex groups:
 - select mesh
 - in 3d window - go to weight paint mode - ctrl+tab
 - go to buttons window => editing(F9) = >link and materials => vertex groups =>browses available vertex groups
 - if no one please send me your imported model
[jade.jpg](https://xentaxbackup.github.io/file/3850_jade.jpg)
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-01-29T10:12:36+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

Szkaradek123, thanks, now everything works!

[](http://s53.radikal.ru/i140/1101/32/7ba0c50e5616.jpg)
## Post #6
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2011-02-05T02:27:09+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

I'm a bit confuse, When you open up the blend file, what do you do after when it's open, like, how do you use that script to respond to begin with, once it open onto blender?
## Post #7
- Username: RanJ
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 06, 2011 9:57 am
- Post datetime: 2012-02-14T15:54:35+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

This works perfectly but when i try to import a Vehicle, i get a python error. Can someone please put up a Vehicle Importer?
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T14:05:03+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

Can you upload samples?
## Post #9
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2012-02-16T01:11:02+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

which version of the game? pc or ps3?
## Post #10
- Username: RanJ
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 06, 2011 9:57 am
- Post datetime: 2012-02-20T04:21:12+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: JD2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 01, 2011 11:40 pm
- Post datetime: 2012-04-30T10:21:02+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

Talk about throwing out the baby with the bathwater.  This is a perfect example of a legal file which was needlessly removed from this forum.

Anyone have a working download link for this Just Cause 2 importer for Blender?
## Post #12
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-09-13T17:25:50+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

> Reply from Szkaradek123
>
> The contents of this post was deleted because of possible forum rules violation.My friend, why do you want to delete the script, could you re-upload, although this is a old game, but also worth sharing, thank you
## Post #13
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-09-16T17:48:02+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

> Reply from Szkaradek123
>
> The contents of this post was deleted because of possible forum rules violation.






Blender 249 importer for Just Cause 2
Update:2014-09-14
-unpack tab archiva (only parts with 'SARC' chunk) for skinned meshes
-import skeleton from bsk file
-import skinned meshes from rbm file

How use:
- install Blender249 and Python 26
- unpack importer
- click Blender249.blend
- in Text Window press alt+p
- select: bsk or tab or rbm type fileHello my friend, thank you for your help, your work is great, thanks very much. Still would like to ask some questions, and I double clicked after running the blend files, error messages appear.(importerror: bad magic number in F:\blender-2.49-win64\.blender\scripts\newgamelib\_init_.pyc) My Blender is 2.49 64bit and 32bit, the runtime environment is python2.5 and python2.6(blender2.49 by default python2.5) cannot be used , please help me, God, thank you again for your help .
ok，My friend, I have solved a step, I used Blender biped.BSK 2.49A can import, but I cannot import the extracted mc01_lod1-Rico.RBM file, please help
## Post #14
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-09-28T08:51:21+00:00
- Post Title: Just Cause 2 - character importer (.rbm)

There are no news?
I would like to import the vehicles
