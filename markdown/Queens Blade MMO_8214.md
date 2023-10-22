## Post #1
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-07T23:31:26+00:00
- Post Title: Queens Blade MMO

Here is a quickbms script to extract these archives.

```
get files short
get null short
filexor "0x73 0x64 0x66 0x61 0x73 0x6C 0x64 0x66 0x6B 0x6A 0x66 0x73 0x6C 0x6B 0x65 0xA4 0xA9 0xA4 0xB8 0xA4 0xA7 0xA4 0xA9 0xA4 0xA9 0xA4 0xA4 0xA4 0xB7 0x73 0x64 0x66 0x21 0x40 0x40 0x23 0x21 0x40 0x46 0x24 0x47 0x67 0x66 0x67 0x64 0x73 0x00"
for i = 0 < files
get id long
putarray 0 i id
next i
for i = 0 < files
get id1 long
putarray 1 i id1
next i
for i = 0 < files
getarray OFFSET 1 i
if OFFSET == -1
getdstring null 0x310 #this is the recursive directory info but we can skip it in this game
endif
if OFFSET != -1
getdstring basename 0xF8
get SIZE long
get UNK01 long
get UNK02 long
getdstring NULL 0x18
getdstring NAME 0x1EC
getdstring basename 0x8
putarray 2 i SIZE
putarray 3 i NAME
endif
next i
filexor ""
savepos base
for i = 0 < files
getarray OFFSET 1 i
getarray SIZE 2 i
getarray NAME 3 i
math OFFSET + base
if NAME != 0
log NAME OFFSET SIZE
endif
next i

```
## Post #2
- Username: kraken973
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 21, 2010 11:31 pm
- Post datetime: 2012-02-07T23:57:18+00:00
- Post Title: Queens Blade MMO

Thanks  
Now we must found a viewer or model converter.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T01:04:56+00:00
- Post Title: Queens Blade MMO

Are you going to work on the models? They're pretty hot  
The items and map assets looked pretty straightforward, so the models are probably not too hard either.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-08T01:11:49+00:00
- Post Title: Queens Blade MMO

go for it its all yours.
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-08T02:10:40+00:00
- Post Title: Queens Blade MMO

I didn't know there was a Queen's Blade MMO. That must be a fascinating/terrifying online experience. (assuming it follows the anime thematically, which I was unable to stomach except when extremely stoned... although exploding milktits of death is pretty hilarious in concept even when I'm not stoned)

Godspeed, finale00. Godspeed.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T02:58:10+00:00
- Post Title: Queens Blade MMO

Well considering the trailer you'd think it might.
[http://www.youtube.com/watch?v=m7Tpy4LqfIo](http://www.youtube.com/watch?v=m7Tpy4LqfIo)

Though there appear to be naked models in this game, which I have not found....
## Post #7
- Username: s25jin
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 15, 2011 1:11 am
- Post datetime: 2012-02-08T04:39:04+00:00
- Post Title: Queens Blade MMO

somebody upload client please..
## Post #8
- Username: s25jin
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-08T04:43:27+00:00
- Post Title: Queens Blade MMO

[http://queens.zcdn.co.kr/queens/Client/ ... club_2.exe](http://queens.zcdn.co.kr/queens/Client/QueensClientSetup-CBT-Gameclub_2.exe)
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-08T04:55:46+00:00
- Post Title: Queens Blade MMO

go finale00 go! bunch of sicko perverts.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T06:28:19+00:00
- Post Title: Queens Blade MMO

So I found some nude models....  
I'm sure that's what people were looking for right?
So that when the animations are loaded, you can have a naked girl with huge guns running around right?

Of course, that should generate more interest in this game.

[http://i.imgur.com/hY2n8.jpg](http://i.imgur.com/hY2n8.jpg)

Like holy crap how does a game even get away with this. Her clothes are see-through!

[http://i.imgur.com/MOIJr.jpg](http://i.imgur.com/MOIJr.jpg)

I wouldn't be surprised if there's clothes-ripping as well when you get hit....

The game makes no sense from the models I'm seeing. You have huge mecha enemies....with women joined to them for some reason. It's as if the women are there for the sake of being there.

Oh and ya, a single model has multiple meshes. I just haven't figured out how to parse it.
And materials are referenced by name.

The bra and panties are a separate mesh stored in a separate folder. I guess in-game you can decide what bra they should wear (if any?)
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-08T07:37:01+00:00
- Post Title: Queens Blade MMO

> Reply from finale00
>
> So I found some nude models....
## Post #12
- Username: kraken973
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 21, 2010 11:31 pm
- Post datetime: 2012-02-08T08:12:48+00:00
- Post Title: Queens Blade MMO

A other game of LivePlex have nudity
The Invincible Online
[http://img235.imagevenue.com/img.php?im ... 2_60lo.jpg](http://img235.imagevenue.com/img.php?image=850635430_LivePlex18_122_60lo.jpg)
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-08T12:35:54+00:00
- Post Title: Queens Blade MMO

start a new topic with a client download and a sample archive if you want help with the format.
## Post #14
- Username: raelizer
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 08, 2012 8:37 pm
- Post datetime: 2012-02-08T12:40:27+00:00
- Post Title: Queens Blade MMO

hey chrrox which program did you use to actually view the .mesh files because ive tried everything i have and am unable to load anything. ive even tried neosis and blender both with your plugins.
