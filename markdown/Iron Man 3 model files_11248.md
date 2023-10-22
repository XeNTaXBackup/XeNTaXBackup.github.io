## Post #1
- Username: Nintynuts
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 26, 2011 1:46 am
- Post datetime: 2014-02-23T23:58:31+00:00
- Post Title: Iron Man 3 model files

Hello,
I have been researching how to read the model files from the gameloft game Iron Man 3 (in my case for android).
So far I have:
- Extracted the OBB
- Extracted the model (bdae) and texture (pvr) archives
- Converted the textures
- Identified the useful parts of the model files

Other users on this forum; renato (who also frequents [http://www.therpf.com/f78/iron-man-3-su ... ea-183397/](http://www.therpf.com/f78/iron-man-3-suit-reference-idea-183397/) as Balmung) and zaramot have made progress on this already.

Here is my problem...
I can generate a mesh with UV coordinates from a single file by manually tweaking a max script to select different areas of the file, but I would like to understand the file structure better in order to be able to navigate to this point based on data in the file, and possibly also get more from it like bones, skinning (for animation) and materials (mainly so I know it inverts the normals for the mirrored half). At the moment only the first 3 floats and the last long are being used from the 52 bytes of each vertex, and I'd like to know what they are (I expect probably normals and stuff, but haven't tested)
As well as knowing the patterns to look for in the hex to do it manually, I have also found the array lengths in the file too, but only relative to the mesh/vertex data, not the start of the file as it moves.

I am attaching an excel spreadsheet with the analysis I have been trying to do on the file.
- Sheet 1 - High Level: this page summarises what sections I (think I) have identified in the file structure, two examples the Mk 2 and Mk 42 (first and last in the game)
- Sheet 2 - Header Analysis (Low Level): this page contains dumps of each armour file's header section. I have identified very little of it, but I have managed to identify patterns and try to break it into sections based on this. The left hand column details the min, median, max and mode values for each long in the file (taking into consideration the gaps I have made to try to mark sections). To the best of my understanding, most of this seems to be junk. The values usually just increase by 4 from an initial starting number marked in red at the top. You will notice on the left there is also a percentage. I find this useful to see where there are file-unique numbers which might be useful. One thing to bear in mind is that I'm mostly taking interest in the DIFFERENCES between the long in the file and the previous long, not the actual value. One last note - Mark 38 (Igor) doesn't seem to match up with any of this. Don't ask me why...

If this header data is indeed junk, at least the last 4 longs in each file are identical, so that lets me jump to the strings, which are easy to navigate through.

I would really appreciate any assistance in decoding these files further from someone with more experience with binary file reverse engineering.

NOTE: The zipped excel sheet has a macro for converting hex to a float I found on the net. Nothing dodgy. I had to remove all the formulas in the second column of each file to reduce the file size to upload, so just copy the formula down for each file to restore it (I don't know why excel can't compress this somehow).
[Hex Translator.zip](https://xentaxbackup.github.io/file/7038_Hex Translator.zip)
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-02-25T12:48:08+00:00
- Post Title: Iron Man 3 model files

Hi Nintynuts, I recieved your message, so I'm working on this now. I'm going to finish maxscript if I will have time. I've got models imported for all Iron Man costumes with bones+weights. still must finish script for all data types+nice skeleton hierarchy (didn't find parenting info yet).
[Iron_Man_3_Mark_36.jpg](https://xentaxbackup.github.io/file/7041_Iron_Man_3_Mark_36.jpg)
## Post #3
- Username: Nintynuts
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 26, 2011 1:46 am
- Post datetime: 2014-02-25T22:06:18+00:00
- Post Title: Iron Man 3 model files

> Reply from zaramot
>
> Hi Nintynuts, I recieved your message, so I'm working on this now. I'm going to finish maxscript if I will have time. I've got models imported for all Iron Man costumes with bones+weights. still must finish script for all data types+nice skeleton hierarchy (didn't find parenting info yet).

Hey, thanks for replying. Glad to see you're making progress. Did you get to have a look at my spreadsheet? Does any of my structural analysis seem right to you (does it match what you've found)?

I would be very interested in any hints you could give me. I would like to try and figure as much out for myself as I can, but as I'm new to this I'm a bit stuck.
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-02-26T20:12:55+00:00
- Post Title: Iron Man 3 model files

Hi, no I haven't checked your spreadsheet yet, but I will. I will share info a bit later. As I understand this format .bdae is pretty common for android, game Batman: The Dark Knight Rises uses same format and it's similar to Iron Man. Just different version I guess.
[bat.jpg](https://xentaxbackup.github.io/file/7079_bat.jpg)
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-03-07T09:48:41+00:00
- Post Title: Iron Man 3 model files

Here's simple script to import Iron Man's armors with bones/weights and to analyze format a bit. Don't try it on files with _noskin at the end of the file's name, they aren't skinned meshes (no skeleton inside) - script will crush!
[Iron_Man_3.7z](https://xentaxbackup.github.io/file/7078_Iron_Man_3.7z)
## Post #6
- Username: Nintynuts
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 26, 2011 1:46 am
- Post datetime: 2014-03-08T00:06:21+00:00
- Post Title: Iron Man 3 model files

> Reply from zaramot
>
> Here's simple script to import Iron Man's armors with bones/weights and to analyze format a bit. Don't try it on files with _noskin at the end of the file's name, they aren't skinned meshes (no skeleton inside) - script will crush!

Thanks, I'll look at it this weekend hopefully. Did you get around to looking at my spreadsheet? (I guess I'll see whether I'm right when I look at your script)
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-06-11T22:17:56+00:00
- Post Title: Iron Man 3 model files

zaramot, great work on the script. can you look into Knight Rival's files, seems same .bdae, but your script don't wont import geometry, not crashing though
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-06-12T19:57:13+00:00
- Post Title: Iron Man 3 model files

Maybe you could provide samples? If those .bdaes are more similiar to Iron Man's ones, it will be not hard to get models.
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-06-12T21:19:19+00:00
- Post Title: Iron Man 3 model files

> Reply from zaramot
>
> Maybe you could provide samples? If those .bdaes are more similiar to Iron Man's ones, it will be not hard to get models.
sure, here it is
[http://www.mediafire.com/download/jcgtv ... armors.zip](http://www.mediafire.com/download/jcgtv3b5advrycr/rival_knights_ios_armors.zip)

btw, i got dark knight rises, but your script doesn't work with it, can you tell me why?
## Post #10
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-06-13T07:43:33+00:00
- Post Title: Iron Man 3 model files

I didn't released Dark Knight Rises script, .bdae format there differs much from Iron Man's
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-06-13T08:55:48+00:00
- Post Title: Iron Man 3 model files

> Reply from zaramot
>
> I didn't released Dark Knight Rises script, .bdae format there differs much from Iron Man's
would you release script for dark knight? the game has so many rare models.
## Post #12
- Username: xtrem1275
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 01, 2017 3:45 pm
- Post datetime: 2017-01-01T17:34:33+00:00
- Post Title: Iron Man 3 model files

Hello good morning and happy new year,my name is Cesar Diaz Espinosa, I'm from Mexico, and I'm new to the page, I hope to be able to contribute, looking at the network on the iron man armor 3 of the android game, to make the armor in papercraf, to scale, I found this page, and extracted some of the armors, but could tell me How to extract the textures, the armatures I extracted are mark 15,18,19,20,24,27,28,32,36,43, the mark 31 marks me error in the script, thanks I hope someone could guide me, and If anyone wants the models they will gladly share them
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-01-01T17:42:30+00:00
- Post Title: Iron Man 3 model files

If you extracted android version, than textures are just .tga files. So, you could rename texture extension into .tga and use any image software you like. And be prepared for some uv's edits, when I was working on these sample I didn't have textures, they may look nice, though - they are a bit off xD

P.S. I advice you to use iOS version of the game, textures there are twice bigger in size than in android version
## Post #14
- Username: xtrem1275
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 01, 2017 3:45 pm
- Post datetime: 2017-01-01T18:50:54+00:00
- Post Title: Iron Man 3 model files

Hello zaramot, the files of the iron man 3 game that I have, the textures comes in .and format, I am not an expert on the subject, but I like to learn to do new things, you could guide me how to convert them or change the format to tga, bmp Or jpg, thanks for your quick response
## Post #15
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-01-01T19:36:25+00:00
- Post Title: Iron Man 3 model files

This "conversion" will be extremely easy xD Just change .and extension to .tga and you will see, that those .and files are just .tga files which you could open with photoshop for example
## Post #16
- Username: xtrem1275
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 01, 2017 3:45 pm
- Post datetime: 2017-01-02T00:29:55+00:00
- Post Title: Re: Iron Man 3 model files

Thanks I did what you indicated but, I get error, in photoshop, just change the extension to. Tga, and says that the file can not decompose read error, I'll keep trying something I'm doing wrong
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-02T01:38:05+00:00
- Post Title: Re: Iron Man 3 model files

can you please upload some samples that giving you problem?
## Post #18
- Username: xtrem1275
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 01, 2017 3:45 pm
- Post datetime: 2017-01-02T02:28:45+00:00
- Post Title: Re: Iron Man 3 model files

These are the files that come in the textures folder, and I'll attach the model in obj format, Put the download link is in mediafire
[http://www.mediafire.com/file/ytce4xrq1 ... ark_15.rar](http://www.mediafire.com/file/ytce4xrq1gb9nag/mark_15.rar)
## Post #19
- Username: xtrem1275
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 01, 2017 3:45 pm
- Post datetime: 2017-01-02T03:30:21+00:00
- Post Title: Re: Iron Man 3 model files

These are the files that come in the textures folder, and I'll attach the model in obj format, Put the download link is in mediafire
[http://www.mediafire.com/file/ytce4xrq1 ... ark_15.rar](http://www.mediafire.com/file/ytce4xrq1gb9nag/mark_15.rar)
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-02T05:03:42+00:00
- Post Title: Re: Iron Man 3 model files

yeah these don't look like typical tga and they have pvr in the header,
unfortunately i never have much luck with pvr texture data or mobile
texture formats in general.  

edit
the structure seems to follow legacy pvr specs here
[http://cdn.imgtec.com/sdk-documentation ... Legacy.pdf](http://cdn.imgtec.com/sdk-documentation/PVR+File+Format.Specification.Legacy.pdf)
and according to the "Pixel Format" of the samples they are ETC
## Post #21
- Username: xtrem1275
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 01, 2017 3:45 pm
- Post datetime: 2017-01-02T06:54:46+00:00
- Post Title: Re: Iron Man 3 model files

Thanks for your help, I'll keep looking to see if I can find a solution, thanks for your time, we'll keep in touch, on this page there's a lot I can learn and improve goodnight
## Post #22
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-01-02T09:18:03+00:00
- Post Title: Re: Iron Man 3 model files

Yes, those files aren't .tga xD Then, it's depends on the version of the game. Though, there's a way to help you. For those files you can use PVRTexTool it's a part of PVR SDK and it's free. Or here I uploaded files from android version I used (. change extention from .and to .tga) or last variant you could use iOS version, and I recomend you to do it, textures are better there, and you can open-convert them with PVRTexTool I mentioned above.

[https://www.sendspace.com/file/bpk7o0](https://www.sendspace.com/file/bpk7o0)
## Post #23
- Username: xtrem1275
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 01, 2017 3:45 pm
- Post datetime: 2017-01-02T17:56:19+00:00
- Post Title: Re: Iron Man 3 model files

Thanks, the truth I only saw on the internet that sometimes you can extract the models of android games and download a page that already had the apk and data, and extracted the models, I do not remember which version it was but said it was the That I had the last armors, I am part of a page that is called [https://elpaisdelpapercraft.blogspot.mx/](https://elpaisdelpapercraft.blogspot.mx/) and we are trying to gather all the armors to make them to scale, I have several models that I have compiled, for some years, some Few models I have done are simple but as I told you I want to learn, and to learn you have to surround yourself with people who know, thank you
## Post #24
- Username: xtrem1275
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 01, 2017 3:45 pm
- Post datetime: 2017-01-02T18:17:28+00:00
- Post Title: Re: Iron Man 3 model files

When I finish editing the models and I will put them on the page you will be in the credits for the great help that they gave me, and I hope to learn more from you, thank you, now start editing, in maya and then in pepakura, thanks and you have a good day
## Post #25
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-01-02T19:18:14+00:00
- Post Title: Re: Iron Man 3 model files

No problem  I'm glad to help! Actually I'm collecting ironman's armors myself - I have a lot of high-poly variants, and I guess all models from most games xD Like from Iron Man 1 and 2 from Xbox 360 models
## Post #26
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-01-02T20:45:37+00:00
- Post Title: Re: Iron Man 3 model files

Sorry if this can be a offtop,but can you make a Bdae converter for Spider-Man Unlimited?
Samples: [http://bit.ly/2i3pABZ](http://bit.ly/2i3pABZ)
Thanks!
P.S Extractred from Android version if you interested
## Post #27
- Username: xtrem1275
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 01, 2017 3:45 pm
- Post datetime: 2017-01-03T03:23:44+00:00
- Post Title: Re: Iron Man 3 model files

Excellent models, the ones I need I have to be in low poly so the assembly is easier, I saw some images of how the other armors that are not in the game are made and I'm also working on it joining the parts of the models in Maya,I attach an image on which I am basing to make them, and in photoshop arranging the textures if they serve you when you have them ready I can share them with you and whoever needs them, thanks again for your help
[mark 8.jpg](https://xentaxbackup.github.io/file/12151_mark 8.jpg)
## Post #28
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-13T04:29:59+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from zaramot
>
> Hi, no I haven't checked your spreadsheet yet, but I will. I will share info a bit later. As I understand this format .bdae is pretty common for android, game Batman: The Dark Knight Rises uses same format and it's similar to Iron Man. Just different version I guess.

Script The Dark Knight Rises please.
## Post #29
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-02-19T08:58:39+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from zaramot
>
> I have a lot of high-poly variants, and I guess all models from most games xD Like from Iron Man 1 and 2 from Xbox 360 models

Kinda interested in how many polygons they have(if they're from IM2 X360), so would you mind showing some wireframes? Besides, it would be awesome if you happen to know some methods to get these models & textures from X360, coz as I know so far it seems difficult to extract the textures.
## Post #30
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-02-19T10:55:28+00:00
- Post Title: Re: Iron Man 3 model files

Models from xbox-360/ps3 aren't high-poly at all, though quite nicely made. I have ironman outfits used for 3d printing - those models are starting from 1.5 to 5 millions of polygons in most complex ones. Though, there are some a bit lower like 300-700k of polygons. I was talking about them when said about high-poly xD And for xbox-360 ironman 1 and 2 - you're right, the harder part is to get textures.
## Post #31
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-02-20T10:34:33+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from zaramot
>
> Models from xbox-360/ps3 aren't high-poly at all, though quite nicely made.
 Yeah, they ain't high-poly comparing with those we called, but I'd like to compare them with IM3 iOS version, or MH 2016, to see which ones are higher res.
## Post #32
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-02-20T10:42:48+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from zaramot
>
> Here's simple script to import Iron Man's armors with bones/weights and to analyze format a bit.

I tried the iOS version, but the UVs ain't at the right place. Would you update the script if possible?
## Post #33
- Username: Megan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 21, 2017 7:45 pm
- Post datetime: 2017-03-21T11:49:21+00:00
- Post Title: Re: Iron Man 3 model files

I think you can search the net for the model that is ok to print without any problems or additional inconveniences. 
For example here is a some good websites with models and I bet saw there a model of Iron Man 3 : [http://3dinsider.com/3d-model-website-database/](http://3dinsider.com/3d-model-website-database/)
## Post #34
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-03-23T11:40:28+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from Megan
>
> I think you can search the net for the model that is ok to print without any problems or additional inconveniences. 
For example here is a some good websites with models and I bet saw there a model of Iron Man 3 : http://3dinsider.com/3d-model-website-database/

Well actually I'd  already found these models with proper UVs on TF3DM years ago, BUT I do want to give it a try myself.
Anyway, thanks for the reply!
## Post #35
- Username: Willi Miner
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 16, 2018 8:07 pm
- Post datetime: 2018-03-16T12:28:11+00:00
- Post Title: Re: Iron Man 3 model files

Is it possible for someone to upload the .FBX files of the iron man 2/ 1 3D models? I've been looking everywhere for these models online and now that I've found someone who has successfully exported them, I can't seem to find a link to download the models. Thank you
## Post #36
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-05-02T09:55:47+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from zaramot
>
> Here's simple script to import Iron Man's armors with bones/weights and to analyze format a bit. Don't try it on files with _noskin at the end of the file's name, they aren't skinned meshes (no skeleton inside) - script will crush!
Is it possible to modify this script for 3D Max 2010?
## Post #37
- Username: Honorsoft
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 25, 2021 3:55 am
- Post datetime: 2022-08-19T21:28:38+00:00
- Post Title: Re: Iron Man 3 model files

I don't use Max, so I was wondering if anyone knew of any scripts for Noesis, QuickBMS or Blender? Thanks in advance for any advice or assistance.
## Post #38
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-20T14:20:20+00:00
- Post Title: Re: Iron Man 3 model files

Speaking of bdae meshes (with signature BRES)? Usually they are rather simple structured.

Thing is that all links to bdae samples in this thread have expired.
## Post #39
- Username: Honorsoft
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 25, 2021 3:55 am
- Post datetime: 2022-08-25T16:31:52+00:00
- Post Title: Re: Iron Man 3 model files

Here's a BDAE link for "flying_malibu_beach_to_stark.bdae" (3mb) and does have a BRES signature - version 44 (I think):
[https://drive.google.com/file/d/1XLhONn ... sp=sharing](https://drive.google.com/file/d/1XLhONnuC9Ayhl5IT9ug1_LoiX3-fe9Nh/view?usp=sharing)

I'm more interested in extracting scenery models (and some enemies) since Iron-man and player models are everywhere online but no one ever posts ripped scenery.

If someone could assist me with converting some scenery and other enemy BDAE's it would be appreciated (without me using 3DSMax/Max)
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-25T17:47:41+00:00
- Post Title: Re: Iron Man 3 model files

Thanx! As I wrote meshes are rather easy to obtain from bdae, usually:
.



flying_malibu_beach_1.jpg (230.2 KiB) Viewed 148 times
## Post #41
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-25T18:10:11+00:00
- Post Title: Re: Iron Man 3 model files

FVFsize of next mesh is different. Also not sure whether everything is correct here:
.



flying_malibu_beach_2.jpg (238.81 KiB) Viewed 146 times
## Post #42
- Username: Honorsoft
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 25, 2021 3:55 am
- Post datetime: 2022-09-02T16:50:15+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from xtrem1275 ↑Mon Jan 02, 2017 1:34 am at Mon Jan 02, 2017 1:34 am
>
> 
Hello good morning and happy new year,my name is Cesar Diaz Espinosa, I'm from Mexico, and I'm new to the page, I hope to be able to contribute, looking at the network on the iron man armor 3 of the android game, to make the armor in papercraf, to scale, I found this page, and extracted some of the armors, but could tell me How to extract the textures, the armatures I extracted are mark 15,18,19,20,24,27,28,32,36,43, the mark 31 marks me error in the script, thanks I hope someone could guide me, and If anyone wants the models they will gladly share them

I would like to get some models from the game, I have them in BDAE format but I need them in any other format, except max. I have gotten all the textures already.
## Post #43
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-09-02T22:32:42+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from Honorsoft ↑Sat Sep 03, 2022 12:50 am at Sat Sep 03, 2022 12:50 am
>
> 
I would like to get some models from the game, I have them in BDAE format but I need them in any other format, except max. I have gotten all the textures already.
[original MAX script](https://forum.xentax.com/viewtopic.php?f=16&t=11248#p92899)
plugin for Noesis. many models give an error. everything is the same as in the original script for Max



 fmt_bdae_IronMan.zip
(1.64 KiB) Downloaded 48 times


*EDIT: I made my plugin from scratch, supports all models (characters and static objects), real bones with parent indexes). but the problem is with UVs (need to scale manually, most characters don't need it)
## Post #44
- Username: Honorsoft
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 25, 2021 3:55 am
- Post datetime: 2022-09-02T23:13:17+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from Durik256 ↑Sat Sep 03, 2022 6:32 am at Sat Sep 03, 2022 6:32 am
>
> 
original MAX script
plugin for Noesis. many models give an error. everything is the same as in the original script for Max

Thanks so much, this looks like exactly what I was looking for. I am going to try it now.

EDIT:  I tried it (Noesis64) and got this error:
Detected file type: Iron Man
24
28
32
36
1868
2108
2112
2156
2160
2164
2168
2172
2176
2180
2184
2188
2192
2196
2200
2204
2208
2212
2216
2276
2280
2300
2304
2360
2240
2244
2248
2252
2364
2368
2388
2392
2412
2416
2436
2440
2552
2556
2560
151328
2572
2576
172348
172412
172416
172428
172432
172436
172508
172512
172516
172588
172592
172596
172668
172672
172676
172748
172752
172756
172828
172832
172836
172908
172912
172916
172988
172992
172996
173068
173072
173076
173148
173152
173156
173228
173232
173236
173400
173308
173312
173316
173412
173416
173420
173504
173532
173596
173692
173608
173708
173620
173724
173632
173740
173644
173756
173656
173772
173668
173788
173680
173804
173832
173860
173924
173936
173968
Last Read @  336
>>>>>>>>>>>>>>>>>>>> 172916 172988
Mesh Off @  172916
Vert Section @  172976
Face Section @  173040
Traceback (most recent call last):
  File "C:\*******\noesisv4464\plugins\python\fmt_bdae_IronMan.py", line 170, in noepyLoadModel
    Face_array +=[fa,fb,fc]
MemoryError

...I am more of a programmer and artist and don't understand much of that, but it is closer than anything I've tried so far.
-I will try more with Hex2Obj though, it looks like you had success.
## Post #45
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-10-02T16:36:53+00:00
- Post Title: Re: Iron Man 3 model files

> Reply from zaramot ↑Thu Feb 27, 2014 4:12 am at Thu Feb 27, 2014 4:12 am
>
> 
Hi, no I haven't checked your spreadsheet yet, but I will. I will share info a bit later. As I understand this format .bdae is pretty common for android, game Batman: The Dark Knight Rises uses same format and it's similar to Iron Man. Just different version I guess.

How did you get these models from TDKR? I can't find the script anywhere.
