## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-09-05T18:14:36+00:00
- Post Title: Kill Switch - DAT files

hello

please Look File
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-09-07T11:00:32+00:00
- Post Title: Kill Switch - DAT files

This is what I've got so far - not sure how correct it is though.

```
| Killswitch *.dat |
+------------------+

4 - Unknown
4 - Number Of Files?
4 - Unknown

// for each file
12 - Description (null) (filled with junk)
4 - Unknown
4 - Unknown
4 - Unknown
4 - Unknown
4 - Filesize [+12] (including the file header)
4 - Unknown
4 - Filenames Description Length
X - Filename (Exceluding extension) (null)
X - ID String (null)
X - Category? (null)
X - Full Path (including filename and extension) (null)
X - Full Path (null)
4 - Filesize [-24]
X - File Data
```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-09-07T19:20:26+00:00
- Post Title: Kill Switch - DAT files

Please look file *.rws (another file package from game kill switch)
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-09-08T12:48:13+00:00
- Post Title: Kill Switch - DAT files

I don't think this file is an archive - it looks to me like a single sound file that has been split up into fixed-size chunks within, thus allowing better streaming of data.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: GenericModder
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 24, 2021 7:43 am
- Post datetime: 2021-03-23T23:56:56+00:00
- Post Title: Kill Switch - DAT files

Hello everyone, just joined in hoping someone could take another look into the .dat files.

These are definitely archives containing textures, texture dictionaries, even scripts and a host of other files.

It's been over 16 years since anyone's touched this that I can see, and with the recent release of a prototype PS2 demo of this game it could certainly be useful to access the contents.

Not sure that I can upload any of these files per the forum's rules, so let me know what would be best. You can try searching for the free PC Demo which contains one level's .dat file

If you need any more information or anything let me know. New here (first post) so /shrug
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-24T08:13:15+00:00
- Post Title: Kill Switch - DAT files

You can upload some samples to external sites like Google Drive or Mega.nz and share the links with us.
Link to the demo is also fine I think.
## Post #7
- Username: GenericModder
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 24, 2021 7:43 am
- Post datetime: 2021-03-25T03:54:21+00:00
- Post Title: Kill Switch - DAT files

Awesome, thanks for the clarification.

Here's the .DAT for 'Desert2', the level available in the Demo (Which is identical to the final game's Desert2):
[https://mega.nz/file/OTp2kTxT#G6xFmk0VQ ... fMYzrCJVgY](https://mega.nz/file/OTp2kTxT#G6xFmk0VQA-1d4my8n5HBlSrTnXSYeIC0fMYzrCJVgY)

Based on taking a peek with a hex editor, there are files contained within, though it seems to be a bit of a hybrid file. Each .DAT makes what might be a function call 'StopSystem'. They list file paths/names of a file and then, presumably, the data for the file.

I've had no luck manually pulling any file data out, so hoping someone more experienced can crack this.

If you need anything else, file-wise, let me know. ~GM
## Post #8
- Username: GenericModder
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 24, 2021 7:43 am
- Post datetime: 2021-03-25T05:50:24+00:00
- Post Title: Kill Switch - DAT files

Figured I'd upload another file just for comparison sake, may help rule out certain bytes.

'Desert3.dat' ~11MB
[https://mega.nz/file/eXo2gAKZ#NG8ykrzCZ ... IUHKNkM64U](https://mega.nz/file/eXo2gAKZ#NG8ykrzCZ5e0x8jmjc74ysJqq3FtuLokwIUHKNkM64U)
## Post #9
- Username: GenericModder
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-25T18:37:58+00:00
- Post Title: Kill Switch - DAT files

Ok, So I have checked your samples and it seems that your DAT files are just some custom containers for RenderWare TXD files.
You can see my documentation here [http://wiki.xentax.com/index.php/Killswitch_DAT](http://wiki.xentax.com/index.php/Killswitch_DAT)

You have basically all the information needed to do some basic extracting, but to view those images properly you need to do more research on "texture header" section. You can use RWAnalyze and some hex editor first.


As for the TXD files, I've been doing some research lately for Teenage Mutant Ninja Turtles.
My documetation for that is here [http://wiki.xentax.com/index.php/RenderWare_TXD](http://wiki.xentax.com/index.php/RenderWare_TXD)
In the programs section you can also find my Python tool for extracting images.


There is also RenderWare SDK available on the web archive. You can check this as well to get some more info.
## Post #10
- Username: GenericModder
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 24, 2021 7:43 am
- Post datetime: 2021-03-26T02:29:33+00:00
- Post Title: Kill Switch - DAT files

I really appreciate you helping out with this.

Going to look through some of the stuff you posted, though I want to point out that these should contain much more than just TXD files.

I believe each level's .DAT contains the model for the level geometry, and may contain models for the objects used on the levels. (Rather than having a centralized location for assets, I believe they're duplicated for each level due to the way the engine's set up).

Offset 2238B4 in Desert2.dat may interest you, as it seems to name a '.level', followed by a path to a texture and a lot of weirdly structured data. There are some things that could potentially be vertices but I'm pretty inexperienced when it comes to this stuff (Still trying to learn!) so I'm not sure.

In theory, everything needed for the level (outside of sound?) should be included in this .DAT, as sound seems to be stored in .RWS files.

There is a separate '.0' file for each .DAT, but this seems to used for scripting and such.

File structure looks like this for each level:


In this case, the .DAT is the majority of the level's assets, the .0 holds the scripts/commands for the level (potentially enemy spawns and such), and the .RWS contains the level's music (called in the level's .0)

While unrelated, I'm uploading the .0 and .RWS for Desert2 in case the .0 provides some clarity. (And the .RWS for future research and potential conversion).

Desert2.0 - [https://mega.nz/file/qH4WDBKT#sxhvvpg_Z ... z4wGXpjiAI](https://mega.nz/file/qH4WDBKT#sxhvvpg_ZXaVfQXig4wzH-uadeAImIkGvz4wGXpjiAI)
DESERT2.rws - [https://mega.nz/file/nTwmVTiS#PLdd9XyGP ... GG6beeqm0Y](https://mega.nz/file/nTwmVTiS#PLdd9XyGPsAql49a74ckom2Ac0qaoNcoTGG6beeqm0Y)

Appreciate any additional help with unpacking these .DAT's! Thanks so much for what you've found so far. ~GM
## Post #11
- Username: GenericModder
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-26T16:07:47+00:00
- Post Title: Kill Switch - DAT files

It seems that you were right and those DAT files also contain other subchunks, not only texture dictionaries.
I have updated the article with the newest findings [http://wiki.xentax.com/index.php/Killswitch_DAT](http://wiki.xentax.com/index.php/Killswitch_DAT)

I have also created a script that will unpack all subchunks with the proper filenames
[https://github.com/bartlomiejduda/Tools ... AT_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Kill%20Switch/Kill_Switch_DAT_Tool.py)


I didn't do any research on DFF, LEVEL, ANM and RWS files to be honest,
so if you need any more info on those types, you could probably read some articles 
on GTA wiki, for example [https://gtamods.com/wiki/RpClump](https://gtamods.com/wiki/RpClump)
Files should be similar in some cases.
## Post #12
- Username: GenericModder
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 24, 2021 7:43 am
- Post datetime: 2021-03-26T16:17:26+00:00
- Post Title: Kill Switch - DAT files

First off - Thank you so much for your help. That's a lot of info you were able to unpack from that, and I really appreciate it.

I'll try out the script later and read through your findings, they seem quite detailed.

If I find out any other information I'll be sure to post it here, perhaps I'll look into extracting content from the .level if I can figure it out.

Thank you again! ~GM
