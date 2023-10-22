## Post #1
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-13T01:53:51+00:00
- Post Title: Spider-Man 3 PC

Hey guys! 

I know there's basically a code for every Spider-man game to date, but I tried giving this one a run using the PCPACK quickbms script and it wasn't coming back with any results. Any chance anyone might be able to take a look at this *.pcpack file and help me get inside? Trying to get my hands on Sand Man and a few other "game exclusives" from in there!

Here's the sample: [https://mega.nz/#!rRAWHJQZ!JrSEP_DTxhCd ... I3pmVqex60](https://mega.nz/#!rRAWHJQZ!JrSEP_DTxhCdiEp597_kJUGvo2OIzqST3I3pmVqex60)

and here's a link to the older quickbms script that deals with pcpacks, but doesn't seem to work with these ones (I assume because they're older): [http://aluigi.altervista.org/bms/spider ... ck_nch.bms](http://aluigi.altervista.org/bms/spiderman_pcpack_nch.bms)

Thanks in advance, guys!
## Post #2
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-03-13T05:28:04+00:00
- Post Title: Spider-Man 3 PC

there is no compression in the file that you uploaded, is just a package of files, even all 3d models can be extracted with hex2obj
## Post #3
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-13T06:43:06+00:00
- Post Title: Spider-Man 3 PC

Looks like I'd better learn Hex2Obj! Thanks for the heads up, my friend!
## Post #4
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-03-13T07:30:12+00:00
- Post Title: Spider-Man 3 PC

I hope someone can help you with this because the package contains lot of assets, is tedious search a specific model
## Post #5
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-13T09:26:34+00:00
- Post Title: Spider-Man 3 PC

its very hard to make a model importer with only one sample.
its a lot easier with several samples of different sizes.
type 36 is models

quickbms script

```
for i = 0 < 152
get hash long
get type long
get offset long
get size long
string NAME p= "%08x" hash
string EXT p= "%02x" type
string NAME += "."
string NAME += EXT
#print "%name%" 
log name offset size
next i

```
## Post #6
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-13T12:54:31+00:00
- Post Title: Spider-Man 3 PC

Hey Chrrox! Thanks for the heads up and for taking a look!
I've got a few more samples for you if you want to take a look:

STORY_MOVIE_4.PCPACK [https://mega.nz/#!bNo0AJAJ!krrflTp5F7MJ ... h9gPjYSpnw](https://mega.nz/#!bNo0AJAJ!krrflTp5F7MJg-Jur-I--aRkQueXVJiz5h9gPjYSpnw)
STORY_MOVIE_4_CUTSCENE5.PCPACK [https://mega.nz/#!bRQHFIiI!URycmQRNU7XR ... qka1VSPg-g](https://mega.nz/#!bRQHFIiI!URycmQRNU7XRhh8UFmRUoS1ydhdLRYN6bqka1VSPg-g)
STORY_MOVIE_1.PCPAChttps [http://mega.nz/#!fQIAHQyB!Qdpnp5E0DMiyK ... SKr5y98uw0](http://mega.nz/#!fQIAHQyB!Qdpnp5E0DMiyKjtSCAYjyeYYlnszFB4eWSKr5y98uw0)
STORY_KINGPIN_1.PCPACK [https://mega.nz/#!aYQ3wbYY!q-hVL5QUDpSr ... IEZTbTH5sw](https://mega.nz/#!aYQ3wbYY!q-hVL5QUDpSr9fBKfpzjYUZq1etY06fTlIEZTbTH5sw)
STORY_MAD_BOMBER_5_JONAH.PCPACK [https://mega.nz/#!vBYDxKoA!k755Y_Wg-3zg ... A-IEafBj0Q](https://mega.nz/#!vBYDxKoA!k755Y_Wg-3zgqxXHvEWPKN6tdzYHklN_bA-IEafBj0Q)
STORY_MAD_BOMBER_5_FLINTTHUG.PCPACK [https://mega.nz/#!3VBlCYzL!fwJxOzSnWlFR ... RSsgxmM0tg](https://mega.nz/#!3VBlCYzL!fwJxOzSnWlFR04gFQ1o-0AcuZ1u2jX4pDRSsgxmM0tg)
CITY_FLINT_THUG.PCPACK [https://mega.nz/#!nJ4h3bTL!e7qOqU3sjJy- ... 4YWbXYNe4o](https://mega.nz/#!nJ4h3bTL!e7qOqU3sjJy--ESsJ6_nTxRrZopqy4jUX4YWbXYNe4o)
CH_PETER.PCPACK [https://mega.nz/#!2dhRTKoZ!IzFsUGX7YLsu ... Qek277_GQU](https://mega.nz/#!2dhRTKoZ!IzFsUGX7YLsuHTcWPDFz9WA08bqd7hotxQek277_GQU)
Q03.PCPACK [https://mega.nz/#!mNxHWDSS!qufQBhhj1tgW ... AUqNT5Fwbg](https://mega.nz/#!mNxHWDSS!qufQBhhj1tgWgw6-lyyYwtYAIJmP-oxV9AUqNT5Fwbg)
## Post #7
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-25T19:45:23+00:00
- Post Title: Spider-Man 3 PC

.36 file contains textures too,not only a models.
I was able to view some texs by using TextureFinder
[http://i.imgur.com/ZUClS3M.jpg](http://i.imgur.com/ZUClS3M.jpg)
If this a possible to make a model importer here are more samples:
[https://mega.nz/#!6wYg0BLC!OvgLUSnrHBpy ... 3wZigDwQTs](https://mega.nz/#!6wYg0BLC!OvgLUSnrHBpyDDloBoYXNx4OtedRprPy63wZigDwQTs)
P.S  All samples from "packs" folder are almost 5gb,so i gathered most interesting files,i hope they will be enough
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-25T21:54:27+00:00
- Post Title: Spider-Man 3 PC

CFman-da16a75a_36.JPG (74.45 KiB) Viewed 956 times
## Post #9
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-26T03:32:29+00:00
- Post Title: Spider-Man 3 PC

If anyone needs or wants any other kinds of files from the game, just let me know and I can add them to the post.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-26T06:59:51+00:00
- Post Title: Spider-Man 3 PC

CA5_Heli-63757bC7_36.JPG (85.33 KiB) Viewed 934 times
## Post #11
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-26T08:58:37+00:00
- Post Title: Spider-Man 3 PC

Looks cool,what about textures? how we can extract them properly?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-26T09:22:20+00:00
- Post Title: Spider-Man 3 PC

HeliTex.JPG (102.21 KiB) Viewed 928 times

just learn the simplest things of cutting bytes from a file and maybe giving them a header...
## Post #13
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-26T09:37:37+00:00
- Post Title: Spider-Man 3 PC

2hard4me,is there any quickbms script which adds dds header? because i'm really noob at this stuff..
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-26T11:16:50+00:00
- Post Title: Spider-Man 3 PC

why not use forum's search?
[viewtopic.php?f=10&t=13040](http://forum.xentax.com/viewtopic.php?f=10&t=13040)

(It's NOT the solution but should give you an idea.)

edit: here's a test DDS for the Heli (you'll need DXTbmp to view it, see my next post)


 Heli_test.zip
(174.41 KiB) Downloaded 29 times
## Post #15
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-26T13:23:27+00:00
- Post Title: Spider-Man 3 PC

i googled "dds header adder" and tried this script
[viewtopic.php?f=18&t=9141&start=0](http://forum.xentax.com/viewtopic.php?f=18&t=9141&start=0)
it doesn't work..it's just adds DDS header,image are still unviewable through XnView or Photoshop (with dds plugin)

But thanks anyways
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-26T17:44:39+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from chrrox
>
> quickbms script
slight modification so it doesn't error on other samples  

```
get FILES long
xmath TABLELEN "FILES * 16"
findloc A1A1A1A1 binary "\xA1\xA1\xA1\xA1"
goto A1A1A1A1
xmath STARTTABLE "A1A1A1A1 - TABLELEN"
goto STARTTABLE
for i = 0 < FILES
	get hash long
	get type long
	get OFFSET long
	get SIZE long
	string NAME p= "%08x" hash
	string EXT p= "%02x" type
	string NAME + "."
	string NAME + EXT
	log NAME OFFSET SIZE
next i
```


*.36 looks like another archive
## Post #17
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-26T17:56:03+00:00
- Post Title: Re: Spider-Man 3 PC

Tried your modified script,it doesn't work with CH_PETER.PCPACK
[http://oi65.tinypic.com/2upqzih.jpg](http://oi65.tinypic.com/2upqzih.jpg)
[https://mega.nz/#!XsRnmKAC!457fy1I-hkPj ... BfeTCA9Rwg](https://mega.nz/#!XsRnmKAC!457fy1I-hkPj9UhE-XnSLPkHa8S3rWt4EBfeTCA9Rwg)
P.S Any chance what you will make Noesis script?
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-26T18:31:58+00:00
- Post Title: Re: Spider-Man 3 PC

okay i updated the script to try and get around the difference   
[viewtopic.php?p=129063#p129063](http://forum.xentax.com/viewtopic.php?p=129063#p129063)
## Post #19
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-26T19:34:37+00:00
- Post Title: Re: Spider-Man 3 PC

Thanks,now most of samples can be extracted successfully.
What about Noesis script to view models or textures? is this a possible?
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-26T19:44:02+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Rutabaga
>
> it doesn't work..it's just adds DDS header,image are still unviewable through XnView or Photoshop (with dds plugin)

But thanks anywaysdon't worry (and don't give up too soon  ):

It's a little bit hard sometimes, you may need DXTbmp.exe to view DDS files with faked headers.

I've added a Heli_test.dds with the zip file in my previous post; you may fiddle around with it.



DXTbmp-Heli-dds.JPG (71.95 KiB) Viewed 426 times



(Maybe you're better off to create a screenshot to bmp in TextureFinder using the "camera button" and convert it to whatever format you want.)

btw, I had a look at the uv map of the heli in blender and it looks very horrible (much worse than that from the hex2obj screenshot); someone has to care for it first.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-26T20:50:26+00:00
- Post Title: Re: Spider-Man 3 PC

had to put a threshold into the uv pos routine to get better results; still very ugly:



Heli-blender.JPG (169.65 KiB) Viewed 422 times

(since I'm not too familiar with textures, mipmaps, etc)
## Post #22
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-27T08:20:43+00:00
- Post Title: Re: Spider-Man 3 PC

Looks very exciting,can you try to extract New goblin model or black suit spidey model?
they are stored in CH_PLAYERGOBLIN.PCPACK and CH_BLACKSUIT.PCPACK files.
Thanks.
P.S Samples (just in case) : [https://mega.nz/#!Wo4i3Y6L!Gyb46_bkH9_i ... OL5wGYIwk4](https://mega.nz/#!Wo4i3Y6L!Gyb46_bkH9_iO1bEdrrW5eDqU2ivQ0EIOOL5wGYIwk4)
## Post #23
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-27T10:26:39+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Rutabaga
>
> Looks very exciting,can you try to extract New goblin model or black suit spidey model?
they are stored in CH_PLAYERGOBLIN.PCPACK and CH_BLACKSUIT.PCPACK files.
Thanks.
P.S Samples (just in case) : https://mega.nz/#!Wo4i3Y6L!Gyb46_bkH9_i ... OL5wGYIwk4

Might be worth waiting rather than asking just for specific models. I know others would like them and it seems like these guys are on to something good, so maybe wait and see what they come up with first.
## Post #24
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-27T10:45:54+00:00
- Post Title: Re: Spider-Man 3 PC

Ok,i'll wait,sorry for the rush
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-27T13:04:38+00:00
- Post Title: Re: Spider-Man 3 PC

Generally I show how it works for one submesh of one model then leave the rest to the customers.
(In this case I might add it to my MakeObj project. Without getting the textures automatically.)



ParaMedic.JPG (140.66 KiB) Viewed 378 times



For coders only:
[viewtopic.php?f=29&t=15955](http://forum.xentax.com/viewtopic.php?f=29&t=15955)
## Post #26
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-27T13:43:36+00:00
- Post Title: Re: Spider-Man 3 PC

MakeObj? what is this?  i used search but i found nothing,only a few mentions
## Post #27
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2017-03-29T10:02:19+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from chrrox
>
> its very hard to make a model importer with only one sample.
its a lot easier with several samples of different sizes.
type 36 is models

quickbms script
Code: Select allgoto 0x394
for i = 0 < 152
get hash long
get type long
get offset long
get size long
string NAME p= "%08x" hash
string EXT p= "%02x" type
string NAME += "."
string NAME += EXT
#print "%name%" 
log name offset size
next i

made a video transcoding this into noesis via python

[https://youtu.be/iTXgRMZR1sY](https://youtu.be/iTXgRMZR1sY)
## Post #28
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-03-29T19:11:25+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from mariokart64n
>
> chrrox wrote:its very hard to make a model importer with only one sample.
its a lot easier with several samples of different sizes.
type 36 is models

quickbms script
Code: Select allgoto 0x394
for i = 0 < 152
get hash long
get type long
get offset long
get size long
string NAME p= "%08x" hash
string EXT p= "%02x" type
string NAME += "."
string NAME += EXT
#print "%name%" 
log name offset size
next i


made a video transcoding this into noesis via python

https://youtu.be/iTXgRMZR1sY
Starting from 1:40 i've heard some mentions about Modding toolset,so is this possible? and we well finally get first moddable Spider-Man game?   
Anyways you did a nice job,but i'm afraid i can't re-write this script as you shown on video,can you leave a link to a complete script,please?
Thanks.
P.S Excuse me if i heard something wrong,because my english isn't very good
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-30T00:36:07+00:00
- Post Title: Re: Spider-Man 3 PC

he was just demonstrating how to make an extraction script in python for Noesis,
extraction is already taken care of here with a modified bms script though   
[viewtopic.php?p=129063#p129063](http://forum.xentax.com/viewtopic.php?p=129063#p129063)

the python script in mario's video is also reading the wrong integer for the file count   

here is my version of that same python script except with additional instruction to simulate the modified bms script  


 extract_Spiderman3_PCPACK.zip
(667 Bytes) Downloaded 157 times
## Post #30
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-30T06:04:37+00:00
- Post Title: Re: Spider-Man 3 PC

Given we have most of the data there, is there any chance we can expect to see some kind of model/rigging/textures script for noesis? Or anything for that matter?
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-30T12:14:21+00:00
- Post Title: Re: Spider-Man 3 PC

I can't show something for Noesis, but the playerGoblin:



playerGoblin.JPG (141.03 KiB) Viewed 456 times
## Post #32
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-30T13:18:47+00:00
- Post Title: Re: Spider-Man 3 PC

Oh nice! Is it possible to get the rigging out too?
## Post #33
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-30T13:38:15+00:00
- Post Title: Re: Spider-Man 3 PC

offtopic:
the only model I'm interesting in is a model of Stan Lee:


but it's in amazing sm2.
## Post #34
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-30T14:04:27+00:00
- Post Title: Re: Spider-Man 3 PC

I have Amazing Spider-Man 2. More than happy to dig out the files for you.
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-30T15:18:29+00:00
- Post Title: Re: Spider-Man 3 PC

blacksuit, after some manual erasing:
[blacksuit.JPG](https://xentaxbackup.github.io/file/12722_blacksuit.JPG)
## Post #36
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-30T15:23:52+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from trexjones
>
> I have Amazing Spider-Man 2. More than happy to dig out the files for you.would be awesome  or they will be boneless? cause' I can rip them by myself though I want them with weights and stuff
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-04T14:50:03+00:00
- Post Title: Re: Spider-Man 3 PC

ok i'm researching this. 

.36 files have a bit spiderish structure. Nothing too complex though. Expect the model/texture conversion tools soon.
## Post #38
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-04T16:01:24+00:00
- Post Title: Re: Spider-Man 3 PC

Sounds awesome,can't wait!   
Will you also make bone extractor or animation tool? or you didn't check that?
## Post #39
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-04T16:40:39+00:00
- Post Title: Re: Spider-Man 3 PC

I don't know. They have 2 skeletons for each model: skeleton and animation skeleton. That happens sometimes. Face animations are made with morphs. No facial bones and there are .MORH files for each character.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-04T20:03:01+00:00
- Post Title: Re: Spider-Man 3 PC

work in progress
## Post #41
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-04T21:27:06+00:00
- Post Title: Re: Spider-Man 3 PC

since daemon1 is likely going to make a complete tool i will just share the work in progress
bms script i have so far for texture data extraction so it doesn't completely go to waste.   
this bms script extracts the texture data with names and adds headers.


 SpiderMan3_PC_36_ddsExtract.zip
(1.14 KiB) Downloaded 185 times
## Post #42
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-04-05T05:31:40+00:00
- Post Title: Re: Spider-Man 3 PC

You guys are amazing! Thank you so much for looking into these...!
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-05T05:44:00+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from AceWell
>
> okay since daemon1 is likely going to make a complete tool i will go ahead and share the work in progress

i see you used a few workarounds to get the data: searching for 4-letter IDs and hashes instead of reading the data from where they must be.

But I also needed skeletons and mesh descriptions, so I parsed the whole data structure properly.
## Post #44
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-05T06:58:57+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from daemon1
>
> I parsed the whole data structure properly.
i hope so, you are a programmer and i am not!
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-05T07:15:37+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from AceWell
>
> daemon1 wrote:I parsed the whole data structure properly.
i hope so, you are a programmer and i am not!

Yes you are. You've written a bms script, and its also a program.
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-05T11:32:07+00:00
- Post Title: Re: Spider-Man 3 PC

Alright, skeleton is working. Just need a little more testing and its all done.
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-06T08:10:22+00:00
- Post Title: Re: Spider-Man 3 PC

Tool requires only 1 parameter: name of .36 file.

It will extract all resources from there, converting static and skeletal models to SMD, textures to DDS or TGA (for paletted textures which are usually diffuse/spec maps)

You need to rotate model 180deg and bones will not have correct angles, I may correct that later. There are no face bones, facial animations are done with morphs.
## Post #48
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-06T08:53:23+00:00
- Post Title: Re: Spider-Man 3 PC

Awesome,thanks you!
But i have a problem..after drag and dropping .36 file to your programm exe i got a some .smd,mat and .anim files,how i can open them?
if i remember correctly smd is valve format,but what about .anim and etc.?

P.S Also,you mentioned paletted textures,are this texture paletted?
[http://i.imgur.com/MHt3kZz.png](http://i.imgur.com/MHt3kZz.png)
If yes,how i can edit this texture to give it normal look?
## Post #49
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-06T09:39:10+00:00
- Post Title: Re: Spider-Man 3 PC

.anim is game format, you can't open them. I extract them so maybe someone will like to research them.

I'm only converting models and textures, all other files are just game files.

That texture is combined specular and other masks. Spec is blue channel i think.
## Post #50
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-06T10:12:19+00:00
- Post Title: Re: Spider-Man 3 PC

Ok,thanks.
I tried to import smd to 3ds max using smd plugin,this is what i got:
[http://i.imgur.com/NcYrcGp.png](http://i.imgur.com/NcYrcGp.png)
also i tried to use milkshape but it have no Fbx output..
any suggestions?
## Post #51
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-06T10:33:30+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Rutabaga
>
> Ok,thanks.
I tried to import smd to 3ds max using smd plugin,this is what i got:
http://i.imgur.com/NcYrcGp.png
also i tried to use milkshape but it have no Fbx output..
any suggestions?

no, i dont have 3dmax. Ask people who used that plugin. Also try converting it with noesis to other format.
## Post #52
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-06T11:00:41+00:00
- Post Title: Re: Spider-Man 3 PC

Oh,i almost forgot about Noesis..
Thank you,now everything works perfect!

Edit: After exporting model using Noesis and importing it to 3ds max,i assigned all materials,and rendered..
rendered model looks strange..normals problem?
[http://i.imgur.com/w4TcWnr.png](http://i.imgur.com/w4TcWnr.png)
## Post #53
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-04-06T12:35:24+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Rutabaga
>
> Oh,i almost forgot about Noesis..
Thank you,now everything works perfect!

Edit: After exporting model using Noesis and importing it to 3ds max,i assigned all materials,and rendered..
rendered model looks strange..normals problem?
http://i.imgur.com/w4TcWnr.pngthe polygons of this model probably inverted so you have to invert them back.
## Post #54
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-06T17:52:39+00:00
- Post Title: Re: Spider-Man 3 PC

Thanks now everything looks better
[http://i.imgur.com/8LxugSg.png](http://i.imgur.com/8LxugSg.png)
Btw,i can't find Peter's Jacket diffuse map,what i should to do? this jacket (upper body) have only bump,ao and spec maps..
[http://i.imgur.com/zzzhxpa.png](http://i.imgur.com/zzzhxpa.png)
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-06T18:42:26+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Rutabaga
>
> Thanks now everything looks better
http://i.imgur.com/8LxugSg.png
Btw,i can't find Peter's Jacket diffuse map,what i should to do? this jacket (upper body) have only bump,ao and spec maps..
http://i.imgur.com/zzzhxpa.png

peter's costume has no diffuse map. Its made with solid colors. Can't you see it by looking at his model?
## Post #56
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-07T10:35:49+00:00
- Post Title: Re: Spider-Man 3 PC

Ok,tnx.
Today i tried to extract a few models from BROCK_BEATDOWN.PCPACK file.I imported smd models into 3ds max and applied materials but can't find Jameson eye diffuse map,what i'm doing wrong?
[http://i.imgur.com/scFMFJR.png](http://i.imgur.com/scFMFJR.png)
[http://i.imgur.com/sRdVRvk.png](http://i.imgur.com/sRdVRvk.png)
## Post #57
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-04-07T10:52:30+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Rutabaga
>
> Ok,tnx.
Today i tried to extract a few models from BROCK_BEATDOWN.PCPACK file.I imported smd models into 3ds max and applied materials but can't find Jameson eye diffuse map,what i'm doing wrong?
http://i.imgur.com/scFMFJR.png
http://i.imgur.com/sRdVRvk.pngseems like characters sharing eye texture. try to look at another archive. sometimes archive with chared textures are called 'common', 'cmn' or just 'shared'.

p.s.: btw daemon is not the person you should addressed that kind of questions to, so don't wait his response on this — he's doing the format reversing and leaves resource researching on users shoulders
## Post #58
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-07T13:37:22+00:00
- Post Title: Re: Spider-Man 3 PC

Ok,thanks.
Now i extracted every .36 file from pcpack files (397 files in total) how i can drag and drop them into Apkf tool executable? when i drag and drop 10-20 files (for example) the tool extracts only 1 file.
Does tool have batch support or something like this? if yes,what i need to write in command line?

Thanks in advance.
## Post #59
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2017-04-07T15:50:46+00:00
- Post Title: Re: Spider-Man 3 PC

it is possible to rip buildings/city models too?
## Post #60
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-07T16:02:46+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Rutabaga
>
> Does tool have batch support or something like this? if yes,what i need to write in command line?you could try out this

```
for %%f in (*.36) do Spiderman3_APKF.exe %%f
```
in a test.cmd file.

Use it in a folder where Spiderman3_APKF.exe and some *.36 files reside.

But start with two *.36 only; if there's more than 2 *.36 files in the folder: have fun with sorting all the produced files.
## Post #61
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-07T18:09:33+00:00
- Post Title: Re: Spider-Man 3 PC

Thanks,now i have almost every mesh and texture from this game
But some textures looks strange
[http://i.imgur.com/urwCTLC.png](http://i.imgur.com/urwCTLC.png)
and tool crashes on some big files like ee185533.36 for example
btw here all 397 .36 files,just in case if id-daemon can take a look and fix crashes/textures.
[https://mega.nz/#!H450GaRS!VovkvYGAUxsk ... WGMmWxiPoE](https://mega.nz/#!H450GaRS!VovkvYGAUxskgS3SvfhZU1QkHb8-ihJ4bWGMmWxiPoE)

Thanks.
## Post #62
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-29T15:11:58+00:00
- Post Title: Re: Spider-Man 3 PC

Checking this now. Candy was crashing because she had 3 different color diffuse images instead of 1. Some models have up to 8 variants of diffuse (generic human faces for ex). Big file issues are also fixed.



Tool updated. 

Tool requires only 1 parameter: name of .36 file.

It will extract all resources from there, converting static and skeletal models to SMD, textures to DDS or TGA (for paletted textures which are usually diffuse/spec maps)

There are no face bones, facial animations are done with morphs.
[Spiderman3_APKF.rar](https://xentaxbackup.github.io/file/12871_Spiderman3_APKF.rar)
## Post #63
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-04-29T17:32:51+00:00
- Post Title: Re: Spider-Man 3 PC

Thanks a lot,now everything works a way better,and i managed to extract contents of big 36 file (ee185533) with no problems.
Thanks you so much!
Edit: Some textures are black
[http://i.imgur.com/it2OLz7.png](http://i.imgur.com/it2OLz7.png)
but i'm glad what you fixed crashing
## Post #64
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-29T18:08:18+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Rutabaga
>
> Thanks a lot,now everything works a way better,and i managed to extract contents of big 36 file (ee185533) with no problems.
Thanks you so much!
Edit: Some textures are black
http://i.imgur.com/it2OLz7.png
but i'm glad what you fixed crashing

yes they are black, because there's no information in those slots. There's no way to tell this other than export them. The number of variants must be power of 2. Like 4, 8 or 16. Some of them are used, some not.
## Post #65
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-09T07:46:39+00:00
- Post Title: Re: Spider-Man 3 PC

Another little update, model rotated 180deg, now it corresponds to the skeleton. Still I don't know the reason why some meshes are scaled 50%, hope its not a big trouble.
## Post #66
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-05-12T12:04:52+00:00
- Post Title: Re: Spider-Man 3 PC

Looks like tool is now complete and have no problems.
If you will have some free time,i'll would like to see tool for Web of Shadows and if this will be a possible of course.
Samples: [https://mega.nz/#!bgQHXAoR!nDHkeK3of8Eb ... n4cm7jKA84](https://mega.nz/#!bgQHXAoR!nDHkeK3of8EbpdLkpDPi7EAphEm-98yFgn4cm7jKA84)
Thanks in advance!
## Post #67
- Username: Big4Rig
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 12, 2015 5:51 am
- Post datetime: 2017-07-22T22:41:12+00:00
- Post Title: Re: Spider-Man 3 PC

In relation to the Web of Shadows PCPACK format, it seems that after using the quickbms uncompressor script here: [http://aluigi.altervista.org/bms/spider ... ck_nch.bms](http://aluigi.altervista.org/bms/spiderman_pcpack_nch.bms)

The uncompressed pcpack file becomes similar to the Spider-Man 3 format (They run off the same engine, so no surprise there). However, there are slight differences in the format, and I can't seem to get any of the other scripts to work on it. I included examples of a default compressed PCPACK and that same PCPACK decompressed.

[http://puu.sh/wQuVm.zip](http://puu.sh/wQuVm.zip)

(edit): It should also be noted that the uncompressed PCPACKS contain the same APKF model format
## Post #68
- Username: Big4Rig
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 12, 2015 5:51 am
- Post datetime: 2017-08-26T02:12:09+00:00
- Post Title: Re: Spider-Man 3 PC

The Spiderman3_APKF script functions on the Web Of Shadows extracted .36 files, but the issue is that the meshes are flattened into their UV coordinates (but the actual UV coordinates themselves are a flat line, almost as if thee UV's and triangles are getting swapped on conversion). Bones extract fine, and oddly enough vertex groups are still properly in tact as well. 

example of rvb_pedfemale005.smd [http://puu.sh/xjFSM.png](http://puu.sh/xjFSM.png)
example of rvb_pedfemale023.smd [http://puu.sh/xjFYK.png](http://puu.sh/xjFYK.png)
here is the .36 file in question (from ACT1.PCPACK) [http://puu.sh/xjFVn.36](http://puu.sh/xjFVn.36)
## Post #69
- Username: MrPool
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 22, 2017 8:03 am
- Post datetime: 2017-09-10T20:00:35+00:00
- Post Title: Re: Spider-Man 3 PC

After dragging the .36 files to the "Spiderman3_APKF" tool there is no file left
Do you know what the mistake might be?
## Post #70
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-10-01T04:58:48+00:00
- Post Title: Re: Spider-Man 3 PC

Is there any way to mod .36 files?
I would like to change main character (spider-man) mesh into venom (just for example) mesh,and pack it back into .PCPACK format ,is this a possible?

Thanks,i hope you understand me.
## Post #71
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-01T07:02:40+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from MrPool
>
> After dragging the .36 files to the "Spiderman3_APKF" tool there is no file left
Do you know what the mistake might be?
many of daemon1's tools write extracted files out to C:\Documents and Settings\Acewell folder on my computer 
regardless of where the source file or exe is. maybe check a similar location on yours for the extracted files?
## Post #72
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-01T07:40:41+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from AceWell
>
> many of daemon1's tools write extracted files out to C:\Documents and Settings\Acewell folder on my computer regardless of where the source file or exe is.

This is probably because you have UAC on, and Windows redirects output to your user's folder, because it has no write access to the folder where the source file or exe is.
## Post #73
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-01T08:15:45+00:00
- Post Title: Re: Spider-Man 3 PC

no UAC here on XP as far as i know
## Post #74
- Username: Valamis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 25, 2018 7:18 am
- Post datetime: 2018-10-24T23:47:18+00:00
- Post Title: Re: Spider-Man 3 PC

Hi.
May anyone share some Spider-man 3 the game extracted files? For me it is too complicated to use this tool. I don't understand that and where is the ReadMe file for how to use? I would be grateful for any models but the most I need New Goblin model with his flying board/glider, Venom and maybe construction-site-building from grand finale (last mission where you fight Venom and Sandman, I would need that part of building when you fight with Venom). Thanks in advance. I am going to import and rig these models in Daz Studio  

1. I tried to use Spiderman3_APKF but it tells program stopped working, help. I use Windows 8.1
## Post #75
- Username: LordKiriYT
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Oct 28, 2018 2:55 am
- Post datetime: 2018-10-31T15:12:11+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Valamis
>
> Hi.
May anyone share some Spider-man 3 the game extracted files? For me it is too complicated to use this tool. I don't understand that and where is the ReadMe file for how to use? I would be grateful for any models but the most I need New Goblin model with his flying board/glider, Venom and maybe construction-site-building from grand finale (last mission where you fight Venom and Sandman, I would need that part of building when you fight with Venom). Thanks in advance. I am going to import and rig these models in Daz Studio  

1. I tried to use Spiderman3_APKF but it tells program stopped working, help. I use Windows 8.1

drag and drop the .36 file to the tool
## Post #76
- Username: Valamis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 25, 2018 7:18 am
- Post datetime: 2018-10-31T15:36:00+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from LordKiriYT
>
> Valamis wrote:Hi.
May anyone share some Spider-man 3 the game extracted files? For me it is too complicated to use this tool. I don't understand that and where is the ReadMe file for how to use? I would be grateful for any models but the most I need New Goblin model with his flying board/glider, Venom and maybe construction-site-building from grand finale (last mission where you fight Venom and Sandman, I would need that part of building when you fight with Venom). Thanks in advance. I am going to import and rig these models in Daz Studio  

1. I tried to use Spiderman3_APKF but it tells program stopped working, help. I use Windows 8.1

drag and drop the .36 file to the tool

Thanks. That worked. It extracted files to the same folder where the file was. I am afraid there are too many 36 files and files inside them for me to find New Goblin player and Venom models and textures  

1. Ok I found venom but he has bugged texture: ch_venom_ppp.tex_0 ( it is called indexed color probably)
2. New Goblin is in c44dbd9b.36. Textures are also weird and don't work as they should. It is like multiple textures are merged into 1 TGA. I can't figure out how to separate them. How do you apply them as I saw in one of previous pictures when one of you managed to texture New Goblin model?
## Post #77
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2019-11-20T21:11:49+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Valamis ↑Wed Oct 31, 2018 11:36 pm at Wed Oct 31, 2018 11:36 pm
>
> 
LordKiriYT wrote:Valamis wrote:Hi.
May anyone share some Spider-man 3 the game extracted files? For me it is too complicated to use this tool. I don't understand that and where is the ReadMe file for how to use? I would be grateful for any models but the most I need New Goblin model with his flying board/glider, Venom and maybe construction-site-building from grand finale (last mission where you fight Venom and Sandman, I would need that part of building when you fight with Venom). Thanks in advance. I am going to import and rig these models in Daz Studio  

1. I tried to use Spiderman3_APKF but it tells program stopped working, help. I use Windows 8.1

drag and drop the .36 file to the tool

Thanks. That worked. It extracted files to the same folder where the file was. I am afraid there are too many 36 files and files inside them for me to find New Goblin player and Venom models and textures  

1. Ok I found venom but he has bugged texture: ch_venom_ppp.tex_0 ( it is called indexed color probably)
2. New Goblin is in c44dbd9b.36. Textures are also weird and don't work as they should. It is like multiple textures are merged into 1 TGA. I can't figure out how to separate them. How do you apply them as I saw in one of previous pictures when one of you managed to texture New Goblin model?

it can be fixed in photoshop
## Post #78
- Username: jamesmiller57
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 7:50 am
- Post datetime: 2020-07-15T00:05:16+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Rutabaga ↑Sun Mar 26, 2017 3:45 am at Sun Mar 26, 2017 3:45 am
>
> 
.36 file contains textures too,not only a models.
I was able to view some texs by using TextureFinder
http://i.imgur.com/ZUClS3M.jpg
If this a possible to make a model importer here are more samples:
https://mega.nz/#!6wYg0BLC!OvgLUSnrHBpy ... 3wZigDwQTs
P.S  All samples from "packs" folder are almost 5gb,so i gathered most interesting files,i hope they will be enough
hey can you tell me how you converted the 36 files into fbx ot obj or how did you view them pls tell me
## Post #79
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2020-07-15T00:59:00+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from jamesmiller57 ↑Wed Jul 15, 2020 8:05 am at Wed Jul 15, 2020 8:05 am
>
> 
Rutabaga wrote: ↑Sun Mar 26, 2017 3:45 am
.36 file contains textures too,not only a models.
I was able to view some texs by using TextureFinder
http://i.imgur.com/ZUClS3M.jpg
If this a possible to make a model importer here are more samples:
https://mega.nz/#!6wYg0BLC!OvgLUSnrHBpy ... 3wZigDwQTs
P.S  All samples from "packs" folder are almost 5gb,so i gathered most interesting files,i hope they will be enough

hey can you tell me how you converted the 36 files into fbx ot obj or how did you view them pls tell me

read through the thread. Everything is there
## Post #80
- Username: jamesmiller57
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 7:50 am
- Post datetime: 2020-07-15T19:05:43+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from daemon1 ↑Thu Apr 06, 2017 4:10 pm at Thu Apr 06, 2017 4:10 pm
>
> 
Tool requires only 1 parameter: name of .36 file.

It will extract all resources from there, converting static and skeletal models to SMD, textures to DDS or TGA (for paletted textures which are usually diffuse/spec maps)

You need to rotate model 180deg and bones will not have correct angles, I may correct that later. There are no face bones, facial animations are done with morphs.
can you please also give me the exe program pls respond
## Post #81
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-07-16T04:32:34+00:00
- Post Title: Re: Spider-Man 3 PC

its attached on a next page
## Post #82
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-08-24T02:57:45+00:00
- Post Title: Re: Spider-Man 3 PC

Has anyone here looked into animation conversion for this game?
## Post #83
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-10-31T23:37:53+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from TrumpetPro ↑Mon Aug 24, 2020 10:57 am at Mon Aug 24, 2020 10:57 am
>
> 
Has anyone here looked into animation conversion for this game?

Bump
## Post #84
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2021-01-14T14:14:12+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from Acewell ↑Thu Mar 30, 2017 8:36 am at Thu Mar 30, 2017 8:36 am
>
> 
he was just demonstrating how to make an extraction script in python for Noesis,
extraction is already taken care of here with a modified bms script though   
http://forum.xentax.com/viewtopic.php?p=129063#p129063

the python script in mario's video is also reading the wrong integer for the file count   

here is my version of that same python script except with additional instruction to simulate the modified bms script  
extract_Spiderman3_PCPACK.zip

Awesome! But I got some problems. When I tried to extract some *PCPACK files, got a mistake


it happens also when I am trying to extract *XEPACK files (the same files but from xbox 360 game directory) 

Here is some samples of PCPACK and XEPACK files:

[https://mega.nz/file/IIEWiBDY#HDyQyQuiz ... 7xPWPpDGeE](https://mega.nz/file/IIEWiBDY#HDyQyQuizZZnT8nCzUQuyh1J9aabmXZBB7xPWPpDGeE)

How can I solve it?
## Post #85
- Username: Mato32DX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 16, 2021 11:57 pm
- Post datetime: 2021-02-17T03:53:52+00:00
- Post Title: Re: Spider-Man 3 PC

Has anyone managed to get deeper into the .PCPACK files? like, being able to export all of the content from those files aside from meshes and .dds textures? Just curious, I want to know if the format can be further modified.
## Post #86
- Username: swordclash117
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 12, 2022 2:13 am
- Post datetime: 2022-08-12T02:21:43+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from shakotay2 ↑Sat Apr 08, 2017 12:02 am at Sat Apr 08, 2017 12:02 am
>
> 
Rutabaga wrote:Does tool have batch support or something like this? if yes,what i need to write in command line?you could try out this
Code: Select all@echo off
for %%f in (*.36) do Spiderman3_APKF.exe %%fin a test.cmd file.

Use it in a folder where Spiderman3_APKF.exe and some *.36 files reside.

But start with two *.36 only; if there's more than 2 *.36 files in the folder: have fun with sorting all the produced files.

I tried doing this but it launches the Spiderman3_APKF exe but just goes in an endless loop, and it doesn't extract any files
## Post #87
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-12T07:41:35+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from swordclash117 ↑Fri Aug 12, 2022 10:21 am at Fri Aug 12, 2022 10:21 am
>
> I tried doing this but it launches the Spiderman3_APKF exe but just goes in an endless loop, and it doesn't extract any filesI had only a few samples, so what do you expect?

"Generally I show how it works for one submesh of one model then leave the rest to the customers."

> Reply from shakotay2 ↑Mon Mar 27, 2017 9:04 pm at Mon Mar 27, 2017 9:04 pm
>
> 

Feel free to improve the code (5 years old):

> Reply from shakotay2 ↑Mon Mar 27, 2017 10:40 pm at Mon Mar 27, 2017 10:40 pm
>
>
## Post #88
- Username: GTHughes2004
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 08, 2021 9:52 am
- Post datetime: 2022-08-13T20:21:46+00:00
- Post Title: Re: Spider-Man 3 PC

Is there any way to reinject extracted contents of the .36 files after modifying (specifically upscaling) them? I've managed to extract a butt ton of them, but cant seem to figure out for the life of me how to reload the .tga and .dds files. The .smd and .mat don't concern me, as I didn't need to change them. Any help would be greatly appreciated.
## Post #89
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-08-16T13:41:48+00:00
- Post Title: Re: Spider-Man 3 PC

> Reply from GTHughes2004 ↑Sun Aug 14, 2022 4:21 am at Sun Aug 14, 2022 4:21 am
>
> 
Is there any way to reinject extracted contents of the .36 files after modifying (specifically upscaling) them?
Theres no way currently, because it would require making another, usually more complex tool
## Post #90
- Username: GTHughes2004
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 08, 2021 9:52 am
- Post datetime: 2022-08-16T17:16:28+00:00
- Post Title: Re: Spider-Man 3 PC

daemon1,
If it is impossible, then I understand. If it isn't, I also understand that you are a busy person, and that asking you to make this aforementioned "more complex tool" would be rather unfair. As such, I appreciate your help. If you think of any possible method in the future, I would be forever greatful if you were to fill us in. Thanks.
## Post #91
- Username: GTHughes2004
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 08, 2021 9:52 am
- Post datetime: 2022-08-29T19:23:42+00:00
- Post Title: Re: Spider-Man 3 PC

Although, how might I get started on making my own rebuilder. Couldn't the offset hex data of the files be modified to allow larger files to be reimported with ease? Well, not with ease, but it'd be possible, wouldn't it? The problem is, how do you find the offset of each texture within the hex data of the .36 file. Once you add the required space, you'd probably have to edit the hex offset of the .PCPACK to accommodate the now larger .36 file. Am I thinking about this right? If so, how do I find these hex values?
## Post #92
- Username: JasonVoorhees
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 14, 2022 5:17 am
- Post datetime: 2022-11-14T19:59:58+00:00
- Post Title: Re: Spider-Man 3 PC

That Would be a pretty interesting theory. I'm Trying To Mod That Videogame Too ;D. I'm Sure That Those Files From which we can extract with the tools would be scattered Everywhere In The .36 File. In Addition, It Is Also Tried To Put The Modified .36 File Inside The .PCPACK File Of The Spider -Man Or The Peter Parker. And From There It Should Found ;D
## Post #93
- Username: JasonVoorhees
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 14, 2022 5:17 am
- Post datetime: 2022-11-14T20:41:27+00:00
- Post Title: Re: Spider-Man 3 PC

I'm Going Through The 2 Different Files. And It Looks Like The .PCPACK Has A .36 Or APKF Container Hidden Inside It


I'm  Going Through The 2 Different Files. And It Looks Like The .PCPACK Has A .36 Or APKF Container Hidden Inside It Muestra 1.jpg (183.82 KiB) Viewed 156 times
## Post #94
- Username: JasonVoorhees
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 14, 2022 5:17 am
- Post datetime: 2022-11-14T20:44:49+00:00
- Post Title: Re: Spider-Man 3 PC

These 2 APKF Headers Are the Same


These 2 Files Have The Same Codes Muestra 2.jpg (183.4 KiB) Viewed 155 times
## Post #95
- Username: JasonVoorhees
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 14, 2022 5:17 am
- Post datetime: 2022-11-14T22:51:12+00:00
- Post Title: Re: Spider-Man 3 PC

The Only Problem I See Is That The Format Of The Mesh Of The 3D Model With This One Are Very Different. I Have No Idea How Someone Converted These Files Into An .SMD From The Source Engine
## Post #96
- Username: JasonVoorhees
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Nov 14, 2022 5:17 am
- Post datetime: 2022-11-15T21:12:46+00:00
- Post Title: Re: Spider-Man 3 PC

Here I Don't Know How I Did It, But Somewhere In The File I Changed The Code, Then I Entered The Videogame And This Happened To Me. A Few Pieces Of The Leg Of The Character Has Been Moved Towards The Straight. This Was A Miracle. I Don't Know How Or Where I Put The Code But It Was A Miracle


I Have Moved Some Pieces Of The Vertices Of The Leg Of The 3D Model In The Videogame Spider-Man 3 Modified Vertices Test.jpg (154.56 KiB) Viewed 143 times
## Post #97
- Username: SpiderGlider
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 04, 2022 12:35 am
- Post datetime: 2022-12-04T13:34:36+00:00
- Post Title: Re: Spider-Man 3 PC

Surely you'd be able to use some hexadecimal diff tool with the original file to see where you changed the code?
