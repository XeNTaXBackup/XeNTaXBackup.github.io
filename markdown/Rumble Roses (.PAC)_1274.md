## Post #1
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-05-25T06:35:07+00:00
- Post Title: Rumble Roses (.PAC)

Here are a few .PAC files from the Rumble Roses games I would like to extract from them in hopes that there will be some way to mod the game.

[http://members.aol.com/gtone999/PAC.zip](http://members.aol.com/gtone999/PAC.zip)

This has two PAC files that were the smallest I could find on the game dvd if you need more examples I will post them.
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-25T06:44:05+00:00
- Post Title: Rumble Roses (.PAC)

The difficulty with Rumble Roses is that the main archives don't seem to have a directory - which means that it is very hard to determine where each file starts and finishes in an archive.

I don't really know why this is the case - maybe it is just something PS2-specific, or maybe there is a separate file which contains the directory?

We will take a brief look at it for you anyway, however unfortunately we cannt guarentee any success for this game.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-25T15:48:48+00:00
- Post Title: Rumble Roses (.PAC)

Here is what I do know about CH.PAC and CH2.PAC.

1. First PAC File starts at 16384 ("PAC" header = 4 bytes)
2. Value of 4 bytes after header gives you relative offset of "YOBJ"
3. Value of 4 bytes after "YOBJ" give you address of "POF0"  (Game is looking for both "YOBJ" and "POF0"--That's a Zero on the end of POF0)
4.  Value of 4 bytes after "POF0" gives you the relative offset of texture listing.
5.  Texture listing has a 16 byte header.  First 4 bytes are the number of textures.
6.  Each 32 byte group thereafter is as follows: 
First byte to NULL = texture name, filler for rest of 16 bytes
Next 4 bytes = "txc" terminating in a NULL
Next 4 bytes = Size of file
Next 4 bytes = Offset (Offset is calculated by: Offset - ((32 * NumberOfThe File) + 12)
Next 4 bytes = filler
7. At this offset is the "RTX3" file, which is the texture.  It appears to be an A8R8G8B8 texture with a CLUT(color lookup table) at the end.  I can view the black and white images but can't seem to understand the CLUT.

What is odd is that this only applies to the odd numbered PAC's inside the CH.PAC and CH2.PAC  The even numbered ones are short and have a couple of RTX files in them.  I also can't find the index numbers for the PAC packets.  Maybe watto or Mr. Mouse can shed some light on this.  It looks like there is alot of math calculations going on here to prevent casual extraction.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-26T07:30:06+00:00
- Post Title: Rumble Roses (.PAC)

Interesting information...must have a look at it.
## Post #5
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-26T19:08:40+00:00
- Post Title: Rumble Roses (.PAC)

Here's an RTX file.  I still can't understand the format.  The trailing CLUT, at least I think it's a CLUT, is less than 1024 bytes(which is what an 8 bit palette with alpha should be).  If I open the RTX in Photoshop as a raw file, 256x256 with a 64 byte header--the black and white image is fine.  I can then change the mode to indexed color and save as a palettized 8 bit DDS.  I then copied and pasted the last 1024 bytes from the original raw into the DDS, replacing the CLUT(which is the 1024 bytes after the 128 byte header).  When I open the new DDS, the colors are almost correct.  This is driving me nuts!  Can anyone give any insight on the conversion or opening of this file??
[RTX_256x256.zip](https://xentaxbackup.github.io/file/267_RTX_256x256.zip)
## Post #6
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-09T05:45:41+00:00
- Post Title: Rumble Roses (.PAC)

Finally solved it thanks to help from Mr.Mouse and Watto.  The directory information starts at 2048 as previously thought.  The CH.PAC starts with "EMD "(<--that's a space at the end) and the CH2.PAC starts with "EMD2".  The next byte is the number of 4 byte sections in the directory starting at 2056.  The byte after this is 128 then two more nulls.  In each set of 4 bytes, the first two are irrelevant.  Appear to be just counters, based on multiples of 16.  The last two bytes define the size of the PAC's as follows:

Raise the decimal value of the number to the next power of 8.  If already a power of 8 then keep it.  Multiply this number by 256 and it will give you the size of the PAC section in bytes.  Each PAC section has 2 PAC's in it.  The second PAC in each section is kind of odd.  No information used in the game.   There are two small pictures in it.  One says "Trish" and the other says "Trish Me"(hmmmm).  All the RTX3's in the PAC's are actually TIM2 files with a custom header.  The first 64 bytes of the RTX3 can be cut off and you can put a proper TIM2 header on to view them. 

These files are definitely unique!
## Post #7
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-11T16:11:55+00:00
- Post Title: Rumble Roses (.PAC)

I finally got a working version.  Posted the link in the Wiki.  You can copy and paste this link in your browser:

[http://www.angelfire.com/oz2/oz21/RRPacXtractor.zip](http://www.angelfire.com/oz2/oz21/RRPacXtractor.zip)

Thanks to everyone who helped!
## Post #8
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-06-13T23:08:05+00:00
- Post Title: Rumble Roses (.PAC)

Great Job Jasmine, seems to work cool for Rumble Roses 

Hoped it would also work for WWE SmackDown vs RAW's PAC Files, but it doesnt 

Could you work something out for that game too?
Dont think it will be too different, theres even the same CH.PAC & CH2.PAC files there, but it wont work with your rumble roses program, it crashed with an error message

Heres the SDvsRAW Thread with some sample files:
[viewtopic.php?t=1305](http://forum.xentax.com/viewtopic.php?t=1305)

So if you feel like trying 
If you dont, thank you anyway
## Post #9
- Username: beowolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 23, 2007 2:09 pm
- Post datetime: 2007-05-23T08:16:49+00:00
- Post Title: Rumble Roses (.PAC)

Is there anyway i could extract the meshes of it?  i've attached a sizable .bpe file which i think could've contain meshes.  is there anyway to sniff out of any 3d extensions in the files with hex? e.g: .obj, .3ds, .lwo, etc...

i'd like to poke on it for some time... so if there are any other leads to this development, id appreciate it if someone could direct me there... thanks!!


edit: is the attachment enough?  i still have 4 more but i can only put one attachment....
[File 00082.part1.rar](https://xentaxbackup.github.io/file/1181_File 00082.part1.rar)
## Post #10
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-05-23T20:49:10+00:00
- Post Title: Rumble Roses (.PAC)

> Reply from beowolf
>
> Is there anyway i could extract the meshes of it?  i've attached a sizable .bpe file which i think could've contain meshes.  is there anyway to sniff out of any 3d extensions in the files with hex? e.g: .obj, .3ds, .lwo, etc...

i'd like to poke on it for some time... so if there are any other leads to this development, id appreciate it if someone could direct me there... thanks!!


edit: is the attachment enough?  i still have 4 more but i can only put one attachment....

bpe as in Byte Pair Encoding? and I'm pretty sure it is compressed but I don't know because I don't have the entire file.
## Post #11
- Username: beowolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 23, 2007 2:09 pm
- Post datetime: 2007-05-24T13:39:35+00:00
- Post Title: Rumble Roses (.PAC)

i could send it to you. but theres tons of those .bpe's too. want one? 

i did a crash course on the bits and bytes thing and poked around the ch1 ch2.pac files with hex.  with my abysmal knowledge in these fields, i found traces of what i might think could be names for joints/bones (yubi01, 02, etc) for the character, but then, there were names such as "mouth" within proximity, and i hardly think they would use joints/mouth for bones.  inside the pacs, they also have a few strings of X,Y,Z coordinates with floating point values right after them.  still... i've yet to find the right extension for meshes, and if the bmps are already appended as BM8, what of the mesh extensions? ED$? M@0? *&J?  ~~nyaaarggghh~~
## Post #12
- Username: beowolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 23, 2007 2:09 pm
- Post datetime: 2007-05-24T13:48:05+00:00
- Post Title: Rumble Roses (.PAC)

hmmm.... they have this on the root directory.  it was PACLIST.H but i had to rename it .doc for upload.  i dont remember they put list like this in the game
[PACLIST.doc](https://xentaxbackup.github.io/file/1182_PACLIST.doc)
## Post #13
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2007-05-24T15:53:29+00:00
- Post Title: Rumble Roses (.PAC)

i use yobj as the extensions of mesh. since it's the first 4 letter of the file header of mesh.

i made a viewer last year. so i have some experience in RR 
[RR.jpg](https://xentaxbackup.github.io/file/1183_RR.jpg)
## Post #14
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-05-24T17:28:44+00:00
- Post Title: Rumble Roses (.PAC)

Uh thats incredible
## Post #15
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2007-05-25T04:46:29+00:00
- Post Title: Rumble Roses (.PAC)

Hey, Mike, where the hell can I get that viewer?  And do you have any information on the PAC file model data locations.  I would love to know how you extracted those models!!
## Post #16
- Username: beowolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 23, 2007 2:09 pm
- Post datetime: 2007-05-25T12:32:13+00:00
- Post Title: 

bloody hell... so thats what the yobj is after all!... its been bugging me for quite some time.  so most likely the meshes could be archived as an .obj, just a guess ^^;  cuz when i think about it... konami did say that they modeled cy girls in maya (output usually .obj), soon after that, rr came out... and that ninja cygirls has some resemblance with the bloody shadow.

and yea... an extractor would be really great mike!
## Post #17
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2007-06-09T23:22:30+00:00
- Post Title: 

The exporter will convert multi rr yobj file to a single wavefront object file.
Currently support exctacted file only, so you must extact yobj by other tool.
Tips: You may also darg and drop one or more .yobj file over the dialog box of RROExporter.
[RROExporter.rar](https://xentaxbackup.github.io/file/1202_RROExporter.rar)
## Post #18
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-10T11:30:03+00:00
- Post Title: 

Thanks for the sharing, I thought the tool will never appear but I am wrong.   

But the problem is how to extract the yobj out of pac!?
I try manually copy the 'YOBJ" section out of pac but it didn't work!

How to do it ? Thanks
## Post #19
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2007-06-13T14:43:31+00:00
- Post Title: 

Copy RRUnpack.exe to the folder where your want the files to be extracted. drag and drop .pac onto it to extract. make sure you have enough disk space to store the extract file. RRUnpack will NOT handle any IO error.

If you want to extract the files to different location, it must run the tool in console window. 
The syntax is: RRUnpack [drive:][path]source [[drive:][path]destinaton] (wildcard are NOT supported).
[RRUnpack.rar](https://xentaxbackup.github.io/file/1212_RRUnpack.rar)
## Post #20
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2007-06-13T23:20:33+00:00
- Post Title: 

Any chance to get the viewer I would like to use it to test texture edits it would really help to make it easier then having to burn a new dvd-r/install the game to hard drive each time.
## Post #21
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-06-13T23:45:09+00:00
- Post Title: 

sounds like it exports to normal OBJ, so we can use any 3d software.. but yeah active viewers still kick ass!!   

hey mike, would you be interested in making a DOA4 model viewer?

models were extracted by volt, but can only be seen, using a long process through 3dmax... :p

edit:
[](http://img227.imageshack.us/img227/5696/reiko332vl1.jpg)
jasmine, how do i get alpha extraction on your old texture exporter?
## Post #22
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2007-06-14T04:32:37+00:00
- Post Title: 

Mario, I hate to revisit that mess of code in the original texture extractor.  Would probably be easier to start from scratch.  Mike can you share your source code so that I can understand the file format better?  I fooled with this file format for quite some time and I really impressed with the progress that you made.  If you could even post the format on the Wiki it would benefit all those that are working on RR.
## Post #23
- Username: beowolf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 23, 2007 2:09 pm
- Post datetime: 2007-06-14T05:26:55+00:00
- Post Title: 

I can't seem to extract any textures. i only have the .mtl in the output, but its pointless without the actual textures themselves.  am i the only one here with this problem?
## Post #24
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-06-14T10:35:14+00:00
- Post Title: 

yes....,   lol

just use jasmines old texture extractor
## Post #25
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2007-06-14T23:28:56+00:00
- Post Title: 

here is the source. I tried to clean it up a bit but it still look messy.

@Mario_Kart
I thought i wouldn't have time to start a new project. i've been busy with my  work lately.
[RRUnpack_src.rar](https://xentaxbackup.github.io/file/1220_RRUnpack_src.rar)
## Post #26
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2007-06-15T12:15:00+00:00
- Post Title: 

Mike, thanks for the source but I was actually referring to the obj converter program source.  I'm trying to understand the data layout for the mesh inside the pac sections of the pac file.  Any help would be appreciated.
## Post #27
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-22T20:13:04+00:00
- Post Title: 

Hi jasmine and Mike,

Since "RRPacXtractor" didn't extract alpha channel and some images (4 bits index) didn't extract correctly as well. I decided to write my own. 

The result seems a bit strange on both color and alpha! I thinks it the wrong method I used to convert the indexed color to full color! I wonder did you guys know how TIM2 indexed color work!?




See [viewtopic.php?t=2664](http://forum.xentax.com/viewtopic.php?t=2664) for more details on my problem!
## Post #28
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2007-06-22T22:47:55+00:00
- Post Title: 

I posted the file format information in the other thread.
## Post #29
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2007-07-07T05:45:49+00:00
- Post Title: 

Hey, Mike, could you share the information that you know about the YOBJ file format?  I could really use the information in creating an Exporter/Importer.
## Post #30
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2007-08-17T06:28:23+00:00
- Post Title: 

hey, jasmine, can you also look at compatiblity with smackdown shut Your Mouth and Here comes the pain a the exporter for RR extracts the models from these game... and would love an importer
## Post #31
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-08-23T11:55:11+00:00
- Post Title: 

did anyone look at the new PAC format for rumbe roses for xbox360?
## Post #32
- Username: DarknessValtier
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Feb 07, 2009 11:47 pm
- Post datetime: 2009-08-23T06:31:24+00:00
- Post Title: 

please, help!
i unpack the CH2.PAC files, and convert the YOBJ for OBJ, and i import to 3D max but look...

what is this?
## Post #33
- Username: peterson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 07, 2010 7:58 am
- Post datetime: 2010-02-10T12:59:42+00:00
- Post Title: 

> Reply from DarknessValtier
>
> please, help!
i unpack the CH2.PAC files, and convert the YOBJ for OBJ, and i import to 3D max but look...

what is this?
Hey, dude, check if your generated .obj contains commas (,) as decimal separators. It should be dots (.) instead.

In this case, change your regional settings (decimal separator -> .)

Regards
peterson
## Post #34
- Username: derekhhh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 23, 2010 2:52 am
- Post datetime: 2010-03-23T10:23:39+00:00
- Post Title: 

hi all,
sorry to revive this old thread.  I've been trying to extract some models from RR and it seems I'm missing the program for extracting textures... "RRPacXtractor is it?

Might anyone have a working link to this program?  Or maybe some program that converts the txc files to tga?

Thanks!
## Post #35
- Username: gledson999
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 18, 2012 10:59 am
- Post datetime: 2012-03-18T03:24:18+00:00
- Post Title: 

hello mike you RRunpacker.exe and RROexporter are awesome but can you send for me an RRviewer and a tools that import a edited files back to *.PAc?

thank for you reply

I'll Create a Nude patch for Rumble rose
## Post #36
- Username: Judgment2
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-03-18T15:59:00+00:00
- Post Title: 

Create the tool yourself?
## Post #37
- Username: ginkou
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 10, 2012 1:53 am
- Post datetime: 2012-04-16T20:16:38+00:00
- Post Title: 

hello everybody!

I found these pictures on website japanese for Rumble Rose XX xbox360:

h ttp://[www.coregrafx.info/sexy/src/1334589077352.jpg](http://www.coregrafx.info/sexy/src/1334589077352.jpg)
h ttp://[www.coregrafx.info/sexy/src/1334502352548.jpg](http://www.coregrafx.info/sexy/src/1334502352548.jpg)
h ttp://[www.coregrafx.info/sexy/src/1334510735836.jpg](http://www.coregrafx.info/sexy/src/1334510735836.jpg)

do you know what tools, they use to make these mods.
I also want to make my mods for this game.
someone can help me? I'm not programmer    but I'm good at drawing.
please i need a helping hand.   

sorry for my bad english.
## Post #38
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2012-07-15T05:35:20+00:00
- Post Title: 

The last post in this thread
[http://www.coregrafx.info/sexy/moegrafx.php?res=7254](http://www.coregrafx.info/sexy/moegrafx.php?res=7254)
mentions an editing tool from a 2ch user, if anyone is still interested in pursuing this.
## Post #39
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2012-07-15T17:28:05+00:00
- Post Title: 

any idea what that tool is and where exactly to go to find it?
## Post #40
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2012-07-15T18:54:08+00:00
- Post Title: 

unfortunately, no. that particular imageboard has always been very cagey about sharing info, it's only since mr fluffles/sectus started posting there that useful info started flowing.
## Post #41
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2012-07-19T16:08:41+00:00
- Post Title: 

Does anybody still has jasmine RRPacXtractor tools?Or can anybody reuploaded it? Angelfire link is dead,and maybe the wiki page about rumble roses tools need to be updated
## Post #42
- Username: irishwhip
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Mar 29, 2007 10:00 am
- Post datetime: 2012-07-30T12:27:07+00:00
- Post Title: 

can anyone make sense of these threads? Google translate is a rather blunt instrument with japanese.
[http://www.coregrafx.info/sexy/moegrafx.php?res=7550](http://www.coregrafx.info/sexy/moegrafx.php?res=7550)
[http://www.coregrafx.info/sexy/moegrafx.php?res=7577](http://www.coregrafx.info/sexy/moegrafx.php?res=7577)

They seem to be using a combination of quickbms and x-packer
## Post #43
- Username: rtdesign3d
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 03, 2011 7:46 pm
- Post datetime: 2012-12-26T00:03:08+00:00
- Post Title: 

Hello people, sorry to be reviving this topic again, but how do I convert the textures? I found no program that converts the .txc files 

Is there any method?  

Thank you for your attention
## Post #44
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-06-15T07:04:14+00:00
- Post Title: 

Looking for pac files  for rumble rose xx. do anybody have  one.
## Post #45
- Username: masterfangex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 24, 2022 6:49 am
- Post datetime: 2022-09-24T04:42:30+00:00
- Post Title: 

Hello , i was wondering if there where any new mod tools out for Rumble Roses (ps2) im currently using the old tool by Jasmine but i was wondering if there is a tool that can read ch.pac and ch2.pac the correct way for importing textures or meshes instead of only extracting , ive seen a few youtube videos of someone injecting svr characters to rumble roses, i made a bmp edit of bloody shadow although her skin came out on the yellow side   
on another note i can get menu.PAC to open with game graphic studio the ntsc version you can edit the title screen but on ntsj this is hidden , i was mostley wondering if there was a new pac editor tool out becuase most of these files are close to opening
## Post #46
- Username: Judgment2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 15, 2023 1:47 am
- Post datetime: 2023-01-14T17:52:24+00:00
- Post Title: Re: Rumble Roses (.PAC)

Hello y'all i was looking for a Rumble Roses BMS script, i can't seem to unpack .pac archive... i keep getting errors and stuff does anyone have a rumble roses bms script ??
