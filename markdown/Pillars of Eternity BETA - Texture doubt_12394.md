## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-15T19:05:41+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

I have right [here](https://mega.co.nz/#!dolXCTqQ!_huJ7-iErbSPB3D6woXX00FzpOqzP-Yt-toPPWrVihw) a couple samples of textures from Pillars of Eternity, but I don't understand what they are used for, or if they have a tint mask or something like that. 
Can someone help? Why are NormalMaps so weird?
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-16T15:54:07+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

Textures with C are color maps, alpha is specular.
Textures with A are translucent maps.
Textures with N are bump maps but alpha is swapped with green channel, blue must be white.


Here is tool for GIMP to convert Bump Maps.
Edit: Cheeck my new posts.
## Post #3
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-16T17:31:59+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

> Reply from PredatorCZ
>
> Textures with C are color maps, alpha is specular.
Textures with A are translucent maps.
Textures with N are bump maps but alpha is swapped with green channel, blue must be white.


Here is tool for GIMP to convert Bump Maps.

thanks! a lot! loads of info!
it's code and I am unsure how to use it  lemme download GIMP...
will your tool work both ways?

If I can make a Specular Map, how can I put it in the alpha channel of the diffuse map?

Translucent Map = Ambient Occlusion?
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-16T17:43:46+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

> Reply from Devilot
>
> 
thanks! a lot! 
it's code and I am unsure how to use it  lemme download GIMP...
will your tool work both ways?

Translucent Map = Ambient Occlusion?
Transparency or translucency defines seethru points in mesh, so practically it is an alpha channel of image.
But some engines uses some weird ways to store this texture data, in this way its stored away becouse not every color texture is transparent.

The Instructions are in readme. 

Its not working for reverse ways but U can reverse that by take Green and put it to Alpha, take Red channel and put it to Green and Blu channel.
And Voila.

I can make reversing script too.
## Post #5
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-16T17:49:02+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

if you could update the plugin I'd be thankful 

the original game uses .TEX textures, rather than .DDS. do you know if a tool that converts one to the other exists?

So I can't simply copy the specular mask to the alpha channel, can I...?
## Post #6
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-16T17:53:25+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

Are .tex have dds header? if not can u upload sample? (tell what tool did u use for conversion?)
Yes you can copy Specular Image to Alpha Channel of colormap.
## Post #7
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-16T18:01:44+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

let me try to extract a couple.. there we [go](https://mega.co.nz/#!VgtBnahD!NZYO5Q8Dc_hXbxBMyxSINNS6AdSono7MU-LxSRuRQcc)!

Ah, I can simply copy-paste? any recommended tool?
## Post #8
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-16T18:13:44+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

I updated tools, so you can convert and make bump maps.

Also .tex files have dxt data, theyre pretty same as dds but dds have 128 Bytes long header and tex hav only 56 Bytes long but its not problem to convert them back.

For spec channel you can use Gimp or photoshop or any that can manipulate with RGBA channels. I can make tut only for Gimp.
[PoE tools.zip](https://xentaxbackup.github.io/file/8287_PoE tools.zip)
## Post #9
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-16T18:27:16+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

a tutorial would be very nice indeed  also for the copy-paste thing
## Post #10
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-16T19:02:01+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

Okay, A Quest For GIMP, how to basic cook specular map into color map for PoE.

So we you have diffuse map(next time D) and specular map(next time S).

1. If D map does not have an alpha channel is can be created by Layer/Transparency/Add Alpha Channel.
2. It must be sure S have same dimensions as D, if not S map must be scaled. To do that go to Image/Scale Image
 unlink chain between numsliders and listbox in Image Size section, now set Widht and Weight same as D size. Then overwrite image.
3. In D go to Colours/Components/Decompose, select RGBA mode and uncheck Decompose to layers
4. GIMP will make 4 more images find one with alpha in name. Go to Layers/Delete Layer, then drag and drop here specular image file.
5. Go to Colours/Components/Compose, select RGBA and select color for each that mean name-red to Red etc.
6. The result should be same as D texture but with specular alpha channel.

Hope this helps.
## Post #11
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-16T19:46:51+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

It does, thank you  I'm only missing how to convert DDS to TEX!
## Post #12
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-16T20:07:31+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

What tool did u use for convert tex to dds?
## Post #13
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-16T20:17:08+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

I used Unity Asset Viewer, which converts them automatically or not, but can't do the other way round...
## Post #14
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-16T20:20:58+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

Oh, well actually, Unity Assets Explorer CAN import changed DDS images back to archive.
[viewtopic.php?f=10&t=10085](http://forum.xentax.com/viewtopic.php?f=10&t=10085) Third post is tutorial.
## Post #15
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-16T20:29:39+00:00
- Post Title: Pillars of Eternity BETA - Texture doubt

it can import them but it can't change them, right?
## Post #16
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-16T20:36:47+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

No, it will inject them right into archive, its all described in 5th post of that topic.
## Post #17
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-16T20:38:51+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

I'd still like a method to change them manually, if you have the time and desire to write one 
This is because, more likely than not, to create entirely new content an override-like method will be used, I am sure, we won't get to fiddle with the archives.
## Post #18
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-16T20:50:54+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

But UAE can make tex from dds, and also it can inject it back to archive, It wont overwrite it, it just change some data, no need to worry, game will go smooth as original. Look, Im not an Unity modder and probably never be, but something tells me you want to make some skins from thore textures and also want them back in game right?
## Post #19
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-16T21:00:29+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

> Reply from PredatorCZ
>
> But UAE can make tex from dds, and also it can inject it back to archive, It wont overwrite it, it just change some data, no need to worry, game will go smooth as original. Look, Im not an Unity modder and probably never be, but something tells me you want to make some skins from thore textures and also want them back in game right?

right and wrong  I want to add something entirely new to the game, as soon as it will be possible.
This method
"6. To import into the archive changed DDS-image:
a) Extract image from the archive (with converting it into the DDS-format).
b) Edit it in a photo editor. Make sure that saved it in the right format (the same as the original), and that the file size is the size of the original file.
c) Put the modified image to the same location where the original image was extracted.
d) Find in window of program tex-file, click the right mouse button and select "Import This File from DDS". Image imported into assets-file in place of the original picture.
e) To save the new assets-file, click "Save as Assets-file"

only allows for overwrite
## Post #20
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-17T15:31:56+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

Unfortunately thats the only way to mod Unity games for now, the full mod tool pack is far from over and maybye probably never will be done becouse Unity is very complex engine and newer versions can change everything.
## Post #21
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-17T15:56:20+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

I see. Unless or until the developer releases modding tools...
Can I still have the tutorial?
## Post #22
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-17T16:33:33+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

Developers of Unity have their Unity SDK on their website. You can create your own game with that tool, it a free like UDK, but in unity you cannot open assets archives, they're builded along with game.

Oh and tutorial for what?
## Post #23
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-17T16:52:54+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

the tutorial for making DDS -> TEX.

I have the engine... it is still not what I expected, but better than nothing
## Post #24
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-17T17:00:55+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

You already posted it few posts ago.
You just grab tex file after d) part.
## Post #25
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-17T17:42:37+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

I did? but that's not what I mean..
## Post #26
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-18T13:07:20+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

I know this method is complicated and I agree there should be made standalone tex converter.
## Post #27
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-19T08:32:09+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

GIMP cannot do it?
## Post #28
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-19T17:27:36+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

GIMP does not support TEX files, also tex files are very complex format, tex can be ETC,ATC,PVRTC,DXT,ASTC or uncompresed 16,24 or 32 bits textures. So its a lots of formats.
## Post #29
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-20T09:18:19+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

Well you said those are Tex\DDS right?
## Post #30
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-20T09:47:59+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

Yes from this game tex files are dxt compressed (dds).
## Post #31
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-20T10:27:56+00:00
- Post Title: Re: Pillars of Eternity BETA - Texture doubt

Well, I can always try to ask if DDS works on the official forums...
