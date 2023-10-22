## Post #1
- Username: grnbriar
- Rank: VIP member
- Number of posts: 6
- Joined date: Mon Sep 05, 2005 5:35 am
- Post datetime: 2005-09-04T23:47:58+00:00
- Post Title: BloodRayne2 TEX bit format

Since the BloodRayne TEX to BMP tool doesn't recognize the BloodRayne 2 format, I was trying to write one. I have the image coming up and am trying to figure out the bits per color. There are two bytes per pixel. It's not 4444 or 565. Does anyone know the bit format used in the previous tex converter?
## Post #2
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2005-09-05T01:27:45+00:00
- Post Title: BloodRayne2 TEX bit format

Unforunetly both my site and BloodRayne.uk are down at this moment. I don't know about UK but my site should be just maintainance down time. There are a few very talented people posting scripts and code to answer both your posted questions. In fact woc put together a very good Perl script to convert the textures. Others have improved on it since.

 You may be able to find some answers to your questions here also.

[http://www.bloodraynemassacre.com/skinzphp/portal.php](http://www.bloodraynemassacre.com/skinzphp/portal.php)

 Xentax will extract the POD's and the texture conversion has already been done by a few people. The big difference is the indexing method. While BR1 is 8bit indexed TRI decided to screw with everyones mind with a crippled 24bit indexed. I was successful in getting a 24bit with alpha and a 32bit with alpha working in the demo. TRI complained the textures were to big of a resource killer but Rayne sure looked nice in 24bit true color. Not to mention the alpha allows for actual changes in the outfits.
 Anyway I hope BloodRayne.uk will be back up soon (it's been down a while) because there are some powerful programmers there working on modding BR2.

 also try here: [http://www.bloodrayne.net/cgi-bin/blood ... l?board=pz](http://www.bloodrayne.net/cgi-bin/bloodrayne_forum/YaBB.pl?board=pz)
## Post #3
- Username: grnbriar
- Rank: VIP member
- Number of posts: 6
- Joined date: Mon Sep 05, 2005 5:35 am
- Post datetime: 2005-09-08T17:57:54+00:00
- Post Title: BloodRayne2 TEX bit format

Thanks for the direction. I still have not been able to register at the massacre site, but I'll keep trying. I want to get the tex converter, rather than write one. I'm still hunting for any model info.
## Post #4
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2005-09-09T22:41:50+00:00
- Post Title: BloodRayne2 TEX bit format

My site is more down than up lately but as of this posting it is up. Bloodhammer makes a good stab at BR2 in the woc section. 

[http://www.sparedlife.com/forum/Index.php](http://www.sparedlife.com/forum/Index.php)

 Take your time and look around, there may be some useful information you can use.
## Post #5
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T22:55:57+00:00
- Post Title: BloodRayne2 TEX bit format

> Reply from SparedLife
>
> My site is more down than up lately but as of this posting it is up. Bloodhammer makes a good stab at BR2 in the woc section. 

http://www.sparedlife.com/forum/Index.php

 Take your time and look around, there may be some useful information you can use.
Nice Perl Scripts
## Post #6
- Username: grnbriar
- Rank: VIP member
- Number of posts: 6
- Joined date: Mon Sep 05, 2005 5:35 am
- Post datetime: 2005-09-10T02:35:15+00:00
- Post Title: BloodRayne2 TEX bit format

Thanks!
Lots of info!
I still want to be able to rad and write the BR2 model files into my app for making mods. This shoul dget me working with the non-animated models to start with.
## Post #7
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2005-09-10T05:49:57+00:00
- Post Title: BloodRayne2 TEX bit format

> Nice Perl Scripts

 I am but a lowly beginner at Perl. I am hoping that one day the light bulb will go on in my head and I will finally understand how to use the information posted here. When I began learning Perl I did it because most of the games I had did not have tools for skinning. Dragon Unpacker and MultiEx can extract a lot of games but for the most part that is it. I needed some way to edit the extracted textures and then get the game to use them when there were no tools for editing available. Not to mention the unpacker programs don't support individual texture files. 
 Before Perl I either used a HEX editor to convert the textures to a editable state or begged all over the internet for someone to write a simple conversion program. The latter mentioned was nearly impossible to obtain. Since posting my Perl scripts I have had so many great responses from other frustrated skinners that I feel it was worth the time to learn.

 Your welcome grnbriar
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-10T06:27:55+00:00
- Post Title: BloodRayne2 TEX bit format

> Reply from SparedLife
>
> Nice Perl Scripts 

 I am but a lowly beginner at Perl. I am hoping that one day the light bulb will go on in my head and I will finally understand how to use the information posted here. When I began learning Perl I did it because most of the games I had did not have tools for skinning. Dragon Unpacker and MultiEx can extract a lot of games but for the most part that is it. I needed some way to edit the extracted textures and then get the game to use them when there were no tools for editing available. Not to mention the unpacker programs don't support individual texture files. 
 Before Perl I either used a HEX editor to convert the textures to a editable state or begged all over the internet for someone to write a simple conversion program. The latter mentioned was nearly impossible to obtain. Since posting my Perl scripts I have had so many great responses from other frustrated skinners that I feel it was worth the time to learn.

 Your welcome grnbriar

Nice ! Keep it up!
## Post #9
- Username: grnbriar
- Rank: VIP member
- Number of posts: 6
- Joined date: Mon Sep 05, 2005 5:35 am
- Post datetime: 2005-09-10T06:31:05+00:00
- Post Title: BloodRayne2 TEX bit format

I do 3D C++ programming for a living for the last 3 years (20 year+ programmer), my own toys and contract work for 3D app companies. I've been building my own OpenGL based app, ToolBox, to read and write Poser and game engine formats, mostly the indie ones - 3DGS and Torque for folks building their own games, but I would also like to use it to mod some commercial games, BR2 being my favorite. I started it as an OpenGL sample program and have made it into my game modeler. Since it is my app, I can add whatever odd tools, importers I want. I'll post a pic when I have Rayne loaded!
Thanks for your help, if you need a custom converter, yell. I add whatever I can figure out either as part of toolbox or a stand alone or plugin.
