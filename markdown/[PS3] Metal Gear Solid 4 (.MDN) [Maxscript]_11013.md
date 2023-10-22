## Post #1
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2013-12-01T17:07:45+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

This has been updated to a Noesis plugin;

[viewtopic.php?f=16&t=23455&p=171475&hil ... +4#p171475](https://forum.xentax.com/viewtopic.php?f=16&t=23455&p=171475&hilit=metal+gear+solid+4#p171475)
## Post #2
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2013-12-01T17:22:41+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Thanks alot!
## Post #3
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2013-12-01T17:23:03+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

nice work JayK!

THIS IS THE END!
## Post #4
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2013-12-01T17:25:47+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from ratanegra
>
> nice work JayK!

THIS IS THE END!

Added your xentax name to the post :p
## Post #5
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-12-01T17:29:50+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Very interesting indeed. 
Noob question, how to get the files from the PS3 disc? Do you have to have a jailbreak ps3 ?

edit: I don't own a ps3 anyways  any chance someone can send me any samples by pm? I'd like to add support for python(noesis/blender). Thanks!
## Post #6
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2013-12-01T17:33:50+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from JayK
>
> Added your xentax name to the post :p
all credits for you bro!
## Post #7
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-12-01T17:36:02+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Excellent work JayK really men thank you.
## Post #8
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2013-12-01T17:40:30+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

No problem guys, but I like I said it's incomplete, that manual change to end reading the face buffer at the end, some uvs being messed up, etc, but I won't have much time until Christmas so I thought I might as well just release this version for now, hopefully I can improve it in the future (or someone else can take over now :p )
## Post #9
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-12-02T04:10:56+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Hey JayK iam a bit confused with the texture part i mean i use the arcsys.bms from the link wich unpack the seg files but after that i 
get a file like "00000000000000b6_unpacked.seg"  then what´s the next step?

Any way i wish i could help you with the format but i have not idea or the knowledge for that. =/
## Post #10
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2013-12-02T07:43:21+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Now all you have to do is open that unpacked seg in texturefinder
## Post #11
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-12-02T07:53:40+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

thank you. please continue working on it and toss audio files as well if you can
## Post #12
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2013-12-02T11:06:41+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Once unzipped the "segs" files, must join in numerical order with a hex editor for not lose textures.
Other option is rename and join with filesplitter.

This fact must find the hexadecimal strings and start extraction
1- 0200100000000000
2- 0200300000000000

for the moment only is possible to convert textures with "texture finder"
[](http://imageshack.com/a/img834/5141/g1ih.jpg)
## Post #13
- Username: halflifedave
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 10, 2008 2:05 pm
- Post datetime: 2013-12-04T02:20:11+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

I just ran the mdn bms script on all slot files on the bluray disk and no results were returned. Is there something I need to do to the files before running the bms script?
## Post #14
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-12-04T05:49:06+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from ratanegra
>
> Once unzipped the "segs" files, must join in numerical order with a hex editor for not lose textures.
Other option is rename and join with filesplitter.

This fact must find the hexadecimal strings and start extraction
1- 0200100000000000
2- 0200300000000000

for the moment only is possible to convert textures with "texture finder"

Lol, if you have that single file, just paste a 512x512 pixels DTX1 header in any hex editor and you'll get the correct texture without capturing it with texture finder.
## Post #15
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2013-12-04T07:48:51+00:00
- Post Title: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from halflifedave
>
> I just ran the mdn bms script on all slot files on the bluray disk and no results were returned. Is there something I need to do to the files before running the bms script?

You shouldn't have to do anything to it first, what version of the game do you have? Can you pm me your slot_radio.slot file or whatever its called

Edit: nvm just use Chrrox's script now :p

> Lol, if you have that single file, just paste a 512x512 pixels DTX1 header in any hex editor and you'll get the correct texture without capturing it with texture finder.

Many of them have MIP maps and such
## Post #16
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-12-07T07:17:21+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Incoming prob tonight
## Post #17
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2013-12-07T09:02:07+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from cra0
>
> Incoming prob tonight
nice! 

edit: I offer myself as a beta tester
## Post #18
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-12-09T05:03:03+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from ratanegra
>
> cra0 wrote:Incoming prob tonight
nice! 

edit: I offer myself as a beta tester
No need public beta fast release
[http://dev.cra0kalo.com/?p=40%3Cbr%20/%3E](http://dev.cra0kalo.com/?p=40%3Cbr%20/%3E)
## Post #19
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-12-16T07:17:37+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

any update on this? more breakthroughs?
## Post #20
- Username: Devilot
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-12-16T11:43:31+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

[viewtopic.php?f=10&t=11018](http://forum.xentax.com/viewtopic.php?f=10&t=11018)
## Post #21
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2013-12-16T14:40:13+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from Devilot
>
> any update on this? more breakthroughs?
Well apart from decrypting the mgo2 files no, its not something I'm going to release though.
## Post #22
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-12-16T14:43:07+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

why not?
## Post #23
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2013-12-16T19:33:56+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

It's something for the savemgo project.
## Post #24
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2013-12-21T17:24:52+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Where is the file .seg for extract textures?
## Post #25
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2013-12-21T18:49:37+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from logansan25
>
> Where is the file .seg for extract textures?
in .slot & stages.dat files.
## Post #26
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-12-23T22:42:35+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

anyone had any luck with the sdpack.dat? I believe it holds all of the oneshot sfx.
## Post #27
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2014-01-09T17:12:21+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from JayK
>
> Devilot wrote:any update on this? more breakthroughs?
Well apart from decrypting the mgo2 files no, its not something I'm going to release though.
noooo i want this D:
## Post #28
- Username: Imogene
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 15, 2012 11:43 am
- Post datetime: 2014-01-16T03:07:07+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Does anyone have the Big Mama model?
## Post #29
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2014-01-23T23:51:08+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Out of sheer curiosity, since this works for MGO as well, does anyone know anyone who has the most recent version of MGO on a disc stashed anywhere somewhere? 

I've been trawling the net for a fer hours and sadly it doesn't seem like any of the content servers are still up. considered the game was discontinued, it's not proving easy to find anything.
## Post #30
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-02-02T14:57:51+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Here are some tools I made to get textures which I never really finished, will only work on 64 bit windows as the zlib library i used was 64 bit and I can't be bothered to change that. Drag the file you want to  extract textures from onto the mgs4txndumper.exe  or run it from the command line, and you should get a .txndump output, drag that file on txnextractor.exe and it will output a folder full of txn files, which are just dds files with a 0x20 header before the content. you can open these in texturefinder using a shift of 32 to cut out the header. 

I was making a txn2dds converter but there's just not enough in the header to determine the resolution size, all you can go off of is the size of the file, so I don't feel like continuing on that. 

```
https://dl.dropboxusercontent.com/u/6871888/SavemgoTools/mgs4txndumper.exe
```


```
https://dl.dropboxusercontent.com/u/6871888/SavemgoTools/txnextractor.exe
```
## Post #31
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2014-02-02T23:17:57+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Thanks you very much for that men now that i have a little more time i can rip all the stuff from this game.
## Post #32
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-09-18T18:33:29+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Is there any way to batch convert with TextureFinder (or at least fix that it only exports to BMP whats actually in view, anything off view, not exporter) or the MGS tool?

The game has a lot of texture, and opening almost 40k textures one by one takes one hell of a long time.

I'm so pleased this stuff works so far though, its awesome.
## Post #33
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2014-09-24T08:02:25+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

For data extracted from dat files, all the information necessary to dump things to DDS is available within the TXN and DLD/DLZ files without using Texture Finder.

i have put together a simple console app to dump all the files in a directory.  Should make it a little easier to do some batch conversion.

Assumes directory structure and file names as created by my mgsextract app.  There may still be some forms of the files this does not support.

Quickly done with very little error checking, so be careful.  Will make a more polished version later.

Hope it helps.
[txn_dumper.rar](https://xentaxbackup.github.io/file/7857_txn_dumper.rar)
## Post #34
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2014-09-24T10:37:16+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Updated txn_dumper in previous post.

Here is a slot file extractor based on the mgsextractor release earlier.  Works on a single file at a time currently.

Same caveats apply.
[slot_extract.rar](https://xentaxbackup.github.io/file/7849_slot_extract.rar)
## Post #35
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-09-24T19:38:14+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

This is awesome, though unfortunatly all the textures just look like this for me: 



These are from the .slot files txn/dld etc but I had the same issue when trying it on the stage files.

Tried opening these using various software I own that opens .dds and it doesn't work, any ideas?

I feel like I'm doing something wrong, but outside of the end result, it doesn't look like I am.
## Post #36
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2014-09-24T19:52:21+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Hmm, strange.  can you send me one of your resulting dds files?  Which files were you extracting?

i may have made a slight miscalculation in the DDS header that some tools are more strict about than what i was using to view them.
## Post #37
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-09-24T21:52:23+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from revelation
>
> Hmm, strange.  can you send me one of your resulting dds files?  Which files were you extracting?

i may have made a slight miscalculation in the DDS header that some tools are more strict about than what i was using to view them.

Sure thing, I've picked out several, these are all from various slot files.

[https://www.dropbox.com/sh/azf19y7homu8 ... iT49a?dl=0](https://www.dropbox.com/sh/azf19y7homu8qnj/AABY4IWVJBOJOQpvvwi5iT49a?dl=0)

The tools I'm using to view them are Fcheck (it comes with Maya) and Sage Thumbs (which is what makes the thumbnails, but will also allow me to convert).
Fcheck refuses to even open the files. I'm using the most uptodate version of Photoshop, so there appears to be no DDS plugin for it.

If you let me know what you were using I'll take a crack at viewing them with that.
## Post #38
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2014-09-24T22:11:49+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Well i still have versions of the DirectX SDK installed, so DirectX Texture Tool works for me.

Will see if i can find some things to validate the files on my end for other viewers.


EDIT:  Updated file in original post.  Give it a try and see if it helps.  Strange that so many other programs would be so unforgiving on the format.
## Post #39
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-09-25T14:22:37+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from revelation
>
> Well i still have versions of the DirectX SDK installed, so DirectX Texture Tool works for me.

Will see if i can find some things to validate the files on my end for other viewers.


EDIT:  Updated file in original post.  Give it a try and see if it helps.  Strange that so many other programs would be so unforgiving on the format.

Great the thumbnails show up correctly now thankyou.

Sage thumbs handles them fine, but Mayas fcheck still has issue with them (god damn fcheck, even has issues with some of the DDS files from Rayman honestly, few, but some).

If you're curious to checkout Fcheck, I can upload the .exe file for you. can't 100% say if you'll need other files or not though, as I don't entirely know what it uses, ie: DDL's etc, it just comes in the install base directory of Maya, along with the Maya exe files.

This is going really well. Doing all this just to replace textures in Twin Snakes with textures from MGS4. Now all I need is to figure out the model format from Twin snakes and replacing character textures will also be as easy as environments.
## Post #40
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2014-09-25T23:04:32+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Glad it helped.  i can always try fcheck as well if you like.

Yeah, sorry on the model format front.  i know i promised a release to you a long time ago and never got around to it.  i will see about getting more information on the mesh, texture, and animation formats out.  Need to clean up a few things and adjust for the endianess of TTS i believe.  i will check again and let you know, but i am planning on working on MGS2 - 4 and TTS to complete the work i have done on them so far. i already have a start of the old plugin for noesis, just need to update and finish it (had not gotten to adding textures or animation support in that version yet).

Will see what i can do.
## Post #41
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-09-26T09:51:12+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from revelation
>
> Glad it helped.  i can always try fcheck as well if you like.

Yeah, sorry on the model format front.  i know i promised a release to you a long time ago and never got around to it.  i will see about getting more information on the mesh, texture, and animation formats out.  Need to clean up a few things and adjust for the endianess of TTS i believe.  i will check again and let you know, but i am planning on working on MGS2 - 4 and TTS to complete the work i have done on them so far. i already have a start of the old plugin for noesis, just need to update and finish it (had not gotten to adding textures or animation support in that version yet).

Will see what i can do.

Don't worry about Fcheck, I don't think many people outside me use it, and the current method is fine.
Though what might be easier for many people is noesis support for txn and MDL files. I'm personally quite happy with things as they are now, its only a few steps and isn't really much time or effort to do. Though some people want everything through noesis, because its quicker I guess, so maybe adding noesis support for it might be cool.

I think you might possibly have me confused with someone else i regards to the TTS models, I don't remember ever requesting them, I would like them but I never put in a request if I remember correctly.

I've actually got the source code for an MGS1 (PC) model viewer, and DIR extractor, but I can't compile them without errors, I'm not a c++ coder, I know more C# and Java, so I can't work out most of that anyway. But if you want I can pass you over the source, its not mine, I found it online somewhere a while back, but if you're aiming for full MGS series support, it might help if you ever consider stuff for MGS1PC. I know Solidus converts the Twin Snakes textures, animations aren't all that useful for most people I think, just models and textures (especially stages, stages are always cool). If you end up needing and files you might not have, give me a shout and I'll try to see what I have laying about.

What you've done so far, and how quick it was. For me thats more than enough.

I've a bunch of model formats I've been trying to put into Noesis for a while now and just have no luck, so any breakthrough is a good day for me.
## Post #42
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2014-09-26T15:11:20+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Heh,
Well it was more about MGS format information in general.  i originally asked you about a few things back when Turfster's tools were still being discussed in one of the original MGS2 related threads. (Yeah, it has been that long).

Either way, it turns out i actually had an old version of Maya installed (about as old as the discussions just mentioned, heh) which has fcheck as well.  Strange thing is that fcheck is actually passing on the format handling work to imgcvt.exe in most cases, which so far actually handled conversion of these dds files fine.  But for whatever reason some of them do not make it back through the pipe opened by fcheck in order to display it.  Not sure if it is the same issue in later versions of these tools within Maya.

I did do another update of the file above, but it only sets a particular bit in the dds header differently.

Do not know about "quick", as i have been sitting on some of this stuff (and other format work) for a while now.  Guess it is about time i finally get around to cleaning it up, finishing and releasing some of it.
## Post #43
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-09-26T16:09:42+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from revelation
>
> Heh,
Well it was more about MGS format information in general.  i originally asked you about a few things back when Turfster's tools were still being discussed in one of the original MGS2 related threads. (Yeah, it has been that long).

Either way, it turns out i actually had an old version of Maya installed (about as old as the discussions just mentioned, heh) which has fcheck as well.  Strange thing is that fcheck is actually passing on the format handling work to imgcvt.exe in most cases, which so far actually handled conversion of these dds files fine.  But for whatever reason some of them do not make it back through the pipe opened by fcheck in order to display it.  Not sure if it is the same issue in later versions of these tools within Maya.

I did do another update of the file above, but it only sets a particular bit in the dds header differently.

Do not know about "quick", as i have been sitting on some of this stuff (and other format work) for a while now.  Guess it is about time i finally get around to cleaning it up, finishing and releasing some of it.

Could be the same, so far as I know fcheck itself hasn't ever really had any updates, so its always operated the same way.

Ah you mean back when Turfster was about, yeah that was 7 years ago now, no wonder I don't remember then.

I meant "Quick" as in for the end user, viewing a model with all its textures in noesis is quicker for the end user than extracting and converting stuff. Model wise right now its a gamble, just opening hundreds of .mdl files until you find the model you're after, takes longer to put together, but average Joe won't need more than noesis and the games files to get everything he wants.

If you ever discover you're sitting on FF9's World map format, share it. Thats a file I've been staring at forever.
## Post #44
- Username: GHzGangster
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 15, 2014 1:00 pm
- Post datetime: 2014-09-27T14:18:28+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Have you looked at stage collision data, or anything similar at all, revelation?
Jay and I have been looking into custom stages on MGS4/MGO2–we've been able to do some things like texture modification, object swapping, and .GEOM swapping.

The .GEOMs seem to contain the collision data among other things like spawn points and object coordinates.
I thought they were just composed of mainly verts, but I tried going through what I thought were the verts and looking at them in Blender, but they don't resemble the stage at all. 

I̶ ̶t̶h̶i̶n̶k̶ ̶M̶G̶S̶2̶ ̶(̶P̶C̶)̶ ̶a̶l̶s̶o̶ ̶u̶s̶e̶d̶ ̶t̶h̶e̶ ̶.̶G̶E̶O̶M̶s̶,̶ ̶b̶u̶t̶ ̶i̶t̶'̶s̶ ̶h̶e̶a̶d̶e̶r̶ ̶w̶a̶s̶ ̶a̶ ̶b̶i̶t̶ ̶d̶i̶f̶f̶e̶r̶e̶n̶t̶ ̶f̶r̶o̶m̶ ̶M̶G̶S̶4̶.̶

EDIT: I think I was looking at the scenerio.gcx files from both games, not the geoms.
## Post #45
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2014-10-01T21:02:28+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

i have not looked into the geom data as of yet.  Mainly because i have not finished implementing everything related to mesh, texture, and animation data yet.

The gcx files are related to scripting.  i have not looked into those much either.  i'll see if i can find the method(s) that process geom data in MGS4 if i can.  If you do happen to know of an equivalent format in MGS2, that would be even easier for me to find.
## Post #46
- Username: GHzGangster
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 15, 2014 1:00 pm
- Post datetime: 2014-10-02T22:55:49+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from revelation
>
> i have not looked into the geom data as of yet.  Mainly because i have not finished implementing everything related to mesh, texture, and animation data yet.

The gcx files are related to scripting.  i have not looked into those much either.  i'll see if i can find the method(s) that process geom data in MGS4 if i can.  If you do happen to know of an equivalent format in MGS2, that would be even easier for me to find.
I haven't really messed with MGS2 too much, I really just installed it to see if I could find any similarities. Last thing I was going to do was re-implement the debug printing, but I need to work on MGO instead .

Also, Jay is slowly finding out some of the geom data, I was looking at too much at once I guess.
## Post #47
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-10-07T10:54:19+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Do we happen to know whats in the DEMO.DAT file at all, its 12GB.

Any idea if its simply animation data that references models, or if it contains models and textures too, that're specific to the demoscenes.
## Post #48
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-11-25T12:45:30+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Revelation, in your exploration of Twin Snakes, did you come across a font file at all? Using Dolphin I get all the text dumped out 1 by 1 for every line spoken in cutscene or codec, so I'm assuming that the font file used may just be the font that comes installed on the gamecube itself perhaps?
## Post #49
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2015-07-12T17:55:49+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Hey everyone,
Unfortunately I dont have the disk space to download 25 GB of the game.
Could someone extract Metalgear Rex and Ray for me ?
I am willing to pay for the models with textures.
## Post #50
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-28T01:22:48+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from lionheartuk
>
> I'm personally quite happy with things as they are now, its only a few steps and isn't really much time or effort to do. Though some people want everything through noesis, because its quicker I guess, so maybe adding noesis support for it might be cool.
post some MSG4 PS3 texture samples (.seg/.txn ?) for examination and i will try to make a Noesis python script.
## Post #51
- Username: AaronTheSnob
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 18, 2019 6:59 am
- Post datetime: 2019-07-26T12:19:57+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Okay, so I've been trying to rip Snake's model and animations from the game, and I've been successful for the most part. The only problem I have is the weird skinning weights. Is this normal, or did I do something wrong?

If it makes any difference, the model was ripped in Max 2017 from the European version of the game.



incorrectweights_4.JPG (126.23 KiB) Viewed 252 times
## Post #52
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2020-02-05T21:33:23+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from revelation ↑Wed Sep 24, 2014 4:02 pm at Wed Sep 24, 2014 4:02 pm
>
> 
For data extracted from dat files, all the information necessary to dump things to DDS is available within the TXN and DLD/DLZ files without using Texture Finder.

i have put together a simple console app to dump all the files in a directory.  Should make it a little easier to do some batch conversion.

Assumes directory structure and file names as created by my mgsextract app.  There may still be some forms of the files this does not support.

Quickly done with very little error checking, so be careful.  Will make a more polished version later.

Hope it helps.

I am sorry for asking this so many years later, but the program is not working. It just creates empty folders.
I do not have any way of properly converting TXN files, especially because texture finder does not let me get the alpha channels, so getting help on this would be great.
## Post #53
- Username: Kactusdog
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 03, 2020 4:51 am
- Post datetime: 2020-04-03T18:18:08+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

I am in the same boat! I will give you an update if I find a way. I recommend joining the MGSV modding discord.
## Post #54
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2020-04-05T09:03:19+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

I've attached an updated txnextractor, this is how to use it;

you can use it by doing txnextractor.exe [txnfile] [cache_d.dlz] [cache.dlz]
or if theres just one file that doesnt use mipmaps txnextractor.exe [txnfile] [cache_nodld.dlz]
I'm not sure what tool you're using for getting files out, hopefully revel8ns one's if so you can identify the hashes of the dlz files, although they'll have the dld extension: cache_d = 65B9CC (the biggest, contains the texture at highest mip level) cache = 62196B  smaller of the two, contains all the lower mips. You'll want to run it against both of these
you should get a folder output called TxnExtract which will have a hashed folder name of the txn, then hashed named dds files inside
[txnextractor.rar](https://xentaxbackup.github.io/file/17884_txnextractor.rar)
## Post #55
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2020-06-21T15:41:34+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from JayK ↑Sun Apr 05, 2020 5:03 pm at Sun Apr 05, 2020 5:03 pm
>
> 
I've attached an updated txnextractor, this is how to use it;

you can use it by doing txnextractor.exe [txnfile] [cache_d.dlz] [cache.dlz]
or if theres just one file that doesnt use mipmaps txnextractor.exe [txnfile] [cache_nodld.dlz]
I'm not sure what tool you're using for getting files out, hopefully revel8ns one's if so you can identify the hashes of the dlz files, although they'll have the dld extension: cache_d = 65B9CC (the biggest, contains the texture at highest mip level) cache = 62196B  smaller of the two, contains all the lower mips. You'll want to run it against both of these
you should get a folder output called TxnExtract which will have a hashed folder name of the txn, then hashed named dds files inside

I'm sorry, but how do I use this? What does "doing txnextractor.exe [txnfile] [cache_d.dlz] [cache.dlz]" even mean? Do I have to run it via a bat.file? It keeps telling me it's not a valid application. It doesn't run the same way the txn_dumper did either.

Has anyone made any progress on an actual txn converter instead of all this console dumper nonsense? Sorry if I seem rude, but I am just immensely frustrated with the tools for this game. Nothing ever seems to work for me.
## Post #56
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2020-06-21T21:37:43+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

amazing how a game this old doesnt have proper tools at all yet
## Post #57
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-06-22T00:44:29+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from Rin ↑Mon Jun 22, 2020 5:37 am at Mon Jun 22, 2020 5:37 am
>
> 
amazing how a game this old doesnt have proper tools at all yet

It has texture converters, texture extractors, animation extractor and converters, model and stage extraction, audio extraction and even tools for the videos. What more could you hope for? Thats, everything the game has basically.
## Post #58
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2020-06-22T13:05:27+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from lionheartuk ↑Mon Jun 22, 2020 8:44 am at Mon Jun 22, 2020 8:44 am
>
> 
Rin wrote: ↑Mon Jun 22, 2020 5:37 am
amazing how a game this old doesnt have proper tools at all yet


It has texture converters, texture extractors, animation extractor and converters, model and stage extraction, audio extraction and even tools for the videos. What more could you hope for? Thats, everything the game has basically.

Texture converters that do not work, model extractors that give broken rigging with no texture assignment and more. If you happen to have miraculously working tools that I am somehow not aware of, please do tell us, because all the tools in this thread seem to just be the same ones from years ago.
## Post #59
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2020-06-22T13:21:38+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from Portugalotaku ↑Mon Jun 22, 2020 9:05 pm at Mon Jun 22, 2020 9:05 pm
>
> 
lionheartuk wrote: ↑Mon Jun 22, 2020 8:44 am
Rin wrote: ↑Mon Jun 22, 2020 5:37 am
amazing how a game this old doesnt have proper tools at all yet


It has texture converters, texture extractors, animation extractor and converters, model and stage extraction, audio extraction and even tools for the videos. What more could you hope for? Thats, everything the game has basically.


Texture converters that do not work, model extractors that give broken rigging with no texture assignment and more. If you happen to have miraculously working tools that I am somehow not aware of, please do tell us, because all the tools in this thread seem to just be the same ones from years ago.

They are the same ones from years ago, I've used them a number of times, they all work.
Unless model extracting and texture extracting use the same tool, you'd expect them to not line up, its then upto the person doing the ripping to assign the textures in a 3D software of their choice.

The texture rippers work perfectly fine, I haven't used them for a long time but I know they work because I, to this day, have a number of MGS4 textures and the only texture tools are from this exact thread.

The tools are 'particular', as in, they take an exact format, and for textures I believe you need to extract a file, then convert whats extracted, then finally you get your textures, but it requires multiple steps, and yes it is a little painful I'll admit. you could try checking out the trikzme youtube channel that has a bit more information about various MGS game hacking tools, and how to use them etc.
## Post #60
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2020-06-22T13:38:56+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from lionheartuk ↑Mon Jun 22, 2020 9:21 pm at Mon Jun 22, 2020 9:21 pm
>
> 
Portugalotaku wrote: ↑Mon Jun 22, 2020 9:05 pm
lionheartuk wrote: ↑Mon Jun 22, 2020 8:44 am


It has texture converters, texture extractors, animation extractor and converters, model and stage extraction, audio extraction and even tools for the videos. What more could you hope for? Thats, everything the game has basically.


Texture converters that do not work, model extractors that give broken rigging with no texture assignment and more. If you happen to have miraculously working tools that I am somehow not aware of, please do tell us, because all the tools in this thread seem to just be the same ones from years ago.


They are the same ones from years ago, I've used them a number of times, they all work.
Unless model extracting and texture extracting use the same tool, you'd expect them to not line up, its then upto the person doing the ripping to assign the textures in a 3D software of their choice.

The texture rippers work perfectly fine, I haven't used them for a long time but I know they work because I, to this day, have a number of MGS4 textures and the only texture tools are from this exact thread.

The tools are 'particular', as in, they take an exact format, and for textures I believe you need to extract a file, then convert whats extracted, then finally you get your textures, but it requires multiple steps, and yes it is a little painful I'll admit. you could try checking out the trikzme youtube channel that has a bit more information about various MGS game hacking tools, and how to use them etc.

Models coming with unassigned textures would not be a problem if texture names were not hashes and required you to check thousands of files to find the one that matches the UV's. In that scenario, it's ridiculous to not have assigned textures. 
Plus, rigging is still broken.

None of the texture converters ever worked for me. All txn_dumper does is produce empty folders and txn_extractor does nothing at all. It's not helped by the fact that the instructions are immensely vague. Again, I'm sorry if I come out as rude, I am just incredibly frustrated with the tools for this game. Like Rin said, the game does not have any proper tools, only rather basic and unintuitive ones.
## Post #61
- Username: cobaltbluebengal
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 04, 2016 12:15 am
- Post datetime: 2020-06-24T11:20:55+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

Super cheeky, but could someone extract Raiden from MGS4? Sepcifically the injured one and the one in the epilogue with his son. love the series (I have no idea how to rip a PS3 disc - nor have a bluray drive) but would love to do a fan art render of him in Blender and haven't seen the models available on the likes of DeviantArt or anything
## Post #62
- Username: AEDude
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 26, 2021 3:31 am
- Post datetime: 2021-04-29T19:12:49+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

I have managed to rip most of the main characters. I have also located the Haven Troopers, PMC soldiers, some vehicles including the huge war ships, some weapons including all the BB specialized weapons and the rail gun from REX.

I'm working on Raiden soon and I think I'll be finished after he is ripped!

There is just one problem, I don't know hoe to access any of the textures! All the models are UV unwrapped, I just need the texture files  If anyone knows how to code please PM me so we can work on a script (edit it to locate and pair the textures with the mesh files while extracting).

I already have the script to extract meshes.
## Post #63
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-04-29T19:19:38+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

This is outdated. It's better to use the Noesis Plugin ([viewtopic.php?f=16&t=23455&p=171475&hil ... +4#p171475](https://forum.xentax.com/viewtopic.php?f=16&t=23455&p=171475&hilit=metal+gear+solid+4#p171475)) which will automatically apply textures for you.
## Post #64
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2021-04-30T14:11:11+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from JayK ↑Fri Apr 30, 2021 3:19 am at Fri Apr 30, 2021 3:19 am
>
> 
This is outdated. It's better to use the Noesis Plugin (viewtopic.php?f=16&t=23455&p=171475&hil ... +4#p171475) which will automatically apply textures for you.

Holy moly, this is quite something.
## Post #65
- Username: cobaltbluebengal
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 04, 2016 12:15 am
- Post datetime: 2021-07-26T13:55:35+00:00
- Post Title: Re: [PS3] Metal Gear Solid 4 (.MDN) [Maxscript]

> Reply from AEDude ↑Fri Apr 30, 2021 3:12 am at Fri Apr 30, 2021 3:12 am
>
> 
I have managed to rip most of the main characters. I have also located the Haven Troopers, PMC soldiers, some vehicles including the huge war ships, some weapons including all the BB specialized weapons and the rail gun from REX.

I'm working on Raiden soon and I think I'll be finished after he is ripped!

There is just one problem, I don't know hoe to access any of the textures! All the models are UV unwrapped, I just need the texture files  If anyone knows how to code please PM me so we can work on a script (edit it to locate and pair the textures with the mesh files while extracting).

I already have the script to extract meshes.

Will you release the models you have managed to export?
