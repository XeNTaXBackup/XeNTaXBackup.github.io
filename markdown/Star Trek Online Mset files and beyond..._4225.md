## Post #1
- Username: Enforcer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 27, 2010 11:39 pm
- Post datetime: 2010-03-15T13:48:05+00:00
- Post Title: Star Trek Online Mset files and beyond...

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: JohnFord
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 18, 2010 7:04 pm
- Post datetime: 2010-12-16T03:21:28+00:00
- Post Title: Star Trek Online Mset files and beyond...

Heya,

I'm trying to extract some of the models from the game as well.  I've extracted all the bins and now I'm left with .mset files and no idea how to view them.

Did you make any progress with this?

Any assistance would be appreciated.

Nick
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-16T11:18:10+00:00
- Post Title: Star Trek Online Mset files and beyond...

the link is dead can you upload it to mediafire or sendspace.
## Post #4
- Username: JohnFord
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 18, 2010 7:04 pm
- Post datetime: 2010-12-17T16:21:23+00:00
- Post Title: Star Trek Online Mset files and beyond...

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: JohnFord
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 18, 2010 7:04 pm
- Post datetime: 2010-12-23T08:08:32+00:00
- Post Title: Star Trek Online Mset files and beyond...

Any hope of getting this to work?

Does anyone know a way to directly capture models from the game client?
## Post #6
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-04T15:19:36+00:00
- Post Title: Star Trek Online Mset files and beyond...

Sorry for the necro post but ive made a development with 3dripperDX, if you enter this command line in 3dripperDX while trying to run the Live servers GameClient.exe you will be able to log into the game and rip 3D from the game. (The Locale can be changed for what ever country you are in)

```
-Locale English -server 208.95.184.38 -server 208.95.184.42 -server 208.95.184.192 -server 208.95.184.129 -server 208.95.184.129 -server 208.95.184.43 -LoginServerShardIPAndPort Holodeck 208.95.184.38 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.30 7001 -LoginServerShardIPAndPort Holodeck 208.95.184.42 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.42 7001 -LoginServerShardIPAndPort Holodeck 208.95.184.192 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.192 7001 -LoginServerShardIPAndPort Holodeck 208.95.184.129 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.129 7001 -LoginServerShardIPAndPort Holodeck 208.95.184.43 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.43 7001 -console
```

Here's an example of something I've been able to rip from STO (rendered in 3ds max 2012):

hope this helps you all out
## Post #7
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-02-02T14:20:53+00:00
- Post Title: Star Trek Online Mset files and beyond...

> Reply from flarespire ↑Tue Jun 04, 2013 11:19 pm at Tue Jun 04, 2013 11:19 pm
>
> 
Sorry for the necro post but ive made a development with 3dripperDX, if you enter this command line in 3dripperDX while trying to run the Live servers GameClient.exe you will be able to log into the game and rip 3D from the game. (The Locale can be changed for what ever country you are in)
Code: Select all-Locale English -server 208.95.184.38 -server 208.95.184.42 -server 208.95.184.192 -server 208.95.184.129 -server 208.95.184.129 -server 208.95.184.43 -LoginServerShardIPAndPort Holodeck 208.95.184.38 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.30 7001 -LoginServerShardIPAndPort Holodeck 208.95.184.42 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.42 7001 -LoginServerShardIPAndPort Holodeck 208.95.184.192 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.192 7001 -LoginServerShardIPAndPort Holodeck 208.95.184.129 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.129 7001 -LoginServerShardIPAndPort Holodeck 208.95.184.43 7422 -LoginServerShardIPAndPort Holodeck 208.95.184.43 7001 -console
Here's an example of something I've been able to rip from STO (rendered in 3ds max 2012):

hope this helps you all out

This doesn't seem to work anymore, as far as I know 3D Ripper DX works only on 32 Bit applications but I don't think STO is 32 bit anymore, it gives me an error when attempting to launch the GameClient.exe now.
## Post #8
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2021-02-08T12:46:20+00:00
- Post Title: Star Trek Online Mset files and beyond...

Ninja Ripper supports 64 bit applications and the same command line should work in theory, however, Cryptic made changes to the engine that for some reason now garbles all UVW data on ripped meshes, so you're best bet is dumping the .mset's and converting them to obj using the gibbed.crypticstudios tools. Those tools should show up with a quick google search.
