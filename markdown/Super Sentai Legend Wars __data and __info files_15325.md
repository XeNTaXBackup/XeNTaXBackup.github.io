## Post #1
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2016-10-04T08:23:21+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

I managed to extract the music files from the CPKs, but the ADX files for the BGM must be encrypted. I can hear the music but it has a lot of static. So far nothing I've tried can decrypt those (but if anyone wants to take a crack at it: [http://www.mediafire.com/file/e798o7aajb2w1p5/ADX.rar](http://www.mediafire.com/file/e798o7aajb2w1p5/ADX.rar)).

But what I'm most interested in are the card animations for the "legend" cards (hopefully they're one single file, but I'm guessing the animated parts are comprised of various images):


(Droid4X recorded with Fraps, which sure works well enough, but gaining the actual files would be even better and possibly provide an image without the boarders)

So far I haven't figured out where those files are. Might be in the "UnityCache" folder with the "__data" and "__info" files... but so far nothing I have for extracting Unity files can handle those.

Uploaded a sample file: [http://www.mediafire.com/file/s8k41tp62 ... a_info.rar](http://www.mediafire.com/file/s8k41tp62m8lovm/data_info.rar)


I would appreciate any and all help. Even a nudge in the right direction would be great.
## Post #2
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2016-10-16T07:04:46+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

Well I've spent the past almost 2 weeks on this and am no closer to extracting anything beyond the garbled music.

Any help would be definitely appreciated.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-16T09:45:55+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

UnityEX can open your __data file and you can export source files from it   
[http://www.zoneofgames.ru/forum/index.p ... opic=36240](http://www.zoneofgames.ru/forum/index.php?showtopic=36240)
## Post #4
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2016-10-17T00:41:12+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

> Reply from AceWell
>
> UnityEX can open your __data file and you can export source files from it   
http://www.zoneofgames.ru/forum/index.p ... opic=36240

Wow it really can! Thank you!  I hope I can find what I'm looking for in all of this.
## Post #5
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2016-10-17T10:29:40+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

Hi AceWell, if I can use your expertise once more? I found the files I was looking for, they're in a PVR format which I can open/convert just fine with PVRTexTool.   

However with certain cards (like the one I used as an example) there are minor animations. I think the PVR works as the "base" image, and for cards that have animations there's a .tex file (well actually looks like they all have them?) but despite using at least six different tools to try and convert these into something, I'm getting nothing but pixelated and/or empty results.

Uploaded a sample here: [http://www.mediafire.com/file/6cih4ii23 ... _00121.rar](http://www.mediafire.com/file/6cih4ii232c3jpo/card_00121.rar) and a few other TEX samples plucked at random if that'll give a better idea of what is going on: [http://www.mediafire.com/file/v9eek0s5n ... W_TEXs.rar](http://www.mediafire.com/file/v9eek0s5n36o34a/SSLW_TEXs.rar) . If you can take a look and give me an idea of what to do I would again be most appreciative!
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-17T20:53:42+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

unfortunately i'm not a mobile texture compression expert (or any kind of expert),
i usually just let the Unity tools handle most of that   
you can open your card_00121.tex.pvr sample in Xnview, i think this was the plugin
[http://newsgroup.xnview.com/viewtopic.php?t=27877](http://newsgroup.xnview.com/viewtopic.php?t=27877)

TextureFinder can open your 37_Logo.tex as rgba32, didn't try them all though.
## Post #7
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2016-10-18T03:47:01+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

> Reply from AceWell
>
> unfortunately i'm not a mobile texture compression expert (or any kind of expert),
i usually just let the Unity tools handle most of that

Well you're more knowledgeable than I. 

> Reply from AceWell
>
> you can open your card_00121.tex.pvr sample in Xnview, i think this was the plugin
http://newsgroup.xnview.com/viewtopic.php?t=27877

Yeah, works well in that program with the plugin and PVRTexTool.

> Reply from AceWell
>
> TextureFinder can open your 37_Logo.tex as rgba32, didn't try them all though.

Indeed, I found that TOS Tex Converter works well for all the "logo" named files, but so far the other card .tex files are showing up as blank (in TOS Tex Converter) or a mess (in TextureFinder).

Coming so close to having it all figured out...but still so far.
## Post #8
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-11-09T07:25:42+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

In my case the game folders are empty, can you tell me when the game downloads the data files?
## Post #9
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-11-10T04:58:29+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

> Reply from Cloud452
>
> I managed to extract the music files from the CPKs, but the ADX files for the BGM must be encrypted. I can hear the music but it has a lot of static. So far nothing I've tried can decrypt those (but if anyone wants to take a crack at it: http://www.mediafire.com/file/e798o7aajb2w1p5/ADX.rar).

But what I'm most interested in are the card animations for the "legend" cards (hopefully they're one single file, but I'm guessing the animated parts are comprised of various images):


(Droid4X recorded with Fraps, which sure works well enough, but gaining the actual files would be even better and possibly provide an image without the boarders)

So far I haven't figured out where those files are. Might be in the "UnityCache" folder with the "__data" and "__info" files... but so far nothing I have for extracting Unity files can handle those.

Uploaded a sample file: http://www.mediafire.com/file/s8k41tp62 ... a_info.rar


I would appreciate any and all help. Even a nudge in the right direction would be great.

Is there any possibility of you uploading the folders with the data files? I've figured out how to extract this type of file using unity assets bundle extractor and unity studio, but i need to check one by one.
## Post #10
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-11-18T21:36:00+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

Sorry for bumping this topic, but seems like not a single tool can unpack these "__data" Unity packages, and not a single script can import them aswell.
I've already tried the latest version of Unity Studio, UnityEX and Unity Assets Bundle Extractor, these tools can't unpack it.
Also, Chipicao's max script can't directly import it too.
It's not related to Super Sentai Legend Wars, but, still, it has the same format.
This one contains mainly meshes and textures:

[http://www9.zippyshare.com/v/oQI3IAIi/file.html](http://www9.zippyshare.com/v/oQI3IAIi/file.html)
## Post #11
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-11-19T16:10:02+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

> Reply from Automotive Gaming
>
> Sorry for bumping this topic, but seems like not a single tool can unpack these "__data" Unity packages, and not a single script can import them aswell.
I've already tried the latest version of Unity Studio, UnityEX and Unity Assets Bundle Extractor, these tools can't unpack it.
Also, Chipicao's max script can't directly import it too.
It's not related to Super Sentai Legend Wars, but, still, it has the same format.
This one contains mainly meshes and textures:

http://www9.zippyshare.com/v/oQI3IAIi/file.html

This is the method I know to extract this type of file. Unfortunately not all __data files have templates and textures, so you need to extract them one by one to know the contents of the file.

* Important step: The extraction procedure must be performed on another partition, in my case a pen drive, the programs used and files must be on the same partition of the procedure.

Contents of the .rar file: instructions in txt, extracted files and demo images of the procedure, just follow the instructions of the txt file and images to do the tutorial correctly.

This method was tested in the Kamen Rider Battle Rush game, and in the sample file posted, I'm not sure if it works in other games. I hope I have helped.

Unity Studio: [http://www.mediafire.com/file/d1x0mljln ... Studio.zip](http://www.mediafire.com/file/d1x0mljlntet2z7/Unity-Studio.zip)

Unity Assets Bundle Extractor 32 bits: [http://www.mediafire.com/file/a8996pcgr ... _32bit.zip](http://www.mediafire.com/file/a8996pcgrv4jhtt/AssetsBundleExtractor_2.0_32bit.zip)

Unity Assets Bundle Extractor 64 bits: [http://www.mediafire.com/file/6tjws6670 ... _64bit.zip](http://www.mediafire.com/file/6tjws6670ys6z6q/AssetsBundleExtractor_2.0_64bit.zip)

Tutorial: [http://www.mediafire.com/file/1ujw3r166 ... +Files.rar](http://www.mediafire.com/file/1ujw3r166f4yf48/Tutorial+Extract+__data+Files.rar)
## Post #12
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2016-12-18T22:45:08+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

I am looking for any tutorials on how to copy the super sentai legend wars complete cached flder Android version because I couldn't find any files in my data cache folder. Any help would be appreciated.
## Post #13
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-12-26T05:52:14+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

> Reply from sasimiv11
>
> I am looking for any tutorials on how to copy the super sentai legend wars complete cached flder Android version because I couldn't find any files in my data cache folder. Any help would be appreciated.

This is impossible for this game, you need to play to have access to the models, (Super sentai legend wars, kamen rider battle rush, DC Legends, Star Wars Galaxy of heroes, etc.). The more you play, the more models you have.
## Post #14
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2016-12-31T01:09:50+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

> Reply from dswd2015
>
> sasimiv11 wrote:I am looking for any tutorials on how to copy the super sentai legend wars complete cached flder Android version because I couldn't find any files in my data cache folder. Any help would be appreciated.

This is impossible for this game, you need to play to have access to the models, (Super sentai legend wars, kamen rider battle rush, DC Legends, Star Wars Galaxy of heroes, etc.). The more you play, the more models you have.
I did play this game in Android version but I still couldn't can't files in cache folder Do I need to root my machine?
## Post #15
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-12-31T01:48:15+00:00
- Post Title: Super Sentai Legend Wars "__data" and "__info" files

> Reply from sasimiv11
>
> dswd2015 wrote:sasimiv11 wrote:I am looking for any tutorials on how to copy the super sentai legend wars complete cached flder Android version because I couldn't find any files in my data cache folder. Any help would be appreciated.

This is impossible for this game, you need to play to have access to the models, (Super sentai legend wars, kamen rider battle rush, DC Legends, Star Wars Galaxy of heroes, etc.). The more you play, the more models you have.
I did play this game in Android version but I still couldn't can't files in cache folder Do I need to root my machine?

I have the same problem in three games, super sentai legend wars, saint seiya zodiac brave and one piece dance battle, all the game folders are empty. I'm going to test the game on an android routed device to test.
## Post #16
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2016-12-31T02:09:22+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

I know someone did find models from super sentai legend game IOS version (with jailbroken apple device) I have an iPod but I couldn't get the game because different regions(Canada not Japan)
## Post #17
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-09T19:00:26+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

Yes, you need root. Use the root browser to access the data - cache folder.
## Post #18
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-09T19:06:13+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from sasimiv11
>
> I know someone did find models from super sentai legend game IOS version (with jailbroken apple device) I have an iPod but I couldn't get the game because different regions(Canada not Japan)

Talk to [http://krocobengel.deviantart.com/](http://krocobengel.deviantart.com/)
## Post #19
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2017-01-10T19:35:08+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from dswd2015
>
> Yes, you need root. Use the root browser to access the data - cache folder.
Alright How do you root your machine? Because I need to get go buster models for making costumes. I make costumes for nonprofit organizations.
## Post #20
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-01-10T20:45:20+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from sasimiv11
>
> dswd2015 wrote:Yes, you need root. Use the root browser to access the data - cache folder.


Alright How do you root your machine? Because I need to get go buster models for making costumes. I make costumes for nonprofit organizations.

Download bluestacks rooted or droid4x. Install root browser to access the folders. Search on youtube how to share emulator files with windows.
## Post #21
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2017-01-11T04:58:44+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from dswd2015
>
> sasimiv11 wrote:dswd2015 wrote:Yes, you need root. Use the root browser to access the data - cache folder.


Alright How do you root your machine? Because I need to get go buster models for making costumes. I make costumes for nonprofit organizations.

Download bluestacks rooted or droid4x. Install root browser to access the folders. Search on youtube how to share emulator files with windows.
Thank you very much for your help. I hope I can get this done soon.
## Post #22
- Username: sasimiv11
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 01, 2016 4:03 pm
- Post datetime: 2017-01-11T04:59:20+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from dswd2015
>
> sasimiv11 wrote:dswd2015 wrote:Yes, you need root. Use the root browser to access the data - cache folder.


Alright How do you root your machine? Because I need to get go buster models for making costumes. I make costumes for nonprofit organizations.

Download bluestacks rooted or droid4x. Install root browser to access the folders. Search on youtube how to share emulator files with windows.
Thank you very much for your help. I hope I can get this done soon.
## Post #23
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2017-04-12T15:20:24+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

Not related to Super Sentai but to do with _data and _info files. I am using UnityEX to go through individual folders to figure out how to extract the right mesh and textures (For Dark Avenger 3)
Finally found some .mesh files. However UnityEX is not bale to extract the source files foe .mesh files however it can export the .mesh file. Problem is I am not able to find any tools or scripts for importing .mesh files in Blender or 3DS Max....Any idea?

> Reply from dswd2015
>
> 

This is the method I know to extract this type of file. Unfortunately not all __data files have templates and textures, so you need to extract them one by one to know the contents of the file.

* Important step: The extraction procedure must be performed on another partition, in my case a pen drive, the programs used and files must be on the same partition of the procedure.

Contents of the .rar file: instructions in txt, extracted files and demo images of the procedure, just follow the instructions of the txt file and images to do the tutorial correctly.

This method was tested in the Kamen Rider Battle Rush game, and in the sample file posted, I'm not sure if it works in other games. I hope I have helped.

Unity Studio: http://www.mediafire.com/file/d1x0mljln ... Studio.zip

Unity Assets Bundle Extractor 32 bits: http://www.mediafire.com/file/a8996pcgr ... _32bit.zip

Unity Assets Bundle Extractor 64 bits: http://www.mediafire.com/file/6tjws6670 ... _64bit.zip

Tutorial: http://www.mediafire.com/file/1ujw3r166 ... +Files.rar
## Post #24
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-04-30T22:07:58+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from parttimegamer15
>
> Not related to Super Sentai but to do with _data and _info files. I am using UnityEX to go through individual folders to figure out how to extract the right mesh and textures (For Dark Avenger 3)
Finally found some .mesh files. However UnityEX is not bale to extract the source files foe .mesh files however it can export the .mesh file. Problem is I am not able to find any tools or scripts for importing .mesh files in Blender or 3DS Max....Any idea?
dswd2015 wrote:

This is the method I know to extract this type of file. Unfortunately not all __data files have templates and textures, so you need to extract them one by one to know the contents of the file.

* Important step: The extraction procedure must be performed on another partition, in my case a pen drive, the programs used and files must be on the same partition of the procedure.

Contents of the .rar file: instructions in txt, extracted files and demo images of the procedure, just follow the instructions of the txt file and images to do the tutorial correctly.

This method was tested in the Kamen Rider Battle Rush game, and in the sample file posted, I'm not sure if it works in other games. I hope I have helped.

Unity Studio: http://www.mediafire.com/file/d1x0mljln ... Studio.zip

Unity Assets Bundle Extractor 32 bits: http://www.mediafire.com/file/a8996pcgr ... _32bit.zip

Unity Assets Bundle Extractor 64 bits: http://www.mediafire.com/file/6tjws6670 ... _64bit.zip

Tutorial: http://www.mediafire.com/file/1ujw3r166 ... +Files.rar

Unfortunately I do not know a way to import .mesh files into Blender or 3D Max, the method I know to extract __data files is described in the tutorial.
## Post #25
- Username: k1995
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 09, 2016 3:30 pm
- Post datetime: 2017-08-29T09:56:50+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

Hello. I don't understand how you extracted the [Kamen Rider Storm Heroes],
You can teach me 1 I have used UnityEX -Unity.Studio.v0.7.0 -AssetsBundleExtractor
Trying to get the model but failed. I found the model file. But it was blank after opening. He was encrypted. I don't know how to crack him. Can you teach me?
## Post #26
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2017-08-30T13:17:36+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from k1995
>
> Hello. I don't understand how you extracted the [Kamen Rider Storm Heroes],
You can teach me 1 I have used UnityEX -Unity.Studio.v0.7.0 -AssetsBundleExtractor
Trying to get the model but failed. I found the model file. But it was blank after opening. He was encrypted. I don't know how to crack him. Can you teach me?

Sorry, the topic is about Super Sentai Legend Wars. The game Kamen Rider Transcend Heroes ended on 31/08/2017, can not be extract.
## Post #27
- Username: k1995
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 09, 2016 3:30 pm
- Post datetime: 2017-09-24T15:11:56+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from dswd2015
>
> k1995 wrote:Hello. I don't understand how you extracted the [Kamen Rider Storm Heroes],
You can teach me 1 I have used UnityEX -Unity.Studio.v0.7.0 -AssetsBundleExtractor
Trying to get the model but failed. I found the model file. But it was blank after opening. He was encrypted. I don't know how to crack him. Can you teach me?

Sorry, the topic is about Super Sentai Legend Wars. The game Kamen Rider Transcend Heroes ended on 31/08/2017, can not be extract.
I'm sorry, because I really want to know. At another post, God, he's gone. That's too bad. I really can't say how your model was converted before
## Post #28
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-02-16T16:03:49+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

Hello. Sorry for bumping this thread.

I tried to export files from _data files by following the tutorial, but after conversion, the Asset Bundle Extractor keep crashing when I open some of the large asset files (which I assume where the models are). Popup messages like "cannot read beyond the stream" or "invalid bundle version" keep appearing.

Anyone can help with this?
## Post #29
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-02-18T12:02:35+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from kaiser21
>
> Hello. Sorry for bumping this thread.

I tried to export files from _data files by following the tutorial, but after conversion, the Asset Bundle Extractor keep crashing when I open some of the large asset files (which I assume where the models are). Popup messages like "cannot read beyond the stream" or "invalid bundle version" keep appearing.

Anyone can help with this?

Post the date file you're trying to extract so I can parse the error.
## Post #30
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-02-18T13:57:59+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from dswd2015
>
> kaiser21 wrote:Hello. Sorry for bumping this thread.

I tried to export files from _data files by following the tutorial, but after conversion, the Asset Bundle Extractor keep crashing when I open some of the large asset files (which I assume where the models are). Popup messages like "cannot read beyond the stream" or "invalid bundle version" keep appearing.

Anyone can help with this?

Post the date file you're trying to extract so I can parse the error.

thanks for replying.

I assume this is the file that you ask, since it contains meshes like LHAND, RHAND, and similiar files like that.],based on what I see with UnityEx.

[https://drive.google.com/file/d/1T8iscy ... ACs0n/view](https://drive.google.com/file/d/1T8iscy2ArHJQyn_W6ps74ErzQd5ACs0n/view)
## Post #31
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-02-18T23:23:59+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from kaiser21
>
> dswd2015 wrote:kaiser21 wrote:Hello. Sorry for bumping this thread.

I tried to export files from _data files by following the tutorial, but after conversion, the Asset Bundle Extractor keep crashing when I open some of the large asset files (which I assume where the models are). Popup messages like "cannot read beyond the stream" or "invalid bundle version" keep appearing.

Anyone can help with this?

Post the date file you're trying to extract so I can parse the error.

thanks for replying.

I assume this is the file that you ask, since it contains meshes like LHAND, RHAND, and similiar files like that.],based on what I see with UnityEx.

https://drive.google.com/file/d/1T8iscy ... ACs0n/view

I extracted the files that you posted and I did not find any errors, probably you should have done the wrong tutorial. Analyze the file I extracted, open the CAB-Character file using unity studio.

[http://www.mediafire.com/file/s55edkx4m ... e2eecf.rar](http://www.mediafire.com/file/s55edkx4mb9v8z6/51199a68f86d1ffe567aa0b65b23d949a3e2eecf.rar)
## Post #32
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-02-19T04:26:01+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

Which version of Unity Studio should I use?
I used the Unity Studio that you provided in this thread, and I cannot open the CAB-character with it. The Unity Studio will display "no children".

Edit: I also tried to open CAB-, but unity studio give this error message instead
[unity studio error.png](https://xentaxbackup.github.io/file/13927_unity studio error.png)
## Post #33
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-02-19T06:53:36+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

Turns out, I used an obsolete Unity Studio.

Now I'm using the latest version of Unity Studio, and finally I can extract the models.
Thank you very much! 
[test kyoryugold.jpg](https://xentaxbackup.github.io/file/13929_test kyoryugold.jpg)
## Post #34
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2018-02-19T22:25:01+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from kaiser21
>
> Turns out, I used an obsolete Unity Studio.

Now I'm using the latest version of Unity Studio, and finally I can extract the models.
Thank you very much!

To prevent unity studio from closing during the extraction process you must install this program [https://www.autodesk.com/products/fbx/fbx-review](https://www.autodesk.com/products/fbx/fbx-review)
## Post #35
- Username: wphilipkun
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 26, 2018 11:52 pm
- Post datetime: 2018-05-09T06:52:48+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

> Reply from dswd2015
>
> kaiser21 wrote:Turns out, I used an obsolete Unity Studio.

Now I'm using the latest version of Unity Studio, and finally I can extract the models.
Thank you very much! 

To prevent unity studio from closing during the extraction process you must install this program https://www.autodesk.com/products/fbx/fbx-review

Please detail the 3d model of the game "battle rush". I tried your way in this path but failed ....
viewtopic.php?f=21&t=15325

This is the cache file from my "Battle Rush" game
[http://www.mediafire.com/file/p579waw3l ... Shared.rar](http://www.mediafire.com/file/p579waw3lwdru1q/Shared.rar)
## Post #36
- Username: ZONE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 08, 2018 1:38 pm
- Post datetime: 2018-10-08T05:47:14+00:00
- Post Title: Re: Super Sentai Legend Wars "__data" and "__info" files

Hello. Sorry for bumping an old thread, but I would like to know how to extract card art from this game. I never tried extracting anything from any game before so I have no clue what I'm doing. Any help would be appreciated. Or if someone else has all the card art, that would be great if you could share.
