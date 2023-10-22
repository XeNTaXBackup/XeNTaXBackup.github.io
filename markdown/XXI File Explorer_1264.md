## Post #1
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-21T01:03:02+00:00
- Post Title: XXI File Explorer

Here's a link to a program to export and import DDS files into the WAD files of XXI.  Please read the readme.txt file in the installation directory if you have any problems.   Have fun!!


[http://www.angelfire.com/games5/shipyar ... rSetup.zip](http://www.angelfire.com/games5/shipyard/XXIExplorerSetup.zip)
## Post #2
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-05-21T01:31:57+00:00
- Post Title: XXI File Explorer

> Reply from jasmine
>
> Here's a link to a program to export and import DDS files into the WAD files of XXI.  Please read the readme.txt file in the installation directory if you have any problems.   Have fun!!


http://www.angelfire.com/games5/shipyar ... rSetup.zip

Thanks great tool makes exporting the textures easy but still trying to figure out why it won't import my edited ones.
## Post #3
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-21T02:32:36+00:00
- Post Title: XXI File Explorer

> Reply from SuperSSonic
>
> jasmine wrote:Here's a link to a program to export and import DDS files into the WAD files of XXI.  Please read the readme.txt file in the installation directory if you have any problems.   Have fun!!


http://www.angelfire.com/games5/shipyar ... rSetup.zip

Thanks great tool makes exporting the textures easy but still trying to figure out why it won't import my edited ones.

Thanks for the compliment.  As far as your edited files go, make sure you leave the DDS header on them.  The program automatically strips the headers back off when it imports.  Sequence is as follows:

1. Open WAD file

2. Export needed K file

3. Open K file

4. Export needed texture, making sure to select correct DXT type and dimensions.  This is at first trial and error.  You can save a file listing as text so that you can make notes.  Most clothing textures are DXT1 with 4 mipmaps and 256x512.  Most bump files are DXT5 at 256x256.  

5. Edit DDS file in Photoshop, etc.  Make sure they have mipmaps(usually 4) if the originals did.  The file sizes will give you a hint.

6. Open the K file, if not already open, and highlight the name of the file that was edited.  You have to make sure the modded DDS files are in the same directory that you extracted to and that they have the EXACT same name. Click import.  It will automatically strip the DDS header and reinsert.

7.  Open WAD file and Highlight the K file that you edited.

8.  Click import.  It will automatically compress the file before import and add necessary nulls to satisfy the file size for the WAD file.

9.  Upload to box!

I also sent you a pm about Rumble Roses.  Been working on that for awhile and would appreciate some insight.
## Post #4
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-05-21T03:05:44+00:00
- Post Title: XXI File Explorer

I tried those exact steps but so far I only get this message whenever I import:  File Not Present or Incorrect File Size.  Right now I'm just trying to change the hair color of Lita so in the program I choose DXT5 256 X 512 with these settings it appears correctly in photoshop.  I change the color then save the file in DXT5 format and tell it to use existing mip maps.  I then go back to the program and choose import and that is why I'm posting this of course.
## Post #5
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-21T03:17:57+00:00
- Post Title: XXI File Explorer

Lita's hair.dds is a DXT5 with 4 mipmaps.  The program exports it as a DXT5 with no mipmaps.  You will have to generate the mipmaps yourself.(I'll see what I can do with the code)  The plugin that is installed with MS DirectXSDK is a much better plugin for Photoshop.  It has DXT1-DXT5 and you can select the number of mipmaps to generate when the file is saved.
## Post #6
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-05-21T03:25:45+00:00
- Post Title: XXI File Explorer

> Reply from jasmine
>
> Lita's hair.dds is a DXT5 with 4 mipmaps.  The program exports it as a DXT5 with no mipmaps.  You will have to generate the mipmaps yourself.(I'll see what I can do with the code)  The plugin that is installed with MS DirectXSDK is a much better plugin for Photoshop.  It has DXT1-DXT5 and you can select the number of mipmaps to generate when the file is saved.

Thanks for the tip about adding the mip maps it imported fine after adding them in photoshop.  So I guess it is safe to assume that if it doesn't import then you must add mip maps.
## Post #7
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-21T03:54:03+00:00
- Post Title: XXI File Explorer

New version has DXT5 with MipMaps, DXT4 with MipMaps and even 1024x1024(though I don't think there are any).  Just redownload and reinstall.
## Post #8
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-05-21T04:56:06+00:00
- Post Title: XXI File Explorer

> Reply from jasmine
>
> New version has DXT5 with MipMaps, DXT4 with MipMaps and even 1024x1024(though I don't think there are any).  Just redownload and reinstall.

Thanks the new version works great.  I have one last question how do you make some clothes appear invisible?
## Post #9
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-21T06:02:37+00:00
- Post Title: XXI File Explorer

The clothes aren't invisible.  Game won't support alpha that I'm aware of.  Have to manually edit bra and panty to skin.
## Post #10
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-05-21T06:38:36+00:00
- Post Title: XXI File Explorer

> Reply from jasmine
>
> The clothes aren't invisible.  Game won't support alpha that I'm aware of.  Have to manually edit bra and panty to skin.

VV

Figured that it was a BNP match after thinking about it some more.
## Post #11
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-21T11:31:47+00:00
- Post Title: XXI File Explorer

Ah, that was the BNP match.  THEY removed the clothes.
## Post #12
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-05-24T08:18:34+00:00
- Post Title: XXI File Explorer

When I click export it does nothing? Any help?
## Post #13
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-05-24T18:25:01+00:00
- Post Title: XXI File Explorer

You must have the model.k file in the same directory as the program had the same problem then did that and it solved it.
## Post #14
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-05-25T16:25:49+00:00
- Post Title: XXI File Explorer

Thankyou so much!
## Post #15
- Username: CrazyChris
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-26T12:36:47+00:00
- Post Title: XXI File Explorer

This Tool is really usefull, Thanks!


I have a few suggestion for the next Version:

1. We should be able to reimport files of any size and import completely new ones. Tahnks to the XML based Charakter and Envoirenment Indexes we could than Add new Characters and Arenas without overwriting existing ones.

2. It would be really Cool if your Program could convert the *.res files to the DDS Fileformat, i think the res files are just DDS Files without DDS File Header.


Thats it for the moment, I am going to Finish my Bret Hart 1997 Atirre now.
## Post #16
- Username: nautilas
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 02, 2005 6:37 am
- Post datetime: 2005-06-04T17:25:47+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

This was made by XTC to the Max from UTRR Forums and the dds files were saved by me with the correct settings


[http://www.angelfire.com/folk/uploads/Batista_WM21.zip](http://www.angelfire.com/folk/uploads/Batista_WM21.zip)
## Post #17
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-05T14:05:30+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

The arm Textures seem to be corrupted, they can not be opened in Photoshop, not even with a different header.
## Post #18
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-05T17:31:01+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

no there not they open fine
## Post #19
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-06-08T23:19:17+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

> Reply from jasmine
>
> The clothes aren't invisible.  Game won't support alpha that I'm aware of.  Have to manually edit bra and panty to skin.

I figured out that the game does support alpha channels:

17+ To View Links

[http://img.photobucket.com/albums/v150/ ... NLita1.jpg](http://img.photobucket.com/albums/v150/super_saiyan_sonic/NLita1.jpg)
[http://img.photobucket.com/albums/v150/ ... NLita4.jpg](http://img.photobucket.com/albums/v150/super_saiyan_sonic/NLita4.jpg)
[http://img.photobucket.com/albums/v150/ ... NLita3.jpg](http://img.photobucket.com/albums/v150/super_saiyan_sonic/NLita3.jpg)

Also can anyone point me to a program that I can create bump maps with?
## Post #20
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-09T05:26:23+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

Did you alter the actual skin or this present in the game?  In other words, did you have to "paint" the bra and panty to skin tone?
## Post #21
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-06-10T00:51:49+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

> Reply from jasmine
>
> Did you alter the actual skin or this present in the game?  In other words, did you have to "paint" the bra and panty to skin tone?

Yeah I still had to edit the bra and panty but made the Shirt and Shorts invisible using Alpha channels.  I'm sure if i were to make the bra and panty textures invisible there would be holes in the character.
## Post #22
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-10T09:17:48+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

I had someone send me the Goldberg.K file so I could play around with some of his textures until I get my Xecuter chip in the mail. I tried to load the K file, and it seems to load, but there are no textures to extract. Why is this? Does that particular K file not have textures? Or is there some problem with the program running on my PC? I'm pretty sure I have all of the runtimes, so I don't know. If anyone can clue me in that would be great....

IF it IS that particular K file, would someone be kind enough to send me a few K files WITH textures? I would just like to play around with the textures a bit and get the feel for the tool before my chip arrives....
## Post #23
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-10T21:37:23+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

Does anyone have the link to the UTRR Forums? I haven't been there in ages and I thought I'd see what's going on there....
## Post #24
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-10T21:53:05+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

The UTRR Forums went down a long time ago, very sad, good RAW PC Mods were made by the members of that site.
## Post #25
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-10T22:35:36+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

what are you talking about dude utrr's is stil up and running its just got a new forum link 

edit here you go

[http://s8.invisionfree.com/rawpcheaven/index.php](http://s8.invisionfree.com/rawpcheaven/index.php)
## Post #26
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-10T23:02:58+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

Thanks! I didnt know that!
## Post #27
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-11T05:51:06+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

I figured out that my problem was just that particular .K file. So there's no problem now, as other .K files work fine. However, can someone tell me where the blood textures are located? I would have guessed they would be in the indivudual wrestler's .K file, but that doesn't seem to be the case....
## Post #28
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-12T00:11:05+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

The Blood Textures are located in "DVD.WAD\characters\damagetex\Wrestlers_Name".

They are named:

Torso.res
Torso_bump.res
Torso_dm2.res
Torso_bump_dm2.res
Torso_dm3.res
Torso_bump_dm3.res
Head.res
Head_bump.res
Head_dm2.res
Head_bump_dm2.res
Head_dm3.res
Head_bump_dm3.res
## Post #29
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-12T01:38:40+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

How do you import .wav files in the .wad files.
## Post #30
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-12T11:01:17+00:00
- Post Title: Finished Batista Mod for Wrestlemania XXI

You can import them with the XXIExplorer.
They come into the DVD2.WAD file, there are all sounds, even entrance themes, but not the licensed Background Music.
## Post #31
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-12T13:13:50+00:00
- Post Title: 

What is needed to edit the blood files? Obviously they don't export as DDS files....
## Post #32
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-12T13:34:48+00:00
- Post Title: 

You have to Hex edit the RES files, just replace the first 20 bytes of each RES File with a DXT3 Header and edit them in Photoshop. 
After you edited them just Hex edit the old header back and reimport them into the WAD file.
## Post #33
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-12T23:22:16+00:00
- Post Title: 

I have been given a little Webspace and my own Modding Thread over at wrestlinggames.de Forum!

Currently there are six Mod ready to Download, complete with Pictures!

Heres the Link to the Thread:

[http://www.wrestlinggamesboard.de/index ... opic=14181](http://www.wrestlinggamesboard.de/index.php?showtopic=14181)
## Post #34
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-12T23:23:44+00:00
- Post Title: 

Hopefully .RES support will be added to WM21explorer. That would save A LOT of time. Even though WM21 has recived mixed reviews to say the least, if people can easily edit all of the game files I can see this game becoming a wrestling fan's best friend....
## Post #35
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-12T23:39:15+00:00
- Post Title: 

If we could just import completly new files of any size into the WAD files, WrestleMania 21 would be busted WIDE open.
## Post #36
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-12T23:43:36+00:00
- Post Title: 

Holy crap man, awesome mods! How did you do Euegene's jacket? It must have either been left in the game unused, or you edited the character model. The HHH is fantastic by the way, just awesome. May I make a few suggestions? Try to do Shawn Michaels from his Ironman match with Bret, or his WM14 match with Austin. That would be awesome. Mankind with his classic brown attire would be cool too. Or even the new ECW Duldey's. So many possibilities....
## Post #37
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-12T23:55:44+00:00
- Post Title: 

Thanks,

The Developers completed Eugenes Attire, even showed it in early movies of the game, but refered to "eugene.k" and not "eugene_entrance.k" in the "chractertable.xml" as entrance Model.


Tommorow I will start on Batistas new Attire and maybe Music, and after that I will make new HBK Outfits.
## Post #38
- Username: rockcamero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 13, 2005 9:27 am
- Post datetime: 2005-06-13T01:29:45+00:00
- Post Title: 

i have a ?  how do u do this"You have to Hex edit the RES files, just replace the first 20 bytes of each RES File with a DXT3 Header and edit them in Photoshop.
After you edited them just Hex edit the old header back and reimport them into the WAD file." whats a dxt3 header?and can u send me those lita .k files?
## Post #39
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-13T03:22:41+00:00
- Post Title: 

Here you go:

I use Hex Workshop, but any hex editor will do. Then paste this:

4444 5320 7C00 0000 0710 0800 0001 0000 0002 0000 0000 0200 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 2000 0000 0400 0000 4458 5434 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0010 0000 0000 0000 0000 0000 0000 0000 0000 0000

Over this:

0100 0400 0000 0000 0000 0000 290F 9108 0000 0000

Easy as pie really, these instructions are pretty simple, so pretty much everyone should be able to figure it out....

Oh and CrazyChris, the mods are great, but can I offer one tiny piece of advice? Try toning down the blood on the chest just a little bit. The blood on the face is perfect, but the chest is just a bit too much. Try to give it a more "dripping down" look rather than the "smeared on". Although I like the smearing, it's just a bit to much. No offense though, becuase IT IS awesome stuff. A lot better than I could do. Keep up the great work....
## Post #40
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-13T04:03:45+00:00
- Post Title: 

Hey Chris, Your Mods are great.


But, how do you edit the .k files?


Also, I know how to import new titantrons if anybody wants to know how.
## Post #41
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-13T09:57:57+00:00
- Post Title: 

Which file creates the shine effect on tights? I did a heel version of Orton with black and gold tights, but it has the standard blue shine to it. So it's black with a blue polish....
## Post #42
- Username: rockcamero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 13, 2005 9:27 am
- Post datetime: 2005-06-13T14:29:30+00:00
- Post Title: 

how do u import new trons??
## Post #43
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-13T15:38:01+00:00
- Post Title: 

CrazyChris, I tried importing a new blood texture, but I get this message in WM21 explorer:

File is greater than size needed (After compression!)

The thing is, I've got the file size the EXACT same size as the original file. I don't see what is causing the problem and it SHOULD work as far as I can tell. I've included the file, please have a look at it. Maybe you will see some problem I overlooked....
[res.zip](https://xentaxbackup.github.io/file/281_res.zip)
## Post #44
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-13T16:01:03+00:00
- Post Title: 

This is a known Problem with certain RES files but I found a work araound:

Resize Image to 256x128 and save, reopen and resize it back to 512x256 and save it again, now it will import correctly.



Here is the Working RES File:
[Torso_dm3.zip](https://xentaxbackup.github.io/file/283_Torso_dm3.zip)
## Post #45
- Username: rockcamero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 13, 2005 9:27 am
- Post datetime: 2005-06-13T17:53:20+00:00
- Post Title: 

i got a question?  i soft modded my xbox but i have a problem with my music,,,where do i put  custom soundtracks and what format? like what folder and stuff.
## Post #46
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-13T18:53:05+00:00
- Post Title: 

To import trons, you need to convert your videos to xmv. 

there is a tool for that  I think it is called xmvconverter(google)
Also I think your video must be in wndows media 8 format for the xmvconverter to work.

Videos are located in...

cutscene/video



I have a video up of a CrazyChris cena update with my titantron.


[Download](http://www.megaupload.com/?d=162YGS0C)


ALSO 

I can't get the dds file to export from the .k files, what should I be doing?
## Post #47
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-13T21:03:17+00:00
- Post Title: 

Wich .k file makes Problems? The CAW .k and goldberg.k files cant be opened with the XXIExplorer.
## Post #48
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-13T21:25:53+00:00
- Post Title: 

No wrestler works for me.
## Post #49
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-13T22:01:50+00:00
- Post Title: 

Thanks for the .res help CrazyChris, worked fine. Now I understand why your blood textures were distorted a bit....

By the way, do you know where the reflection info is located? I've got a heel Orton made, with black and gold tights, but it still has the default blue polish. So they end up looking kind of green. I need to either remove the polish, or make it so it shines black. Any help would certainly be appreciated....
## Post #50
- Username: rockcamero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 13, 2005 9:27 am
- Post datetime: 2005-06-13T23:42:26+00:00
- Post Title: 

hey hammer make sure the .k file is in the same directory as the XXI eplorer application.
## Post #51
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-14T00:40:29+00:00
- Post Title: 

Thanks, it works now.
## Post #52
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-14T04:15:05+00:00
- Post Title: 

> Reply from Rob Minion
>
> CrazyChris, I tried importing a new blood texture, but I get this message in WM21 explorer:

File is greater than size needed (After compression!)

The thing is, I've got the file size the EXACT same size as the original file. I don't see what is causing the problem and it SHOULD work as far as I can tell. I've included the file, please have a look at it. Maybe you will see some problem I overlooked....

The file import size is not going to be a problem shortly.  Here's the issue:

The file has a header with the indexes at the top.  The indexes are not in sequential order, they are in order alphabetically by file name.  If an import file is larger than the original, then each header index has to be changed in relation to it's file match.  Smaller files are easy to import by adding nulls to the end to make them the same size as the original.
It's possible now.  I'll let everyone know when the bugs are all worked out.  This is a work in progress, slow progress.  

The ability to even duplicate characters is possible now.  This should allow you to create your own characters.  Below is Stacy Vs Stacy, even though the name says Trish.  Didn't edit the graphics at the top, yet.
[StacyVsStacy.jpg](https://xentaxbackup.github.io/file/284_StacyVsStacy.jpg)
## Post #53
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-14T04:26:22+00:00
- Post Title: 

> Reply from jasmine
>
> Rob Minion wrote:CrazyChris, I tried importing a new blood texture, but I get this message in WM21 explorer:

File is greater than size needed (After compression!)

The thing is, I've got the file size the EXACT same size as the original file. I don't see what is causing the problem and it SHOULD work as far as I can tell. I've included the file, please have a look at it. Maybe you will see some problem I overlooked....

The file import size is not going to be a problem shortly.  Here's the issue:

The file has a header with the indexes at the top.  The indexes are not in sequential order, they are in order alphabetically by file name.  If an import file is larger than the original, then each header index has to be changed in relation to it's file match.  Smaller files are easy to import by adding nulls to the end to make them the same size as the original.
It's possible now.  I'll let everyone know when the bugs are all worked out.  This is a work in progress, slow progress.  

The ability to even duplicate characters is possible now.  This should allow you to create your own characters.  Below is Stacy Vs Stacy, even though the name says Trish.  Didn't edit the graphics at the top, yet.

Yes. This is great news.


Also, I found a much quick way to get superstars in such as Goldberg.

You can just edit the character_table and replace a unwanted superstar. 

When the program, is realease there will be no need to replace a superstar.
## Post #54
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-14T09:22:30+00:00
- Post Title: 

Ive been working on a Cena Shirt but it is not turn out right on him, but good on Bubba Ray Dudley

I imported the normal texture and bump map.
## Post #55
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-14T12:11:39+00:00
- Post Title: 

Anyone know how to edit digits_dm3.res?

I made white boots for HHH, bit they turn black at the bottom when he bleeds becuase I didn't edit this file. I know you can edit some of the other blood textures by adding a DXT3 header. But this file doesn't work that way. DXT1 is the only DDS header that gives a result at all, and it's jumbled. The image dimensions are 512 X 256. If anyone can help that would be great....
## Post #56
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-14T17:37:08+00:00
- Post Title: 

The digits_dm3.res file is DXT3 and 256x256.
## Post #57
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-14T17:39:59+00:00
- Post Title: 

> Reply from jasmine
>
> Rob Minion wrote:CrazyChris, I tried importing a new blood texture, but I get this message in WM21 explorer:

File is greater than size needed (After compression!)

The thing is, I've got the file size the EXACT same size as the original file. I don't see what is causing the problem and it SHOULD work as far as I can tell. I've included the file, please have a look at it. Maybe you will see some problem I overlooked....

The file import size is not going to be a problem shortly.  Here's the issue:

The file has a header with the indexes at the top.  The indexes are not in sequential order, they are in order alphabetically by file name.  If an import file is larger than the original, then each header index has to be changed in relation to it's file match.  Smaller files are easy to import by adding nulls to the end to make them the same size as the original.
It's possible now.  I'll let everyone know when the bugs are all worked out.  This is a work in progress, slow progress.  

The ability to even duplicate characters is possible now.  This should allow you to create your own characters.  Below is Stacy Vs Stacy, even though the name says Trish.  Didn't edit the graphics at the top, yet.

Great Work Jasmine!

With this I could create new Attires without overwriting the old ones! 
And even new Arenas are Possible, because the .knv files contain the same headerless DDS Files as the .k files.
## Post #58
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-14T18:30:08+00:00
- Post Title: 

hey everybody anyone wanna try out my orton red and gold tights and take a picture for me? ill give you full credit for the pic thanks dudes!!

[http://www.geocities.com/xtc_stuart/Randyorton.zip](http://www.geocities.com/xtc_stuart/Randyorton.zip) 

/\ download here thanks
## Post #59
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-14T18:38:44+00:00
- Post Title: 

Trying it as I type.

You should upload the whole .k file if you plan on giving it to people with no experince of this stuff.
## Post #60
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-14T18:53:19+00:00
- Post Title: 

o ok sorry ill do that next time you making me a pic mate?
## Post #61
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-14T18:55:09+00:00
- Post Title: 

I was going to take a pic, but it wont allow me to import the .k file into the dvd.wad

it says the file is greater than size needed.
## Post #62
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-14T18:59:49+00:00
- Post Title: 

thats kinda strange try resaving my orton legs to another format of dds
## Post #63
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-14T19:10:47+00:00
- Post Title: 

Still didnt work.
## Post #64
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-14T21:03:30+00:00
- Post Title: 

tried saving them as all the type's? you see orton is a tricky texture it has this stupid thing protecting the texture
## Post #65
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-14T21:06:41+00:00
- Post Title: 

Is it working in your game?

If it is just upload your .k file. Since yours fit in the dvd.wad.
## Post #66
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-06-14T21:21:41+00:00
- Post Title: 

very nice work jasmine, Im sure Ill start working with it as soon as the new program is released.
## Post #67
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-14T21:39:41+00:00
- Post Title: 

nah myne dosent seem to work but me and james crane are working our backside's off to get it working for you guys
## Post #68
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-15T01:32:16+00:00
- Post Title: 

> Reply from CrazyChris
>
> The digits_dm3.res file is DXT3 and 256x256.

AHHH! I feel like such a fool! I tried that header and it failed, so after you posted this, I went back and checked it just to be sure, and sure enough, I had a small typo in my header. What a goof!

Oh, by the way, I noticed that your angle has the same problem my Orton has. Your Angle has a shiny singlet top, but just the top, not the bottom. Even though your Angle has a blue singlet, is has a slight red shine to it. Do you know what cuases this? My Orton has a blue shine on his black tights. This must be fixable, I would image there is a reflection map somewhere....
## Post #69
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-15T04:17:45+00:00
- Post Title: 

Can somebody tell me why my trunk look like this?

The Change colors also from Orange to Black.
## Post #70
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-15T04:49:51+00:00
- Post Title: 

CrazyChris, what did you use to edit the WM21 wav files? I see you got Cena's theme, I was going to screw with some of the music, but they are not standard wav files. Is there a tool to use? Or did you change the header to some other format?
## Post #71
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-15T14:14:45+00:00
- Post Title: 

> Reply from Rob Minion
>
> CrazyChris wrote:The digits_dm3.res file is DXT3 and 256x256.

AHHH! I feel like such a fool! I tried that header and it failed, so after you posted this, I went back and checked it just to be sure, and sure enough, I had a small typo in my header. What a goof!

Oh, by the way, I noticed that your angle has the same problem my Orton has. Your Angle has a shiny singlet top, but just the top, not the bottom. Even though your Angle has a blue singlet, is has a slight red shine to it. Do you know what cuases this? My Orton has a blue shine on his black tights. This must be fixable, I would image there is a reflection map somewhere....

Yeah, this Problem is anoying, I think the Material Shaders are located in the ModelData.bin file but I cant find a way to Open or edit these Files. 


@Hammer:
Add your .k file as an Attachment and I will look at whats causing this error.


The WM21 Sound Files are 22kHz, 4bit Xbox ADPCM WAV files, you can find the Xbox ADPCM Codec at xbins.
## Post #72
- Username: rockcamero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 13, 2005 9:27 am
- Post datetime: 2005-06-15T14:55:34+00:00
- Post Title: 

does anybody know where i can get a texture of brock lenars tattoos? so i can insert it in wwe 21
and rock's big chest and arm tattoo?
## Post #73
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-15T16:39:20+00:00
- Post Title: 

Here's some pics of my HHH mod. Credit goes to CrazyChris for the beard, knee pads, and face blood. The rest is mine 

[http://xs.to/xs.php?h=xs33&d=05243&f=Snapshot0.jpg](http://xs.to/xs.php?h=xs33&d=05243&f=Snapshot0.jpg)

[http://xs.to/xs.php?h=xs33&d=05243&f=Snapshot1.jpg](http://xs.to/xs.php?h=xs33&d=05243&f=Snapshot1.jpg)

[http://xs.to/xs.php?h=xs33&d=05243&f=Snapshot2.jpg](http://xs.to/xs.php?h=xs33&d=05243&f=Snapshot2.jpg)

[http://xs.to/xs.php?h=xs33&d=05243&f=Snapshot3.jpg](http://xs.to/xs.php?h=xs33&d=05243&f=Snapshot3.jpg)
## Post #74
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-16T04:01:26+00:00
- Post Title: 

Here's XXI Explorer v1.2 Setup and Source.  Everyone have fun with it.  I'm moving on to others.  Thanks for all the help and support!

XXI Explorer v1.3 fixed for Window95 and above.  See later post!!
## Post #75
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-16T04:02:57+00:00
- Post Title: 

You are the greatest, Thanks


Edit

I have the run-time files but it still wont work.

It wont even let me register the file with command Prompt.
## Post #76
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-16T05:41:09+00:00
- Post Title: 

Don't understand that.  I just completely removed the program and the zlibtool.ocx and it installed fine.  Anyone else have this problem?
## Post #77
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-16T10:13:36+00:00
- Post Title: 

Yeah, I'm actually having the same problem....

Edit:
I seem to have figured out the problem. The zlibtool.ocx file included with V2 is corrupted. I took the .ocx file from V1 and the tool works fine. So there is a workaround....
## Post #78
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-16T10:57:32+00:00
- Post Title: 

for christ sake now i fucked my xx1 thing up thanks to this stupid v2 i uinstall number 1 then i click to install again it comes up with a stupid message something.dll wasnt found

THANKS A BUNCH

edit 

right i installed v2 and when i go to click to open it it says that zilpb file thing is not found can someone attach to there post the thing i need to put in the folder as i dont have v1 in my pc now
## Post #79
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-16T13:58:43+00:00
- Post Title: 

Chill out. No need to get mad over it, it's a simple fix. Plus it's not like it ruined your work or anything. The tool just won't run. These are user created tools man, appreciate the fact that you are even able to mod this game at all, becuase without people like Jasmine and Brien J, you wouldn't be....

With that said, here's the file. Just install V2, then paste this over the one in C:\Windows\System32....
[zlibtool.zip](https://xentaxbackup.github.io/file/287_zlibtool.zip)
## Post #80
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-06-16T14:22:53+00:00
- Post Title: 

> Reply from XTC
>
> for christ sake now i fucked my xx1 thing up thanks to this stupid v2 i uinstall number 1 then i click to install again it comes up with a stupid message something.dll wasnt found

THANKS A BUNCH
Don't act like a jerk or you will be banned.
## Post #81
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-16T15:06:37+00:00
- Post Title: 

i was making a joke out my situation i wasnt mad or anything well if i upset you or anything 

am sorry
## Post #82
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-06-16T15:23:27+00:00
- Post Title: 

And now I hear that you've been harassing my own fucking brother on MSN. You're banned, loser.
## Post #83
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-16T15:40:11+00:00
- Post Title: 

Great Work Jasmine!

But Your Program corrupts the DVD3.WAD file when importing anything into it, so that the Game crashes while Loading.   

All other WAD files work exept DVD3.WAD.
## Post #84
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-16T19:59:44+00:00
- Post Title: 

You were trying to update an arena?
## Post #85
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-16T20:52:41+00:00
- Post Title: 

It seems to corrupt my DVD.WAD file. It seems to happen when the tool reindex certain files. Say I import a .K file, it imports fine without reindex. But if I import a .RES file, it wil reindex, but then the game locks up before the match....
## Post #86
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-16T21:28:15+00:00
- Post Title: 

Sorry for everyone's trouble with v1.2 but I don't understand why.  I have downloaded the install and completely reinstalled version 1.2.  No problems with the files.  The zlibtool.ocx that was included with v1.2 is a custom compile using zlib v1.14, which is what the game uses.  I did this to ensure the best compression and compatability with the game.  If replacing the zlibtool.ocx with the original works then, by all means, use that.  But the origin of the problem remains a mystery to me.  This software was a lot of fun programming and if anyone else has the desire to continue with it, the source link is included above.

Laters,
Jasmine
## Post #87
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-16T22:06:00+00:00
- Post Title: 

Ok,  another problem, the game won't stop loading, after I selected my two wrestlers, its been loading for over 5 mins and counting I have no Idea whats the problem.

Can anybody else get the game to load after you, imported a new texture?
## Post #88
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-17T11:17:48+00:00
- Post Title: 

I sure hope someone picks up where Jasmine left off. This tool has so much potential. It's a shame V2 is so buggy for some of us. Just out of curiousity, CrazyChris, how is V2 working for you?
## Post #89
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-17T12:09:20+00:00
- Post Title: 

The V2 is perfectly working for me, and thanks to this I am now in the making of the ModPack v1.

This will add new Wrestlers, new Attires, new Titantrons and new high Quality 48kHz Entrance Themes.

And the best thing is that you only need ONE file to import into the WAD Archives, the rest can now be loaded completly externally!

Heres a Screenshot of it:

[http://www.wrestlinggamesboard.de/index ... t&p=215530](http://www.wrestlinggamesboard.de/index.php?showtopic=14181&view=findpost&p=215530)


The only problem I have is the DVD3.WAD file, the XXIExplorer corrupts the file when Importing anything into it.

Thats sad because the developers left a buttload of Developer Arenas in the game like:

ModelViewer.knv
Chracterbuild.knv
Chracterbuil_Divas.knv
WeaponTestRoom.knv

and so on.
## Post #90
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-17T13:16:46+00:00
- Post Title: 

I REALLY wish I could get V2 to run properly. When I use the V1 .ocx file, the program runs, but it seems to corrupt my files. When I use the V2 .ocx, it simply refuses to run. I get this message:

Component zlibtool.ocx or one of it's dependencies not correctly registered. A file is missing or invalid.

Of course, if you try to register it, you get:

Loadlibrary (zlibtool.ocx) failed. The specified module could not be found.

Chris, could you post your zlibtool.ocx file? I know I'm grasping at straws, but I really need to figure this out. There's got to be a reason for this, most likely something on or missing from a select few PC's that is cuasing a problem. Something that Jasmine couldn't test for. Although, the fact that V1 works fine, and V2 WILL RUN with V1's ocx, should be a clue....
## Post #91
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-17T23:42:14+00:00
- Post Title: 

Jasmine, I know you are pretty much finished with this project, but if you could just create an updated .ocx file, that may fix things for all of us. The secret has to be in the .ocx. Me and a couple others can't even run it on the V2 .ocx, and CrazyChris, who has had the best results with V2, even he can't work with DVD3.WAD. And on the other hand, I can run V2 with V1 .ocx, but it corrupts almost everything, obviously becuase it still requires code from the V2 .ocx. Don't get me wrong, I already appreciate the fact that you have given us a tool at all. Without you, we wouldn't be modding this game. But if you could put just a little more time into this tool, I'm sure you could get it working for everyone, and then it would be the ultimate tool. I understand if you are finished with the project and don't wan't to resume work on it, but again, if you could just create a new and improved .ocx file, I'm sure we can all use it. I hope you will consider it, becuase if everyone could use this tool, WM21 modding could really take off. If you decide to give it one last try, I'll help however I can. If you need my PC specs, list of programs I use, or files i need or need to get rid of, just let me know....

Edit:
Just a small note, the V2 .ocx acts is if there is no .ocx at all. The same message comes up regardless of whether you have the V2 .ocx or no .ocx at all. Here's the message:

Component zlibtool.ocx or one of it's dependencies not correctly registered. A file is missing or invalid. 

Plus is won't register. If you try, you get this:

Loadlibrary (zlibtool.ocx) failed. The specified module could not be found. 

So what seems to happening, is that a select few computers ARE NOT recognizing the file. It's as if it's not there. Why? I have no clue, but the original .ocx IS recognized and it WILL run the tool. But it's also missing some code, so it corrups the files you work with.

Maybe you can try creating of .zip of the files rather than an installer. Again, I'm grasping for straws, but who knows? Also, what runtimes\.dlls\files are you working with? I have the standard VB6 runtimes, but there are also updates and service packs that I don't have....
## Post #92
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-18T01:51:47+00:00
- Post Title: 

Rob are you running Windows98 and Chris are you running XP?  I built the zlibtool.ocx on an XP computer and I think it is built for WinVersion XP.  This could be the problem.  Is everyone that's having a problem with v1.2 running Window98?
## Post #93
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-18T02:51:44+00:00
- Post Title: 

Actually, I'm running XP Pro SP2. Even though I'm running XP, I still think you are on to something. The original zlibtool.ocx was built on Windows 95. Yet, it works on my XP system, and the XP built version that you made does not. You said you think it was built for WinVersion XP, but since the Win95 version works for all of us, if you could add support for that or 98, it may just take care of the problem....

Also, are you running Service Pack 2? If not, that could also explain a few things. I've seen many instances of programs working on systems prior to SP2, then not working on SP2....

Either or both of these issues might just be our prolem....
## Post #94
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-18T03:14:15+00:00
- Post Title: 

Here you go.  I recompiled the Zlibtool.ocx with the correct headers and tried it on an old Windows98 computer.  Worked fine.  Let me know if you have any problems.

[http://www.angelfire.com/games5/shipyar ... 3Setup.zip](http://www.angelfire.com/games5/shipyard/XXIExplorerv13Setup.zip)

[http://www.angelfire.com/games5/shipyar ... Source.zip](http://www.angelfire.com/games5/shipyard/XXIExplorerv13Source.zip)
## Post #95
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-18T03:39:44+00:00
- Post Title: 

It pains me to say it, but sadly, the new tool has the same problem. Now I'm pretty much out of ideas. Do you have Service Pack 2? That could still be a possibility if you don't have SP2. If you don't, I'll take SP2 off my old PC and try it. Did you add win98 and 95 support? Or just 98? That's about the only other thing I could think of, maybe 95 is the only thing that will work for some of us. But anyway, I can't thank you enough for trying. I really appreciate it. Maybe we'll figure it out yet....
## Post #96
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-18T04:23:03+00:00
- Post Title: 

I know for one thing, I didnt have the problem with the zlibtool.

I check to see if it still corrupts my files.
## Post #97
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-18T04:25:27+00:00
- Post Title: 

I am out of ideas.  The service pack level on my computer should not matter whether the ocx runs on yours, but I have SP2.    I compiled it with 95 and up support.  The computer I ran it on is an old computer with a non-updated Windows98 on it and it worked fine.  The only thing I can tell you to try is to open "Run" and type "regsvr32.exe zlibtool.ocx" and see if it will register.  Also, if you are running XP then you must be at administration level.
## Post #98
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-18T05:08:08+00:00
- Post Title: 

Well, it looks like I'm S.O.L., I do appreciate everything you did though. I can always use V1, so I still have a few options. I'd love to know if V3 fixed the problem Chris was having with the DVD3.WAD. Let us know when you find out, Chris....

Although, the only other thing I can say about my situation, is that all three of my PC's have the same problem, and they all run XP, installed from the same disc, by me. So whatever the problem is, it's something that occured in the way I setup my PC's, becuase one of my PC's is not even connected to the internet, it's got the original XP files right from the disc, and it STILL has the same problem....
## Post #99
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-18T06:42:15+00:00
- Post Title: 

Hammer, are you saying that v1.3 DID fix your problem with Zlibtool?
## Post #100
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-18T13:16:33+00:00
- Post Title: 

Okay, here is the situation:

Version 1.0 works fine.
Version 1.1 corrupts all archives when importing.
Version 1.2 does ONLY run with an older zlibtool.ocx with 53kb file size, the newer 139kb file will give the error everyone here gets.
Version 1.3 will run fine with the new 69kb zlibtool.ocx file 

BUT...

Version 1.2 and 1.3 will destroy every WAD Archive when importing a file that is smaller or even the size of the original file, the program says "File Imported succesfuly" but the Archive is unuseable after that.
Only files that are significant bigger than the original will import righlty.

And in addition to that Version 1.2+1.3 will render the DVD3.WAD file unuseable no matter what you do with it. Every time you import something, even bigger than the original, the game cant read it anymore.

It would be nice if you could try to repair the XXIExplorer before you go on to other Projects Jasmine, you seem to be the only programmer that has any interest in WM21 and you where a BIG help already, without you we wouldt be modding this game right now.


P.S.
I am running WindowsXP Professional with ServicePack 1.
## Post #101
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-18T16:11:34+00:00
- Post Title: 

CrazyChris, I will look into the file size problem this weekend.  To be honest, the coding really got entangled a bit when I started trying to reindex the files.  I should be able to fix it but I want to do some extensive tests before I release it.  Glad the new zlibtool fixed your problem with that.  In fairness to Mr. Mouse, we are taking up a lot of space on a forum that is dedicated to his software.  If anyone can suggest a forum to move to I am sure Mr. Mouse would appreciate it.  I like the other forum but I can't read German.
## Post #102
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-18T17:56:31+00:00
- Post Title: 

We could bring this discussion to 

[http://forums.xbox-scene.com/index.php? ... owforum=87](http://forums.xbox-scene.com/index.php?s=f4eba68aae4a3b761e90398385390202&showforum=87)

if you like, my username there is "hans9_9" there are already a few WM21 Threads over there.
## Post #103
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-06-18T18:33:33+00:00
- Post Title: 

Did you release the source code, cause if you did, I can prolly fix it.  I thought i remembered you releasing it, but can't find it now.
## Post #104
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-18T20:17:28+00:00
- Post Title: 

Well, I appreciate your concern, but I assure you we don't mind you talking about this stuff here. We used to have a forum called MexMod Central for topics like this one, actually.
## Post #105
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-18T20:46:50+00:00
- Post Title: 

Ok, we will continue the discussion here then.

@brienj:

Heres the v1.3 Source:

[http://www.wrestlinggames.de/mods/wmxxi ... Source.zip](http://www.wrestlinggames.de/mods/wmxxi/tools/XXIExplorerv13Source.zip)

I hope you can help, especially with the DVD3.WAD problem because thats where the Arenas and and environment table are located.
## Post #106
- Username: rockcamero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 13, 2005 9:27 am
- Post datetime: 2005-06-18T20:57:05+00:00
- Post Title: 

can someone help me ...i soft modded my box and i dont know where i can put my music and what  format, so i can have custom soundtracks for wrestlemania 21?
## Post #107
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-06-18T23:26:29+00:00
- Post Title: 

> Reply from CrazyChris
>
> Ok, we will continue the discussion here then.

@brienj:

Heres the v1.3 Source:

http://www.wrestlinggames.de/mods/wmxxi ... Source.zip

I hope you can help, especially with the DVD3.WAD problem because thats where the Arenas and and environment table are located.
Ouch, it's Visual Basic.  I might not be able to do anything.  

If it was written in any form of C or ASM, I'd be able to help a lot easier.  

Maybe I'll write my own program from scratch, if I have the time, although it would be a command-line tool, more than likely.
## Post #108
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-18T23:37:18+00:00
- Post Title: 

I'll take a look at it. I should have a DVD3.WAD file then ...
## Post #109
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-06-20T08:58:49+00:00
- Post Title: 

I made a few Topless Patches for most of the Divas you can get them here:    

[http://www.freewebs.com/supersonicspeed ... 1mods.html](http://www.freewebs.com/supersonicspeed2004/Wrestlemania21mods.html)

 I included the XXI Explorer Version 1 on the site also hope you don't mine jasmine.  I'm going to try and do more wrestler edits and get them on the site also.
## Post #110
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-20T13:47:32+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> I'll take a look at it. I should have a DVD3.WAD file then ...

Sorry but I cant send you a DVD3.WAD file because its 207MB big.


But on another note, can someone help me with the Entrance CSF files? They are completly editable XML files and contain the whole Information about the Entrances. I already figured out how the lightning is controled as you can see here:

[http://www.wrestlinggamesboard.de/index ... t&p=216144](http://www.wrestlinggamesboard.de/index.php?showtopic=14250&view=findpost&p=216144)

But the Problem is that the Hall lightning effects everything exept the Character Model, the Shadow effect in the link above is realised over the spotlight.

If we could read the Environment KNV and and the Model/Animation BIN files someone sure could make an Editor for Entrances.

Unfortuneatly I dont have any programming skills and hope that some here has any Idea about the CSF and most importantly the Model/Animation BIN files.

Heres the CSF file from Triple H`s Entrance:

[http://www.wrestlinggames.de/mods/wmxxi ... ripleh.csf](http://www.wrestlinggames.de/mods/wmxxi/tools/tripleh.csf)

And heres the ModelData.bin file of Triple H.

[http://www.wrestlinggames.de/mods/wmxxi ... elData.zip](http://www.wrestlinggames.de/mods/wmxxi/tools/ModelData.zip)
## Post #111
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-20T14:26:02+00:00
- Post Title: 

> Reply from CrazyChris
>
> Mr.Mouse wrote:I'll take a look at it. I should have a DVD3.WAD file then ...  

Sorry but I cant send you a DVD3.WAD file because its 207MB big.

I see, but you could use the Filecutter tool and send the first and last 1 mb of the file, plus the exact size of the original?

The Filecutter tool you can find at the link in my signature.
## Post #112
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-20T15:04:29+00:00
- Post Title: 

Okay, heres the file:

[http://www.wrestlinggames.de/mods/wmxxi ... D3.wad.zip](http://www.wrestlinggames.de/mods/wmxxi/tools/DVD3.wad.zip)

The exact file size of DVD3.WAD is "207.503.360 bytes"
## Post #113
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-20T17:36:10+00:00
- Post Title: 

Okay, so , but the Explorer extracts fine from the DVD3.WAD but import fails? Is the DVD3.wad also the biggest file?
## Post #114
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-20T17:58:31+00:00
- Post Title: 

Yes the explorer extracts everything just fine, but importing anything makes the Archive unreadable for the Game.

DVD3.WAD is actually the smallest WAD file, the biggest is DVD2.WAD with 311MB followed by DVD.WAD with 270MB.
## Post #115
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-20T18:42:58+00:00
- Post Title: 

Small update: I removed the code using the Zlibtool.ocx. It now uses zlib.dll (which should be in your windows/system32 dir already if you ever installed MultiEx Commander).



[EDIT] I have changed the file. Please download again, if you already did.
[XXIExplorer1_1.zip](https://xentaxbackup.github.io/file/296_XXIExplorer1_1.zip)
## Post #116
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-20T19:31:18+00:00
- Post Title: 

Thanks for your effort but the Game still crashes after importing something into the DVD3.WAD file.

Its the same Game as before, I import the environments.xml file wich is larger than before, the program Re-Indexes it and after that WM21 will freeze while trying to load DVD3.WAD.

I really dont have a clue what the problem can be.
## Post #117
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-20T20:54:41+00:00
- Post Title: 

Well, I did say it was only a small update. I did not try to fix anything related to the dvd3.wad file. 

I wanted to take away any problems that people had with the zlibtool. 

Does importing work for all the other wads? 100%?
## Post #118
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-20T21:16:46+00:00
- Post Title: 

Ah, I see. 

Yes all other files work fine now, thanks.
## Post #119
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-06-21T01:44:34+00:00
- Post Title: 

It's been a long time since I messed around with the game, but that WAD file isn't cached, right?  Plus the game executable may actually chack that file for any changes.  If I can pull myself away from the other games I am currently invloved with, I will try and take a look at it.
## Post #120
- Username: rockcamero
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 13, 2005 9:27 am
- Post datetime: 2005-06-21T01:47:50+00:00
- Post Title: 

hey supersonic what files do i patch for the divas files u posted?
## Post #121
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-06-21T02:06:48+00:00
- Post Title: 

> Reply from rockcamero
>
> hey supersonic what files do i patch for the divas files u posted?

You patch the .k files with the same names as the patches located in the DVD.wad.
## Post #122
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-21T03:31:53+00:00
- Post Title: 

I think the problem that some people are having with the DVD2.wad file is the format of the WAV files.  They are XBOX ADPCM , 22050 Hz frequency, 2 channels, 4 bit, compressed format(at least the ones I've seen).  You can download the codec at :

[http://www.xbox-scene.com/tools/tools.php?page=driver](http://www.xbox-scene.com/tools/tools.php?page=driver)

You can download a free audio converter to convert to this format(after you install the above codec!) here:

[http://www.dbpoweramp.com](http://www.dbpoweramp.com)

If you want to try yet another version of XXI Explorer, here's a link.  I have tried this with numerous imports and exports with no problems. 

[http://www.angelfire.com/games5/shipyar ... 1Setup.zip](http://www.angelfire.com/games5/shipyard/XXIExplorerv131Setup.zip)

Thanks for the space and time, Mr. Mouse.  And by the way, what did you change to use the zlib.dll compression.  I couldn't get the compression to compress enough without using the zlibtool.ocx compiled with the 1.14 zlib source.  The zlibtool uses the compress2 function and I modified the source to provide max compression.  That shouldn't be a problem now because XXI Explorer will re-index the headers.  

Also, SuperSonic, what format did you use for the DDS files with Alpha??
## Post #123
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-06-21T06:39:08+00:00
- Post Title: 

> Reply from jasmine
>
> 
Also, SuperSonic, what format did you use for the DDS files with Alpha??

I used DXT1 with Mip Maps and the correct size of the texture of course and I then just added an Alpha Channel to them in photoshop and made that all black.  I also did the exact same for the bump files for the clothes and those were in DXT5 with No Mip Maps(not sure if this part is needed but did it just in case).
## Post #124
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-21T11:30:14+00:00
- Post Title: 

> Reply from brienj
>
> It's been a long time since I messed around with the game, but that WAD file isn't cached, right?  Plus the game executable may actually chack that file for any changes.  If I can pull myself away from the other games I am currently invloved with, I will try and take a look at it.

The only Cached WAD file is HD.WAD. 
And yes the executable does a check on the files, if something is wrong with them it gives you a dirty disk error.
## Post #125
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-22T03:40:12+00:00
- Post Title: 

> Reply from CrazyChris
>
> 
The only Cached WAD file is HD.WAD. 
And yes the executable does a check on the files, if something is wrong with them it gives you a dirty disk error.

Actually the game only checks the compressed size of the files in the WAD's.  (Errors within those files, i.e. bad textures, will crash the game simply because the executable can't handle them.)   I know this because XXI Explorer adds NULLS to the end of the compressed files if they are smaller than the originals after compression and before import.  I found this out by first modding with a hex editor.  The only exemption to this seems to be the xml files in the WAD's.  It appears the game is checking the decompressed sizes and validity of the data within.  This may also be a possibility with the model data(if we ever figure that out!).
## Post #126
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-22T06:48:02+00:00
- Post Title: 

If it checks the compressed sizes, surely it must have some table somewhere where to compare them with?
## Post #127
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-06-23T08:33:42+00:00
- Post Title: 

I can't believe the amount of work thats going on here! Thank you all so much!
## Post #128
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-24T03:29:21+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> If it checks the compressed sizes, surely it must have some table somewhere where to compare them with?

Ooops,  I was entirely wrong with that Mr. Mouse.   I was referring to the header offsets.  Anyway, here's a new version of XXI Explorer.  Version 1.5.  It now uses the zlib.dll instead of the zlibtool.ocx(Thanks Mr.Mouse!) and I added right-click import and export(seems to be easier to me). --  Mr. Mouse, I used compress2 instead of compress because I could change the value of the compression to MAX.  I know it's trivial but it eliminates the need to reindex many of the times when importing.  This is why I used the ocx to begin with but, after a little research, I found the info you were talking about in your mod.  Thanks again.   Here's the link:

[http://www.angelfire.com/games5/shipyar ... 5Setup.zip](http://www.angelfire.com/games5/shipyard/XXIExplorerv15Setup.zip)

Hey, somebody figure out those damn model files!  I've lost way too much sleep on them.
## Post #129
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-06-24T13:01:02+00:00
- Post Title: 

Now theres the same error that was on the zlib, but on comdlg32.ocx.
## Post #130
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-24T13:23:55+00:00
- Post Title: 

This is not due to the zlib process I think, but to some new features.
## Post #131
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-24T18:06:03+00:00
- Post Title: 

> Reply from greendayduh
>
> Now theres the same error that was on the zlib, but on comdlg32.ocx.

To anyone having problems with this program, please download this file, unzip and install:

[http://www.angelfire.com/games5/shipyar ... ntimes.zip](http://www.angelfire.com/games5/shipyard/VB6sp6runtimes.zip)

This is the LATEST visual basic runtime files available from microsoft.  This will solve problems people have running the software.  Mr. Mouse, I think I will learn C++ now.
## Post #132
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-06-24T19:45:16+00:00
- Post Title: 

> Reply from jasmine
>
> greendayduh wrote:Now theres the same error that was on the zlib, but on comdlg32.ocx.

To anyone having problems with this program, please download this file, unzip and install:

http://www.angelfire.com/games5/shipyar ... ntimes.zip

This is the LATEST visual basic runtime files available from microsoft.  This will solve problems people have running the software.  Mr. Mouse, I think I will learn C++ now.
If you need any help with C++ let me know.
## Post #133
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-06-24T23:06:03+00:00
- Post Title: 

I'm afraid I still get the same message.
## Post #134
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-06-25T11:23:48+00:00
- Post Title: 

If anyone else has the same toruble as me, I search and downloaded the extra files and I can get the program running. So Ive uoploaded the 2 extras I needed. Extract them to your XXI Explorer folder.

[http://lukereeve.co.uk/extrafiles.rar](http://lukereeve.co.uk/extrafiles.rar)

Note: I imported a larger head.dds and the game crashed.
## Post #135
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-25T21:17:06+00:00
- Post Title: 

Hey, has anybody ever looked at the hex of a Created Wrestler?

When, I did, I saw this.


C:Gigante/Created Character/lukas costumes/Head.res

there are others also.
C:Gigante/Created Character/lukas costumes/Legs.res
C:Gigante/Created Character/lukas costumes/Legs_bump.res
C:Gigante/Created Character/lukas costumes/Torso_bump.res
C:Gigante/Created Character/lukas costumes/Hand_L.res
C:Gigante/Created Character/lukas costumes/Hand_L_bump.res
C:Gigante/Created Character/lukas costumes/Hand_R.res
C:Gigante/Created Character/lukas costumes/Hand_R_bump.res
C:Gigante/Created Character/lukas costumes/Shoes.res
C:Gigante/Created Character/lukas costumes/Shoes_bump.res
C:Gigante/Created Character/lukas costumes/Eye_L.res
C:Gigante/Created Character/lukas costumes/Eye_R.res
C:Gigante/Created Character/lukas costumes/Lowerleg_L.res

Just to name a few, there are tons of them.

Too bad, I can't find that directory.

It would be much easier to make new wrestlers if we could find that
directory.
## Post #136
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-25T21:33:07+00:00
- Post Title: 

> Reply from Hammer
>
> Hey, has anybody ever looked at the hex of a Created Wrestler?

When, I did, I saw this.


C:Gigante/Created Character/lukas costumes/Head.res

there are others also.
C:Gigante/Created Character/lukas costumes/Legs.res
C:Gigante/Created Character/lukas costumes/Legs_bump.res
C:Gigante/Created Character/lukas costumes/Torso_bump.res
C:Gigante/Created Character/lukas costumes/Hand_L.res
C:Gigante/Created Character/lukas costumes/Hand_L_bump.res
C:Gigante/Created Character/lukas costumes/Hand_R.res
C:Gigante/Created Character/lukas costumes/Hand_R_bump.res
C:Gigante/Created Character/lukas costumes/Shoes.res
C:Gigante/Created Character/lukas costumes/Shoes_bump.res
C:Gigante/Created Character/lukas costumes/Eye_L.res
C:Gigante/Created Character/lukas costumes/Eye_R.res
C:Gigante/Created Character/lukas costumes/Lowerleg_L.res

Just to name a few, there are tons of them.

Too bad, I can't find that directory.

It would be much easier to make new wrestlers if we could find that
directory.

Those were the directories on the computer that the game was compiled on.  You are not going to find those directories in the game.  The size of the textures are also missing or placed elsewhere within the CAS files.  Different format than the .k files.
## Post #137
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-25T21:37:48+00:00
- Post Title: 

Too bad.   

But, on a bright note...  
 Jasmine 1.5 works great, I can finally put my mods in.

Here's my Shawn Micheals
## Post #138
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-06-26T08:58:44+00:00
- Post Title: 

Hammer, were your textures same size when u reimported. Because I imported a texture into Charlie Haas K file which was slightly bugger than the the original and it now crashes.
## Post #139
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-06-26T17:18:43+00:00
- Post Title: 

I think it was smaller.
## Post #140
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-06-29T22:19:41+00:00
- Post Title: 

That HBK is really good. You should post it as a download....
## Post #141
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-07-06T02:54:54+00:00
- Post Title: 

> Reply from SuperSSonic
>
> I made a few Topless Patches for most of the Divas you can get them here:    

http://www.freewebs.com/supersonicspeed ... 1mods.html

 I included the XXI Explorer Version 1 on the site also hope you don't mine jasmine.  I'm going to try and do more wrestler edits and get them on the site also.

I just tried inserting these files into dvd.wad and it freezes my game. It would be nice if you actually gave us some info on the mod and why you choose the weird ppf format. Ive succeffuly insterted other mods into the game but cant get this  2 work. Its a real hassle copying the wad files back and forth so please fix this.
## Post #142
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-07-10T02:21:01+00:00
- Post Title: 

> Reply from Online_Dude
>
> 

I just tried inserting these files into dvd.wad and it freezes my game. It would be nice if you actually gave us some info on the mod and why you choose the weird ppf format. Ive succeffuly insterted other mods into the game but cant get this  2 work. Its a real hassle copying the wad files back and forth so please fix this.

EDIT:  Totally new site now with all the skins as separate rars and a couple new ones ignore the site address name:  [http://www.freewebs.com/doa2uskins/](http://www.freewebs.com/doa2uskins/)
## Post #143
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-07-10T14:37:05+00:00
- Post Title: 

In case you people didnt noticed, I have released my ModPack v1 with 31 New Skins and many more!

Heres the Link:

[http://www.wrestlinggamesboard.de/index ... t&p=220243](http://www.wrestlinggamesboard.de/index.php?showtopic=14470&view=findpost&p=220243)


And here are a few Screenshots:

[http://www.wrestlinggames.de/mods/wmxxi ... shots.html](http://www.wrestlinggames.de/mods/wmxxi/mods/modpack_v1/screenshots.html)
## Post #144
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-07-13T02:36:10+00:00
- Post Title: 

Hey Sonic, could you please send the individual .K files to [robminion@hotmail.com](mailto:robminion@hotmail.com)? I'm on 56K and the download always cuts off about halfway through. Plus the server doesn't support resuming, so unles you'll help me out, I'm boned.
## Post #145
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-07-14T12:16:48+00:00
- Post Title: 

Is anyone still Modding beside of me?

We at wrestlinggames.de have found out that the destroyable Announcer Tables are still in the Cage Arenas and working!

Now we have to find a way to get these Tables into the Standard Arenas.
## Post #146
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-07-14T23:38:34+00:00
- Post Title: 

Just about, but if you figure out how to edit the arena's count me back in.


When you find out(if you remember, no biggie) email me @

[KDRUMM2K6@gmail.com](mailto:KDRUMM2K6@gmail.com)
## Post #147
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-07-16T18:19:34+00:00
- Post Title: 

I'm still modding everyday. I just finished a massive update to your modpack, Chris. I've updated it so it adds the refs(Including Hebner), ALL intro attires, The unused Trish attire, the unused Rene Dupree intro attire, plus I've got it so Earl Hebner is now the default RAW ref. Plus I've finished my HIAC HBK, and HHH in blue, red and purple. Here's some pics:

[http://xs36.xs.to/pics/05273/hbk00.jpg](http://xs36.xs.to/pics/05273/hbk00.jpg)
[http://xs36.xs.to/pics/05273/hbk1.jpg](http://xs36.xs.to/pics/05273/hbk1.jpg)
[http://xs37.xs.to/pics/05284/hhh0.jpg](http://xs37.xs.to/pics/05284/hhh0.jpg)
[http://xs37.xs.to/pics/05284/hhh1.jpg](http://xs37.xs.to/pics/05284/hhh1.jpg)
[http://xs37.xs.to/pics/05284/hhh2.jpg](http://xs37.xs.to/pics/05284/hhh2.jpg)
[http://xs37.xs.to/pics/05284/hhh3.jpg](http://xs37.xs.to/pics/05284/hhh3.jpg)

Those HHH pics are a bit outdated, i changed the blue and red HHH so it uses your clean shaven face, Chris. How about this breakable table stuff? sounds very cool, Hopefully this is figured out soon. Also, did you ever figure out how to fix the bloody mats? I've been pretty much just texture modding, so I really haven't been looking into it....
## Post #148
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-07-16T19:40:21+00:00
- Post Title: 

Very good work Rob Minion.

I havent found a solution to the Mat Texture Problem yet.

The developers left the Breakable Announcer tables in the Cage Match Arenas, I hope that Mr.Mouse can help us with the Arena KNV files so that we can add these to the normal Arenas.
## Post #149
- Username: Rob Minion
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 21, 2004 5:03 am
- Post datetime: 2005-07-18T19:15:37+00:00
- Post Title: 

Thanks. I also did a quick Goldberg blood texture:
[gold00.jpg](https://xentaxbackup.github.io/file/365_gold00.jpg)
## Post #150
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-08-02T16:27:31+00:00
- Post Title: 

Anybody made any more progress on this?
## Post #151
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-08-18T11:51:37+00:00
- Post Title: 

XXI Explorer looks to be a little off with its extracting.

After the 4 byte MF10 ID there's a 4 bytes file size. I extracted batwood.k and it has 9 bytes appended to the end of that.

And when opening and extracting ModelData from a .k file using XXI Exp1.5 It also isn't right. It cuts quite a few bytes off the end. And after the ModelData is a full model header it looks.

I hope to see this corrected as It was interfering with me working on model and animation formats. 

But accordingly, this what I have on the model and animation formats.

0X25 4 bytes - Number of bones
[Skeleton Data]
4 bytes - String Length+1
x bytes - bone name
4 bytes - x coord?
4 bytes - y coord?
4 bytes - z coord?
[/skeleton] - Repeat # Bone Times

4bytes - padding/end of skeleton - 01 00 00 00

4bytes - Number of Surfaces
[Surfaces]
4bytes - String length+1
xbytes - surface name
1bytes - subheader length?
xbytes - subheader/special flags?
4bytes - Number of Verts
4bytes - padding?
xbytes - mesh data
4bytes - number of morph targets
[morph target]
4bytes - String Length+1
xbytes - Morph target name
4bytes - number of verts
xbytes - morph data
[/morph target] - repeat # morph target times
4bytes - number of morph targets
4bytes - String Length+1
xbytes - Morph target name
4bytes - padding?
4bytes - morph number (starts at 00)
[/Sufaces] - repeat # surface times

Thats condensed. "Mesh data" contains what looks like 3 sections (probably - vert, poly/normal, uvw), And Morph data is just the verts at different offsets.


Animation:

header
4 bytes - Size of File -1 byte (probably being extracted wrong)
7 bytes - unknown
4 bytes - Number Bones (65 for all files I've looked at)
4 bytes - end of Bone Index
4 bytes - unknown
4 bytes - unknown

There's a 260 byte Bone? Index (4 byte blocks, 65 blocks) with pointers into the actual data.

thq_stancerotate was easiest to follow. Each data block was 10 bytes. But some of the larger anims have much larger blocks and they don't all have the same size blocks internally. I couldn't find any size offsets offhand.

Anyways full animation goes in this format.

Header
Unknown Chunk
Index
Unknown Chunk
Data Chunk

referenceSkeleton.bpc - Listing of various skeleton packages?
## Post #152
- Username: Satan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 07, 2005 12:05 am
- Post datetime: 2005-09-10T22:36:42+00:00
- Post Title: 

I'm having problems making skins for superstars using XXI Explorer v1.5. I know you have to export the superstars .k file and export the dds files you want to edit. My problem is whenever I edit a skin it crashes the game. I've tried different dds and k files but the result is always the same   How should I go about it ? Are there certain dds formats/dimensions I should use or maybe a different XXI Explorer version ? Any help would be appreciated.
