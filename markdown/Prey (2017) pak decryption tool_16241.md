## Post #1
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-05-05T22:01:09+00:00
- Post Title: Prey (2017) pak decryption tool

Version 3 released.
[Download here.](http://sktest.aruarose.com/PreyConvert_003.7z)

Changelog:
Version 1:
Initial release

Version 2:
Fixed file size check

Version 2:
Added support for the Mooncrash DLC
## Post #2
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-05-06T14:00:37+00:00
- Post Title: Prey (2017) pak decryption tool

Thank you very much!
Is there a way to make it work with the larger files of the game? It gives this error message on all ~1+GB files:
## Post #3
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-05-06T15:56:15+00:00
- Post Title: Prey (2017) pak decryption tool

Yeah, I just noticed that. Looking into it.
## Post #4
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-05-06T17:24:59+00:00
- Post Title: Prey (2017) pak decryption tool

Works perfect now thank you!
## Post #5
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2017-05-07T14:50:05+00:00
- Post Title: Prey (2017) pak decryption tool

any way to pack the pak file back up?

also any way to get the xml files to be unencrypted?
## Post #6
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-05-07T15:49:12+00:00
- Post Title: Prey (2017) pak decryption tool

Recompile of the old binary XML conversion tool I made for Crysis 3 or whatever.
[Download.](http://sktest.aruarose.com/BinXMLDecode_001.7z)

As for the repacking, it might accept .zip files renamed to .pak, I'm not sure if files NEED to have signatures or if it works without them.
## Post #7
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2017-05-08T21:59:47+00:00
- Post Title: Prey (2017) pak decryption tool

There're  *.skin and *.skinm files. Do you know open this files? I try noesis rename *.skin to *.cgf but doesn't work
## Post #8
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-05-09T17:09:44+00:00
- Post Title: Prey (2017) pak decryption tool

> Reply from DarthphoeniX
>
> There're  *.skin and *.skinm files. Do you know open this files? I try noesis rename *.skin to *.cgf but doesn't work
Rename the .skinm files to cgf and use this tool [viewtopic.php?f=33&t=13137](http://forum.xentax.com/viewtopic.php?f=33&t=13137)
## Post #9
- Username: windswept
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 25, 2016 6:35 am
- Post datetime: 2017-05-23T00:11:58+00:00
- Post Title: Prey (2017) pak decryption tool

> Reply from o0Crofty0o
>
> DarthphoeniX wrote:There're  *.skin and *.skinm files. Do you know open this files? I try noesis rename *.skin to *.cgf but doesn't work
Rename the .skinm files to cgf and use this tool viewtopic.php?f=33&t=13137

The tool download link goes to a file not found.
## Post #10
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-05-24T15:50:41+00:00
- Post Title: Prey (2017) pak decryption tool

Not quite works....
Smoothing is destroyed, still unknown how to make textures work

Update.
For now most reliable way for me is ninjaripper for meshes+intelGPA for textures.
Would like to have models rigged though, and max res textures from the game files. I don't think i can run it with max settings for textures on my GTX 750Ti...

Proof of concept
[http://i.imgur.com/LZkEY3H.png](http://i.imgur.com/LZkEY3H.png)
## Post #11
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-05-24T22:36:22+00:00
- Post Title: Prey (2017) pak decryption tool

Smoothing isn't really destroyed on my end(in blender at least).

You have to combine the split textures to one image in a hex editor and then you can load and convert them with the latest version of Noesis. I can write a short tutorial for you here if it helps anything^^
Rigged models would be amazing, but there's no way with existing tools i think.
## Post #12
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-05-24T22:43:35+00:00
- Post Title: Prey (2017) pak decryption tool

Yes, tutorial for that might help dramatically!
Please, do that!))
## Post #13
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-05-25T00:23:54+00:00
- Post Title: Prey (2017) pak decryption tool

Ok what you need:
[Noesis](http://forum.xentax.com/viewtopic.php?f=33&t=4582) (huge thanks here to MrAdults for supporting the normal map format of these properly, even Photoshop doesn't like them much)
[Hex Editor](https://mh-nexus.de/en/hxd/)
[Intel .dds plugin for Photoshop (for the specgloss map thingies)](http://gametechdev.github.io/Intel-Texture-Works-Plugin/)
This .zip with headers:


 BC4_Headers.zip
(625 Bytes) Downloaded 155 times


1. Textures are made of these files:

The .dds contains the header info and i think smallest mip level, 1-8 files are increasing mips of the texture. Just take the biggest one (with the highest number, in this case 8, it is the most HD version)

2. Open the .dds and the .8 file in HxD. Switch to the .8 file and select everything with ctrl+a, then copy it with ctrl+c. 

3. Switch to the .dds file and select everyting starting at Offset 94 to the end:

(94 is important, if you do it at for eg 95 your texture will be shifted sidewards and not match the UV)
Then simply paste with ctrl+p and save with ctrl+s.

4. Open texture in Noesis and convert to your format of choice.
You can alternatively open these in Photoshop using the Intel plugins mentioned above. For that open your texture in HxD again and change this small part from whatever it is to 01 (thanks to chrrox for figuring this out): 


5. You may have noticed that _ddn (normal maps) usually don't just have the 1-X files but also files called like 6a,7a,8a. 1-8 belong to normal map, 1a-8a belong to the gloss map.
You have to convert it seperately (as far as i know anyway). I don't know where the game gets this header from, it isn't the .a file. I figured it's BC4 textures however and added a .zip to this post that has headers for the dimensions i came across in the files. The gloss maps here share the dimensions the normal maps have (4k normal map = 4k gloss map). So if it is 4k, open BC4_4k_header.dds and the .8a file in HxD, copy everything from the .8a file again and paste it below the header (offset 80). Save it under a new name you will find easy.
Noesis displays these as plain white, but Photoshop with the linked plugins loads them fine.

6. I noticed that for some reasons the normal map channels seem to be switched (red should be green, green should be red). If you don't do that shading might look quite bad in whatever software you render in.

7. You're finally done and can load them all on your model! Yey!
## Post #14
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-05-25T07:10:12+00:00
- Post Title: Prey (2017) pak decryption tool

Thank you very , much!
Could you also direct me on where have you found player character's model? I'm looking female version too.
Also for other stuff, like psychoscope, backpack and helmet to complete the set.
## Post #15
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2017-05-25T10:10:20+00:00
- Post Title: Prey (2017) pak decryption tool

Here is a video tutorial if someone need it:

[https://www.youtube.com/watch?v=Izyyyh-mz98](https://www.youtube.com/watch?v=Izyyyh-mz98)

You should get something like this:


Here are samples for the Shotgun:
[http://www.mediafire.com/file/9fs8l4c9n ... rienDS.zip](http://www.mediafire.com/file/9fs8l4c9nhsuxps/Shotgun-Textures-personnalheaders-AdrienDS.zip)
## Post #16
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-05-25T10:15:32+00:00
- Post Title: Re: Prey (2017) pak decryption tool

@devilsnake88: very nice work on making it a video tutorial! However, i really recommend to convert at least the normal maps through Noesis. Photoshop loads the Blue channel as flat grey, however it is supposed to be white with some details in it: [Shotgun example](https://cdn.pbrd.co/images/auimdOuXH.jpg)

As for the linked textures: There are 4k versions of them in the files. Also both NR and GPA don't really know what to do with the normal and gloss maps of this game. It doesn't surprise me all that much. I think getting textures directly from the game files and using Noesis on everything but the gloss maps is the best solution. Gloss maps (.8a,etc) only properly work in Photoshop. 

Either way make sure you unpack all the games .pak files, then it's mostly easy to find things. Path to preorder shotgun is this:
d:\...\Objects\weapons\ShotgunPreord\1P\
for the mesh check the .skinm here:
d:\...\Objects\weapons\Shotgun\1P\ShotgunPreorder1P_01.skinm
Sometimes characters or items also have a .cfg file, but those are lower poly than the according .skinm one.

Morgan's models (male and female) are in:
d:\...\Objects\characters\Humans\MorganKarl\
d:\...\Objects\characters\Player\Male\
d:\...\Objects\characters\Player\Female\

In some cases you might not find textures directly next to the models (pajamas model of Morgan from the beginning for example). If you found the mesh you will see a .mtl file close to it however. Open that in HxD or a text editor and you can read what files it points to and where. In this model's case it points to
"objects/characters/humans/pajamas/textures/morgan_pajamas_genfemalebody01_diff.tif"
you won't find the .tif in that folder, but the .dds version will be there. Eyes, eyelashes, etc are all listed in these .mtl files for the head too.

Oh and one last thing, in "Objects\characters\HumansFinal\" there's a .cdf file for every character you meet in the game. You can open these in HxD or Text editor too and read what models are used to create these characters and where to find them in the files 

EDIT: d:\...\Objects\Accessories\   has Psychoscope etc
## Post #17
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2017-05-25T12:21:36+00:00
- Post Title: Re: Prey (2017) pak decryption tool

> Reply from o0Crofty0o
>
> @devilsnake88: ...
Thank you.
Yes I know it 
Anyway, Great job to you guys.
## Post #18
- Username: judgedead53
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 26, 2017 3:22 am
- Post datetime: 2017-05-25T20:28:32+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Thanks for all this tools and tutorials, working perfectly 

For the textures, I personally use a texture converter made for Star Citizen and it works perfectly for every type except cubemaps : [https://forums.robertsspaceindustries.c ... -converter](https://forums.robertsspaceindustries.com/discussion/369524/sc-texture-converter) (not sure if I'm allowed to post a link to another forums, feel free to remove it)

I have a few problems though. My main goal is to edit one texture and to put it back in the game. I've sorta did it but I was hoping an easier way.
The image I want to edit is "Objects-part5.pak\Objects\Environment\Props\Tech\Monitor_Mounted_A\Monitor_Mounted_A_3x5_diff.dds". Extracting it with the tool above works fine but I have some problems to extract every mipmap manually (info about that later). 
- Edited a few pixels, and repacked in the dds did not work (seems logic, replacing 7 sub-image with 1 big). Get a black texture in game.
- Edited only the biggest mipmap (with HxD) had 0 differences In Game, even on Very High.
- Edited every mipmaps (with HxD), filling whole random bytes with FFs works, but the monitors seems to use different mipmaps.

So my main question is, is there a simpler way to edit this image than to edit each byte of each mipmaps ? Or are there at least, some docs about the file format of .dds ?


Now the second part. Extracting the texture with the automated tool gives me a dds with each mipmaps on different layers. 
Is it possible to split this file so that the Prey successfully read it ?
I also tried to extract every mipmaps manually using the method o0Crofty0o described previously. It works fine for the biggest one, but all the other ones renders blank, even in Photoshop with the Intel plugin (I did try to export through Noesis, edit the byte to 01 and opening in Photoshop). 
Any ideas of what could have gone wrong ?


Sorry for all the questions. I'm a bit new in all this stuff but I'd really like to achieve this. Thanks for reading
## Post #19
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-05-25T22:45:42+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Either it's me using tool wrong, or Hex Edit method proved better quality of assets.
Gamma, alpha transparency destroying the image or else
Normal maps are unusable if gained through this tool, just for me for some reason

[http://imgur.com/a/qdnkc](http://imgur.com/a/qdnkc)

First one is obtained via tool, second one via hex edit
## Post #20
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-05-25T23:25:57+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Yeah i too think the tool doesn't work properly on Prey. Especially the normal maps turn out very wrong and most textures end up too dark. 
Thank you anyway 

Would you mind telling how you inject the textures back into the game at all? I'd like to try, maybe i can figure something out.
## Post #21
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-05-26T06:23:53+00:00
- Post Title: Re: Prey (2017) pak decryption tool

As far as I know, Sir Kane's tool just decrypts the zip archive and there is no manipulating with its content. So you are barking up the wrong tree
## Post #22
- Username: judgedead53
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 26, 2017 3:22 am
- Post datetime: 2017-05-26T16:21:45+00:00
- Post Title: Re: Prey (2017) pak decryption tool

I've used the tool to extract "flat" textures, didn't mess with normal maps at all. But since it's made for another game, the results might be messed up, yeah.

The way I edit and reinject the textures is to edit each mipmap byte by byte with HxD, putting them back in the .zip the decryption tool gave me, and renaming it to .pak. The game doesn't seem to care if it's signed or encrypted and loads it anyway. It's the only thing I could think of that worked. 

For example, I filled each mipmap (from .1 to .6, didn't edit the header one) with a different value for each one, from AA to FF. Here is the result : [http://i.imgur.com/mRBmGor.jpg](http://i.imgur.com/mRBmGor.jpg) (the original one : [http://i.imgur.com/sopMvQh.jpg](http://i.imgur.com/sopMvQh.jpg) )

As merlinsvk said, my questions might be off-topic there, and if you guys say so, I'll create another thread
## Post #23
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-05-26T19:10:11+00:00
- Post Title: Re: Prey (2017) pak decryption tool

OH Spolers!
Well. modding might be interesting, not just retextures.
Problem is, i don't understand why we can't just use CryEngine SDK tools to get assets....
## Post #24
- Username: judgedead53
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 26, 2017 3:22 am
- Post datetime: 2017-05-28T08:01:01+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Alright, I made some good progress on retexturing, figured I would share it here  
Here's the first edit I managed to put in game (admire my beautiful photoshop skills ) : [http://i.imgur.com/I78niuD.jpg](http://i.imgur.com/I78niuD.jpg)

Now the "how did you do this" :
1. First, you want to know what is the original format of the image. I personally used [Nvidia Texture Tools](https://developer.nvidia.com/legacy-texture-tools) on the header dds. 
Mine was BC1 sRGB.


2. Extract your texture using [o0Crofty0o's method](http://forum.xentax.com/viewtopic.php?p=130909#p130909).
3. Load it up into Photoshop and edit it as you wish.
4. Save the image using the format we found earlier.
5. Generate the mipmaps. Divide your image size by 2, save it on the good format. Do it again until you've reached the same amount of mipmaps the game has.
There might be a way to generate them automatically that I don't know of.


6. Now, open every dds you've generated and remove their header (the 94 first bytes) and name them the same way the game originally did (.dds.6 for example)
7. Replace the files in the decrypted pak, rename it to .pak and replace the original crypted file by this new one.
8. Enjoy .

PS: I'm sorry if that's not very clear, my english is not really good :/
## Post #25
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-05-28T09:55:55+00:00
- Post Title: Re: Prey (2017) pak decryption tool

I wish there was a tool or batch script to do all that stuff.
Doing it manually is a chore
## Post #26
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-05-29T20:17:30+00:00
- Post Title: Re: Prey (2017) pak decryption tool

How to edit the font this game?

file:[http://www.mediafire.com/file/bct7etvv93uyle7/Font.rar](http://www.mediafire.com/file/bct7etvv93uyle7/Font.rar)
## Post #27
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-05-31T19:11:38+00:00
- Post Title: Re: Prey (2017) pak decryption tool

> Reply from Taner038
>
> How to edit the font this game?

file:http://www.mediafire.com/file/bct7etvv93uyle7/Font.rar

Anyone?
## Post #28
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-06-09T20:22:52+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Up.
## Post #29
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2017-06-11T03:06:17+00:00
- Post Title: Re: Prey (2017) pak decryption tool

So I found the files for the maps inside the UI, in Textures/ArkAutoMaps/, but they're all low-detail. They don't include the pathways, stairs, etc. Is there something I'm missing for the extra detail? I've done a lot of searching inside the file system, and I can't seem to find anything else. I was also looking for the UI textures for the workstations, and the small avatar images for the TranScribe audio logs, and can't seem to find those either. Is there a different .pak file other than Objects and Textures that they might be hiding in?
## Post #30
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-06-11T13:10:28+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Gamedata.pak, then Libs\UI\Textures.
## Post #31
- Username: jflieger
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 11, 2017 10:59 am
- Post datetime: 2017-06-12T00:43:22+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Excellent, thanks a bunch.
## Post #32
- Username: skinnermedia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 30, 2017 1:55 am
- Post datetime: 2017-07-29T17:59:21+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Thank you so much for this tool! I needed to extract Morgan (female and male) and I will be doing so later on today.

Edit:
I am really sorry if this was already explained somewhere else, or if I am just a complete idiot but....
How do you use this to extract models? Every time I attempt to use it, nothing happens.

Edit 2 xD:
I have figured it out, sorry! Thanks again for the tool!
## Post #33
- Username: jopopo1986
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 20, 2010 5:35 am
- Post datetime: 2017-09-12T14:03:49+00:00
- Post Title: Re: Prey (2017) pak decryption tool

I tried to decrypt the english.pak from the localization folder but i get the error "couldn't decrypt content"



Am i doing something wrong?  

edit: it worked with "Star Citizen Pak Extractor" instead
## Post #34
- Username: Keeperv85
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 06, 2010 8:41 am
- Post datetime: 2017-12-17T11:52:38+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Hello Guys!

Thanks for this tool, working great!

I want to translate ingame signpost, example this:

[](https://mobilarena.hu/dl/upc/2017-12/302988_examp.jpg)

...but... I have no idea where is this... uhm... texture (?).

Pls help! Thanks!
## Post #35
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2017-12-18T19:57:10+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Yes, this is a texture, everything except screens and monitors is a texture.
## Post #36
- Username: Keeperv85
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 06, 2010 8:41 am
- Post datetime: 2017-12-20T21:00:33+00:00
- Post Title: Re: Prey (2017) pak decryption tool

> Reply from phill05
>
> Yes, this is a texture, everything except screens and monitors is a texture.

Ok. Thanks!

..and any idea, how can i find these?
## Post #37
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2018-06-11T17:21:15+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Prey Mooncrash files can't be decrypted. Any chance for an updated tool?
## Post #38
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2018-06-13T18:24:22+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Updated the first post in this thread with a new version that supports the Mooncrash DLC.
## Post #39
- Username: spennser
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 30, 2016 1:12 pm
- Post datetime: 2018-06-14T20:28:55+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Would this work for audio files?
## Post #40
- Username: TacoBellLord
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 24, 2019 12:26 pm
- Post datetime: 2019-02-24T04:53:19+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Alright, so thank you for this stuff but to be honest I don't understand it. I just came here trying to find a way to get Prey character and model files from the game's files for use in blender. So first off how do I get 7zip to work because my computer says it is downloading it and once it's downloaded it does nothing. I try to open it and it asks if I want to allow it to open because its downloaded from the internet but once I hit yes it doesn't do a single thing. Also how do I get the Cryengine converter to do stuff? Can one of you guys help me out please, I don't know very much about file types and windows and stuff like that. I'm new to all this stuff so if any of you could put it in simple terms, like in a series of steps I'd be far more than grateful.
## Post #41
- Username: evilvasile
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 03, 2019 4:34 am
- Post datetime: 2019-04-02T20:53:24+00:00
- Post Title: Re: Prey (2017) pak decryption tool

> Reply from TacoBellLord ↑Sun Feb 24, 2019 12:53 pm at Sun Feb 24, 2019 12:53 pm
>
> 
Alright, so thank you for this stuff but to be honest I don't understand it. I just came here trying to find a way to get Prey character and model files from the game's files for use in blender. So first off how do I get 7zip to work because my computer says it is downloading it and once it's downloaded it does nothing. I try to open it and it asks if I want to allow it to open because its downloaded from the internet but once I hit yes it doesn't do a single thing.

If you're using Windows 10, it should natively recognize .zip files. If not, you can always try WinRar: [https://www.win-rar.com/download.html](https://www.win-rar.com/download.html)

> Reply from TacoBellLord ↑Sun Feb 24, 2019 12:53 pm at Sun Feb 24, 2019 12:53 pm
>
> Also how do I get the Cryengine converter to do stuff? Can one of you guys help me out please, I don't know very much about file types and windows and stuff like that. I'm new to all this stuff so if any of you could put it in simple terms, like in a series of steps I'd be far more than grateful.

Do you mean how to use the PreyConvert.exe tool to decrypt the pak files?

If so, you need to open CMD (Windows Key + R, then type 'cmd' and run it) and run the PreyConvert.exe tool with the input and output file as arguments, so it would look something like this

```

```


Edit:

Oh yea, actually, I registered here because I wanted to mention, late last year when I ran into this thread, I was looking for a way to get to where the game keeps the Recycling data. 

Long story short, I needed to extract tons of files while looking for it, and I ended up making a GUI tool to automatically run the decryption tools for the pak/xml files. I just kept it to myself until now, but now it's on github if anyone cares: [https://github.com/evilvasile/EvilExtractor](https://github.com/evilvasile/EvilExtractor)

I'm pretty sure you could just do this with a simple batch script or something, but I don't know anything about that and i know C#, so this was easier for me, haha.

I've attached a pic of what it looks like, for the tool itself check the git.
[Example.png](https://xentaxbackup.github.io/file/15993_Example.png)
## Post #42
- Username: TheTwilightDancer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 01, 2018 7:00 am
- Post datetime: 2019-04-15T03:27:03+00:00
- Post Title: Re: Prey (2017) pak decryption tool

I wonder, if any tools out there support conversion of fully rigged and skinned models from the game yet. Trying to find simple to use tools since I can't figure out how to go through more complicated steps. I got the Prey convert tool to unpack the assets, but I wanna be able to use fully rigged and skinned models in Blender. Anyone know of any tools? CGF Converter doesn't yet support Prey files. Or at the very least, anyone have any fully skinned and rigged models of Morgan Yu, weapons, Operators, and Typhon? I wanna get a hold of them.
## Post #43
- Username: fordyi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 21, 2019 12:43 am
- Post datetime: 2019-07-20T16:45:57+00:00
- Post Title: Re: Prey (2017) pak decryption tool

HI all, 

I cant seem to get this to work with the latest pak file which is inside typhon hunter. It's called "Pinkeye-windowsnoeditor.pak". I was hoping to decrypt this to take a look at the VR implementation and see if there was a way to merge vr inputs into the main game. Preyconvert.exe returns and error, "failed to open Pinkeye-windowsnoeditor.pak for reading. "
## Post #44
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-07-20T22:52:12+00:00
- Post Title: Re: Prey (2017) pak decryption tool

> Reply from fordyi ↑Sun Jul 21, 2019 12:45 am at Sun Jul 21, 2019 12:45 am
>
> 
HI all, 

I cant seem to get this to work with the latest pak file which is inside typhon hunter. It's called "Pinkeye-windowsnoeditor.pak". I was hoping to decrypt this to take a look at the VR implementation and see if there was a way to merge vr inputs into the main game. Preyconvert.exe returns and error, "failed to open Pinkeye-windowsnoeditor.pak for reading. "

Typhon was created with UE4, not CryEngine like Prey and Mooncrash.
It's due to outsource or whatever, who knows.
## Post #45
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2019-07-21T02:52:27+00:00
- Post Title: Re: Prey (2017) pak decryption tool

> Reply from lolwatt ↑Sun Jul 21, 2019 6:52 am at Sun Jul 21, 2019 6:52 am
>
> 
fordyi wrote: ↑Sun Jul 21, 2019 12:45 am
HI all, 

I cant seem to get this to work with the latest pak file which is inside typhon hunter. It's called "Pinkeye-windowsnoeditor.pak". I was hoping to decrypt this to take a look at the VR implementation and see if there was a way to merge vr inputs into the main game. Preyconvert.exe returns and error, "failed to open Pinkeye-windowsnoeditor.pak for reading. "


Typhon was created with UE4, not CryEngine like Prey and Mooncrash.
It's due to outsource or whatever, who knows.

yeah and it's pak has a AES key on it. that i can NOT figure out how to crack
## Post #46
- Username: fordyi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 21, 2019 12:43 am
- Post datetime: 2019-07-21T07:25:18+00:00
- Post Title: Re: Prey (2017) pak decryption tool

> Reply from lolwatt ↑Sun Jul 21, 2019 6:52 am at Sun Jul 21, 2019 6:52 am
>
> 

Typhon was created with UE4, not CryEngine like Prey and Mooncrash.
It's due to outsource or whatever, who knows. 
[/quote]

Well that already drastically complicates things. I was just hoping to port over the VR inputs into the base game. But with different engines being used, that's already out the window. So it would mean either converting the entire base game into UE4 or writing from scratch a VR implementation for cryengine?
## Post #47
- Username: Locane
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 25, 2019 3:06 pm
- Post datetime: 2019-07-25T07:09:15+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Registered to come and say:

If you are trying to extract a mod you installed to edit and it is named *.pak, try just renaming it to *.zip and extracting it with winrar or winzip.  It might just be zipped.

I had to do that for [https://www.nexusmods.com/prey2017/mods/7](https://www.nexusmods.com/prey2017/mods/7) to up the amount of Mineral material.

Edit:  Although now I'm not sure the mod is working at all, or if it ever was.
## Post #48
- Username: theraineydaze
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 22, 2021 8:29 am
- Post datetime: 2021-06-22T00:31:28+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Does anyone have a mirror for this?
## Post #49
- Username: Sqeegie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 21, 2021 12:22 am
- Post datetime: 2021-09-15T16:27:51+00:00
- Post Title: Re: Prey (2017) pak decryption tool

> Reply from theraineydaze ↑Tue Jun 22, 2021 8:31 am at Tue Jun 22, 2021 8:31 am
>
> 
Does anyone have a mirror for this?

Just replace the original domain with "sirkane.io". I.e. [https://sirkane.io/PreyConvert_003.7z](https://sirkane.io/PreyConvert_003.7z)
[PreyConvert_003.7z](https://xentaxbackup.github.io/file/20791_PreyConvert_003.7z)
## Post #50
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-09-20T15:38:37+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Thanks, this method works great for the textures from Sniper Ghost Contracts for about 90% of the textures. Some of them are still not converted correctly no matter what I do, however. Would anyone here be ok to receive a PM with some sample files that I can't convert? 

Cheers
## Post #51
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-09-20T20:49:04+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Ok, fixed the problem. For anyone else, you have to lower the resolution size for some textures in the dds header. For example, you may need to make a 1024x1024 header say 512x512 to make the texture load in noesis correctly.
## Post #52
- Username: not a russian spy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 15, 2022 11:43 am
- Post datetime: 2022-01-15T13:51:31+00:00
- Post Title: Re: Prey (2017) pak decryption tool

> Reply from HeliosAI ↑Thu May 25, 2017 8:23 am at Thu May 25, 2017 8:23 am
>
> 
Ok what you need:
Noesis (huge thanks here to MrAdults for supporting the normal map format of these properly, even Photoshop doesn't like them much)
Hex Editor
Intel .dds plugin for Photoshop (for the specgloss map thingies)
This .zip with headers:
BC4_Headers.zip
1. Textures are made of these files:

The .dds contains the header info and i think smallest mip level, 1-8 files are increasing mips of the texture. Just take the biggest one (with the highest number, in this case 8, it is the most HD version)

2. Open the .dds and the .8 file in HxD. Switch to the .8 file and select everything with ctrl+a, then copy it with ctrl+c. 

3. Switch to the .dds file and select everyting starting at Offset 94 to the end:

(94 is important, if you do it at for eg 95 your texture will be shifted sidewards and not match the UV)
Then simply paste with ctrl+p and save with ctrl+s.

4. Open texture in Noesis and convert to your format of choice.
You can alternatively open these in Photoshop using the Intel plugins mentioned above. For that open your texture in HxD again and change this small part from whatever it is to 01 (thanks to chrrox for figuring this out): 


5. You may have noticed that _ddn (normal maps) usually don't just have the 1-X files but also files called like 6a,7a,8a. 1-8 belong to normal map, 1a-8a belong to the gloss map.
You have to convert it seperately (as far as i know anyway). I don't know where the game gets this header from, it isn't the .a file. I figured it's BC4 textures however and added a .zip to this post that has headers for the dimensions i came across in the files. The gloss maps here share the dimensions the normal maps have (4k normal map = 4k gloss map). So if it is 4k, open BC4_4k_header.dds and the .8a file in HxD, copy everything from the .8a file again and paste it below the header (offset 80). Save it under a new name you will find easy.
Noesis displays these as plain white, but Photoshop with the linked plugins loads them fine.

6. I noticed that for some reasons the normal map channels seem to be switched (red should be green, green should be red). If you don't do that shading might look quite bad in whatever software you render in.

7. You're finally done and can load them all on your model! Yey!

Actually THERE IS .a file (at least in my case) for glossy maps! But! It's corrupted! So, if you can fix it, it will work just like the rest(i mean that you will be able to do the same thing as with that 1kb .dds files). This also will allow you to WORK WITH GLOSSY MAPS IN NEOSIS!

Here is the way how to solve the problem:

1. Open the .a file in Hex Editor

2. Paste 44 44 53 20 before other stuff that must go after it

3. Save it

4. Work with it like with .dds file from the step 2 of the original post


I hope you will understand what I am trying to say, I also hope that it helped someone  

Not a native English speaker, so... yea
## Post #53
- Username: whynotll83
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 19, 2019 4:30 pm
- Post datetime: 2022-10-12T08:17:55+00:00
- Post Title: Re: Prey (2017) pak decryption tool

No matter what order I paste in hex I can't extract the gloss texture, I don't understand what "before other stuff that must go after it" means.
## Post #54
- Username: whynotll83
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 19, 2019 4:30 pm
- Post datetime: 2022-10-12T21:16:07+00:00
- Post Title: Re: Prey (2017) pak decryption tool

Using hex workshop, changing dx10 to whatever "ATI1" is lets me open the file in photoshop, I got the solution by using the star citizen converter and comparing the differences in file.
Also I confused pasting with replacing as hex doesn't let me write without replacing existing numbers.
