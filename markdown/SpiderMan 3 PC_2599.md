## Post #1
- Username: yorky
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 28, 2007 10:39 pm
- Post datetime: 2007-04-28T21:30:35+00:00
- Post Title: SpiderMan 3 PC

hi all i want to ask if anyone are able to creat one unpacker for the files from spider man 3 .PCPACK files. i am going to upload one exemple i hope someone can help thx.
[CA5_CHENTHANKS.rar](https://xentaxbackup.github.io/file/1138_CA5_CHENTHANKS.rar)
## Post #2
- Username: yorky
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 28, 2007 10:39 pm
- Post datetime: 2007-05-04T20:40:41+00:00
- Post Title: SpiderMan 3 PC

anyone got any luck with it ? is it a hard format to discovery ?
thx
## Post #3
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-05-04T23:22:49+00:00
- Post Title: SpiderMan 3 PC

The graphics may not be compressed. I only saw a few bytes at the bottom of your sample but they may be 32bit DDS.
 I don't suppose you have a direct link to a file of the demo of this game.
## Post #4
- Username: yorky
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 28, 2007 10:39 pm
- Post datetime: 2007-05-05T01:20:34+00:00
- Post Title: SpiderMan 3 PC

hi sparedlife i have searched around for some spiderman 3 demo but i haven´t finded. but i have uploaded more pcpacks from spiderman3 maybe will help you a bit more. you can get them here: [http://homepage.esoterica.pt/~nx8ybp/pcpacks.rar](http://homepage.esoterica.pt/~nx8ybp/pcpacks.rar)

Thx for your atention
## Post #5
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-05-06T23:21:56+00:00
- Post Title: SpiderMan 3 PC

The textures are in uncompressed format, at least what I looked at. Story_Lizard_2_V_TBM has several graphics in it. There is no DXT header for each file but there is an index with description that points to each graphic. 

there are mips



After looking a little more I see there are also some kind of indexed graphics. Maybe 8bit indexed DDS because they still have mips. 

I can't figure out how the program finds the graphics based on the library file's graphic pointer structure.

```
00 02 00 00 00 02 00 00 01 00 00 00 0A 00 00 00
44 58 54 31 00 00 00 00 00 00 00 00 00 00 00 00
```


 The above code says it's a 512X512 DXT1. I'm assuming the first part is the needed offset and file size but the graphic starts at 22144 or 5680h
## Post #6
- Username: yorky
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 28, 2007 10:39 pm
- Post datetime: 2007-05-09T20:24:36+00:00
- Post Title: SpiderMan 3 PC

looks great, the only prob is i have no idea how to extract the files from this packs and maybe a viewer for the textures...
anyone around can give a litle help here plz
thx
## Post #7
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-05-18T02:24:00+00:00
- Post Title: SpiderMan 3 PC

Any info on how to extract the music?
## Post #8
- Username: Vugam
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 31, 2007 11:18 pm
- Post datetime: 2007-06-07T18:36:03+00:00
- Post Title: SpiderMan 3 PC

Yeah. Only open the music with Adobe Audition. No problems in the type of file.
## Post #9
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-17T16:30:50+00:00
- Post Title: SpiderMan 3 PC

> Reply from Vugam
>
> Yeah. Only open the music with Adobe Audition. No problems in the type of file.

AA == CoolEdit Pro 2.0.  $$$$$

Any "free" tool to unpack the sounds/music/soundtracks?  These are files with the suffix of .PCSSB but they seem to be FSB3.1 files.  Unfortunately the ToWav tool doesn't pull the sound file out like it did with the Battlestations Midway FSB3.1 files.  Must be a compresses format or something.
## Post #10
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-17T16:36:13+00:00
- Post Title: SpiderMan 3 PC

> Reply from Dandapani
>
> Vugam wrote:Yeah. Only open the music with Adobe Audition. No problems in the type of file.

AA == CoolEdit Pro 2.0.  $$$$$

Any "free" tool to unpack the sounds/music/soundtracks?  These are files with the suffix of .PCSSB but they seem to be FSB3.1 files.  Unfortunately the ToWav tool doesn't pull the sound file out like it did with the Battlestations Midway FSB3.1 files.  Must be a compresses format or something.

NM.  Just rename from PCSSB to MP3 and play them.

[http://216.239.51.104/search?q=cache:P_ ... cd=5&gl=us](http://216.239.51.104/search?q=cache:P_5uR9_v6koJ:boards.gamefaqs.com/gfaqs/genmessage.php%3Fboard%3D938765%26topic%3D35668994+PCSSB+file&hl=en&ct=clnk&cd=5&gl=us)
## Post #11
- Username: dertyjerzian
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 25, 2007 9:17 pm
- Post datetime: 2007-08-02T05:14:05+00:00
- Post Title: SpiderMan 3 PC

hey everyone, I joined to ask about this. I'll
stick around though, I'm a mod enthusiast and what nots.

Anyways, how the heck can I get to the dds textures in SM3?
## Post #12
- Username: dertyjerzian
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 25, 2007 9:17 pm
- Post datetime: 2007-08-08T03:06:50+00:00
- Post Title: SpiderMan 3 PC

> Reply from SparedLife
>
> The textures are in uncompressed format, at least what I looked at. Story_Lizard_2_V_TBM has several graphics in it. There is no DXT header for each file but there is an index with description that points to each graphic. 

there are mips



After looking a little more I see there are also some kind of indexed graphics. Maybe 8bit indexed DDS because they still have mips. 

I can't figure out how the program finds the graphics based on the library file's graphic pointer structure.
Code: Select all05 00 00 FC 7F E1 89 16 00 00 00 00 00 00 00 00
00 02 00 00 00 02 00 00 01 00 00 00 0A 00 00 00
44 58 54 31 00 00 00 00 00 00 00 00 00 00 00 00

 The above code says it's a 512X512 DXT1. I'm assuming the first part is the needed offset and file size but the graphic starts at 22144 or 5680h

Yes m8, but how to open and empty the pcpack files?
I'm very new here, I understand there is a program for this stuff?

I mod GTA, if anyone knows how to mod GTA, you'll follow exactly 
what I am looking for: at least an extract method, hopefully
a replace/import method. I'll delete me previous post.

Thank you everyone. 

On a side note, I imagine there must be many modder homebrew
enthusiasts here, would love to hear about the funnest games to
work on, open for PMs 

edit: hmm, I can only delete this one, what would defeat the purpose...

Perhaps a merge when things roll on then? sorry for teh double post then,
usually you can.
## Post #13
- Username: dertyjerzian
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 25, 2007 9:17 pm
- Post datetime: 2007-08-16T11:09:09+00:00
- Post Title: SpiderMan 3 PC

Still wondering how to use the textures from my spider man three game guys   

Is this like, not a modding forum or something?
## Post #14
- Username: yorky
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 28, 2007 10:39 pm
- Post datetime: 2007-08-20T12:00:25+00:00
- Post Title: SpiderMan 3 PC

dertyjerzian i think ppl just ignore this game because it has a hard format or something, seems they are unable to open it because of that you/me/others are being ignored..
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-08-20T16:34:45+00:00
- Post Title: SpiderMan 3 PC

> Reply from dertyjerzian
>
> Still wondering how to use the textures from my spider man three game guys   

Is this like, not a modding forum or something?

Yes it's a modding forum i think, but some formats are a bit hard to know how it works.

Example: Some people still waiting for mod Joint Tasks Forces, this game uses a encription.

Only can i say it's..."be patient"
## Post #16
- Username: dertyjerzian
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 25, 2007 9:17 pm
- Post datetime: 2007-08-30T21:14:32+00:00
- Post Title: 

Ok, I just read the last post with a texture in it and it seemed like all was needed was some way to tell windows it is an dds due to no headers or whatever. I wish I could get to those textures though  Just want to extract them, not mod the spiderman game  Thanks guys.
## Post #17
- Username: dertyjerzian
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 25, 2007 9:17 pm
- Post datetime: 2007-10-09T12:31:15+00:00
- Post Title: 

Thanks guys,

I just figured (I dnt know how to mine this kind of data, so it was an easy assumption) that the post above with the texture in it said they were pretty basic, now that I read it again after all this time, I can see there are indeed hints there that this is a difficult format.

Sorry guys
