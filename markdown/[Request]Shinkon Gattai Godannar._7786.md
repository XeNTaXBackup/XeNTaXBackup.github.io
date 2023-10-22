## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-12-01T05:16:27+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

Hello all,
I have a some LWCV files. 
[viewtopic.php?f=10&t=5682](http://forum.xentax.com/viewtopic.php?f=10&t=5682)
Unpacked from eeMemory.bin file.
I used Hex Editor to extract the LWCV files.
*.lcv              unidentified
*.tm2             texture
*.unidentified   ?
Can anyone help me to convert this format ?
Here are samples.

Thanks.
## Post #2
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-19T06:30:15+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

Come on, no one has interest in the lcv files?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T06:34:26+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

PS2 formats tend to be really ugly so I ignore them most of the time.
Well, pretty much all the time.

Will need better techniques to figure those out.
## Post #4
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-19T07:04:25+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

Maybe, lcv file has several part.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T07:05:12+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

Not only that, it also looks ugly.
You're probably better off looking at PS3/360 games.

It's pretty clear that out of all of the formats that have been reversed, most of them tend to be PC games or PS3/360.

The other ones are like...just takes a whole lot of work.
## Post #6
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-19T10:38:02+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

The game developer is "Natsume"
lcv 3d Model, tm2 texture. 
The same format is used in the Battle Assault 3 featuring Gundam Seed.
I'm sorry I couldn't help.
## Post #7
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-19T15:51:27+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

Deleted the article.
## Post #8
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-19T21:29:29+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

Hey, I have some information and data that might be useful for extracting model data from this game.
First of all, it would be possible to extract the models directly from the file structure, without ripping them from save states. The file structure is as such:
AFS.LST
DATA.AFS
SADX.AFS
SLPS_203.80
BOOT.PAC
IOPRP280.IMG
SFD.AFS
SYSTEM

The DATA.AFS compressed file contains the models and textures, and opening it should be relatively easy, considering .AFS is a very common compressed file type. 

The TIM2 textures have already been cracked, and are viewable, as seen in another of the threads about this game. 

The model files will be the only real problem, but that is where hex editor and PCSX2 save states come in. 
After several hours of epic gameplay, I have unlocked most of the mechs from the game using PCSX2. I then took a save state of the two mechs I want the models of, Volspina and Core Gunner. Volspina is such an awesome design for a mech, I have obsessed over having a textured model of it in my 3ds Max viewport ever since I learned this game existed. The save state is here:

```
http://www.mediafire.com/?bmaa6z2etwr0q96
```


I don't know how to extract the files from the save state, but apparently a lot of other people on this forum do, so here it is. The version of PCSX2 is 9.8.
## Post #9
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-20T05:05:08+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

> Reply from kingfisher13
>
> state is here:
Code: Select allhttp://www.mediafire.com/?bmaa6z2etwr0q96
I don't know how to extract the files from the save state, but apparently a lot of other people on this forum do, so here it is. The version of PCSX2 is 9.8.

Model and texture are kept inside a eeMemory.bin of the SLPS-20380 (927D3EB4).00.p2s.
extract data is here
## Post #10
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-20T15:39:42+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

Thanks, I looked at the files- the textures, like I thought, are easily extracted and viewed. I sent the models to our mutual helper, who will look into cracking the format. If we could get some other people to look at the format, that would be good. Alon, could you get some more people on this project? I don't really know anybody here, but maybe you could get some people in on this.
## Post #11
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-20T21:22:26+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

Allright, my associate from the PS2 model ripping website has made some progress with the model files... here it is:
"The vertexes appear after the following header:
01 01 00 01 00 80 ?? 78
Where ?? is the number of vertexes
the vertexes are in implicit tristrips where
you connect the first vertex to the second to the third.
Then the second to the third to the fourth.
The third to the fourth to the fifth ect.
Some culling will still need to be done.
As for UV coords or Normal Mappings I am not sure."

So as you can see, it is quite possible to reverse-engineer these formats. I bet we will have this model format figured out by the end of the month, if not sooner.
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-20T21:33:31+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

its the same thing as xenosaga just look at that example.
## Post #13
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2012-02-20T23:21:54+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

This format actually doesn't look all that difficult.

LWCV contains offset to DTHD section.

DTHD contains offsets to the RTDT and TXDT sections.

RTDT contains offsets to the BNDT sections.

BNDT contain bone information and offsets to the LYDT sections.

LYDT possibly bounding box data? and contains offsets to the SFDT sections.

SFDT contains offsets to the SDMA and DRAW sections.

SDMA and DRAW both use ps2 VIF tags to store the information (as do most later release ps2 games, for optimization purposes)

Offsets are relative to the sections they are contained within.

Haven't looked any deeper than the above quick glance at the format, so there may still be some hidden quirks.



As far as ps2 formats go, this is by no means ugly (at least initially).  Especially since it not further compressed or bit packed like some are.  Early generation ps2 formats before more developers were knowledgeable of the benefits of VIF tags, used a lot more tricks to make things smaller and more compact.

i have tried to explain the ps2 VIF tags, but in most cases it might be too much of a hassle to deal with for non-programmers, and so they are usually just brute-forced through as in kingfisher13's description above.  Once you understand how the tags are usually unpacked into even more understandable structured layouts, they become easier to deal with.
## Post #14
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-21T01:00:40+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

NICE. Thanks, Revelation. Although, that wasn't me who found out the stuff I listed, it was an associate. I have no knowledge of hex editor or programming at all. XD My experience is with model design, animation, and rendering.
Revelation, if you could keep searching the format, that would be awesome. I bet we could make a simple converter plugin or something within the month, considering what you said about the format. Chrrox, whassup, dude? It would be awesome if you would also join us in the project, since you know the format, maybe you could get started on a conversion program, possibly to a format which supports bone structure, such as FBX or Collada (I'm pretty sure they do anyway)?
## Post #15
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-21T07:24:16+00:00
- Post Title: [Request]Shinkon Gattai Godannar.

Other than that, same model format as their other two games. 
Battle Assault 3 featuring Gundam Seed
DICE DNA Integrated Cybernetic Enterprises
Natsume's other games also use the same format.
## Post #16
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-21T09:08:29+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Ok, i will upload some samples soon of this game.
I would be very grateful for your interest and support.
## Post #17
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-21T10:20:50+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Deleted the article.
## Post #18
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-21T15:06:16+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Nice, looks like we got a bunch of people interested. I wouldn't bring up different games, though... We should focus on Godannar, and its specific format, just in case there are some slight differences in coding.
## Post #19
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-02-22T08:17:23+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

> Reply from kingfisher13
>
> Nice, looks like we got a bunch of people interested. I wouldn't bring up different games, though... We should focus on Godannar, and its specific format, just in case there are some slight differences in coding.
To make my intentions clear, i deleted the article.
We should focus on Godannar, too
## Post #20
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-23T14:57:17+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

wait, that's it?

No more progress? I thought this was working out... sorry, but this isn't going to end this way. I will have those models, textured and in a usable format, even if I have to find someone else to help me with it.
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-23T17:32:12+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

I wouldn't mind looking at PS2 formats if the only special thing to know about are those VIF tags. Like, a spec on what the common commands mean and how they should be dealt with.

Or better yet, a library that already handles all of those tags so I can just call them if I run into one...
## Post #22
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-23T22:17:01+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Hmm.... I'm not the one to come up with such a thing, but we have (at least, had) a bunch of prime programmers working on this. Maybe they could come up with what you need.
## Post #23
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-24T09:54:52+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

The way I see it, this post is not so attractive by others.
Good luck.
## Post #24
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-24T15:14:24+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

What do you mean, not so attractive by others? The format isn't difficult, as was stated earlier. It simply requires a little effort... It seems like whenever I contribute to a thread, everybody disappears. It's almost like cyber-bullying... Just because some of us don't have the programming experience that is favored on this forum, that doesn't mean our projects are worthless.
## Post #25
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-24T15:21:20+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

just post lots of tit pics from the game and you'll get finale00's reinterest in no time .
## Post #26
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-24T15:22:56+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Oh, I'm sorry. I didn't mean to.
You don't need to care about it  
Maybe the communication didn't go well because my English is not that good.
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-24T15:50:24+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

> Reply from kingfisher13
>
> What do you mean, not so attractive by others? The format isn't difficult, as was stated earlier. It simply requires a little effort...

Ya, it isn't difficult...from someone who's spent much time looking at PS2 stuff.
I didn't even know about VIF tags until someone mentioned it.

If there were better tools and more info it'd probably be better.

If the people that have worked on it can provide info for VIF tags that would be great.

> It seems like whenever I contribute to a thread, everybody disappears. It's almost like cyber-bullying... Just because some of us don't have the programming experience that is favored on this forum, that doesn't mean our projects are worthless.

Lol what.

I don't think there was much interest from the start. Of course, if you know people that can do this stuff I guess you can just ask them.

On the other hand, programming is also not difficult; it just requires a little effort.
 If you can communicate with humans you are likely able to communicate with a computer, who will listen to you word-for-word like a total slave.
## Post #28
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2012-02-24T23:40:31+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

i explain a bit about how the VIF tags are parsed here:
[viewtopic.php?p=52244#p52244](http://forum.xentax.com/viewtopic.php?p=52244#p52244)
More information can be found in the ps2 sdk documentation as well.  i can try and explain more of what i understand of them though.

This is a decent site to see some information on a number of ps2 formats that use the VIF tags, or at least see the names of some of the games.  Most of the ones on that site use them.
[http://ps23dformat.wikispaces.com/](http://ps23dformat.wikispaces.com/)

i have been planning on turning my parsing code into a set of re-useable functionality, but there is some cleanup and other tasks i need to do to make it more useful for general use.

i am not opposed to helping with the format, i am simply fairly backlogged on my format work at the moment and would really like to get caught up.  i am involved in the Force Unleashed, Resident Evil 4, Resident Evil 5/Devil May Cry 4, RAGE Engine (Red Dead Redemption, GTA4, etc.), Dragonball Raging Blast, Street Fighter 4, Metal Gear Solid 2 - 4, Zone of the Enders, CryENGINE, Forza, Marvel vs Capcom 3, Assassin's Creed, Prince of Persia, Final Fantasy 13, God of War, Kingdom Hearts, Ninja Gaiden, Super Smash Brothers, and Metroid Prime format research, among others, as well as i don't even remember how many additional formats i have said i would help with outside the forums that i still have to get back to.  And i still don't think that covers all the formats i would like to get started with that i have already put off.  So i try to make time for them eventually.  As i reach a new roadblock in one format i get back to another with a fresh set of eyes and can usually make more progress.
## Post #29
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T00:20:27+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Is there like specific things to look out for that would indicate that a tag is coming up.
Or do those tags just randomly appear whenever the devs felt like using it?

Like

```
   dword
   dword
   dword
   dword VIF tag
   ...
}

```
## Post #30
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2012-02-25T04:04:36+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Unfortunately the VIF blocks are completely specific to packaging up data/commands to the ps2 and have no relation to the data structures the developer may have chosen.  So you still have to decipher the base format to determine where the counts, offsets and sizes of the blocks may be.  Another thing to be aware of is that things are often processed and unpacked from this data in 16-byte aligned blocks.  As such a lot of the sizes and addresses used are usually specified in quad word count (qwc) form, which is simply the actual size divided by 16.  There are a number of commands that can be specified by the structures from setting up how values are masked, what to unpack, where to unpack, and when to actually execute the commands associated with the buffer.

```
		{
		case 0x00: // NOP
			vifStart += 4;
			break;
		case 0x01: // STCYCL
			cl = vifTag->stcycl.cl;
			wl = vifTag->stcycl.wl;
			vifStart += 4;
			break;
		case 0x02: // OFFSET
			vif1_ofst = (vifTag->commnd.imm & 0x3FF);
			vifStart += 4;
			break;
		case 0x03: // BASE
			vif1_base = (vifTag->commnd.imm & 0x3FF);
			vifStart += 4;
			break;
		case 0x04: // ITOP
			vif0_itop = (vifTag->commnd.imm & 0x3FF);
			vifStart += 4;
			break;
		case 0x05: // STMOD
			vif0_mode = (vifTag->commnd.imm & 0x3FF);
			vifStart += 4;
			break;
		case 0x06: // MSKPATH3
			vifStart += 4;
			break;
		case 0x07: // MARK
			vifStart += 4;
			break;
		case 0x10: // FLUSHE
			vifStart += 4;
			break;
		case 0x11: // FLUSH
			vifStart += 4;
			break;
		case 0x13: // FLUSHA
			vifStart += 4;
			break;
		case 0x14: // MSCAL
			vifStart += 4;
			break;
		case 0x15: // MSCALF
			vifStart += 4;
			break;
		case 0x17: // MSCNT
			vifStart += 4;
			break;
		case 0x20: // STMASK
			vif0_mask = *((uint32*)(vifStart + 4));
			vifStart += 8;
			break;
		case 0x30: // STROW
			vif0_r[0] = *((uint32*)(vifStart + 0x04));
			vif0_r[1] = *((uint32*)(vifStart + 0x08));
			vif0_r[2] = *((uint32*)(vifStart + 0x0C));
			vif0_r[3] = *((uint32*)(vifStart + 0x10));
			vifStart += 0x14;
			break;
		case 0x31: // STCOL
			vif0_c[0] = *((uint32*)(vifStart + 0x04));
			vif0_c[1] = *((uint32*)(vifStart + 0x08));
			vif0_c[2] = *((uint32*)(vifStart + 0x0C));
			vif0_c[3] = *((uint32*)(vifStart + 0x10));
			vifStart += 0x14;
			break;
		case 0x4A: // MPG
			vifStart += ((((vifTag->commnd.num) ? (vifTag->commnd.num) : (256)) << 1) + 1) << 4;
			break;
		case 0x50: // DIRECT
			vifStart += ((((vifTag->commnd.imm) ? (vifTag->commnd.imm) : (65536)) << 2) + 1) << 4;
			break;
		case 0x51: // DIRECTHL
			vifStart += ((((vifTag->commnd.imm) ? (vifTag->commnd.imm) : (65536)) << 2) + 1) << 4;
			break;
		default: // UNPACK
			// ...
			break;
		}


```


If you are using the hex editor 010 Editor, the structure i pasted in the link of the previous message is the one i use.  And can be compared against the parsing above to get an idea of how some of this relates.

The UNPACK command is the one most are interested in usually, as a lot of formats never set the cycle or masking to anything other than the defaults.  But for a complete parser you have to take those into account as well.  [viewtopic.php?p=52244#p52244](http://forum.xentax.com/viewtopic.php?p=52244#p52244) is a partial explanation of the UNPACK functionality.

* i'll see if i can add more details.  Questions will help direct my focus...and if there is any clarification of anything stated so far?
## Post #31
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-02-25T20:13:07+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Sweet, thanks for the work, dudes. I could post a few screenshots of the mechs I want, just to attract some more programmers XD
[Capture_069.jpg](https://xentaxbackup.github.io/file/5107_Capture_069.jpg)
## Post #32
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-19T12:19:27+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Any update? any  reply?
I simply does not relinquish this post.
## Post #33
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-03-20T15:13:27+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Is that it?

Dudes, this project was coming along so well, lets not stop now!

C'mon, programmers, lets crack this format!
## Post #34
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-20T16:01:54+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Lol really, I don't think we actually did anything.
## Post #35
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-20T22:16:03+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

I think I'm probably in a similar boat to revelation on this, I don't think my VIFcode interpreter is complete or tested enough to expose through the Noesis API, cause I haven't tested it a lot and my existing use of it has involved some per-game hacks in the actual interpreter code. I've recently come across another game that needs to use it though, so maybe by the end of that I'll have it to a state where I feel it's solid enough, at least in the way it passes data back to the user, to finally expose it to the plugin API.

And as far as looking at this game personally, again same boat as revelation, way too much crap on my plate/todo list already.
## Post #36
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2012-03-22T15:18:56+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Well, whenever you have the time, we would love to have you guys work on this again. These models are too awesome to just let go, wouldn't you agree?
## Post #37
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2021-01-19T14:59:03+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Long time no see.

Using Ninja Ripper, files were obtained via pcsx2, but flat files were obtained.
Texture files are normal



tex_0379_0out.png (54.86 KiB) Viewed 122 times
## Post #38
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-02-13T15:55:54+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Hello.

i made adaptaion in LZS.

this tool will decompress your files.

just drag your lzs file in the exe or put arguments program.exe infile outfile
[](https://ibb.co/379G0Kt)
## Post #39
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-14T09:31:06+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

> Reply from Rabatini ↑Sun Feb 13, 2022 11:55 pm at Sun Feb 13, 2022 11:55 pm
>
> 
Hello.

i made adaptaion in LZS.Hello. Thanks.
I'd prefer bms scripts for decompression. So any chance you tell us which adaption you made?
## Post #40
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-02-21T19:32:21+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Hello.
I don´t think aluigi has implanted this LZ VARIANT in his program.

Here the decompress and compress tul.

commando
Shinkon Gattai Godannar.

```
to decompress
program -c file.lzs -noinfo 
To compress
```

To capitain tsubasa ps2
Battle Assault 3 featuring Gundam Seed
DICE - DNA Integrated Cybernetic Enterprises


```
to decompress
program.exe -c file.lzs 
To compress
```

[LZS_PS2.zip](https://xentaxbackup.github.io/file/21837_LZS_PS2.zip)
## Post #41
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-21T20:09:03+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

Thanks, but that's the exe only. Doesn't help too much.

But I understand that other than Aluigi you don't want to share your results.
## Post #42
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2022-03-28T02:03:17+00:00
- Post Title: Re: [Request]Shinkon Gattai Godannar.

how to convert lcv to obj?


 ch02_00.7z
(67.43 KiB) Downloaded 16 times
