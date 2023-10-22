## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-30T19:58:00+00:00
- Post Title: Warlords Of Draenor - WoW expansion

Hi guys, been looking forward to seeing the new 3D models from the newest expansion World Of Warcraft - Warlords Of Draenor.

It looks like WoWHead already succeeded in doing this:

[http://www.wowhead.com/news=233947/warl ... 791:0:10+0](http://www.wowhead.com/news=233947/warlords-of-draenor-modelviewer-new-3d-models-and-warlords-character-models#modelviewer:1:53791:0:10+0)

but.. I searched high and low and got nothing...
the usual way does not seem to be working
I don't seem to get the older version of the alpha to extract the models...

So anyone has the model of these awesome models, preferable, Duraton, Blackhand and Grommash

T.
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-30T20:17:44+00:00
- Post Title: Warlords Of Draenor - WoW expansion

Ok, I found a way to extract the model and texture from the site 

when (in Chrome) you check out the html, you get

```
	<param name="quality" value="high">
	<param name="allowscriptaccess" value="always">
	<param name="allowfullscreen" value="true">
	<param name="menu" value="false">
	<param name="bgcolor" value="#181818">
	<param name="wmode" value="direct">
	<param name="flashvars" value="model=53153&modelType=8&contentPath=http://wow.zamimg.com/modelviewer/&hd=true">
</object>

```


when you copy this and paste it in an html file you can see the model

in Chrome you can do Inspect Element ( using right mouse button) and check the resources.

There you see a XHR node which holds all the textures used in png and the model in  .MO3 format, so you can download each one of these file.

Now I'll be looking for a way to import the .MO3 file and its animations into max.

T.
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-30T20:41:28+00:00
- Post Title: Warlords Of Draenor - WoW expansion

here is a small sample of such a mo3 file, so if there is anyone that can give some help...

T.
[axe_2h_draenorquest95_b_01.zip](https://xentaxbackup.github.io/file/7405_axe_2h_draenorquest95_b_01.zip)
## Post #4
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-31T22:02:02+00:00
- Post Title: Warlords Of Draenor - WoW expansion

From what I got is that the first 132 bytes contains the header, the rest is compressed and holds all the other data.

Since the compressed binary array is decompressed using binaryArray.uncompress(), a method used in ActionScript, I need to find a similar way to decompress that compressed array, up till now, no luck.. yet.

Need to get into actionscript....
T.
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-05-31T23:58:02+00:00
- Post Title: Warlords Of Draenor - WoW expansion

[out]
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-06-01T09:44:54+00:00
- Post Title: Warlords Of Draenor - WoW expansion

Hey Wobble thanks for the info, what is this CASC file format ?

Because all I want is the Blackhand model :/

( from the Blizzard Website )

> Introducing Our New File Format: CASC
>
> For nearly 20 years, Blizzard games have used a file format called Mo’PaQ (MPQ for short) as a way to compress and store game files. We’ve been able to introduce some great new technology using MPQ, such as our streaming client, but we’ve really pushed the file format far beyond what it was ever intended to be used for. Today, it’s become the source of a number of technical limitations for World of Warcraft.
>
> 
>
> To address these limitation and help us develop new technologies that will improve everyone’s game experience for years to come, we’re introducing a new proprietary file format that we call CASC (Content Addressable Storage Container). We’ll be using this new format in the Warlords of Draenor alpha and beta tests, and our intent is to convert everyone to the new format in a pre-expansion patch.
>
> 
>
> As geeky as it may sound, we’re extremely excited to be moving to this new file format. It provides a ton of benefits not only for us and our ability to support and patch the game, but also for players. Here are just a few of the benefits of the new CASC file format:
>
> 
>
> File Corruption—File repair tools are a thing of the past. The file structure maintains itself, helping to prevent errors during installation.
>
> Speed—Real-world game performance should increase for many players thanks to a non-redundant file structure—in layman’s terms, the game can find the assets it’s looking for more quickly.
>
> Patching—Updating your game files should be faster and more reliable. Patch data is integrated seamlessly, and no longer requires double the installation size on-disk when patching.
>
> Client Hotfixing—CASC allows us to be able to hotfix client game data, similar to server hotfixes, giving us the ability to address client-side issues that would normally require a patch.
>
> Streaming—The new format provides better support for streaming data and gives us greater flexibility to define how content updates are delivered and released.
>
> Expandable—The file structure is built to allow easy integration of new technologies in the future that we haven’t even thought up yet.
>
> . . . and more!
>
> We’re already using this file format for Heroes of the Storm’s Technical Alpha test, and we’re looking forward to reaping its benefits for WoW. As we mentioned, the first big step in transitioning all WoW players over will be converting everyone’s World of Warcraft installs to the new file format prior to the expansion. Our goal is to make sure that’s as seamless and painless a changeover as possible, using as much of the existing installed data as possible to reduce additional downloads. We’ll have more info on the file conversion process as we get closer to the launch of Warlords of Draenor.

T.
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-06-01T13:27:28+00:00
- Post Title: Warlords Of Draenor - WoW expansion

[out]
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-06-01T18:08:00+00:00
- Post Title: Warlords Of Draenor - WoW expansion

Yeah, I got the official beta download, just not the invite to play it, yet.

But with the new format, I don't see any of the new models available, except on WoWHead, I'm wandering how they got these models in their modelviewer...

T.
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-06-07T11:06:43+00:00
- Post Title: Warlords Of Draenor - WoW expansion

Hi guys I found some stuff on other sites and so on.

I compiled this to an useable exe.

With this you can extract all the files from all of the data.xxx files.

you can also add an extension, so that you can get specific files from the data.xxx files. Leaving the option of extension empty will extract all the files.

this also works for the Heroes of the Storm (Starcraft 2 DOTA)

Heroes of the storm has the known m3 and dds files in the data file. Yet the importer for max seems to be unable to import everything correctly

Warlords of Draenor has the known m2, skin and blp files. If you can match the skin file with the m2 file, you can import it into max with the existing m2 importer for max

Have fun

T.
[BlizzardDataFiles.zip](https://xentaxbackup.github.io/file/7445_BlizzardDataFiles.zip)
## Post #10
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-06-10T12:00:21+00:00
- Post Title: Warlords Of Draenor - WoW expansion

BTW, the above file is NOT a sample file as mentioned on the homepage, but an exe that extracts the data.xxx files

and this also works with Heroes Of The Storm

T.
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-06-10T15:17:57+00:00
- Post Title: Warlords Of Draenor - WoW expansion

[out]
## Post #12
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-06-11T20:14:09+00:00
- Post Title: Warlords Of Draenor - WoW expansion

No, the m2 files are the same, I can easily import the new npc orcs like Thrall and Blackhand using the existing m2 import scripts

T.
## Post #13
- Username: troll1981
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 10, 2014 2:28 am
- Post datetime: 2014-06-17T15:10:45+00:00
- Post Title: Warlords Of Draenor - WoW expansion

Can somebody upload WOW Draenor Beta Client to mega and send the downloadlink here or via Private Message?
## Post #14
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-06-17T19:13:38+00:00
- Post Title: Warlords Of Draenor - WoW expansion

[out]
## Post #15
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-07-07T13:53:03+00:00
- Post Title: Warlords Of Draenor - WoW expansion

Really, I have a Battle.net account but not the possibility to download the game beta ?

T.
## Post #16
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-07-30T08:44:45+00:00
- Post Title: Re: Warlords Of Draenor - WoW expansion

> Reply from TaylorMouse
>
> Really, I have a Battle.net account but not the possibility to download the game beta ?

T.Hello, my friends, thank you for sharing your work is great. Thank you so much
## Post #17
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-07-30T09:15:24+00:00
- Post Title: Re: Warlords Of Draenor - WoW expansion

> Reply from TaylorMouse
>
> Hi guys I found some stuff on other sites and so on.

I compiled this to an useable exe.

With this you can extract all the files from all of the data.xxx files.

you can also add an extension, so that you can get specific files from the data.xxx files. Leaving the option of extension empty will extract all the files.

this also works for the Heroes of the Storm ( 2 DOTA)

Heroes of the storm has the known m3 and dds files in the data file. Yet the importer for max seems to be unable to import everything correctly

Warlords of Draenor has the known m2, skin and blp files. If you can match the skin file with the m2 file, you can import it into max with the existing m2 importer for max

Have fun

T.
Hello, my friends, I would like to ask a question, is keeping an unpacked directory structure or file name. Thank you very much for your help
## Post #18
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2014-07-30T10:44:43+00:00
- Post Title: Re: Warlords Of Draenor - WoW expansion

> Reply from TaylorMouse
>
> No, the m2 files are the same, I can easily import the new npc orcs like Thrall and Blackhand using the existing m2 import scripts

T.

You can share your M2 import scripts?
## Post #19
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-08-02T14:47:58+00:00
- Post Title: Re: Warlords Of Draenor - WoW expansion

Sure, here it is

T.
[m2_import_v0.4.zip](https://xentaxbackup.github.io/file/7626_m2_import_v0.4.zip)
## Post #20
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2014-08-02T15:02:22+00:00
- Post Title: Re: Warlords Of Draenor - WoW expansion

> Reply from TaylorMouse
>
> Sure, here it is

T.

TKS
## Post #21
- Username: yianti
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Apr 01, 2008 5:03 pm
- Post datetime: 2014-08-02T15:11:11+00:00
- Post Title: Re: Warlords Of Draenor - WoW expansion

> Reply from TaylorMouse
>
> Sure, here it is

T.
[20140802231031.jpg](https://xentaxbackup.github.io/file/7627_20140802231031.jpg)
## Post #22
- Username: warzonefury
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jan 31, 2013 10:43 pm
- Post datetime: 2014-11-16T16:15:45+00:00
- Post Title: Re: Warlords Of Draenor - WoW expansion

Hello !

Can you explain how use your .exe for extract?

I don't understand what command i must use for do that
## Post #23
- Username: syrise
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 20, 2014 12:08 pm
- Post datetime: 2014-11-20T04:19:24+00:00
- Post Title: Re: Warlords Of Draenor - WoW expansion

i know this post ins probably somewhat ancient, but hopefully someone will still respond to this..

i was trying to get some sound effects out out the Draenor, which has currently already been released.., and as i stumbled upon this, i immediately had 2 questions..

should i put the BlizzardDataFiles.exe into the same folder with the ***.xxx files to make some sense out of them, or do i have to write a file for the exe to know where to take those *.xxx files from...

the second question: is there a less painful way to get any senseful information out of this CASC archive ?

right now i extracted literally everything out of the Draenor CASC archive... which is 460421 file... this will most probably crash at some point..

after that's done... intending to try out that BlizzardDataFiles.exe

any insight regarding on how to make sense out of that CASC, would be more than appreciated

-Syr
## Post #24
- Username: kokoilie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 12, 2015 1:13 am
- Post datetime: 2017-04-09T18:13:26+00:00
- Post Title: Re: Warlords Of Draenor - WoW expansion

About the export from the game i'd use Ladik's mpq editor, I think the newest version supports the CASC structure.
For the .m2 models I just finished moc script in autoit but for now it only works for models from legion expansion, will check others later(it will probably be some tweaks to how the header is arranged), if anyone wants to try it out let me know and i'll compile it.
example .m2 files from pandaria, vanilla and wotlk for dissection would be appreciated. For now i'll work on making it work with cata.
