## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-26T05:43:12+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

Instructions:
* Place ripper.exe where .A, .B, and .C files are.
* Run ripper.exe.
* Wait for a while.
* Locate LWO files.
* Locate appropriate textures.
* Convert textures to TGA using Photoshop.
* Move TGA files to where LWO is.
* Open LWO in LightWave.
* Texturing is automatic; if it asks where textures are, point to same directory and voila.

Example:
* The following picture below, her LWOs are in LINKDATA_A/0400 directory. Her textures are in  LINKDATA_A/0896 directory.
* Remember, all tits need to be reoriented lol.

Notes:
* Character models are in pieces.
* Tits are not oriented correctly.
* You will have to transfer all tits to Maya or Max to reorient; LW does not rotate vertex normals along with geometry.
* Hair also typically has to be moved, but not reoriented, to the right place as well.
* Geometry with cloth physics are not implemented.
* No bones yet. Has UV, normals, weights. Too lazy to do bones right now.
* No level geometry yet; those are located in G1E files.
* G1M files contain characters, props, ships, and skyboxes; that's what you get.
* There is also LOD geometry in the files, you can recognize them because they do not have UVs.


[ripper.7z](https://xentaxbackup.github.io/file/5462_ripper.7z)
## Post #2
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-05-26T10:29:43+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

omg..u are awesome xD
## Post #3
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-05-26T11:31:04+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

Thank you howfie, Nice job on this one.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-26T11:50:22+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

no problem. you guys are welcome, enjoy. it's too bad nami's skirt is cloth and is thus missing. i don't think they use [this](http://developer.download.nvidia.com/SDK/10.5/direct3d/Source/Cloth/doc/Cloth.pdf) technique, but one day if I have some more time I'll read it lol.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-05-26T19:29:01+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

> Reply from howfie
>
> it's too bad nami's skirt is cloth and is thus missing.

How unfortunate indeed.
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-26T21:11:45+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

You make it sound like seeing a skirtless girl with her panties exposed is a bad thing har har har.
## Post #7
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2012-05-27T02:06:08+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

aweeeeeeeeeeeesome
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-05-27T05:37:27+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

Infortunatly its imposible found this game.
## Post #9
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-05-27T05:50:21+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

How did you know lightwave was my favorite 3D app ;-D

No more OBJ importing/exporting

Also, if you want to use the .DDS images in LW you could use this plugin, it's a D3D exporter for LW but you can load only the DDS.p file and get DDS image support:

[http://www.dstorm.co.jp/dsproducts/Free ... xport.html](http://www.dstorm.co.jp/dsproducts/FreePlugins/Object_IO/DirectX_Export.html)
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-27T06:33:43+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

actually, i have been aware of that dstorm plugin for many years now, but I thought it didn't work with anything greater than LW9. a lot of people on the newtek forums have complained about it. there is also [this](http://forums.newtek.com/showthread.php?t=121697) one as well. when i get home in a few days i will check it out and if it works well i will change the TGA requirement in the next release. you can also load the lwos in a hex editor and do a replace all... replace .tga with .dds.
## Post #11
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-06-11T09:23:04+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

hi, thanks for this tutorial.
I have a problem: '.lwo' are pieces of characters and it's ok, I can open them but...about the textures? How can I open them? I think them are the '.g1m' files but I really don't know how to open. You say that I have to use photoshop but it never can open those kind of files, so I tryed to use texture finder but I can't found the true settings.
Can you help me?
thanks in advance.

P.S.= I use photoshop CS6
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-11T10:10:33+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

textures are dds files; g1m files are game model files (m = model)

install NVIDIA DDS plugin for photoshop
[http://developer.nvidia.com/nvidia-text ... -photoshop](http://developer.nvidia.com/nvidia-texture-tools-adobe-photoshop)

open up DDS files in photoshop

for each image, Shift + Ctrl + S to save as

save as tga

put tgas where lwo file is at
## Post #13
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-06-11T10:18:58+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

> Reply from howfie
>
> textures are dds files; g1m files are game model files (m = model)

install NVIDIA DDS plugin for photoshop
http://developer.nvidia.com/nvidia-text ... -photoshop

open up DDS files in photoshop

for each image, Shift + Ctrl + S to save as

save as tga

put tgas where lwo file is at
and where are those dds files?
I just have folder like '406' but there are just '.lwo' and '.g1m'
Maybe this is because I extracted just 'LINKDATA.A'
But that's what appear when I open the game folder: PS3_GAME>USIDIR>LINKDATA_PS3   and there is just the '.A' files...where are the '.B' and '.C' files?
thanks in advance for the reply.

P.S.= searching better I found that the folders after 1000 contain dds files, so have I to search the right folder for every character? or am I doing something wrong?
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-11T10:40:04+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

the game has B and C files; if yours does not have it, you probably didn't extract the game right. or if you downloaded it, you downloaded a bad rip. most textures are in the C file.
## Post #15
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-11T11:00:56+00:00
- Post Title: [PS3] One Piece Kaizoku Musou

There should be 6000+ dds files. You have a bad rip.
## Post #16
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2012-06-11T13:20:15+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Will you be supporting the DLCs as well?
## Post #17
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-06-11T14:10:14+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from howfie
>
> There should be 6000+ dds files. You have a bad rip.
thanks for your information I'll try extract again the game.
## Post #18
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-06-11T14:15:08+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from howfie
>
> textures are dds files; g1m files are game model files (m = model)

install NVIDIA DDS plugin for photoshop
http://developer.nvidia.com/nvidia-text ... -photoshop

open up DDS files in photoshop

for each image, Shift + Ctrl + S to save as

save as tga

put tgas where lwo file is at

I think PS has a batch convert feature inside the File menu, not sure tho it might be something new, I use CS5, will check it when I get home.

> Reply from skyvenom
>
> Will you be supporting the DLCs as well?

This i don't know if it's gonna be available, as far as I know you can't export DLCs from the PS3 as easy as the 360's, if anyone can do share ;-D

> Reply from howfie
>
> actually, i have been aware of that dstorm plugin for many years now, but I thought it didn't work with anything greater than LW9. a lot of people on the newtek forums have complained about it. there is also this one as well. when i get home in a few days i will check it out and if it works well i will change the TGA requirement in the next release. you can also load the lwos in a hex editor and do a replace all... replace .tga with .dds.

The DDS plugin works with the latest version of LW (10.1/11) the only problem is the way LW handles transparency as in you need 2 separate files, one for the diffuse channel and another for the transparency channel, if you use only one file with embedded transparency LW will show either the texture or the transparency but not both at the same time   , 3D studio max can do this I wonder why LW can't.
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-11T17:18:50+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Just use imagemagick for batch converting needs for common formats.
Hasn't failed me yet and you can write batch files/shell scripts.
## Post #20
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-06-11T20:05:31+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

I already try several times download this game, but only its imposible, if somebody can upload only the characters and send PM with link this can be usefully, Btw i have the .aar files for the WII version of One_Piece_Unlimited_Cruise_2 if anyone its interested in take a view can be Usefully Since i never see this One Piece Game can be ripped.
## Post #21
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-06-14T10:41:24+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

I have another problem: if I import the model in 3d studio max it misses quality, is there any way to fix this problem?
thanks in advance for the reply.
[](http://imageshack.us/photo/my-images/38/68040258.png/)

sorry for the bad quality of the image.
## Post #22
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-06-14T13:53:26+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from kuraudo94
>
> I have another problem: if I import the model in 3d studio max it misses quality, is there any way to fix this problem?
thanks in advance for the reply.


sorry for the bad quality of the image.

From what i can see u tried to export the model from c4d to 3dsmax..in what format? obj? If that, there is no missed quality, simply the normals and mesh smoothing were lost during the 3d format conversion. Acutally c4d doesen't have a good default exporter for obj, so if u don't know 3dsmax so well u can install an alternative export plugin for c4d called riptide which is able to preserve the mesh smooth.
## Post #23
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-06-14T14:09:03+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from kuraudo94
>
> I have another problem: if I import the model in 3d studio max it misses quality, is there any way to fix this problem?
thanks in advance for the reply.


sorry for the bad quality of the image.

Just apply a smooth modifier and hit 1 ¬¬

Try to get a basic 3ds max tutorial to start to learn some basic things.
## Post #24
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-14T16:20:19+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Yeah, darko is right. Lw supports custom vertex normals,  3ds Max does not, you must use a modifier.
## Post #25
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-06-14T18:31:46+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from Darko
>
> 
Just apply a smooth modifier and hit 1 ¬¬

Try to get a basic 3ds max tutorial to start to learn some basic things.

I'm gonna sound like a LW fanboy but that is why I don't like 3DS Max, I know some people can do wonders with it, but for me the whole thing is too convoluted XD

LW is more intuitive and a lot simpler, also not so much of a resource hog like 3DS max.
## Post #26
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-06-15T09:27:50+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from howfie
>
> Yeah, darko is right. Lw supports custom vertex normals,  3ds Max does not, you must use a modifier.
thanks...this is the last thing I never know: where are located the textures? I can found just rufy's textures and them are not in the same folder of 3d models.
Thanks in advance for the reply.
EDIT:problem resolved, from the folder '885' there are textures of characters.
Thanks to you for the help and the tutorial.
## Post #27
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-16T09:10:42+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from skyvenom
>
> Will you be supporting the DLCs as well?

Most likely not. I tend not to buy any PS3 DLCs since most of them are NPDRM encrypted. For example, I have Neptunia MKII's swimsuit DLCs that I extracted from my PS3 last year, but the ISM2 files are all EDAT files. SUX. There are some new tools that are supposed to decrypt them but I haven't tried them yet.
## Post #28
- Username: skittles
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 10, 2010 1:25 pm
- Post datetime: 2012-06-27T01:24:46+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Hi,
I am having an odd issue...the ripper works fine, I get all the files, open in lightwave, etc....all that is fine(so thanks for that!). But I don't know virtually anything about lightwave, so I export as OBJ and import that into 3dsmax....
now that's where the issue comes into play, and I was hoping maybe someone might have an idea as to what is going on. It seems when I import the obj in max that the UV coords are....well, I'm not sure the proper word to describe it....
what happens is when I apply a texture to a surface that surface turns totally black. It's not the normals, I checked that....it's something to do with the UVs because when I reset them I can get the maps to show, but obviously the original UVs are gone at that point, so it does me no good.
Not being an expert with max either, I feel like I'm missing some simple fix here perhaps. Any ideas? TIA!
## Post #29
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-06-27T03:24:43+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

In lightwave you need to assign the proper UV setting and UV map inside the surface editor or you will end up with OBJs with no UV that will turn into strange colors when textures are applied.
## Post #30
- Username: skittles
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 10, 2010 1:25 pm
- Post datetime: 2012-06-27T03:54:27+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

[Update]
Well, it seems while that was the 1st part of my issue, my trials are not yet over. The UVs are getting corrupted somehow when I export from lightwave...not being really familiar with lightwave, I really am not sure where to look at this point. I've tried everything I can think of and nothing works...I have read on several forums that lightwave 10 has a known bug like this...anyone can confirm that? At any rate, this is what I'm ending up with(lightwave on left 3dsmax on right):

[](http://img101.imagevenue.com/img.php?image=840158459_Untitled_1_122_392lo.jpg)

The model is actually quite smooth..that's the messed up UV coords you're seeing...ugh, dunno what to do at this point. Anyone have any suggestions?

[UPDATE 2]
Well, I found a workaround for the problem I was having. After opening & combining the models in lightwave and making sure all the maps are right, I save a new LWO file out. Then I import that LWO file into a program called Shade12(which luckily has a fully functional 30 day trial). Shade12 is able to then export them with all the proper UVs intact and without any other noticeable issues. So YAY! 

so Thanks again for the tool, and thanks also for pointing me in the right direction at the start of my problem. I"m really glad to have everything working the way I need it to now. My only request would just be maybe next time port straight to obj, but otherwise 9/10. Great ripper program.
## Post #31
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-09T17:17:04+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

ripper was written for the japanese version of the game.
## Post #32
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-09T18:47:39+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

OK, looking at source code, the following happens:

1. Ripper scans current directory and all subdirectories for any .A, .B, and .C files. Make sure that LINKDATA.A, LINKDATA.B, and LINKDATA.C are THE ONLY .A, .B, .C files inside the folder along with ripper.

2. Ripper opens up each file and the first thing it does is look at the first four bytes. The first four bytes must be 0x077DF9. If it is not, you get that error message. Post a screencap of your A, B, C files loaded in a hex editor. Maybe you have a bad rip.
## Post #33
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-09T21:39:58+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

bad rip; that data is still encrypted. how did you get the data from your PS3? is it jailbroken + with custom firmware + true blue?
## Post #34
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-09T21:47:06+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

ps3 needs to be jailbroken with custom firmware. cannot have firmware greater than 3.55 on your current machine to jailbreak.

best way is to just download it now (since you own the game). as some other guy noted, it is impossible to find (it is on newsgroups though if you are willing to pay $10 for a month worth newsgroup access to get what you want).
## Post #35
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-09T21:52:31+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

i tried to get the bones and some of the bones were in place, but for some things like skirts and stuff the bones were really fucked up (like they use the same transforms as the cloth parts); so yeah, no bones for this game unfortunately.
## Post #36
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2012-10-23T17:40:45+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Anything new released recently that might help us get those DLC files?
## Post #37
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-23T21:33:43+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Don't have files to test. Pm me if you have them.
## Post #38
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2012-12-14T17:06:47+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

I like the tool. No source code to research(pity).
## Post #39
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-12-15T00:19:34+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

[http://code.google.com/p/sticklove/sour ... _piece.cpp](http://code.google.com/p/sticklove/source/browse/trunk/source/xentax/ripper/ps3_one_piece.cpp)
## Post #40
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2012-12-16T01:10:50+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou


## Post #41
- Username: weling2010
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Feb 10, 2012 3:35 pm
- Post datetime: 2013-04-12T03:47:24+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

I try to get the models One Piece Kaizoku Musou 2 ripped by Caravan using the same exe (thank howfie for the ripper) but only extract the textures, I wonder if someone else already tried? i don't know if this version by caravan was ripped fine or maybe models encrypted are otherwise
## Post #42
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-12T04:50:23+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

reason: there are new model types in g1m format. i am working on it, but it may take a while.
## Post #43
- Username: jooped
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 25, 2010 3:30 am
- Post datetime: 2013-04-13T04:14:20+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from weling2010
>
> I try to get the models One Piece Kaizoku Musou 2 ripped by Caravan using the same exe (thank howfie for the ripper) but only extract the textures, I wonder if someone else already tried? i don't know if this version by caravan was ripped fine or maybe models encrypted are otherwise

From what I have seen the only difference in the g1m files is the fact that their headers are G1M_0035 and G1MF0022 rather than G1M_0034 and G1MF0021. If you really need the models you could just batch swap the headers and they should convert that way, granted I haven't converted enough models to see if the only thing that has changed are the headers.
## Post #44
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-13T09:49:54+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

interesting, so just changing the version number actually works?
## Post #45
- Username: jooped
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 25, 2010 3:30 am
- Post datetime: 2013-04-13T18:12:59+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from howfie
>
> interesting, so just changing the version number actually works?

For the most part, I know post-TS Nami and Robins hair doesn't convert but I think that is because their hair uses cloth physic.
## Post #46
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-13T18:31:08+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

oh ok, thx for the report. this game uses FVFs, even for the cloth stuff, so any new vertex format is going to boink the ripper. for the most part i didn't notice much is the same, as these musou game really like to reuse stuff lol.
## Post #47
- Username: weling2010
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Feb 10, 2012 3:35 pm
- Post datetime: 2013-04-19T19:33:49+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from jooped
>
> weling2010 wrote:I try to get the models One Piece Kaizoku Musou 2 ripped by Caravan using the same exe (thank howfie for the ripper) but only extract the textures, I wonder if someone else already tried? i don't know if this version by caravan was ripped fine or maybe models encrypted are otherwise

From what I have seen the only difference in the g1m files is the fact that their headers are G1M_0035 and G1MF0022 rather than G1M_0034 and G1MF0021. If you really need the models you could just batch swap the headers and they should convert that way, granted I haven't converted enough models to see if the only thing that has changed are the headers.

thanks for the reply jooped and howfie I'll try swap the headers, but the models I really want are the girls (nami, perona, robin)
## Post #48
- Username: jooped
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 25, 2010 3:30 am
- Post datetime: 2013-04-19T21:49:44+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from weling2010
>
> jooped wrote:weling2010 wrote:I try to get the models One Piece Kaizoku Musou 2 ripped by Caravan using the same exe (thank howfie for the ripper) but only extract the textures, I wonder if someone else already tried? i don't know if this version by caravan was ripped fine or maybe models encrypted are otherwise

From what I have seen the only difference in the g1m files is the fact that their headers are G1M_0035 and G1MF0022 rather than G1M_0034 and G1MF0021. If you really need the models you could just batch swap the headers and they should convert that way, granted I haven't converted enough models to see if the only thing that has changed are the headers.

thanks for the reply jooped and howfie I'll try swap the headers, but the models I really want are the girls (nami, perona, robin)

that's fine but just remember that none of the post time skip girls' hair converts right
## Post #49
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-07-05T06:31:25+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

I keep endlessly getting more and more .bin and .arc files endlessly. Is it supposed to do this?
## Post #50
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2013-08-30T10:57:52+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Can you export the animation files?
## Post #51
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-30T11:01:44+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

no animations.

speaking of which, blender support for both KM1 and KM2 coming soon (of course, minus cloth... still can't get the right transforms from the cloth control points which are defined in the NUNO chunk, i can get close to replicating the cloth, but close is still not close enough).
## Post #52
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-12-21T21:10:09+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Was never able to find the formulas for the cloth... can get close... but still odd looking. Oh well, screw it lol. So I'll just release this anyways. It should work with both KM1 and KM2 Japanese versions of the game.

[ripping program + plugin](http://www.sticklove.com/content/semory/crap/onepiece2jap.7z)

For KM2: 

660 = monkey
661 = zorro
662 = nami
663 = usopp
664 = sanji
665 = tony tony chopper
666 = nico robin
667 = franky
668 = brook
669 = ace
670 = boa
671 = jinbe
672 = edward newgate
673 = buggy
674 = dracule mihawk
675 = crocodile
676 = marshall d. teach
677 = pacifista
678 = kizaru
679 = aokiji
680 = akainu
681 = enel
682 = perona (SEND) 1171 textures
683 = smoker male
684 = marco
685 = monkey d garp male
686 = trafalgar law
687 = krieg
688 = arlong
689 = hatchan
690 = lapahns
691 = wapol
692 = mr. 2
693 = mr. 3
694 = rob lucci
695 = kaku : giraffe form
696 = jabra
697 = blueno
698 = sentomaru
699 = pacifista
700 = minotaurus
701 = magellan
702 = hannyabal
703 = ivankov
704 = ???
705 = ???
706 = ???
707 = ???
708 = ???
709 = ???
710 = ???
711 = ???
712 = ???
713 = ???
714 = ???
715 = ???
716 = ???
717 = ???
718 = ???
719 = ???
720 = ???
721 = ???
722 = ???
723 = ???
724 = ???
725 = ???
726 = ???
727 = monkey (chibi)
728 = zorro (alternate)
729 = chopper (alternate)
730 = arm and leg morphs?
731 = robot???
732 = nothing
733 = hand holding 4 swords each.
734 = ???
735 = ???
736 = environment map???
737 = environment map???
738 = environment map???
739 = big hand???
740 = nothing
741 = ???
742 = dragon
743 = environment map???
744 = environment map???
745 = chibi samurai outfit???
746 = zorro alternate???
747 = ???
748 = another chibi model???
749 = another chibi model???
750 = another chibi model???
751 = zorro alternate???
752 = zorro alternate???
753 = zorro alternate???
754 = plant???
755 = chopper (alternate)
756 = bird/wolf
757 = some stupid simple character with tongue sticking out
758 = ??? some enemy
759 = ??? some enemy
760 = ???
761 = ???
762 = nami (main player outfit)
763 = usopp (alternate)
764 = sanji (alternate)
765 = tony tony chopper (alternate)
766 = nico robin (alternate)
767 = frankie (alternate)
768 = brook (alternate)
769 = ???
770 = ???
771 = nami (drum kingdom)
772 = nami (kimono)
773 = nami (swimsuit)
774 = usopp?
775 = sanji?
776 = tony tony chopper
777 = nico robin (kimono)???
778 = ???
779 = boa
780 = buggy???
781 = buggy???
782 = ???
783 = ???
784 = ???
785 = nothing
786 = environment map???
787 = environment map???
788 = environment map???
789 = nico robin
790 = ???
791 = environment map???
792 = environment map???
793 = environment map???
794 = environment map???
795 = environment map???
796 = environment map???
797 = environment map???
798 = environment map???
799 = environment map???
800 - 870 = environment map???
871 - 970 = ship ores and other objects
971 = monkey head morphs
0972 = 1041 more head morphs
1042 = apple
1043 = tomatoes on a plate
1044 = kabobs on a plate
1045 = ham with a bone on a plate
1046 = looks like an udon bowl on a plate
1047 = looks like an udon bowl on a plate
1048 = cup
1049 = chicken and chopsticks
1050 = generic sword and axe
1051 = viking helmet
1052 = disc
1053 = disc
1054 = disc
1055 = coin bag
1056 = suitcase with money in it
1057 = sword embedded in pile of chunk
1058 = board
1059 - 1140 = animation files
1141 - 1590 = character textures
1668 - 1678 = pattern textures
## Post #53
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-12-21T23:03:10+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Hey howfie, did you manage to fix the compile heart bug in your ripping tool??
## Post #54
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2013-12-22T03:30:05+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Did you have omitted 'convert to LWO'? 
how to use 'smcimport.py'?
sorry noob question
## Post #55
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-12-22T03:38:09+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

open text panel in blender 2.49b
open script in panel
run script
open smc file
profit
## Post #56
- Username: Strife1989
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 12, 2012 9:52 pm
- Post datetime: 2013-12-22T06:38:23+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

hello howfie i used the tool you made for this game to extract the Shin Gundam Musou data, it all worked great except the 3d models they are still .g1m 
can you please help me ???
## Post #57
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-12-22T07:08:19+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

thank you for the report. the gundam game is on my todo list. cant say when i can get to it. the last few releases were stuff i completed months ago, like in july. i'm still fighting some shitty infection. fucken first time they said it was bronchitis, then a sinus infection, and im still sick. maybe i got the crabs lol.
## Post #58
- Username: Strife1989
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 12, 2012 9:52 pm
- Post datetime: 2013-12-22T07:16:00+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

sorry to hear that, hope you get better
if you ever get a chance to work on the gundam game it would be great i need those models really bad
## Post #59
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2013-12-31T16:43:24+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Can someone upload the .A .B ... files from KM2?
It'd be a great help for the project I want to realize!
## Post #60
- Username: neff10
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 18, 2012 2:17 pm
- Post datetime: 2014-02-20T20:28:49+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from loriscangini
>
> Can someone upload the .A .B ... files from KM2?
It'd be a great help for the project I want to realize!
too big man.. download from piratebay
## Post #61
- Username: jrush
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 25, 2012 6:10 pm
- Post datetime: 2014-05-25T22:46:43+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Hey, so sorry for bumping this topic. But I'm having a problem with ripping the models. Everytime I try to use the ripper tool on LINKDATA.A,B,C or D.

It
Processing LINKDATA.A
Reading file 1 of 1864

Then
Failed to create bin file.

Can anyone please help me?
## Post #62
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-05-26T00:35:08+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

You should always use latest version of ripping program and run as Administrator since lots of files and folders must be created and deleted.
[2014-05-20.7z](https://xentaxbackup.github.io/file/7379_2014-05-20.7z)
## Post #63
- Username: jrush
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 25, 2012 6:10 pm
- Post datetime: 2014-05-26T01:22:29+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Thanks for the tool, I didnt have this one. I start it as an administrator, put the tool in the same folder as the LINKDATA files but It doesnt seem to work for me. 

It starts and exits immediately. I just need Law's model.
## Post #64
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-05-26T02:24:35+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

What's the error message on the black console window for the new tool? Same error message? Is a LINKDATA_A folder ever created? Create a LINKDATA_A folder where the LINKDATA.A file is and then run the tool. If files are created inside the folder and the tool works then it's a folder permissions problem. Also, your LINKDATA.A file should be 1.70 GB.

Also make sure you have this:
[http://www.microsoft.com/en-us/download ... px?id=5555](http://www.microsoft.com/en-us/download/details.aspx?id=5555)

even though everyone and their mothers should already have it on their computers.
## Post #65
- Username: jrush
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 25, 2012 6:10 pm
- Post datetime: 2014-05-26T03:00:52+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

My LinkData.A file is 812mb, LinkData.B is 839mb, LinkData.C is 1.26gb and LinkData.D is 1.08gb. 

I tried it again with the folder created and got the same error message as before. 

I guess my LinkData file is the wrong one?
## Post #66
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-05-26T03:16:10+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Can you show a screencap of:

1. The program, right before you click OK.
2. The folder where the LINKDATA files are at.

Like so:
## Post #67
- Username: jrush
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 25, 2012 6:10 pm
- Post datetime: 2014-05-26T03:22:45+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Thanks for taking the time to help me,  I really appreciate it.

This is a screencap.

My version is actually One Piece Pirate Warriors 2 not Kaizoku Mosou? Could that be the problem?

Can u help me with Law's SMC files?
## Post #68
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-05-26T03:30:29+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

I don't know where the files are, there are no filenames, and I don't like One Piece lol. The game is awful it is so emo lol.

But I now know what's wrong. It's all those periods in the path name.  Rename that folder to something that doesn't have any periods in it. The reason you can't have periods is because I replace them with "_" so that folder name LINKDATA_A doesn't conflict  with filename LINKDATA.A for example. In fact, I would just copy those A, B, C, and D files to C:\ONEPIECE\ and then run the ripper. It should work.

So yeah, rename it and all should be good. And then delete the images you posted, as it shows what "kaizoku" group it came from lol. Oh, and shorten the pathname too, windows can't handle pathnames greater than 255 characters lmao so the extraction may throw errors if the filenames get too long.
## Post #69
- Username: jrush
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 25, 2012 6:10 pm
- Post datetime: 2014-05-26T03:33:36+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from howfie
>
> I don't know where the files are, there are no filenames, and I don't like One Piece lol. The game is awful it is so emo lol.

But I now know what's wrong. It's all those periods in the path name.  Rename that folder to something that doesn't have any periods in it. The reason you can't have periods is because I replace them with "_" so that folder name LINKDATA_A doesn't conflict  with filename LINKDATA.A for example.

So yeah, rename it and all should be good. And then delete the images you posted, as it shows what "kaizoku" group it came from lol. Oh, and shorten the pathname too, windows can't handle pathnames greater than 255 characters lmao so the extraction may throw errors if the filenames get too long.

Dude you are a great person. Thanx. It worked. Thank you so much.
## Post #70
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-05-26T03:34:09+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

no problem lol.
## Post #71
- Username: Lavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 22, 2010 1:17 pm
- Post datetime: 2014-06-07T01:00:18+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Hey howfie, just wondering if you've looked at DW8 models at all? I'm trying to reverse the endian of the console files to use on PC but getting stuck, can't figure out where though. It's likely to be one of the G1MG chunks, and probably chunk 4 with all the vertex data. From chrrox's script I see it reads halffloats if vertexsize[elementarray.faceid] is 0x30, but looking at the data there, it really doesn't look like they would be words. I'm also running into a bunch of vertex sizes not listed in there, 0x8 and 0x78 to name but two.
## Post #72
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-06-07T10:52:04+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

yes, i did ps3 version i think. correct, pc version uses different endian and the pc version of dw8 i heard was a pretty bad port so im not particularly interested. if you are interested, i can release partial source.
## Post #73
- Username: Lavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 22, 2010 1:17 pm
- Post datetime: 2014-06-07T13:30:20+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from howfie
>
> yes, i did ps3 version i think. correct, pc version uses different endian and the pc version of dw8 i heard was a pretty bad port so im not particularly interested. if you are interested, i can release partial source.

It's no worries, I finally cracked it today. Reversed the whole file, yay.
## Post #74
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2014-07-02T23:57:18+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Is there anyway to fix the hair on some of the female models?? Because I'm trying to rip some of them and their hair gets turned into this weird mesh.
## Post #75
- Username: neff10
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 18, 2012 2:17 pm
- Post datetime: 2014-07-22T09:22:36+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Finally i ripped all the maps, but look at ennies lobby:



a lot of strange stamps on some textures, any solution?
## Post #76
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-08-28T07:18:22+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

Maybe I'm doing something wrong but when I open a .smc with Blender the textures won't load, and in the console it says anly failed to load.
I tried to move the textures and the .smc to the same location but same result.

Any way to fix that?
## Post #77
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-08-28T10:38:03+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

create a new blend file in the folder where smc and dds textures are before running script
## Post #78
- Username: senseitag
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 15, 2014 10:54 pm
- Post datetime: 2014-11-16T17:37:30+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

this is possible to rip bone&weight or no?
## Post #79
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-11-16T19:51:39+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

> Reply from senseitag
>
> this is possible to rip bone&weight or no?

Yep, It's possible.
## Post #80
- Username: senseitag
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 15, 2014 10:54 pm
- Post datetime: 2014-11-18T02:22:46+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

how to extract G1M LWO G1T files?
## Post #81
- Username: yuugatamoon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 11, 2014 5:52 pm
- Post datetime: 2015-06-09T09:49:19+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

How do I extract dlc doing ?
## Post #82
- Username: Havie
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jan 21, 2016 2:44 am
- Post datetime: 2016-01-23T18:34:15+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

When I run the Xentax program it opens the CMD box for a split second then closes instantly. I managed to print screen what its saying:
[http://i.imgur.com/Bhc8Ypk.jpg](http://i.imgur.com/Bhc8Ypk.jpg)

Any advice on why this is crashing?
## Post #83
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2018-08-18T13:11:39+00:00
- Post Title: Re: [PS3] One Piece Kaizoku Musou

is there any way to make the ripper work on the english version of the pirate warriors 1/2? those are the only versions i can get my hands on. if it is supposed to work on them then im having the same issue as some people where the cmd window will pop open for about a second and then just close without creating any new files. ive even tried moving the a/b/c files to a folder with a shorter path since that was suggested a few pages back
