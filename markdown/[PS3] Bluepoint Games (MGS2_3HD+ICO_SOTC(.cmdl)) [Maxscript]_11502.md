## Post #1
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-05-11T19:43:42+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

I've attached a Maxscript which can be used to import the .cmdl extension that both MGS3 and MGS2 on the HD Collection use. It imports the models with some flipped faces so you'll have to select all the polygons and unify them. It has support for UV's however the models aren't split into separate objects therefore you'll have to apply the textures by selecting polygons. Bones aren't supported as I have no experience in that area however the file structure is rather simple therefore anyone that does would be able to figure it out fairly simply.

you can access the cmdl files by extracting the psarc files on the disc, there are a few tools that can do this. Textures are contained in ctxr files, I've also included a tool I made to convert ctxr files to gtf files, you can then use gtf2dds, a tool which is part of the sony sdk, to convert them to dds, thanks to thisistheend/ratengera for divulging information about the ctxr in [this topic](http://forum.xentax.com/viewtopic.php?f=18&t=7678).

I haven't tested it on all files so let me know if there's a problem with the Maxscript or ctxr2gtf.

EDIT: This also works for other games ported by Bluepoint, such as Ico and Shadow of the Colossus


[Metal Gear Solid 3-2 CMDL.zip](https://xentaxbackup.github.io/file/19480_Metal Gear Solid 3-2 CMDL.zip)
## Post #2
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2014-05-12T17:23:41+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

Thanks JayK.
## Post #3
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2014-05-12T19:16:50+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

great work! ty so much!
## Post #4
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2014-07-22T23:47:47+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

where can you find the map files?
## Post #5
- Username: halflifedave
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 10, 2008 2:05 pm
- Post datetime: 2015-01-07T01:04:55+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

Sorry for the bump, but tried this script out recently.

For MGS3, some of the human models are still missing faces after the polygon is unified. Actually, even the rat model I tested had a few missing faces on the bottom right. Looks to work perfectly with the sorrow_slot files though.
For MGS2, the player model I attempted also still had missing faces and it looks like all the body parts are centered on top of each other.

Thanks again for this script. Hope this feedback is useful.

[http://i.imgur.com/lD4yf7i.jpg](http://i.imgur.com/lD4yf7i.jpg)
[http://i.imgur.com/KHN8Kba.jpg](http://i.imgur.com/KHN8Kba.jpg)
[http://i.imgur.com/6v5nCHf.jpg](http://i.imgur.com/6v5nCHf.jpg)
## Post #6
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2015-01-07T02:25:50+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

Hmm if it's happening on the same rat model I used above, then maybe there are more faces you'll have to flip manually, did you use the unify option only or did you also flip faces manually?
## Post #7
- Username: halflifedave
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 10, 2008 2:05 pm
- Post datetime: 2015-01-07T02:30:15+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

did unify only

just manually flipped the holes from the unify, that fixed it up for the rat works for other models too. thanks
## Post #8
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2015-06-29T21:24:37+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

I updated the title as I realised Bluepoint games use the cmdl format for all the games they port, so this should work for any of their games on PS3, recently tried it with the ICO + SOTC Collection.
## Post #9
- Username: firblind
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Oct 31, 2019 10:06 am
- Post datetime: 2020-08-02T22:52:21+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

Hey! I got the cmdl files from the SOTC PS3 Remaster, and I'm getting an error no matter what model I attempt to import. What model did you import with the script, and what could I have done wrong when getting the CMDL files?
## Post #10
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2020-08-03T16:08:58+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

Hi, if you PM me the file I'll have a look at it, thanks.
## Post #11
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-11-26T15:09:36+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

Little new to this, there's only 1 .psarc file in the MGS3 directory for the HD collection I see called mgs3_misc.psarc and doesn't have anything I want, the other ones have number extensions like .psarc.66608 and such, renaming them didn't work for me. How do I extract these files?
## Post #12
- Username: 316austin316
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 27, 2020 2:14 pm
- Post datetime: 2023-01-28T16:14:11+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

> Reply from AxelNoir ↑Thu Nov 26, 2020 11:09 pm at Thu Nov 26, 2020 11:09 pm
>
> 
Little new to this, there's only 1 .psarc file in the MGS3 directory for the HD collection I see called mgs3_misc.psarc and doesn't have anything I want, the other ones have number extensions like .psarc.66608 and such, renaming them didn't work for me. How do I extract these files?

rename them to .psarc and use the PSArctool to extract what's inside.. forgot to add you gotta rename them from .001 to .010 and then merge all the files together into one .arc except for the last misc.arc
## Post #13
- Username: 316austin316
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 27, 2020 2:14 pm
- Post datetime: 2023-02-04T06:58:33+00:00
- Post Title: [PS3] Bluepoint Games (MGS2_3HD+ICO_SOTC(.cmdl)) [Maxscript]

There's a good amount of MGS 2 Models that don't seem to work
