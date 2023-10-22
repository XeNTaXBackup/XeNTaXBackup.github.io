## Post #1
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2015-04-07T19:57:14+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

Could someone please take a look at the model files from the pc port of Hyperdiemnsion Neptunia Rebirth 1 please.
the most i have got is the mesh using hex2obj but no uv
and the mesh & bones with howfies ripper for the ps3 games by reversing the endians in the file but no uv or weights

Sample: [https://www.mediafire.com/?6f6aa3b68qwplji](https://www.mediafire.com/?6f6aa3b68qwplji)
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-04-07T23:13:26+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

I've had a working MaxScript for the game for a couple of weeks. The only thing I need to do for it, first, is add in coding to set up the textures, then I'll post it here.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-08T03:03:08+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

> Reply from mikulover39
>
> the most i have got is the mesh using hex2obj but no uv
The normals are three half floats at the vertex block position 12 (= offset of 12 bytes to 0x99E0). Visualized as a sphere, see below.
The uvs (half floats) follow at pos 18 and (yeah, just a developer's joke?) 26. 
(From pos 20 there are three half floats with a sum of squares==1.0)



Neptun_Rebirth.JPG (215.92 KiB) Viewed 772 times



(There would be an additional offset required to be introduced in hex2obj but it should stay related to simple formats.)
## Post #4
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-04-08T07:39:29+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

> Reply from RandomTBush
>
> I've had a working MaxScript for the game for a couple of weeks. The only thing I need to do for it, first, is add in coding to set up the textures, then I'll post it here.

I'm stoked to hear this. I feared Nep-Nep might never see game worlds other than GameIndustri.
## Post #5
- Username: esperblade
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 10, 2015 1:19 am
- Post datetime: 2015-04-09T17:34:48+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

Speaking of which... has the link to howfie's old .ism2-to-LS converter disappeared? [viewtopic.php?f=16&t=7269](http://forum.xentax.com/viewtopic.php?f=16&t=7269)

I was going to use it as a reference for making a Blender script for .ism2 files, but it seems the utility is no longer available.

On the Steam Workshop, there's a modding guide for this game, but they're sorely missing model modding info - mainly because of the proprietary format: [http://steamcommunity.com/sharedfiles/f ... ideModal=1](http://steamcommunity.com/sharedfiles/filedetails/?id=409454600&insideModal=1)
## Post #6
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2015-04-13T16:27:09+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

Nice work RTB hope to be seeing the script soon!!

and thanks shakotay2 that helped clear things up
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-04-13T17:47:09+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

nice, RTB. good to see some fresh new blood around here. i kind of lost interest in doing this kind of stuff. finally realizing it is a real life-waster lol.

btw, anyone even play this game? i think i was skipping pictures for an hour before being able to play lmao!
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-14T03:19:41+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

> Reply from howfie
>
> finally realizing it is a real life-waster
No kidding. I wish I could go back in time to my single, unemployed self and be like "you're going to be stuck working your life away with a family pretty soon, so you might want to get a better fucking hobby, and write better code so I don't have to murder you from the future." At least there's some meaning in understanding the full intent and purpose of some data for the sake of propriety, archival, and/or restoration, but going through game after game just to find model data in plain sight is so empty.
## Post #9
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-05-05T01:08:50+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

Random, are you still working on the Maxscript? Haven't heard anything further and would hate for it to get forgotten about.
## Post #10
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-05-05T05:46:29+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

> Reply from ssringo
>
> Random, are you still working on the Maxscript? Haven't heard anything further and would hate for it to get forgotten about.I've been busy with other duties, but I suppose I can upload what I have right now. Still no material importing just yet (haven't updated it since I posted earlier), but everything else seems to be working alright.

[https://mega.nz/#!nlQAAK4S!KtUqFVFcaJD0 ... nwsCDesAwU](https://mega.nz/#!nlQAAK4S!KtUqFVFcaJD0oV5g14o4PpeVwIkLIPVBqnwsCDesAwU)

(EDIT: Whoops, realized I didn't change the UV mapping flip back to normal. Re-download it to fix that.)

(EDIT 2: Just a quick edit to state that yes, this will also work with Re;Birth 2's models. Just use the same QuickBMS script for Re;Birth 1's files to extract 'em.)
## Post #11
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-05-05T07:27:12+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

Cool beans. Thanks for sharing what you have so far. I know you have other stuff here you work on aside from whatever real life things you got going on. In any event, the script is working on Max10 with what I tried. Not seeing any facial features on the models I loaded but clearly see them on your WIP picture earlier. I'm guessing all the facial motions shown in the game are simply texture swaps or morphs? 

If others didn't realize, Aluigi posted the bms script to extract the game files here [http://zenhax.com/viewtopic.php?f=5&t=607](http://zenhax.com/viewtopic.php?f=5&t=607)
## Post #12
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-05-05T16:00:08+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

> Reply from ssringo
>
> Not seeing any facial features on the models I loaded but clearly see them on your WIP picture earlier. I'm guessing all the facial motions shown in the game are simply texture swaps or morphs?You could say that. In-game, it uses a combination of the "base" texture (which will need to be flipped upside-down to match the rest) and the "brows", "eyelid", "mouth" and "pupil" textures. Or you can run the game with Durante's Hyperresolution Neptunia plugin and do a texture dump (you'll need to edit the INI to enable it), that'll give you a pre-assembled but inexplicably double-sized face texture to use as a reference point.

(EDIT: Turns out that it's only inexplicably double-sized because Re;Birth 2 has the full, 1024x1024 resolution face textures compared to Re;Birth 1. That explains that, then.)
## Post #13
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-11-04T17:56:43+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

Hey Random, I noticed that you (I assume) were uploading Neptunia models to The Models Resource. Was wondering if you updated your script any further than what you shared above. 

Also thought I'd share that tools for converting textures were made a while back which I just found out about. Can be found at [http://steamcommunity.com/sharedfiles/f ... =409454600](http://steamcommunity.com/sharedfiles/filedetails/?id=409454600)
## Post #14
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-11-04T19:07:08+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

> Reply from ssringo
>
> Hey Random, I noticed that you (I assume) were uploading Neptunia models to The Models Resource. Was wondering if you updated your script any further than what you shared above. 

Also thought I'd share that tools for converting textures were made a while back which I just found out about. Can be found at http://steamcommunity.com/sharedfiles/f ... =409454600Yeah, that would be me submitting those there.

Anyway, the script in its current form still doesn't have automatic texture importing yet (I'll probably incorporate that before the year's over), but other than that it should work just fine since that's the only thing that's missing.
## Post #15
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-11-04T21:45:22+00:00
- Post Title: Hyperidmension Neptunia rebirth 1 ism2

Thanks again for the script. I've actually learned how to put the face textures together but they are kind of pain in the ass getting everything to line up. Plus putting together the various facial expressions is rather time consuming. It's  all good though. It's forcing me to learn how to use GIMP much better. 

side question: do you know if your script works for fairy fencer F? the game seems to run on the same engine but I don't have it installed to look if the file structure is the same.

Edit: I downloaded Fairy Fencer and although it uses .ism2 files (and an overall similar file structure) your script can't read them (or the ones I tried). I should note that the model folders contain a .cl3 file in the texture folder that's a bit larger than the associated .ism2 file. A modding guide on the Fairy Fencer steam community says the .cl3 file is a model file (so what is the .ism2?). I'll pack up one or three of the model folders if you want to take a look at them. If not, no worries. I'm sure you have enough on your plate already and I already have a lot of Neptunia models to mess around with.
## Post #16
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-11-05T17:36:16+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from ssringo
>
> Edit: I downloaded Fairy Fencer and although it uses .ism2 files (and an overall similar file structure) your script can't read them (or the ones I tried). I should note that the model folders contain a .cl3 file in the texture folder that's a bit larger than the associated .ism2 file. A modding guide on the Fairy Fencer steam community says the .cl3 file is a model file (so what is the .ism2?). I'll pack up one or three of the model folders if you want to take a look at them. If not, no worries. I'm sure you have enough on your plate already and I already have a lot of Neptunia models to mess around with.Use the "Console" version of the script for those. They didn't byteswap the models for Fairy Fencer F's PC version like they did for the Neptunia games, they're just a 1-to-1 copy of the PS3 version's files.

...but you're going to want to use the texture files from the PS3 version anyway, the ones for the PC version are horribly compressed in comparison.
## Post #17
- Username: samasama76
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 03, 2015 8:33 pm
- Post datetime: 2016-02-16T01:39:14+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

can someone make 3DSMAX script for Export ism2 files?
## Post #18
- Username: Mugenh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 05, 2015 1:57 am
- Post datetime: 2016-03-01T22:43:04+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

RandomTBush, you happen to have another download link to your Maxscript for this? The link that is up in the thread seems to not work. Sorry for bringing up an old topic, but I'd appreciate it.
## Post #19
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-03-02T02:26:03+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from Mugenh
>
> RandomTBush, you happen to have another download link to your Maxscript for this? The link that is up in the thread seems to not work. Sorry for bringing up an old topic, but I'd appreciate it.The MediaFire link seems to be working for me, but regardless:
[https://mega.nz/#!nlQAAK4S!KtUqFVFcaJD0 ... nwsCDesAwU](https://mega.nz/#!nlQAAK4S!KtUqFVFcaJD0oV5g14o4PpeVwIkLIPVBqnwsCDesAwU)
## Post #20
- Username: Mugenh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 05, 2015 1:57 am
- Post datetime: 2016-03-02T02:47:50+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from RandomTBush
>
> Mugenh wrote:RandomTBush, you happen to have another download link to your Maxscript for this? The link that is up in the thread seems to not work. Sorry for bringing up an old topic, but I'd appreciate it. The MediaFire link seems to be working for me, but regardless:
https://dl.dropboxusercontent.com/u/278 ... t_ISM2.zip

Ah, alright, in that case, my apologies, no idea why it would not work for me. I do appreciate it, though, thank you very much.
## Post #21
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2016-03-04T05:09:05+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

The title of this topic is misspelled. It should be "Hyperdimension", not "Hyperidmension".
## Post #22
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-03-22T03:50:56+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Hey Random, do you think you could take a look at the newly released (on PC) Neptunia U? While in game looks just like the other games, they changed the format a bit and are using .cat files. I'm hoping it's not a major change and easily figured out. 

I wouldn't even bother asking if not for the 2 new characters and clothing break (which I'm guessing is just a texture swap).  that recycling of assets  

Here's several of the .cat files from the character/costume directory in case you don't have the game. 

[http://www.mediafire.com/download/h66db ... g00c00.rar](http://www.mediafire.com/download/h66db5rpc034s63/g00c00.rar)
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-22T05:55:33+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from ssringo
>
> the newly released (on PC) Neptunia U? While in game looks just like the other games, they changed the format a bit and are using .cat files. I'm hoping it's not a major change and easily figured out.Is a major change (vertices as floats now) but easy to obtain:



n00c00_cat_75perc.jpg (236.63 KiB) Viewed 835 times
## Post #24
- Username: wordhg
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Oct 15, 2013 8:21 am
- Post datetime: 2016-03-22T14:45:09+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from shakotay2
>
> ssringo wrote:the newly released (on PC) Neptunia U? While in game looks just like the other games, they changed the format a bit and are using .cat files. I'm hoping it's not a major change and easily figured out.Is a major change (vertices as floats now) but easy to obtain:
n00c00_cat_75perc.jpg

Societ use of this WordUV
thanks!
## Post #25
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-03-22T21:45:28+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from ssringo
>
> Hey Random, do you think you could take a look at the newly released (on PC) Neptunia U? While in game looks just like the other games, they changed the format a bit and are using .cat files. I'm hoping it's not a major change and easily figured out. 

I wouldn't even bother asking if not for the 2 new characters and clothing break (which I'm guessing is just a texture swap).  that recycling of assets  

Here's several of the .cat files from the character/costume directory in case you don't have the game. 

http://www.mediafire.com/download/h66db ... g00c00.rarI already have the game, heh. Got gifted it the hour it was released. 

But yeah, Neptunia U uses a completely different model format (well it was developed by a different company, so it's not that surprising), I'll be working on making a MaxScript for that game's model format sometime sooner rather than later.
## Post #26
- Username: samasama76
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 03, 2015 8:33 pm
- Post datetime: 2016-04-01T07:53:25+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

.cat file format is using not only models, but also text, texture and ui.
I think .cat is archive file.
I tried this script [viewtopic.php?f=10&t=13001&p=114549&hilit=.cat#p114549](http://forum.xentax.com/viewtopic.php?f=10&t=13001&p=114549&hilit=.cat#p114549) (Developer is same TamSoft)
But I cant extract any files.
Can someone make quickBMS Script for .cat file formats?
## Post #27
- Username: maharnavi
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Dec 10, 2014 10:46 pm
- Post datetime: 2016-04-01T08:32:31+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Hello can anyone help me with the .rp files.They are the files of Infinite crisis.I want to decompress models and animatins and vfx files.
## Post #28
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2016-04-01T12:29:12+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Quickbms scripts for the .cat archives and .gxt textures.
They don't have any file names and I only programmed it to detect 3 different file formats inside the .cat archive.
[Tamsoft.zip](https://xentaxbackup.github.io/file/10666_Tamsoft.zip)
## Post #29
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-04-02T16:14:51+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

My model-importing MaxScript for Neptunia U is almost ready, I just need to fix up the weighting first. And see if I can at least find the material numbers, but that's not completely necessary for characters since they only have like two or three each.
## Post #30
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-04-03T02:28:37+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

MaxScript's done! Doesn't import the materials automatically since there's no filenames for me to work with, but it does give the IDs which is better than nothing.

[https://mega.nz/#!ulpnmaJS!ffrdVu0T81lK ... 8Ac8hYL6FM](https://mega.nz/#!ulpnmaJS!ffrdVu0T81lKBKR3FVkFO4K3jYPi5jtwd8Ac8hYL6FM)

Needless to say, use the QuickBMS scripts that mikulover39 posted above to unpack the *.CAT files first, then use the MaxScript on the *.TMD files. And as always, lemme know if things don't work right.
## Post #31
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-04-04T08:20:55+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Big thank you to mikulover39 and RandomTBush. Even though the selection is limited, I like these models much more than the Rebirth ones. So much easier when you aren't trying to line up/combine 4 or 5 textures to make a single facial expression.
## Post #32
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-04-04T12:45:19+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from ssringo
>
> Big thank you to mikulover39 and RandomTBush. Even though the selection is limited, I like these models much more than the Rebirth ones. So much easier when you aren't trying to line up/combine 4 or 5 textures to make a single facial expression.Well, you should still be able to use those face textures with the Re;Birth models and vice-versa if you wanted to, since the texture mapping for those is the same (barring the additional Costume Break things). And in some cases you might still want to use the Re;Birth models anyway since they've got full finger rigging, Neptunia U's models group together the last three fingers on each hand (unless you don't mind re-rigging things).
## Post #33
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-06-17T13:47:15+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

If you're lucky enough to have the Megadimension Neptunia VII beta (unlike me), I've updated my scripts to support those models now.

[https://mega.nz/#!v44XyRgJ!1ucHqBMJHoMg ... jF29YNqgdo](https://mega.nz/#!v44XyRgJ!1ucHqBMJHoMg5vES8MgL1Vo0PdAJrRPz0jF29YNqgdo)

I've also added in automatic material and texture importing (finally!), fixed bone structures (hopefully! It's a confusing mess, after all) and everything imports as one model now instead of multiple (which means it should also take less time to import). Please note, though -- the models in Megadimension Neptunia VII are actually poorly-optimized compared to the ones in Re;Birth (EVERY polygon uses three unique vertex points instead of reusing existing ones), so expect some models to take upwards of a few minutes to import fully. I'll be applying the same upgrades to the "Console" version of the script sometime later.

And here's three QuickBMS scripts -- [one for unpacking the *.CL3 files](https://mega.nz/#!X4Jj2STR!9_csZJy2ETUg_uDaKYBKjW94KuEQTSUHoVj_tAEzpkQ) (it's just Ekey's Mugen Souls Z script with a different endian, I deserve no credit), [one to unpack the DLC's *.ARC files](https://mega.nz/#!nlA2wRAS!7z88NaTtWVAx2XguTYWIwaKNSR46l0GPVY-Hxep6BKo), and [one for converting the *.TID files to *.DDS](https://mega.nz/#!6sJSiDTa!y24u5ICI9UVZTgThiQ8tFQXdUC4iOdYmRwEL-V0w5cU).

(EDIT: Fixed a couple of goofs on the model importer.)
(EDIT 2: Added a script to unpack the *.ARC files used for the DLC.)
(EDIT 3: Links are no longer dead.)
## Post #34
- Username: samasama76
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 03, 2015 8:33 pm
- Post datetime: 2016-06-26T13:58:22+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Nice script.
Is it difficult to make export ism2 script for 3dsMax?
## Post #35
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-07-06T06:24:21+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Happy to finally be able to mess about with this game's models. Almost everything is working fine for me. EDIT: Autotexturing works if you just extract everything in place. I was moving stuff around like a derp. Faces don't get autotextured for whatever reason but that's no big since ya gotta edit them to make a complete face anyways. 

Not spending too much time with the models just yet as I'm still playing the actual game
## Post #36
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2016-07-07T04:04:30+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Does anyone knows how to use modde files in Megadimension VII? KitServer doesn't work
## Post #37
- Username: StarGundam2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 06, 2016 12:23 pm
- Post datetime: 2016-07-09T15:24:20+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Thanks for all your hard work RandomTBush. If it wasn't for you I wouldn't have been able to mod Nep U. I just have one question for you. I was trying to mod megadimension and I ran into a dilemma. Everything else works with re importing using quickbms. But I can't convert the DDS back into a TID file. I tried rewriting the conversion script to reverse TID and DDS but I ended up with a file 4x smaller. I just don't know what I'm doing. Any help would be greatly appreciated. Thanks for all that you do!
## Post #38
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-07-09T23:23:40+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Uhm, when I try to convert the face .TIDs for VII the .DDS files come out broken. I've tried multiple different scripts and whatnot, and I just can't get them to convert. Is there anything you can do about this? ><

[https://mega.nz/#!L1lzwLxC!KWrdrQ6W1FTw ... u6JqqgFImQ](https://mega.nz/#!L1lzwLxC!KWrdrQ6W1FTwCi8u7NOgZGs0ThlD1aVTfu6JqqgFImQ)
## Post #39
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-10T06:24:17+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

i made a Noesis script that opens your samples  


 tex_HyperdimensionNeptuniaRebirth_tid.zip
(827 Bytes) Downloaded 123 times


it might work with dxt1 and dxt5 tid samples too but i could
not test on them because i don't have any.
## Post #40
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-07-10T08:09:10+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from AceWell
>
> i made a Noesis script that opens your samples  
tex_HyperdimensionNeptuniaRebirth_tid.zip
it might work with dxt1 and dxt5 tid samples too but i could
not test on them because i don't have any.

Thank you! Although, when I load some of the files they end up like this:

Also some of the base textures are a strange colour.
## Post #41
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-10T08:27:10+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from anime663
>
> Also some of the base textures are a strange colour.
maybe the rgba is out of order i don't know
i don't have this game and only had the 2 samples   
show me what it supposed to look like

edit
i edited the script in my previous post, try that one
## Post #42
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-07-10T19:43:53+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Its working perfectly now!! Thanks!

Edit; Oh wait now all the ones that were worknig aren't ; w ;... Could you upload both versions?
## Post #43
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-11T04:33:56+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from anime663
>
> Edit; Oh wait now all the ones that were worknig aren't ; w ;... Could you upload both versions?
i need more than the 2 samples to compare man!   
there is probably a flag that tells which order the rgba is
upload some of the ones that look funky with the new script
## Post #44
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-07-11T04:55:12+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from AceWell
>
> 
i need more than the 2 samples to compare man!   
there is probably a flag that tells which order the rgba is
upload some of the ones that look funky with the new script
[https://mega.nz/#!Ho8CHYTA!9EmD5pmcnQo- ... xTtfuL_Y-U](https://mega.nz/#!Ho8CHYTA!9EmD5pmcnQo-tNEzEarQTRo_IAhCH-sFmxTtfuL_Y-U) here you go~
## Post #45
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-11T06:32:22+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

okay i updated the script again, give it a try and see if it opens all of your tid files properly
## Post #46
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-07-11T07:07:15+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

Seems to be working for them all now! Thanks!!
## Post #47
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-07-11T19:37:17+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from anime663
>
> Uhm, when I try to convert the face .TIDs for VII the .DDS files come out broken. I've tried multiple different scripts and whatnot, and I just can't get them to convert. Is there anything you can do about this? ><

https://mega.nz/#!L1lzwLxC!KWrdrQ6W1FTw ... u6JqqgFImQI was pretty sure I caught those RGBA/ARGB variants with my script, but it's likely that I goofed somewhere. At least AceWell's script is a better alternative to that.
## Post #48
- Username: gaaaerloersq
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 25, 2016 9:06 am
- Post datetime: 2016-10-18T03:11:29+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from RandomTBush
>
> If you're lucky enough to have the Megadimension Neptunia VII beta (unlike me), I've updated my scripts to support those models now:


https://www.mediafire.com/?fk8enghk3k69bxj

I've also added in automatic material and texture importing (finally!), fixed bone structures (hopefully! It's a confusing mess, after all) and everything imports as one model now instead of multiple (which means it should also take less time to import). Please note, though -- the models in Megadimension Neptunia VII are actually poorly-optimized compared to the ones in Re;Birth (EVERY polygon uses three unique vertex points instead of reusing existing ones), so expect some models to take upwards of a few minutes to import fully. I'll be applying the same upgrades to the "Console" version of the script sometime later.

And here's three QuickBMS scripts -- one for unpacking the *.CL3 files (it's just Ekey's Mugen Souls Z script with a different endian, I deserve no credit), one to unpack the DLC's *.ARC files, and one for converting the *.TID files to *.DDS.

(EDIT: Fixed a couple of goofs on the model importer.)
(EDIT 2: Added a script to unpack the *.ARC files used for the DLC.)

Hey RandomTBush I really appreciate your 3Ds Max ISM2 importer plguin but there still seems to be some model cant import with this plugin
## Post #49
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-10-18T05:10:36+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from gaaaerloersq
>
> Hey RandomTBush I really appreciate your 3Ds Max ISM2 importer plguin but there still seems to be some model cant import with this plugin

You need to give him a hint about what model doesn't work and maybe even a sample file. If it gives an error then he'll probably want to know what the error message was. Otherwise he's not going to bother since he has no clue where to look. 

Also, as I've recently learned, the man has a lot on his plate right now so he might not even see this for a while.
## Post #50
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-10-19T03:19:10+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from ssringo
>
> gaaaerloersq wrote:Hey RandomTBush I really appreciate your 3Ds Max ISM2 importer plguin but there still seems to be some model cant import with this plugin

You need to give him a hint about what model doesn't work and maybe even a sample file. If it gives an error then he'll probably want to know what the error message was. Otherwise he's not going to bother since he has no clue where to look. 

Also, as I've recently learned, the man has a lot on his plate right now so he might not even see this for a while.^ Exactly.

I'm guessing it's probably something I missed, like a vertex type that's not supported. If you tell me what the model's name is, I can fix it up.

And on a related note, I've updated the script not too long ago to add support for Trillion: God of Destruction's models.
## Post #51
- Username: gaaaerloersq
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 25, 2016 9:06 am
- Post datetime: 2016-10-20T01:51:20+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from RandomTBush
>
> ssringo wrote:gaaaerloersq wrote:Hey RandomTBush I really appreciate your 3Ds Max ISM2 importer plguin but there still seems to be some model cant import with this plugin

You need to give him a hint about what model doesn't work and maybe even a sample file. If it gives an error then he'll probably want to know what the error message was. Otherwise he's not going to bother since he has no clue where to look. 

Also, as I've recently learned, the man has a lot on his plate right now so he might not even see this for a while.^ Exactly.

I'm guessing it's probably something I missed, like a vertex type that's not supported. If you tell me what the model's name is, I can fix it up.

And on a related note, I've updated the script not too long ago to add support for Trillion: God of Destruction's models.

I c thanks heres some of the file I found that was not importable with the 3Ds max script
but actually thats not what I was looking I was actually looking for something else but I have no clue where the model is and I found only some textures of them so I was wondering if those model might be possibly not in ism2 (I just suspect others file that I dont have any converter for them yet (for example those CWD and MGP2)) or possibly be those ism2 that were not importable
[85310.rar](https://xentaxbackup.github.io/file/11809_85310.rar)
## Post #52
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-10-20T02:17:00+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from gaaaerloersq
>
> I c thanks heres some of the file I found that was not importable with the 3Ds max script
but actually thats not what I was looking I was actually looking for something else but I have no clue where the model is and I found only some textures of them so I was wondering if those model might be possibly not in ism2 (I just suspect others file that I dont have any converter for them yet (for example those CWD and MGP2)) or possibly be those ism2 that were not importable
Judging by the internal filenames (like g/motion/m001.ism2), those appear to be animation files. That would explain why they don't work with the script -- it's only for model files, not animations.
## Post #53
- Username: gaaaerloersq
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 25, 2016 9:06 am
- Post datetime: 2016-10-20T09:02:27+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from RandomTBush
>
> gaaaerloersq wrote:I c thanks heres some of the file I found that was not importable with the 3Ds max script
but actually thats not what I was looking I was actually looking for something else but I have no clue where the model is and I found only some textures of them so I was wondering if those model might be possibly not in ism2 (I just suspect others file that I dont have any converter for them yet (for example those CWD and MGP2)) or possibly be those ism2 that were not importable
Judging by the internal filenames (like g/motion/m001.ism2), those appear to be animation files. That would explain why they don't work with the script -- it's only for model files, not animations.

Thanks I thought those ism2 might be a model and also do you think if its possible if there are others model files which is not ism2 too? because I was trying to find some model but it seems I cant find them anywhere
## Post #54
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-10-20T13:29:03+00:00
- Post Title: Re: Hyperidmension Neptunia rebirth 1 ism2

> Reply from gaaaerloersq
>
> Thanks I thought those ism2 might be a model and also do you think if its possible if there are others model files which is not ism2 too? because I was trying to find some model but it seems I cant find them anywhereProbably. I didn't see any ISM2 files for the Inafune-related things in mk2 and Victory for example, so I'm pretty sure there's another format for those (either that or I've somehow missed 'em). I'll have to look into that later.
