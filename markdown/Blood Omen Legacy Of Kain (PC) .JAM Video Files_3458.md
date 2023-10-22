## Post #1
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-05-03T09:44:30+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Hi there, i'm making enhanced graphics engine for this game. But i got stunned with it's movie format, i have hardly searched web for tools that could deal with JAM video format. But there isn't any. I will be very happy if someone help me with figuring out how to play this video files or decode them into number of images.

Someone could tell that i can rip off video from PSX version of game. It is important to rip it from PC as my enhanced graphics port should do this automatically with PC release user must have (so i don't need to distibute videos with the game).

This is pure video stream file and audio comes with another .VAG file which decodes pretty well.

Here is the link to sample:
[http://darkmaster.quakedev.com/work/act14b.zip](http://darkmaster.quakedev.com/work/act14b.zip)
## Post #2
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-03T12:40:56+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

I don't have the game neither I've played it, so let's get a bit of info:

I see a basic header starting with:

4 bytes -> string literal "JAM" plus a end string "0"
4 bytes -> unsigned short/long 320
4 bytes -> unsigned short/long 240

So I ask you, may be that the video resolution?

Then we have: 

4 bytes -> unsigned short/long 454 NO IDEA yet
4 bytes -> All zeros

Then we have a bunch of data and again: many 00f8 hex repeated for a while (dunno if black screen video or something related with the header)

Finally it starts more mixed data, which may be the actual video.

As I've never worked decyphering video, may someone with more experience in this topic give you better info.
## Post #3
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-05-03T13:02:49+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Balder: yeah, thats video resolution

I will check ingame version of this video and post here whether it begins with black or not

+ don't know if it helps - file compresses badly with WinZip so i guess there is some sort of compression used to store frames.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-03T13:05:11+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

why not use fraps to record the video file or any other video recording program on the pc?
## Post #5
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-05-03T13:25:12+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

chrrox: no point, please read carefully post #1. I need to make my own player for this format or convert it by tool (or number of tools) which could be executed during installation process. Because i can't distribute converted videos.

Balder wrotes:

> Then we have a bunch of data and again: many 00f8 hex repeated for a while (dunno if black screen video or something related with the header)
Yeah, it starts from black screen
## Post #6
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-03T13:42:59+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Oka, so we are not very far from knowing the .jam structure. If known, the problem is solved. I'll code a converter tool for you and give you the source code. I hope C++ will be handy for your project.

So I'm going to analyze it better and I'll post any result I get.

Now I have to leave, I'll look at that when I have another bit of time.

(Just update the topic here If you solve your problem, so I don't work in vain later)  

Best luck, see you
## Post #7
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-05-03T13:48:14+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Balder: thanks alot  C++ would be just good as project is going to be cross-platform
## Post #8
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-03T20:50:18+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Hi again! I've been playing around the .jam a little, I'm finding this format pretty complicated, what I discovered:

4 bytes -> string literal "JAM" plus a 0 byte
4 bytes -> unsigned short/long 320
4 bytes -> unsigned short/long 240
4 bytes -> unsigned short/long 454                     -NO IDEA-
4 bytes -> All zeros ?¿
4 bytes -> 1 0 0 0 or simply 1 ?¿
4 bytes -> 246 18 0 0 0 or 4854 and 0, for example -NO IDEA-
4 bytes -> 44 1 0 255 (or 300 or a very big number)                IMPORTANT-> this value, searched in the hex editor, repeats alongside all the file, as if it were the header of each photogram or something like that.
(All valors as unsigned bytes)
Also, the previous of this last entry and consequent entries, repeat sometimes in the same structure as the shown here, so It may confirm the theory of being some kind of "each frame" header.

Now It'll be good to have some info so we can continue working on this, cause my imagination is blocked for now:
¿Does any of these numbers mean something for you?
¿Clip duration?
¿Could you rip with fraps an avi version of the video so I can go comparing values?
¿Could yo provide another jam file to confirm what is already known?
¿Is this a PC game or another plataform?
¿Is this video in higher graphics or does it use the graphics from the game? (I mean, if it's an script video using the game engine or a real video)

For now that's all. We'll see what can we do.

cheers!
## Post #9
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-05-04T12:26:14+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Balder wrotes:

> Does any of these numbers mean something for you?
dunno, 454 may be a total frames count since movie length is about 17 seconds

> Does any of these numbers mean something for you?
>
> Clip duration?
>
> Could you rip with fraps an avi version of the video so I can go comparing values?
Fraps does not work as game don't use 3D at all. I will rip PSX movies and post links here when finish (guessing existing YouTube webcam rips does not suit for you). Hold on.

> Could yo provide another jam file to confirm what is already known?
sure: [http://darkmaster.quakedev.com/work/ACT12.zip](http://darkmaster.quakedev.com/work/ACT12.zip)

> Is this a PC game or another platform?
PC port of PlayStation1 game. Many of formats was leaved as was in PSX version (tim's for graphics, VAB/VAG for sound and such).  In PSX version game movies were in .STR format (PSX Mjpeg). But for some unknown reason they are JAM in PC Version... 

> Is this video in higher graphics or does it use the graphics from the game? (I mean, if it's an script video using the game engine or a real video)In higher graphics, not using any of game graphics. Real video stream. And (if matter) movies always played with interlacing effect.
## Post #10
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-05-27T06:13:32+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Hi again!
Request is still actual

Sorry, i wasn't able to rip videos from PSX version of game, any of PSX video tool that i have trried just won't play that .STR properly, however program called "PSX Movie Converter" can read some frames, despite of crashes. I was found out that 454 is exactly the frames count ACT14b.JAM has, ACT12.JAM has 636 frames

Here is the link to STR files if they may help:

ACT12.JAM -> [http://darkmaster.quakedev.com/work/act12_str.zip](http://darkmaster.quakedev.com/work/act12_str.zip)
act14b.JAM ->  [http://darkmaster.quakedev.com/work/act14b_str.zip](http://darkmaster.quakedev.com/work/act14b_str.zip)

+ links to Camera-ripped videos:
ACT12.JAM (Higher quality): [http://www.legacy-of-kain.ru/BO_Video/BOvideo8.mp4](http://www.legacy-of-kain.ru/BO_Video/BOvideo8.mp4)
ACT12.JAM (YouTube): [http://www.youtube.com/watch?v=fLA36CouyK8](http://www.youtube.com/watch?v=fLA36CouyK8)

act14b.JAM (Higher quality): [http://www.legacy-of-kain.ru/BO_Video/BOvideo11.mp4](http://www.legacy-of-kain.ru/BO_Video/BOvideo11.mp4)
act14b.JAM (YouTube): [http://www.youtube.com/watch?v=9LsO_bhSfzA](http://www.youtube.com/watch?v=9LsO_bhSfzA)
## Post #11
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-27T17:14:28+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Okay, already downloaded the stuff.

I tell you what I'm doing: with the str's I already have all information about frames and chunks, but as they are compressed and multiplexed I have to work out this format first to see if the uncoded stream helps knowing better the jam.

What it's very strange is the jam being so different from the str, as they are both psx formats. (Talking about the header) But if the encoding is similar we may be able to manage those nasty jams.

Unfortunately this will take time, so don't expect results soon.  

At least I've already learned a lot about psx video formats hehe
## Post #12
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-07-15T05:12:18+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Hi! just curious how it's going? Request is actual

Sorry for possible offtop, i will remove this pic if it's againts the rules. Project is progressing. Here is a day-night sequence (24 minutes converted to several seconds) of Codenamed: Blood Omnicide, a fan blood omen remake that requires those nasty JAM's decoder
## Post #13
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-07-21T16:36:06+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Hi again!

Beautiful screen yeah...!

Actually I don't have time to further investigate this topic, but I'll tell you some helpful info:

Those nasty jams are some kind of str-like play station movies, and so, knowing well the str format you can extrapolate how to deal with the jams, the following links are a complete str specification and an open source str to avi converter which works like a charm:

[http://jpsxdec.googlecode.com/files/STR ... at0-50.txt](http://jpsxdec.googlecode.com/files/STR_file_format0-50.txt) (PLAYSTATION STR format specification)
[http://jpsxdec.googlecode.com/files/jps ... rev463.zip](http://jpsxdec.googlecode.com/files/jpsxdec_v0-35_rev463.zip) (STR2AVI, Includes source code)

With the use of the tool I had confirmed some little things: the four bytes at offset 12 in the header are, as you said, the frames. Furthermore, sector headers and error correction data is not present in the jams, so it can be an "unformatted" str. You'll just have to deal with the chrominance and a pair of concepts which are covered on the previous .txt.

As you can see it's really difficult to work with video compression, but especially this one based on MPEG-1 (not open source) and adapted to playstation.

I'll try to continue giving some support whenever I have free time, but you have a long path ahead before decoding those files.  

'til next time! hope this can help you!
## Post #14
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-08-03T05:37:43+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Balder: thanks for your help! That info about JAM-STR similarity may be quite useful, at least we know what that thing are. I will keep this topic up to date if some progress will be achieved.

Balder: Sorry for possible inconvenient question. How do you think, may exploration or disassembly of exe file that runs the game/videos help with studying decoder math?
## Post #15
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-08-04T12:52:23+00:00
- Post Title: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Of course yes, other people have done it first... the question is how difficult would that be or if it would be more difficult than figuring out the format. If you have some experience you won't loose antything for giving it a try with IDA-Pro or something like that. Personally that's the last resource for me, mostly when I need to "remake" an algorithm exactly like it was, for example for the generation of a range of "random numbers".

Keep on the project man, I see you're achieving interesting results
## Post #16
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-09-28T09:30:48+00:00
- Post Title: Re: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Trying to "massage" data of that JAM's using the knowledge of STR, noting succesful
but here's a bytemap act14b (first 256000 bytes):
## Post #17
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-10-18T00:28:57+00:00
- Post Title: Re: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

It seems like just noise... but would need to see what should appear to figure if it's some correspondance...

Also if you can provide code it may help.

Just don't give up, I tried to figure a format correctly more than a year, once  


See you
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-18T23:15:51+00:00
- Post Title: Re: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Interesting way of looking at data. But an actual file would be better for us to examine!
## Post #19
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-10-19T07:34:28+00:00
- Post Title: Re: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

Mr.Mouse: thanks, it's actually [http://darkmaster.quakedev.com/work/act14b.zip](http://darkmaster.quakedev.com/work/act14b.zip)

Balder: yeah. Entirely failing to workout this format even with your STR specs, i've decided to borrow other Blood Omen files for a while till i get enough experience 

> Also if you can provide code it may help
Nothing special yet. I'm just pick first 256000 bytes of file and exported them to 320x800 TGA, hoping to see something. There's interesting pattern of repeating "3 black pixels" at first black frames. Nothing really informative, but may help at guessing a compression method.

I've crafted a tool that deals with most blood omen files (tiles and maps are only not discovered yet). When i finish sprites exporting i'l plan to make simple JAM exporting code (bringing what we know about it), surely i'l post sourcecode here.

Thanks for your interest!
## Post #20
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-11-20T05:37:17+00:00
- Post Title: Re: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

That's great. As I recently said on other "not closed topics" over here I'm still alive so will keep an eye on this whenever I can.

I bring good news, though. Recently I've been working on decoding lionheart's frm16 format. At the end I checked that there were two subtypes: frm16 "64" and "68" (named after the internal signatures). The first was a modified BMP so very easy to convert and work with. But the second was a modified jpeg compression to include an alpha channel. 

As jpeg works in YUV space of colour (as .JAM) I might learn something to help you then. (Actually my biggest problem with the format is that I  have no idea how this space of colour works)

As always, keep your project going! I'm also doing a remake of a game (HoMM2) and it's lots of fun  

I'll be pleased to help in whatever I can.
## Post #21
- Username: Slappy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 17, 2012 5:28 pm
- Post datetime: 2022-09-25T16:45:00+00:00
- Post Title: Re: Blood Omen: Legacy Of Kain (PC) .JAM Video Files

> I bring good news, though. Recently I've been working on decoding lionheart's frm16 format. At the end I checked that there were two subtypes: frm16 "64" and "68" (named after the internal signatures). The first was a modified BMP so very easy to convert and work with. But the second was a modified jpeg compression to include an alpha channel.

Can you share the tools for that frm16 files?

Ping from [viewtopic.php?t=26146](https://forum.xentax.com/viewtopic.php?t=26146)
