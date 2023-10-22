## Post #1
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-02-20T19:55:30+00:00
- Post Title: [Request] Sly Cooper: Thieves in Time

So i was taking a look at Thieves in Time, and everything looks pretty simple. all the main data is in the sly4.psarc and each level folder has an All_Combined.san.cooked file which contains all data for the level.

Each section starts with PROF followed by the size (thanks chrrox) so it's easy enough to separate. Most models are pretty easy to extract with the Hex2Obj tool and I have little problems getting them though there are some with multiple meshes the I can seem to get the UV's for
Edit:
Fixed the UV issue. There was a bug with hex2obj

Another problem are the character models. I cannot seem to rip them at all.
This is the closest I ever got


Here are some samples of some models that are simple enough to get 
[https://www.dropbox.com/s/rl1i3bd924b50 ... rmodel.zip](https://www.dropbox.com/s/rl1i3bd924b50e8/othermodel.zip)

Here are some character models 
[https://www.dropbox.com/s/mbyq5urp3cm39 ... Models.zip](https://www.dropbox.com/s/mbyq5urp3cm39wv/CharacterModels.zip)

And here is the All_Combined.san.cooked that i'm pulling everything from. (It's the Paris Hideout)
[https://www.dropbox.com/s/2jh5fjom0mmoz ... .cooked.7z](https://www.dropbox.com/s/2jh5fjom0mmozw8/sly4All_Combined.san.cooked.7z)
## Post #2
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-04-09T04:14:42+00:00
- Post Title: [Request] Sly Cooper: Thieves in Time

Still looking for help. I tried all I can with hex2obj and the best I could get with a model is in the image above. The faces seem all wrong but the vertices look like they are in the right place.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-09T22:19:57+00:00
- Post Title: [Request] Sly Cooper: Thieves in Time

maybe you could rip an object using a 3D ripper to get a clue about the correct face indices.

Atm for Mesh_2576(Murray).mdl (the cat) it looks like this:
# 0x5dfea
f 1 2 3 
f 4 2 3 
f 1 5 3 
f 1 2 6 
f 3 6 1 
f 7 6 1 
f 3 8 8 
f 1 6 9 
f 6 8 1 
f 10 6 10 
f 8 11 10 
f 8 6 12 
f 12 8 10 
f 13 10 12 
f 8 14 10 
f 14 12 15 
f 14 12 10 

TriStrips looking worse:
# 0x5dfea
f 1 3 2
f 2 3 4
f 3 2 4
f 4 2 3
f 2 1 3
f 3 1 5
f 1 3 5
f 5 3 1
f 3 2 1
f 1 2 6
f 2 3 6
f 3 1 6
f 6 1 7
f 1 6 7
f 7 6 1
f 6 3 1
f 1 3 8
f 8 8 1
f 8 6 1
f 1 6 9
f 9 6 8
f 6 1 8
f 8 1 10
f 1 6 10
f 6 8 10
f 10 8 11
f 8 10 11
f 11 10 8
f 10 6 8
f 8 6 12
f 12 12 8
f 12 10 8
f 8 10 13
f 13 10 12
f 10 8 12
f 12 8 14
f 8 10 14
f 10 12 14

For a small object like a book you could try to compose the faces manually and compare them to the ones created by hex2obj.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-04-11T12:26:41+00:00
- Post Title: [Request] Sly Cooper: Thieves in Time

Can you provide the .cooked archives you extracted these meshes from?
## Post #5
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2014-04-17T11:48:47+00:00
- Post Title: [Request] Sly Cooper: Thieves in Time

> Reply from shakotay2
>
> maybe you could rip an object using a 3D ripper to get a clue about the correct face indices.

For a small object like a book you could try to compose the faces manually and compare them to the ones created by hex2obj.

I have no idea how to do any of that.

> Reply from Gh0stBlade
>
> Can you provide the .cooked archives you extracted these meshes from?
this is where i pulled everything from
[https://www.dropbox.com/s/2jh5fjom0mmoz ... .cooked.7z](https://www.dropbox.com/s/2jh5fjom0mmozw8/sly4All_Combined.san.cooked.7z)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-24T03:32:50+00:00
- Post Title: [Request] Sly Cooper: Thieves in Time

> Reply from o0DemonBoy0o
>
> Here are some samples of some models that are simple enough to get 
https://www.dropbox.com/s/rl1i3bd924b50 ... rmodel.zip
made a Noesis python script to open your samples  


 fmt_SlyCooperThievesinTime_PS3_mdl.zip
(1.19 KiB) Downloaded 77 times


supports geometry and UVs
