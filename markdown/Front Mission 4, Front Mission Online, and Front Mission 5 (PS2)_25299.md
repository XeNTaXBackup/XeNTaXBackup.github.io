## Post #1
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-04-28T21:27:56+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

Both use the same model formats but the wanzer(mech) and vehicle files are a bit odd- reading the entire vertex buffer results in a point cloud that envelopes the "good" vertices, there seems to be far more files than necessary based on keyword searches, and I can't seem to figure out the face buffer. Anybody care to take a look? I've included a file from each, their 3D Model Researcher screenshots, as well as a rip from the FMO benchmark to serve as a reference.
[Front Mission.7z](https://xentaxbackup.github.io/file/22167_Front Mission.7z)
## Post #2
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-05-05T19:24:32+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

It's been a few days and this all I've learned. 

Vertices are stored as signed shorts with the format XX XX XX XX XX XX 00 10 XX XX XX XX XX XX 00 10 or as floats ending with 00 00 80 3F. Terrain meshes only use floats while non-terrain contains both formats, using one for vertices and one for a yet unknown purpose. They seem to be linked proportionally- the more of one, the more of the other.          



While terrain vertices are directly followed by a face index of shorts, I've yet to find a similar pattern within the entire model portion of the archive. 

 



Attempts to auto-generate the faces went poorly.



Given the lack of an obvious face index, I'm starting to wonder if VIF codes are involved in all this. It's hard to tell given how new I am at this and a relative lack of detailed information on them. Again, any insight is welcomed.
## Post #3
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-05-06T23:33:02+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

The "Emotion Engine User's Manual" has a full list of VIFcodes, I'm surprised it never came up when I searched the forums for "VIF''.
## Post #4
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-05-28T17:29:21+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

I had a major breakthrough today- the faces are stored as byte-triangles where the "partner" of every face is found by shifting the offset by one. I actually found the faces yesterday by starting off at tri-bytes with small values and playing around with the padding, but it was not until I took a close look at how the faces shifted with minor changes to the padding that I realized this was really how the faces were stored and VIFs weren't involved. The faces are sub-grouped, so I'll need 3D Model Researcher Pro.  

 
 

[FM4 Hand Rod.rar](https://xentaxbackup.github.io/file/22270_FM4 Hand Rod.rar)
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-28T18:08:39+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

> Reply from Greg ↑Sun May 29, 2022 1:29 am at Sun May 29, 2022 1:29 am
>
> 
so I'll need 3D Model Researcher Pro.
use noesis and python.

(plugin only for 'FM4 Hand Rod.cl5')
[fmt_cl5.zip](https://xentaxbackup.github.io/file/22271_fmt_cl5.zip)
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-28T20:49:24+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

> Reply from Greg ↑Fri Apr 29, 2022 5:27 am at Fri Apr 29, 2022 5:27 am
>
> 
Both use the same model formats
seems other

update: finalize

(FM4 Item BP >> add ext [.cl5] and delete first 16 bytes(zero))
[fmt_cl5.zip](https://xentaxbackup.github.io/file/22275_fmt_cl5.zip)
## Post #7
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-05-28T21:53:20+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

There is a slight difference in how the Hand Rod is handled between FM4 and FMO, but they and the backpack use the same face format.

 



[FMO Hand Rod.rar](https://xentaxbackup.github.io/file/22273_FMO Hand Rod.rar)
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-29T13:05:43+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

> Reply from Greg ↑Sun May 29, 2022 5:53 am at Sun May 29, 2022 5:53 am
>
> 
use the same face format.
I say just because they are similar doesn't mean they are the same.(file format)   

i update plugin. opens file FM4.
(I have left brief comments if you would like to add support for FMO. differences are not significant)
## Post #9
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-05-29T16:48:54+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

Fair enough. Time to move onto the UVs.
## Post #10
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-06-23T22:54:09+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

Though I've yet to find the UVs, I have since found the face format of vehicles within Front Mission 4 and, in doing so, realized why there are multiple vertex and face formats- as the number of vertices grows, so do the number of bytes necessary to represent them and the faces they form. While it sounds obvious, seeing this in action was a bit of a revelation for me.    

I also poked around Front Mission 5 recently and the way it stores vertices for mechs and vehicles seems pretty odd- models are broken into numerous twenty-vert blocks that contain multiple, unavoidable duplicate vertices. It will be interesting to see how faces and UVs are handled when even a simple cube has 12 extra vertices for some reason.  

As of now, I'm at a total loss as to how to find the UVs for FM4 and FMO. I'm sure they're signed shorts as all three games tile textures when necessary and I think they're interleaved with the data above the vertex block like the faces, but I can't figure out how to "see" and search for them as I eventually did with the faces.
[Examples.rar](https://xentaxbackup.github.io/file/22418_Examples.rar)
## Post #11
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-07-05T12:57:00+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

With the help of the Discord server, the UVs have been found.
[Script-Model-Texture.rar](https://xentaxbackup.github.io/file/22449_Script-Model-Texture.rar)
## Post #12
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-09-29T01:05:36+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

I've finally sat down and wrote an extractor for individual FM4 and FMO files. I'll write a full, archive parsing one once I figure out FM5s format.
[FM4-O basic extractor and files.rar](https://xentaxbackup.github.io/file/22866_FM4-O basic extractor and files.rar)
## Post #13
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-10-03T14:26:40+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

Turns out FM5 UVs are 24 bytes past each vert block. Just need the faces, now.
## Post #14
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-10-03T22:03:06+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

After looking at an old post on Dirge of Cerberus, I've realized the faces are formed through VIFs. Looks like I have everything I need.
## Post #15
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-10-15T19:33:24+00:00
- Post Title: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

I think I've figured out FM5's faces.
## Post #16
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-10-15T20:53:59+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

Got the faces.
## Post #17
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2022-10-28T17:33:53+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

Just finished the basic extractor for FM5. Time to start the full parser.
[FM5 Basic Extractor and Models.rar](https://xentaxbackup.github.io/file/22978_FM5 Basic Extractor and Models.rar)
## Post #18
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2022-12-10T15:05:19+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

What are you using to extract the raw files from Front Mission 4 and 5? 
I think the last time I was digging for content I used Munge Explorer, and then more recently I came across some quickbms scripts on Zentax that I haven't really checked beyond using them for extracting some audio. FMO is easy as you can use the PlayOnline Installer to have nice pleasant directories.
## Post #19
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-01-02T17:35:50+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

I just copy the files manually with Hex Edit, they're easy to distinguish due to their tags. I'll get back to working on a proper extractor in a week or two, by the way.
## Post #20
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-01-12T20:44:36+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

Definitely would be cool, found the Front MIssion Online Driscoll/Raven encounter files, would love to see them in proper 3D
## Post #21
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-02-18T23:14:12+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

I've modified a QuickBMS script written by someone else to parse the archive and only extract potential model files. Now I need to write a mass-converter.
Edit: Looks like the extractor throws an error for FMO and detects only half the model count of FM4 for FM5. Just needs some tweaks.
[FM4O5 Basic DAT Parser.7z](https://xentaxbackup.github.io/file/23430_FM4O5 Basic DAT Parser.7z)
## Post #22
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-03-19T13:23:17+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

Nice, one step closer to being able to get all the mobile weapons from FMO into modeling software.
## Post #23
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-05-19T22:19:44+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

It's been a while- I had to pause my work to finish up some college credits but have since made major and necessary improvements to the FM4 extractor to make identifying models easier- meshes are now separated, faces are properly formed so half of them don't need to be flipped, and the models are now scaled within a millimeter or two of their canonical sizes when imported with units set to "meters". FMO is next.
[FM4 Converter 2.0.7z](https://xentaxbackup.github.io/file/23816_FM4 Converter 2.0.7z)
## Post #24
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-05-20T15:33:03+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

Just need to add scaling to FM5, now.
[FMO Model Converter 2.0.py.7z](https://xentaxbackup.github.io/file/23817_FMO Model Converter 2.0.py.7z)
## Post #25
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-05-20T19:10:35+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

Now back to identifying models. Instead of trying to isolate model files with the DAT Parser, I'll simply dump all the files and go over them with the extractors. I'll have to incorporate exemptions so the process doesn't crash.
[FM5 Model Converter 2.0.7z](https://xentaxbackup.github.io/file/23819_FM5 Model Converter 2.0.7z)
## Post #26
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-05-24T01:56:53+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

Got the DAT parser working even while isolating models and have altered the FM4 script to go over them.
[FM DAT Dumper.7z](https://xentaxbackup.github.io/file/23834_FM DAT Dumper.7z)
## Post #27
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-05-27T17:28:07+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

> Reply from Greg ↑Wed May 24, 2023 9:56 am at Wed May 24, 2023 9:56 am
>
> 
Got the DAT parser working even while isolating models and have altered the FM4 script to go over them.
You mind posting a quick overview of how to use these python scripts? They aren't Noesis plugins? Cmd line? Python Max Scripts? I am not a smart man.  

Attached is a Front Mission Online .DAT obtained from the FMO install tree, from the final retail release of FMO (verwinjp_060823_1647) 
The TIM2s inside it show that is the Raven, and I can see the armature notation. Does this contain the geometry as well?
[D43.zip](https://xentaxbackup.github.io/file/23843_D43.zip)
## Post #28
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-05-27T21:24:35+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

You just need to open them in IDLE or another Python IDE and provide the path of a model file where specified, the final extractor will be more streamlined. I took a look at your file, and I believe it does have geometry in it, but the layout is different from PS2 FMO files. I may need to take a look at the PC version anyhow as I'm not sure if post-launch content is on the PS2 disk.
## Post #29
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-05-27T23:45:18+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

> Reply from Greg ↑Sun May 28, 2023 5:24 am at Sun May 28, 2023 5:24 am
>
> 
You just need to open them in IDLE or another Python IDE and provide the path of a model file where specified,

so at line 20 in FM DAT Dumper.py

```
    with open(,'rb') as POS:
```


I need to put in the path to the Front Mission DAT and POS files?
like:

```
    with open(C\games\PS2\FrontMission5\DVDIMAGE.POS,'rb') as POS:
```


Because IDLE tosses an invalid syntax error here when hitting F5 to run the script and I am totally a stranger to Python, well, writing code in general.

And I'm dumping the Anniversary Edition of FMO, That's the final boxed (PC) release of the game. I can see it has quite a few more bosses, so I am assuming that the boss related equipment/rewards are on it as well. Downside is that it uninstalls the FMO Benchmark soft, which I quite like. I'll have to dig around for what PS2 FMO I have.
## Post #30
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-05-28T00:05:14+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

```
    with open('C\games\PS2\FrontMission5\DVDIMAGE.POS','rb') as POS:
```


Tried this, but then I get new complaints about: Dat Dumper.py

```
    OffsetsLocation = (int.from_bytes(POS.read(4), 'little') * 4) + 8
AttributeError: type object 'int' has no attribute 'from_bytes'
```


I'm apologize that I'm uneducated on this.

EDIT:
Just so I am not triple posting. 


Got it working by going back to your earlier script 'FM4O5 Basic DAT Parser.py' for the files extract, then running the 'FM4 Converter 2.0.py'
A bit much for the novice, but nice to see some raw meshes nonetheless. Having the parts all dumped at 0,0,0 is gross but intact UVs is a rare treat versus the bullshit workarounds with dumping from PCSX2 0.9.8.
Neat, and also an massive milestone. Good going.

I'm gonna go post about it on r/frontmission
## Post #31
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-05-28T01:57:25+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

Have you actually extracted the DAT and POS files from the ISO?
## Post #32
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-05-28T02:35:47+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

> Reply from Greg ↑Sun May 28, 2023 9:57 am at Sun May 28, 2023 9:57 am
>
> 
Have you actually extracted the DAT and POS files from the ISO?
Aw man, I missed your reply on the page jump, and have edited my previous posts multiple times.  
But yeah, I just keep getting errors when trying to extract both with FM4 and FM5 (DVDIMAGE.DAT and DVDIMAGE.POS copied from respective .ISOs with Virtual Clone Drive) 

```
  File "D:\VideoGames\PS2\FM4\FUCK\FM DAT Dumper.py", line 54, in <module>
    with open( + str(offset), 'wb') as model:
TypeError: bad operand type for unary +: 'str'
```


What did I mess up in my inability to casually parse Python?

EDIT
And how do I wildcard the code on line 177 and line 200 of 'FM4 Converter 2.0.py' to process an entire directory? Google is failing me.

```
with open('path to file\file', 'rb') as file:
ln200 
with open('path to file\file.obj','w') as obj:
```
## Post #33
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-05-28T03:43:19+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

So I get thrown the same error with FM4, FM5, and FMO PS2 when attempting to run the 'FM DAT Dumper.py'
IDLE Shell 3.11.3

```
  File "D:\VideoGames\PS2\FM DAT Dumper.py", line 54, in <module>
    with open( + str(offset), 'wb') as model:
TypeError: bad operand type for unary +: 'str'
```
## Post #34
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-05-28T13:44:25+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

But seriously, intact UVs is soooooo nice. Saves so much time, even with splitting apart materials.
## Post #35
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-05-28T14:51:45+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

```
    with open('C\games\PS2\FrontMission5\DVDIMAGE.POS','rb') as POS:
```


I think the problem is a lack of a colon after the drive letter.

```
  File "D:\VideoGames\PS2\FM DAT Dumper.py", line 54, in <module>
    with open( + str(offset), 'wb') as model:
TypeError: bad operand type for unary +: 'str'
```


You need to provide a path in which to create and write the model file, which will be named after its offset in the DAT.

> And how do I wildcard the code on line 177 and line 200 of 'FM4 Converter 2.0.py' to process an entire directory?

You need to use os.listdir to iterate over every file name in a given directory. You probably shouldn't do that as the 2.0 script isn't perfect and I'm still cleaning up issues with false positive faces and multi-model files as I work my way through FM4.
## Post #36
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-05-28T15:56:19+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

> Reply from Greg ↑Sun May 28, 2023 10:51 pm at Sun May 28, 2023 10:51 pm
>
> 
You need to provide a path in which to create and write the model file, which will be named after its offset in the DAT.

Where lol? I'm assuming:

```
with open(+str(offset), 'wb') as model:
```

needs to be:

```
with open('D:\path\to\file\location'+str(offset), 'wb') as model:
```

or something?

Edit
Yeah, that worked (except that the final "location" was appended to the dumped model name, whatever  . 
Still, cool. Now to dig through.
## Post #37
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-05-28T16:19:48+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

> Reply from totally ↑Sun May 28, 2023 11:56 pm at Sun May 28, 2023 11:56 pm
>
> 
Yeah, that worked (except that the final "location" was appended to the dumped model name, whatever  .
You needed to add an extra two backslashes after location.
## Post #38
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-06-02T16:51:44+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

Any plan to add texture extraction to the completed product? Was noticing that dumping TIM2s from FM4 (TextER) results in a lot of garbled mess. My only real success is dumping textures with Ninjaripper and then fixing the half transparency in Photoshop. Though that misses any unused/cut textures like pic related. 
Or just too far outside of the scope of your project?
## Post #39
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-06-03T17:42:54+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

I've been aware that standard texture dumping solutions do not seem to work for FM4/O/5 for quite some time, I planned to ask around about this after the model extraction scripts were complete.
## Post #40
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-06-09T19:05:32+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

> Reply from Greg ↑Sun Jun 04, 2023 1:42 am at Sun Jun 04, 2023 1:42 am
>
> 
I've been aware that standard texture dumping solutions do not seem to work for FM4/O/5 for quite some time, I planned to ask around about this after the model extraction scripts were complete.

Right on.
## Post #41
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-06-23T21:29:21+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

After going through most of the models, I've come to realize that filter files just by their headers was a mistake- it's possible for two different models to share a header after all. After comparing entire files, the current model count is 669.
## Post #42
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-07-07T01:46:53+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

With the release of all the the Structure Arts model kits my anticipation for being able to pull undistorted geometry grows exponentially
## Post #43
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-05T14:09:37+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

I've finished identifying everything in the FM4 dump. I'm going to look into what's going on with the texture before moving on to FMO.
## Post #44
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-07T22:02:07+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

I've taken a look at the textures, experimented with various tools, and have gone so far as to write my own TIM2 extractor- all of this granted some necessary insight. While I can't hazard a guess as to why certain TIM2 extractors have trouble with these games, I believe the trouble with converters is the swizzling methods use. When using Game Graphic Studio, I discovered FM4/O use BGR + I for UI elements, "PS2" for environmentals, and at least one unknown method for everything else. FM5 solely uses BGR + I but only stores UI elements as TIM2s. I guess all that leaves is figuring out what to do with the FM4/O textures.
[FM TIM2 Extractor.7z](https://xentaxbackup.github.io/file/24318_FM TIM2 Extractor.7z)
## Post #45
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-26T21:04:27+00:00
- Post Title: Re: Front Mission 4 and Front Mission Online (PS2)

It took a while, but the last hurdle has been cleared - I've managed to extract weapon, camo, and emblem textures from FMO. Trying to extract these files from any of the PS2 games proved to be a non-starter, they're either compressed or in an entirely different format but, in a stroke of mercy, the PC installer contains them as easily extracted TIM2s. The attached script works on the files from Data1.cab and Data11.cab of FMO Installer totally uploaded [here](https://mega.nz/file/kmAxGCzR#lYARajbxz8Qj-6Dj4x7IGumWMfpsY24Svb8LW9k2ynI).
[FMO TIM2 Extractor.7z](https://xentaxbackup.github.io/file/24388_FMO TIM2 Extractor.7z)
## Post #46
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-10-14T15:00:35+00:00
- Post Title: Re: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

Here's a further improved individual converter for FM4. Working on the textures gave me some ideas on how to further use regex expressions to improve efficiency. Once I modify it for FMO I can finally start identifying models again.
[FM4 Individual Converter 3.0.py.7z](https://xentaxbackup.github.io/file/24432_FM4 Individual Converter 3.0.py.7z)
## Post #47
- Username: totally
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2017 2:27 am
- Post datetime: 2023-10-15T06:43:30+00:00
- Post Title: Re: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

Greg any plans to migrate to some other internet presence since without Xentax (and Zenhax is gone,) there really isn't any simple forum (that I am aware of) for the discussion of game format stuff?
## Post #48
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-10-15T19:12:12+00:00
- Post Title: Re: Front Mission 4, Front Mission Online, and Front Mission 5 (PS2)

Not really. I post my progress here for the sake of posterity, having personally found practical information on the process hard to find. I can't imagine doing this on discord, though I will upload my completed work where ever appropriate. Thanks for uploading that FMO installer, by the way- never would have gotten the textures without it.
