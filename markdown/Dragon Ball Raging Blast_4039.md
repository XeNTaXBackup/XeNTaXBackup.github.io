## Post #1
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-01-11T22:08:26+00:00
- Post Title: Dragon Ball Raging Blast

Hello All,
Looking for a little bit of help i suck at compression methods, heh.  i am currently only assuming the data is compressed given the information i see in the file, but i could be wrong.  Any help figuring things out would be appreciated.  Also if you know of any good resources or tips on picking out compression methods, that would be useful.

Thanks in advance.

```
{
	uint32 fileTag; // "STPZ"
	uint32 unknown0x04;
	uint32 unknown0x08;
	uint32 unknown0x0C;
};

struct _0DCS_HEADER // appears to be little endian
{
	uint32 fileTag; // "0DCS"
	uint32 uncompressedSize;
	uint32 compressedSize; // size of section? - includes this header
	uint32 unknown0x0C; // maximum uncompressed block size? - have not seen '0LCS' sections bigger than this size, but not sure if this is related
};

struct _0LCS_HEADER // appears to be little endian
{
	uint32 fileTag; // "0LCS"
	uint32 uncompressedSize;
	uint32 compressedSize; // size of section? - includes this header
	uint32 unknown0x0C;
};

```

[extract.rar](https://xentaxbackup.github.io/file/2713_extract.rar)
## Post #2
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2010-12-10T14:22:50+00:00
- Post Title: Dragon Ball Raging Blast

Hmm, sorry for bringing back up an old topic but have you had any luck with this so far? I've been trying at it and had no luck since all the files names are the same within them. But when I look at it in Hex Editor I can see they have other files compressed within there. 

I just can't figure out the main compressed file. Since they have no name to it. Just be labeled like b file or something like that.
## Post #3
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-03-23T03:01:48+00:00
- Post Title: Dragon Ball Raging Blast

Well,...i finally found the initial compression method.  Seems to work so far, through will have to test more and ensure that this is the only method used.  The algorithm is so simple i am somewhat embarrassed it took me so long to find it.  Hopefully everything will pan out and the rest of the internal formats will soon follow.

More information to come soon hopefully.
## Post #4
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2011-03-24T14:14:07+00:00
- Post Title: Dragon Ball Raging Blast

Awesome can't wait to see what will come of this.
## Post #5
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-06-21T09:58:10+00:00
- Post Title: Dragon Ball Raging Blast

Few more tests to run, and a number of bms scripts to write, and hopefully you all should be able to play around with things on your own, heh.
## Post #6
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-06-21T10:07:10+00:00
- Post Title: Dragon Ball Raging Blast

> Reply from revelation
>
> 

Few more tests to run, and a number of bms scripts to write, and hopefully you all should be able to play around with things on your own, heh.

Holy cow,you're doing one hell of a work here
Awesome revelation
You deserve tons of cookie,is it possible for you to create FF7 Dirge of cerberus plugin for noesis
## Post #7
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-06-21T10:39:38+00:00
- Post Title: Dragon Ball Raging Blast

> Reply from jaden
>
> 
Holy cow,you're doing one hell of a work here
Awesome revelation
You deserve tons of cookie,is it possible for you to create FF7 Dirge of cerberus plugin for noesis

Don't know if i still have any files from that game to test with.  i know i posted a start to a template in the thread, and from what i remember the format uses ps2 vif tags which i partially explain in a different thread.  Can't remember how far i got initially, but i guess i can take a look again once i get access to the files again.  Depends on how much effort it would take whether or not i would finish it before any of the other formats i am working on though.  But i do plan to get back to a large number of formats that use the vif tags internally.
## Post #8
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-06-21T13:58:15+00:00
- Post Title: Dragon Ball Raging Blast

> Reply from revelation
>
> jaden wrote:
Holy cow,you're doing one hell of a work here
Awesome revelation
You deserve tons of cookie,is it possible for you to create FF7 Dirge of cerberus plugin for noesis

Don't know if i still have any files from that game to test with.  i know i posted a start to a template in the thread, and from what i remember the format uses ps2 vif tags which i partially explain in a different thread.  Can't remember how far i got initially, but i guess i can take a look again once i get access to the files again.  Depends on how much effort it would take whether or not i would finish it before any of the other formats i am working on though.  But i do plan to get back to a large number of formats that use the vif tags internally.

Woo hoo so there's a chance that you're gonna make the plugin for FF7 Dirge of cerberus
I really hope that you're gonna complete the plugin
Thanks a lot for your reply bro
Keep up your heavenly work revelation
## Post #9
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2011-06-22T04:08:19+00:00
- Post Title: Dragon Ball Raging Blast

Awesome work thus far man, have you tested with both PS3 and 360 or just PS3 files? Either way nice work can't wait to see this done!
## Post #10
- Username: bdzsana
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 30, 2011 5:40 am
- Post datetime: 2011-06-30T19:50:26+00:00
- Post Title: Dragon Ball Raging Blast

Wow very nice. I'm intrested in RB models. How it is going? Will you share us the the scripts here if you are ready?:)
## Post #11
- Username: adampajor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 05, 2011 9:46 pm
- Post datetime: 2011-07-01T09:45:47+00:00
- Post Title: Dragon Ball Raging Blast

Wow! This is awesome! I'm very surprised by this! Keep up the good work!!! Hopefully, we will get a nice importer soon!
## Post #12
- Username: toebi1987
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 30, 2010 3:39 pm
- Post datetime: 2011-08-17T22:37:54+00:00
- Post Title: Dragon Ball Raging Blast

any updates?
## Post #13
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-09-16T13:54:17+00:00
- Post Title: Dragon Ball Raging Blast

Have you completed this plugin revelation ??
If the dragon ball plugin for noesis already in complete condition,would you mind sharing it with us thanks a lot
## Post #14
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-10-23T17:08:09+00:00
- Post Title: Dragon Ball Raging Blast

[viewtopic.php?p=61219#p61219](http://forum.xentax.com/viewtopic.php?p=61219#p61219)
## Post #15
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2011-10-25T12:04:28+00:00
- Post Title: Dragon Ball Raging Blast

I've been trying with these 3 files I have them all in the same directory. Unless I'm supposed to do something completely different with them. I'm not quite sure, I read what you said in there and found the vram and the ioram files for the same spr file.

000_goku_0_1p_X360.vram
000_goku_0_1p_X360.spr
000_goku_0_1p_X360.ioram

These files weren't in and order the were just extracted from the afsd of the directory root to it didn't have no _v _m _i folders that related to those files I believe. I mean yes they are there but how would these files apply to them? like I get folders like effect_blast_chara_000_00_i
effect_blast_chara_000_00_m effect_blast_chara_000_00_v for folders and continues going on like that. 

But when I click on to do the spr file says file could not be previewed, so I know I must be doing something wrong in these steps. Unless the 360 models just do not work.

I suppose I just need more clarification on what to do. But still awesome that you did this.

Edit: Nevermind I found out that its because I had the 360 Version instead of PS3 Version. My bad.
## Post #16
- Username: diegoforfun
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 18, 2011 11:15 pm
- Post datetime: 2011-10-26T14:38:55+00:00
- Post Title: Re: Dragon Ball Raging Blast

@Milesgboy
I got the same result as you when i tried my xbox360 files. WHen one friend sent me the ps3 files, i got everything workin great. I had ripped 12 or 13 models yet i'm plannin' to rip all of them
## Post #17
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2011-10-27T01:43:43+00:00
- Post Title: Re: Dragon Ball Raging Blast

Hey Revelation, you think you could make it support Dragonball Ultimate Tenkaichi? Since I'm assuming since they use afs containers and seem pretty much the same. Just when I try to extract it Noesis crashes. Would be nice to get that supported as well, since it so far supports both Raging Blast games for ps3.

But overall it seems to work fine, just some problem with a vertex on some of the noses not being welded together or something, somethings not connected for some of the human meshes. I'm not sure if its supposed to be like that or not. But its a simple manual fix when you look at it.
## Post #18
- Username: Justdragos
- Rank: advanced
- Number of posts: 69
- Joined date: Tue Feb 21, 2012 3:19 pm
- Post datetime: 2012-04-24T12:58:55+00:00
- Post Title: Re: Dragon Ball Raging Blast

Yeah, it would be great if we could extract the models from ultiamate tenkaichi, when i'm tryingto extract the content from the files .afs noesis crashes..(
## Post #19
- Username: GoTuckyourTelf
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 16, 2012 11:10 pm
- Post datetime: 2012-06-21T22:49:40+00:00
- Post Title: Re: Dragon Ball Raging Blast

hey i tried to preview a map model from "st_pack_battle_map_pt_ps3.afs" (it should contain all 14 scenarios) but i can't see anything in the window... it tells me  "55 textures, 1 meshes, 65 materials" but how can i get to see the model?

thank you in advance
## Post #20
- Username: Justdragos
- Rank: advanced
- Number of posts: 69
- Joined date: Tue Feb 21, 2012 3:19 pm
- Post datetime: 2012-09-17T19:56:55+00:00
- Post Title: Re: Dragon Ball Raging Blast

Does anyone know how to export the animations of the characters, because i want to import the characters in a pc game, and i dont want to have to make all the animations .
## Post #21
- Username: Hjturbo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 08, 2017 8:17 am
- Post datetime: 2017-03-08T00:30:09+00:00
- Post Title: Re: Dragon Ball Raging Blast

i know i'm like so many years behind, but where do i get the copy of raging blast ??
