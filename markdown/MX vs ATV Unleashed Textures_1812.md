## Post #1
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-31T10:44:57+00:00
- Post Title: MX vs ATV Unleashed Textures

Hi guys, 

Who can figure out how the textures of this game are stored/what type they are in etc ?

See sample files in this attachment:
[sample2.zip](https://xentaxbackup.github.io/file/667_sample2.zip)
## Post #2
- Username: motoman
- Rank: VIP member
- Number of posts: 4
- Joined date: Sun Apr 02, 2006 3:29 am
- Post datetime: 2006-04-01T19:53:01+00:00
- Post Title: MX vs ATV Unleashed Textures

The DXG is a Cad file if I'm not mistaken. 
I'll open it up at work and see.
## Post #3
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-01T21:27:07+00:00
- Post Title: MX vs ATV Unleashed Textures

I'm thinking it's a DirectX geometry file.
## Post #4
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-03T04:24:33+00:00
- Post Title: MX vs ATV Unleashed Textures

i know that DXF is cad.. but never heard of DXG. i think Kams right its DX
## Post #5
- Username: motoman
- Rank: VIP member
- Number of posts: 4
- Joined date: Sun Apr 02, 2006 3:29 am
- Post datetime: 2006-04-03T05:05:32+00:00
- Post Title: MX vs ATV Unleashed Textures

If thats the case then just using the DDS plugin from Nvidia should let you open these in say PS or PSP. unless of course they are some sort of proprietory file.
Ever try to open them up in Irfanview yet? that opens just about every graphic file known.
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-03T06:02:52+00:00
- Post Title: MX vs ATV Unleashed Textures

the DxT file for sure looks like an ordinary DirectX texture but with the header stripped. someone could try recreating the header and a DDS
header to see if PS views it =o ....i might do it later.
## Post #7
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-03T11:46:27+00:00
- Post Title: MX vs ATV Unleashed Textures

Strobe, if you can get this working, you are the man!  Can this be incorporated within MEX Com?  Something that  strips and re-inserts the header ?
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-03T11:48:12+00:00
- Post Title: MX vs ATV Unleashed Textures

> Reply from Kamshaft
>
> Strobe, if you can get this working, you are the man!  Can this be incorporated within MEX Com?  Something that  strips and re-inserts the header ?
Yes, I could probably write a plugin to handle these files.
## Post #9
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-03T12:46:53+00:00
- Post Title: MX vs ATV Unleashed Textures

Let's see I understand correctly....by handling you mean converting back and forth?  So, we can import a TGA file, and your program would conver it into this propriatary DXT format?
## Post #10
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-04-03T14:06:08+00:00
- Post Title: MX vs ATV Unleashed Textures

> by handling you mean converting back and forth? So, we can import a TGA file, and your program would conver it into this propriatary DXT format?

There are few quite reliable  DDS DXT converters available: 
DXTBMP, Microsoft Imagetool and some AceDXT also from Microsoft. 

But after comparing *.dxt enclosed in the sample with DXT made up by the abovementioned tools I fail to see much similarities. And yet looking at dxm I see some DX multitexturing or multipass commands included.
## Post #11
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-03T14:12:18+00:00
- Post Title: MX vs ATV Unleashed Textures

The dxm is just a text file.
the dxt is the actual texture file.

There is alos the DXG (not autocad), those are the model/mesh files.
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-03T18:43:52+00:00
- Post Title: MX vs ATV Unleashed Textures

> Reply from Kamshaft
>
> Let's see I understand correctly....by handling you mean converting back and forth?  So, we can import a TGA file, and your program would conver it into this propriatary DXT format?

No, I meant, if they were DXT format without headers, I could write a plugin that could recreate the DXT by adding the header.
## Post #13
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-03T20:21:24+00:00
- Post Title: MX vs ATV Unleashed Textures

That would be cool.  What would good is a plugin that would allow to import/auto convert textures!  People are just dying to add their own skins in this game!
## Post #14
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-03T20:53:21+00:00
- Post Title: MX vs ATV Unleashed Textures

As expected, it really is a DXT format with the header stripped.
ive tried creating a DDS + DXT header by hand with the resolution
of 128x128 and DXT1 marker, and that seems to work fine, here is
the result. the only part i dont understand is why the first
part of the image is distorted. maybe there are several textures in the
same file? , if so, there seems to be 2 of them. and for now, one of
them is correctly displayed with the DDS header. have fun. =)
[Acerbis_AI_01c.zip](https://xentaxbackup.github.io/file/675_Acerbis_AI_01c.zip)
## Post #15
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-03T20:58:06+00:00
- Post Title: MX vs ATV Unleashed Textures

Interesting.
## Post #16
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-03T21:12:22+00:00
- Post Title: 

Bravo...
## Post #17
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-04T03:26:50+00:00
- Post Title: 

> Reply from Strobe
>
> As expected, it really is a DXT format with the header stripped.
ive tried creating a DDS + DXT header by hand with the resolution
of 128x128 and DXT1 marker, and that seems to work fine, here is
the result. the only part i dont understand is why the first
part of the image is distorted. maybe there are several textures in the
same file? , if so, there seems to be 2 of them. and for now, one of
them is correctly displayed with the DDS header. have fun. =)

I overlooked the Header for now. But you'll notice for each Image there is a 12 byte header. We'll assume all are DXT1 for now.

Starting at 0x54 is first entry. 12 bytes.
[4] Bytes (Dimension X) 
[4] Bytes (Dimension Y)
[4] Bytes (Block Size) (Good indication these are DXT1 no mip-maps is that X*Y / 2 = DXT1 with no mips.

~Repeat this until end of file (should come up with 5 for this one)

The only problem is I think contents will affect header.
## Post #18
- Username: Kazam
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 04, 2006 4:19 pm
- Post datetime: 2006-04-04T08:25:47+00:00
- Post Title: 

the top of the skin that is distorted might be the fact that that is the helmet. Seeing people can choose from a lot of different helmets.
Same goes for the goggles and the boots.
## Post #19
- Username: WinDev
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 04, 2006 4:27 pm
- Post datetime: 2006-04-04T08:31:19+00:00
- Post Title: 

perhaps DXT3...!?
## Post #20
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-04T08:39:47+00:00
- Post Title: 

> Reply from Kazam
>
> the top of the skin that is distorted might be the fact that that is the helmet. Seeing people can choose from a lot of different helmets.
Same goes for the goggles and the boots.

GOOD POINT kaz. i didnt think about that one.
## Post #21
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-04T09:34:07+00:00
- Post Title: 

i did some further testing. and there seems to be other textures in the file.
ive tried reading the DXT as Mipmapped texture , and that reveals other
textures, which however are read in the wrong resolution, so
I dont belive these are mip maps, instead new textures.

what goes against the case is though, if you look close at the beginning of the file at offset 160 there is a 1000 0000 1000 0000 which would simply translate into 16x16. and further down there is a (offset 304) 2000 0000 2000 000 = 32x32 , and further down (offset 824) 4000 0000 4000 0000 = 64x64

...this cannot be a pure coincidence....its structured just like if there were mip maps in the texture....=o

Edit:
oh, suprise. offset 2854 contains 8000 0000 8000 0000 = 128x128
## Post #22
- Username: Extreme
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 26, 2006 8:21 am
- Post datetime: 2006-04-04T16:24:02+00:00
- Post Title: 

Hi
All the sizes are different hereâ€™s a list of the names and sizes for one of the bike skins
Id help look if I knew what I was looking for lol 
250sx_one_engine.dxt
size 256x128 pixels

250sx_plasticsall.dxt
size 256x256 pixels

250sx_sprockets.dxt
size 256x128 pixels

250sx_exhaust.dxt
size 32x32 pixels

250sx_tripleclamp_metals.dxt
size 128x64 pixels

namedefault.dxt
size 64x128 pixels

250sx_wheels.dxt
size 64x32 pixels

tire.dxt
size 64x32 pixels

Extreme
## Post #23
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-04T16:40:08+00:00
- Post Title: 

> Reply from Strobe
>
> i did some further testing. and there seems to be other textures in the file.
ive tried reading the DXT as Mipmapped texture , and that reveals other
textures, which however are read in the wrong resolution, so
I dont belive these are mip maps, instead new textures.

what goes against the case is though, if you look close at the beginning of the file at offset 160 there is a 1000 0000 1000 0000 which would simply translate into 16x16. and further down there is a (offset 304) 2000 0000 2000 000 = 32x32 , and further down (offset 824) 4000 0000 4000 0000 = 64x64

...this cannot be a pure coincidence....its structured just like if there were mip maps in the texture....=o

Edit:
oh, suprise. offset 2854 contains 8000 0000 8000 0000 = 128x128

You are on the edge of figuring this out! Cool!  Good Luck!
## Post #24
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-04T16:44:57+00:00
- Post Title: 

Maybe these texture files have multiple resolution embedded in the files, to allow for distance drawing, maybe?
## Post #25
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-04T20:42:36+00:00
- Post Title: 

All Textures are embedded as seperate files.

I've already worked out everything except for the Header. They ripped mip maps as a seperate texture if anything.

Edit: All files ripped. Mip Maps are split. File is ascending from lowest to highest resolution.

I need another file to actually work header out.
[sample2.zip](https://xentaxbackup.github.io/file/678_sample2.zip)
## Post #26
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-04T20:46:19+00:00
- Post Title: 

> Reply from Strobe
>
> i did some further testing. and there seems to be other textures in the file.
ive tried reading the DXT as Mipmapped texture , and that reveals other
textures, which however are read in the wrong resolution, so
I dont belive these are mip maps, instead new textures.

what goes against the case is though, if you look close at the beginning of the file at offset 160 there is a 1000 0000 1000 0000 which would simply translate into 16x16. and further down there is a (offset 304) 2000 0000 2000 000 = 32x32 , and further down (offset 824) 4000 0000 4000 0000 = 64x64

...this cannot be a pure coincidence....its structured just like if there were mip maps in the texture....=o

Edit:
oh, suprise. offset 2854 contains 8000 0000 8000 0000 = 128x128

where is a good place to start to try and learn howe to make some of these images viewable. their are about 60 images that i would sure like to be able to look at before i place them into my sky. the .toy file calles it out as a TGA file but all i see in the packs are dxt and the dxm that goes to each file. 

I realize this isn't something im going to learn overnight but id like to learn as much as i can so i don't have to be bugging people to do things for me...

Thanks guys for the intrest in helping our little mx vs atv community. You have no idea how thankfull for what you guys here have allready done.
## Post #27
- Username: Clutch
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 05, 2006 8:49 am
- Post datetime: 2006-04-05T03:52:29+00:00
- Post Title: 

> Reply from Silver
>
> All Textures are embedded as seperate files.

I've already worked out everything except for the Header. They ripped mip maps as a seperate texture if anything.

Edit: All files ripped. Mip Maps are split. File is ascending from lowest to highest resolution.

I need another file to actually work header out.

Your work is much appreciated. These images are starting to look more like the format used in Flat Out and Trackmania. With those games the files are dds 512x512 with usually around 12 mip levels. Silver your work is very promising. I am assuming there is a different dxt compression at work here. The 128 as the higest resolution doesnt seem likely for MVA unleashed. Maybe play around in the 512 with at least 8 to 12 mip levels area would be my guess. Thanks for your efforts.
## Post #28
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-05T04:28:17+00:00
- Post Title: 

> Reply from Clutch
>
> 

Your work is much appreciated. These images are starting to look more like the format used in Flat Out and Trackmania. With those games the files are dds 512x512 with usually around 12 mip levels. Silver your work is very promising. I am assuming there is a different dxt compression at work here. The 128 as the higest resolution doesnt seem likely for MVA unleashed. Maybe play around in the 512 with at least 8 to 12 mip levels area would be my guess. Thanks for your efforts.

I have only that one file to go on. It is 128x128 max file is > 12kb. I'd like to see another one if someone has one greater than 128. I'm thinking they are using mip maps all the way until 8x8. I have to see something bigger to be able to tell.
## Post #29
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-05T04:59:09+00:00
- Post Title: 

HERE IS A COMPLETE GEAR SET AND A BIKE SET.

[http://home.comcast.net/~smesple/Data.rar](http://home.comcast.net/~smesple/Data.rar)

iD ALSO LIKE TO UPLOAD A FEW MODELS.
## Post #30
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-05T05:47:13+00:00
- Post Title: 

> Reply from ocr_smokngrn
>
> HERE IS A COMPLETE GEAR SET AND A BIKE SET.

http://home.comcast.net/~smesple/Data.rar

iD ALSO LIKE TO UPLOAD A FEW MODELS.

Thanks! (seemed my previous post was incorrect now...)

[http://rapidshare.de/files/17237528/Data.rar.html](http://rapidshare.de/files/17237528/Data.rar.html)
I left my 5 second crap vb ripper in there.

.DXT Header: 24 Bytes
[4] Bytes - Uknown
[4] Bytes - Type  54 = DXT3 / 38 = DXT1
[4] Bytes - Uknown
[4] Bytes - Number of Files. (Mip Maps = - 1)
[4] Bytes - Max Resolution X
[4] Bytes -  Max Resolution Y

Each Texture Package is split into own file. For Each File:
[4] Bytes - Dimension X
[4] Bytes - Dimension Y
[4] Bytes - Block/Chunk Size
~ Image

* Each image is listed ascending from lowest resolution to highest.

Edit: oops looks like I found DXT3 :p
## Post #31
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-05T07:04:21+00:00
- Post Title: 

[http://home.comcast.net/~smesple/ecc.BMP](http://home.comcast.net/~smesple/ecc.BMP)
## Post #32
- Username: Clutch
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 05, 2006 8:49 am
- Post datetime: 2006-04-05T07:16:12+00:00
- Post Title: 

Now were cookin! great effort all
## Post #33
- Username: WinDev
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 04, 2006 4:27 pm
- Post datetime: 2006-04-05T09:51:19+00:00
- Post Title: 

Here is a complete RIDERS set and VEHICULES set :

[http://www.osconcept.info/mxvsatv/Rider_Tex.rar](http://www.osconcept.info/mxvsatv/Rider_Tex.rar)
[http://www.osconcept.info/mxvsatv/Veh_Tex.rar](http://www.osconcept.info/mxvsatv/Veh_Tex.rar)
## Post #34
- Username: BPh_Designs
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Apr 05, 2006 7:14 pm
- Post datetime: 2006-04-05T11:16:35+00:00
- Post Title: 

Great to see all what you are doing guys.
Congratulations and thanks for all...
Phil.
## Post #35
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-04-05T11:17:56+00:00
- Post Title: 

This is indeed great way to learn about DXT format. It would be interesting, after you are fully done, to see side by side what was exactly done to disguise the format in this particulary case. Good work.
## Post #36
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-05T12:54:53+00:00
- Post Title: 

After removing their own 12 byte headers (which are scattered around in the file) on each mipmap, it can be read normally. (with DDS header ofcourse)

almost normally....
[Acerbis_AI_01d.zip](https://xentaxbackup.github.io/file/683_Acerbis_AI_01d.zip)
## Post #37
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-05T15:58:34+00:00
- Post Title: 

Is is possible now to go back a forth? Meaing to make their DXT files from a good DDS file?
## Post #38
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-05T16:07:28+00:00
- Post Title: 

Right now I dont see why it shouldnt be possible.
im just waiting for Silver and see if he comes up with something new :X
## Post #39
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-05T17:30:22+00:00
- Post Title: 

It would be nice to get mex com to do it all.  Auto-Convert and all.
## Post #40
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-05T18:22:42+00:00
- Post Title: 

You are really making good progress here, and I was right when I told Kamshaft the following in an email prior my request above: 

> As for the other files, I have taken a look at them, but have not yet figured out exactly what they represent. Sure, there are graphics in there, and quite possibly DDS files (there's a photoshop plugin on the web for DDS files if you don't have it already)  that have been header-stripped, but that's just a wild guess..

Good to know the wild guess wasn't so wild after all.
## Post #41
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-05T21:29:55+00:00
- Post Title: 

After this hopefully, some people will help us figure out the model files (DXG).
## Post #42
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-04-06T18:02:35+00:00
- Post Title: 

> After this hopefully, some people will help us figure out the model files (DXG).

The only lead I got is this [http://discussion.autodesk.com/thread.j ... dID=333785](http://discussion.autodesk.com/thread.jspa?threadID=333785). That would be some obscured and forgoten ACAD application, but rather it is not. 
By sublimal   association I would suspect that it could be more of some DXF format without the header, or also maniacally disguised X file.
EDIT: DXF is definetely not
## Post #43
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-06T18:23:56+00:00
- Post Title: 

here is a sample dxg file. Thanks everyone!

[http://home.comcast.net/~smesple/nat15_treed.rar](http://home.comcast.net/~smesple/nat15_treed.rar)
## Post #44
- Username: Clutch
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 05, 2006 8:49 am
- Post datetime: 2006-04-06T19:47:39+00:00
- Post Title: 

could it be dwg format with stripped header?
## Post #45
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-07T00:20:13+00:00
- Post Title: 


## Post #46
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-09T18:11:23+00:00
- Post Title: 

Actually, the DXT files are DDS files saved with additional headers per mipmap and the mipmaps are saved in reverse order in the DXT files compared to DDS. 

The DXM files can be opened by notepad, as they are text. 

DXG files I haven't figured out yet
## Post #47
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-09T20:54:50+00:00
- Post Title: 

Okay, this might be a handy tool: DXT2DDS.

I created it to enable DXT-->DDS (DXT1) and DDS-->DXT. 

Hope it works good enough on all DXT files.
[dxt2dds.jpg](https://xentaxbackup.github.io/file/686_dxt2dds.jpg)
## Post #48
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-09T21:11:59+00:00
- Post Title: 

I get a runtime error "9", subscript out of range....on the CR125R_ECC_01_Plastics.dxt file, all of them actually.
## Post #49
- Username: motoman
- Rank: VIP member
- Number of posts: 4
- Joined date: Sun Apr 02, 2006 3:29 am
- Post datetime: 2006-04-09T23:27:52+00:00
- Post Title: 

Make sure you have mswinsck.ocx in your systems32 folder.
You may also need MSCOMCTL.OCX
## Post #50
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-09T23:32:24+00:00
- Post Title: 

> Reply from motoman
>
> Make sure you have mswinsck.ocx in your systems32 folder.
You may also need MSCOMCTL.OCX

I got'em
## Post #51
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-10T05:12:36+00:00
- Post Title: 

Oops. Forgot I had been lazy. You als need my DDS header template. 

Here's the file (just unpack everything in the same folder).
## Post #52
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-10T05:26:06+00:00
- Post Title: 

well they open but the files is all weird... i have been using texturefinder to open the files( before now)...and it looks like it does when the offset it off.. most work with offset at 4... ihave the PS plugin installed.


also in texture finder ...they look best on dxt3 or 5
## Post #53
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-10T05:49:05+00:00
- Post Title: 

Obviously, I can only work with examples, so please attach some images you converted using dxt2dds and found with texturefinder. 

I have converted several files to DDS, and I reconverted them to DXT. When I compared the original DXTs with the new DXTs they were exactly the same.

For instance, this Jersey file looks like a jersey to me.

Could be that they should be DXT3 though. Try it.
[Acerbis_Jersey_01.dxt.jpg](https://xentaxbackup.github.io/file/688_Acerbis_Jersey_01.dxt.jpg)
## Post #54
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-10T05:55:33+00:00
- Post Title: 

ok i can open the jersey files...but not the bike

[http://home.comcast.net/~smesple/CR250R ... astics.rar](http://home.comcast.net/~smesple/CR250R_McG_01_Plastics.rar)
## Post #55
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-10T10:10:46+00:00
- Post Title: 

Ah, I see what you mean. The thing is that there are some variables left unexplained in the DXT header. One of them is the second 32-bit value , that is 0x26 in the jersey type of dxt's and 0x36 in the bike type of dxts. This must refer to another type of DDS. I will have a look when I have the time.
## Post #56
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-10T11:42:58+00:00
- Post Title: 

Well, I tried to type set it as a DXT3 and it worked. Check the result. 

So I will adapt the tool to save as DXT3.
[CR250R_McG_01_Plastics.dxt.jpg](https://xentaxbackup.github.io/file/689_CR250R_McG_01_Plastics.dxt.jpg)
## Post #57
- Username: Extreme
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 26, 2006 8:21 am
- Post datetime: 2006-04-10T16:02:55+00:00
- Post Title: 

Nice work Mr Mouse looks like u have cracked it   

Thanks 

Extreme
## Post #58
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-10T17:54:36+00:00
- Post Title: 

Here's the update DXT2DDS, should also support those bike DXTs. 

Read the readme.txt
[dxt2dds.zip](https://xentaxbackup.github.io/file/690_dxt2dds.zip)
## Post #59
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-10T19:09:41+00:00
- Post Title: 

Great Job Mr Mouse...
## Post #60
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-10T19:40:39+00:00
- Post Title: 

Thanks, I hope you guys can use it to good effect! Don't hesitate to drop in and show off some results with this game!
## Post #61
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-10T20:11:45+00:00
- Post Title: 

Does this take a bitmap and make the mip maps automatically, or do we need to recreate it exactly the way you have em?
## Post #62
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-10T21:15:21+00:00
- Post Title: 

This needs DDS files. So, I guess you should load up the DDS file in some editor, edit the main mipmap (in Photoshop you can open without opening the other mipmaps) and then save it creating mipmaps automatically (as again a DDS file). Then convert it to DXT. In between you can copy and save the main mipmap as whatever format you wish ofcourse. The original DXT should serve as a template then (which you converted to DDS).
## Post #63
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-11T01:10:56+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Thanks, I hope you guys can use it to good effect! Don't hesitate to drop in and show off some results with this game!

You have know idea how many people you will make happy when we work out all the kinks of actually loading and using modded skins. But none of this could have been done without Xentax and your support. The best 6$ i ever spent.. So thank you.
## Post #64
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-11T22:10:44+00:00
- Post Title: 

I'm having strange things happening to the textures when re-PAKing the PAK file.

And when you do more than 1,500 files....it crashes...LOL
## Post #65
- Username: dictator-duck
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 12, 2006 3:54 am
- Post datetime: 2006-04-12T02:31:54+00:00
- Post Title: 

i have my skin done and converted it back to dds now how do i repack it to get it back into the common pak ?
## Post #66
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-12T05:19:27+00:00
- Post Title: 

> Reply from Kamshaft
>
> I'm having strange things happening to the textures when re-PAKing the PAK file.

And when you do more than 1,500 files....it crashes...LOL

Please elaborate a bit more, the only way to address issues like this is by knowing exactly what happens to which file when. I call them the Three W's.
## Post #67
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-12T10:19:24+00:00
- Post Title: 

ok.  Selelct about 300 .dxt files, try to do a batch convert.  The error should pop up.
## Post #68
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-12T10:33:20+00:00
- Post Title: 

You mean with the dxt2dds? Yes, that can be. I use only a simple common dialog control with limited buffer for storing filenames, if you select too many files(names) the buffer will overflow and the program will probably crash. I created the tool for the conversion per se, not too much as a complete and stand alone program. 

Perhaps I will take a look at expanding its possibilities further, for now I'd just select a smaller batch of dxt's each time you convert (remembering which you already did). 

The other remark is more interesting. you edited some textures and then repacked them, right? And then the textures looked weird? in this case, it's of vital information to know exactly what you did. My job and family do not allow me to start modding this game (or any other game) myself, as all of any free time I have will go into the MultiEx project and tools to help you out.
## Post #69
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-12T12:02:28+00:00
- Post Title: 

That's cool.  The texture is black on the model, but I'm not sure if it's when I re-PAK the file or what.

When I build a new PAK, sometimes, a different will have a broken texture.

I don't know if it's a PAKer thing, or a DXT2DDS thing.  I'm still looking into this.
## Post #70
- Username: markthompson
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 12, 2006 4:44 am
- Post datetime: 2006-04-12T19:51:34+00:00
- Post Title: 


## Post #71
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-12T20:34:38+00:00
- Post Title: 

Those look great!
## Post #72
- Username: duder
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 12, 2006 6:30 am
- Post datetime: 2006-04-12T20:50:10+00:00
- Post Title: 

i donated my six dollars will i recieve my code for the multiex commander utitlitie today?
## Post #73
- Username: bruceatk
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Apr 03, 2006 1:50 am
- Post datetime: 2006-04-12T21:47:48+00:00
- Post Title: 

You should make DXT2DDS work from the command line then it would be easy to use it from other programs, batch files, etc.

A batch file containing this command would do what Kam wants:

for %i in (*.dxt) do dxt2dds %i

Bruce
## Post #74
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-13T07:51:54+00:00
- Post Title: 

@Markthompson: did you alter anything in those textures? 

@bruce: true, I know a command-line option would've been nice, but I used a somewhat different approach (quick and easy, it's not like I have tons of time , you know). Anyway, I think it won't take too much time to adapt it support command-line input as well. Kamshaft had also send me a file that changes textures in the game when not wanted, I want to look into that as well.
## Post #75
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-13T16:10:57+00:00
- Post Title: 

I found a bug with the DDS2DXT program.
It's crashes when it tries to conver this file.
[nat01_preview_01.zip](https://xentaxbackup.github.io/file/693_nat01_preview_01.zip)
## Post #76
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-13T16:57:47+00:00
- Post Title: Re: DDS2DXT Bug

> Reply from Kamshaft
>
> I found a bug with the DDS2DXT program.
It's crashes when it tries to conver this file.

That's because it's not a dxt file, but a dxg file!
## Post #77
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-13T17:46:15+00:00
- Post Title: Re: DDS2DXT Bug

Here's a new version with command line support. 

Still win32 environment though, it's not a real command line program, but it'll work. 

Read the readme.txt for details.
[dxt2dds.zip](https://xentaxbackup.github.io/file/696_dxt2dds.zip)
## Post #78
- Username: dictator-duck
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 12, 2006 3:54 am
- Post datetime: 2006-04-13T19:55:05+00:00
- Post Title: Re: DDS2DXT Bug

can someone tell me how to import the file into game. i cant seem to get it to work.
## Post #79
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-13T19:58:17+00:00
- Post Title: Re: DDS2DXT Bug

> Reply from Mr.Mouse
>
> Kamshaft wrote:I found a bug with the DDS2DXT program.
It's crashes when it tries to conver this file.

That's because it's not a dxt file, but a dxg file!

Seriously? It had the DXT file extention, strange....
## Post #80
- Username: markthompson
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 12, 2006 4:44 am
- Post datetime: 2006-04-13T22:46:37+00:00
- Post Title: Re: DDS2DXT Bug

I only sharpened the last pic
## Post #81
- Username: bruceatk
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Apr 03, 2006 1:50 am
- Post datetime: 2006-04-14T01:04:19+00:00
- Post Title: Re: DDS2DXT Bug

Thanks for making it command line capable.  

Of course there is always "one more thing".  It has one problem running it from the command line.  It displays a message box before it finishes.  I ran it on 1200 files. On around 150 or so it started getting errors, because I had 150 instances running with 150 message boxes.

How about a /s switch (silent) ?  Does it return a return code if it fails?

Thanks,
Bruce
## Post #82
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-14T06:10:12+00:00
- Post Title: Re: DDS2DXT Bug

Oh god, I had forgotten to remove that message box (it was only for debugging purposes)!!!  I have removed it now. The program will return an errorcode if there are any. 

Get the attached new version!
[dxt2dds.zip](https://xentaxbackup.github.io/file/698_dxt2dds.zip)
## Post #83
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-14T12:02:06+00:00
- Post Title: Re: DDS2DXT Bug

If I try to convert a non DXT file the program tells me that it's converted, there's no error message.

Might want to look into that.
## Post #84
- Username: bruceatk
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Apr 03, 2006 1:50 am
- Post datetime: 2006-04-14T13:02:34+00:00
- Post Title: Re: DDS2DXT Bug

Thanks, I'll check it out tonight.

Bruce
## Post #85
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-14T14:58:50+00:00
- Post Title: Re: DDS2DXT Bug

> Reply from Kamshaft
>
> If I try to convert a non DXT file the program tells me that it's converted, there's no error message.

Might want to look into that.

Well, making the program idiot-proof has not been my priority. That's a chore. And chores are done following the rule:

```

```


The readme states one can convert DXT2DDS and vice versa. It doesn't mention other files.
## Post #86
- Username: bruceatk
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Apr 03, 2006 1:50 am
- Post datetime: 2006-04-15T00:23:09+00:00
- Post Title: Re: DDS2DXT Bug

Kam, How many non-dxt files to you have lying around with a dxt extension?

Mr. Mouse,  I ran it on a directory of 601 DXT files and it successfully converted 552 of them.  49 files it did not create a DDS file for.

Bruce
## Post #87
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-15T05:48:38+00:00
- Post Title: Re: DDS2DXT Bug

> Reply from bruceatk
>
> Kam, How many non-dxt files to you have lying around with a dxt extension?

Mr. Mouse,  I ran it on a directory of 601 DXT files and it successfully converted 552 of them.  49 files it did not create a DDS file for.

Bruce

That's interesting. Can you attach a few examples of those that were not converted?
## Post #88
- Username: bruceatk
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Apr 03, 2006 1:50 am
- Post datetime: 2006-04-15T14:56:15+00:00
- Post Title: Re: DDS2DXT Bug

After playing with it some more about 40 of the files that it wasn't converting were random.  I slowed down the process and it would then consistently convert the same files and not convert 10 of them.  I guess you must be using a temp file that's the same name or something like that, so depending on how fast you run it it might be stepping on itself. 

I slowed it down by moving the conversion into a seperate batch file and adding a check for errorlevel.

I've attached the 10 files that it doesn't convert.  The files that I was converting are all from the vehicle texture part of MVA.

Bruce
[dxt_files_not_working.zip](https://xentaxbackup.github.io/file/699_dxt_files_not_working.zip)
## Post #89
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-16T02:35:52+00:00
- Post Title: Re: DDS2DXT Bug

Those are an Uknown type so it does not know what to do with it. 55

Data inside files looks pretty worthless to me   (Images are no data)
## Post #90
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-22T10:24:55+00:00
- Post Title: Re: DDS2DXT Bug

Seems like the dxt2dss converter has a bug, it seems to currupt the alpha channel, everything else is fine.  Any ideas?
## Post #91
- Username: GheTTo_cR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 22, 2006 7:35 pm
- Post datetime: 2006-04-22T11:54:40+00:00
- Post Title: 

> Reply from Kamshaft
>
> Seems like the dxt2dss converter has a bug, it seems to currupt the alpha channel, everything else is fine.  Any ideas?

I was just about to post this...



It also does it when converting back to DXT... So like Stephen said, any ideas?
## Post #92
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-22T12:10:28+00:00
- Post Title: 

Well, if you have a correct version and an incorrect version of the same picture, please post them. Like I said before, there are some unknown variables in the DXT that may refer to the alpha channel. It might also be that the game knows which alpha channel settings to use, and didn't save this info in the DXT files. If you know what DDS settings there should be please let me know.
## Post #93
- Username: GheTTo_cR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 22, 2006 7:35 pm
- Post datetime: 2006-04-22T19:30:25+00:00
- Post Title: 

I just made a DXT3 .dds file with alpha and converted to .dxt and then converted it back to .dds and the alpha loads fine in PS for that... Probably something with the stock game files then I guess? But how come when I load the .dxt i made with an alpha into the game, the alpha is wrong ingame
## Post #94
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-22T21:13:18+00:00
- Post Title: 

> Reply from GheTTo_cR
>
> I just made a DXT3 .dds file with alpha and converted to .dxt and then converted it back to .dds and the alpha loads fine in PS for that... Probably something with the stock game files then I guess? But how come when I load the .dxt i made with an alpha into the game, the alpha is wrong ingame

That means the game knows what type of alpha to expect from a variable in the DXT file. The DXT that is created is based on a template DXT gotten from a variety of game DXTs. But: it might be that the unknowns in the DXT are referring to alpha stuff, that are not set during conversion.
## Post #95
- Username: GheTTo_cR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 22, 2006 7:35 pm
- Post datetime: 2006-05-30T22:29:08+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> GheTTo_cR wrote:I just made a DXT3 .dds file with alpha and converted to .dxt and then converted it back to .dds and the alpha loads fine in PS for that... Probably something with the stock game files then I guess? But how come when I load the .dxt i made with an alpha into the game, the alpha is wrong ingame  

That means the game knows what type of alpha to expect from a variable in the DXT file. The DXT that is created is based on a template DXT gotten from a variety of game DXTs. But: it might be that the unknowns in the DXT are referring to alpha stuff, that are not set during conversion.

Well I found out when you only use pure white and pure black and everything pixelated and saved as a DDS 'DXT1 ARGB (1 bit Alpha)' it does work... I'm no coder or programmer but I hope this will get someone closer to finding a fix...
## Post #96
- Username: chrisjohn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 03, 2006 6:35 am
- Post datetime: 2006-06-02T23:17:29+00:00
- Post Title: 

bruce..where do i put them.. and i put my skin to a dds and my photoshop cs2 wont open it.. same with the dxt files....
## Post #97
- Username: garasaki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 04, 2007 12:10 am
- Post datetime: 2007-10-26T20:01:36+00:00
- Post Title: 

> Reply from GheTTo_cR
>
> Kamshaft wrote:Seems like the dxt2dss converter has a bug, it seems to currupt the alpha channel, everything else is fine.  Any ideas?

I was just about to post this...



It also does it when converting back to DXT... So like Stephen said, any ideas?

I got that problem too...I don't suppose anyone has made any progress figuring that out??
## Post #98
- Username: MikeyMikey
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 12, 2012 3:28 pm
- Post datetime: 2012-01-12T07:53:06+00:00
- Post Title: 

> Reply from garasaki
>
> GheTTo_cR wrote:Kamshaft wrote:Seems like the dxt2dss converter has a bug, it seems to currupt the alpha channel, everything else is fine.  Any ideas?

I was just about to post this...



It also does it when converting back to DXT... So like Stephen said, any ideas?

I got that problem too...I don't suppose anyone has made any progress figuring that out??

Rookie fix..What works for me when i get that issues sometimes..Open the original skin file and convert to bmp file..then open file with DXTbmp program..import original alpha channel for the skin..save as DDS DXT1  then convert to DXT using DDS2DXT program then add to game files..
=FallGuy=
## Post #99
- Username: staydown
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 20, 2012 5:49 am
- Post datetime: 2012-02-19T22:02:54+00:00
- Post Title: 

does anyone know how to extract the terrain files/greyscale maps from the pak files?
## Post #100
- Username: +COTAY
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 21, 2018 5:54 pm
- Post datetime: 2018-09-03T10:36:16+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> GheTTo_cR wrote:I just made a DXT3 .dds file with alpha and converted to .dxt and then converted it back to .dds and the alpha loads fine in PS for that... Probably something with the stock game files then I guess? But how come when I load the .dxt i made with an alpha into the game, the alpha is wrong ingame  

That means the game knows what type of alpha to expect from a variable in the DXT file. The DXT that is created is based on a template DXT gotten from a variety of game DXTs. But: it might be that the unknowns in the DXT are referring to alpha stuff, that are not set during conversion.
Mr Mouse, please share the source code of your DXT2DDS program. Thanks
## Post #101
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-05-11T00:32:12+00:00
- Post Title: 

> Reply from GheTTo_cR ↑Sat Apr 22, 2006 7:54 pm at Sat Apr 22, 2006 7:54 pm
>
> 
Kamshaft wrote:Seems like the dxt2dss converter has a bug, it seems to currupt the alpha channel, everything else is fine.  Any ideas?

I was just about to post this...



It also does it when converting back to DXT... So like Stephen said, any ideas?
might be because its dxt5 and not dxt3

here is Noesis python script to open the dxt samples from this thread:


 tex_MXvsATVUnleashed_PC_dxt.zip
(836 Bytes) Downloaded 54 times


supports dxt1, dxt5 and morton swizzled paletted rgba32
top level mip only
