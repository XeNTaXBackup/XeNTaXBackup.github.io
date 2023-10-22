## Post #1
- Username: blablukura
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 25, 2012 9:32 pm
- Post datetime: 2012-07-01T07:57:25+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

Hi, Yulgang online is an really old game, so I don't think its encryption is too complicated or may be there is no encryption at all for the files
I need help identify the view and exporter for these files, I tried Noesis but didnt work
sample files link removed =.=" rules not allow
 if someone want to examine the files pm me i'll give the linkss
.d2s is texture file ( u can view it by XnViewer or change file type to .dds, its like .dds file )
.skin is mesh file
.bon is bone file
.ani is animation file
this game has some very cool model (asian martial art style )
[http://yulgang.asiasoft.co.th/images/wallpaper/026.jpg](http://yulgang.asiasoft.co.th/images/wallpaper/026.jpg)
## Post #2
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-01T14:10:32+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

Game resource sharing is against Xentax's newest rules.
[viewtopic.php?p=73429#p73429](http://forum.xentax.com/viewtopic.php?p=73429#p73429)

Moderators delete offending posts so you might want to remove/delinkify if you want to keep your request/post.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-01T18:35:26+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

I looked at the game before and got textured meshes out but I don't remember where I put the script (doesn't seem to be in my dropbox) or what I called it.

[viewtopic.php?f=16&t=7206](http://forum.xentax.com/viewtopic.php?f=16&t=7206)

Lol this is awkward.

EDIT: turns out I never wrote a noesis plugin for it. I wrote one using the sanae3d python script but never converted it. Anyone want to send me models with textures?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-02T02:58:53+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

Here I looked at it a couple minutes ago and wrote the plugin.
[http://db.tt/j4CAFj8N](http://db.tt/j4CAFj8N)

This is the model you sent me:



There are two integers in the header that I'm not sure of, and the first byte might mean something.

There is some more data at the end of the file which I don't really get either.

For the vertex data, based on what I've learned about bone weights, there are three floats that almost add up to 1.0 all the time, followed by 4 bytes that are probably bone indices.

However I'm concerned with the fact that they don't always add up to 1.0; one of them is like 0.3 + 0.5 + 0.15, which is 0.95. Do weights always add up to 1.0?
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-02T03:11:25+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

some games list 3 floats and 4 bone id's then the leftover weight gets assigned to the last bone listed.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-02T03:17:04+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

Oh, I see 4 unique bone indices and 3 floats. That would make sense then, since it would save on space and computing the last weight wouldn't be hard.

Does noesis automatically consider that when I bind weight buffers?
## Post #7
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-02T08:10:03+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

Yes it does, or atleast it seems to do it for the PoE models.
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-12-28T16:56:03+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

Hello! seems that Yulgang files have changed a bit, no more .skin files, there is .act files and the model that is .mdl, someone knows if a script around there?, because I have seen one time ago, but doesn't find it again. Thanks!

[https://www.mediafire.com/file/34u3djeu ... es.7z/file](https://www.mediafire.com/file/34u3djeu4lw858y/yulgang_samples.7z/file)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-29T00:41:28+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

Script see repo of finale00 but the one for .skin doesn't apply (and is very basic).
So hex2obj is the quickest approach for me:
.



aojiaomao.png (92.16 KiB) Viewed 221 times


btw, great that we broke the 10 years anniversary before years' end...
(What would we have if we hadn't our "Riders of dead horses" membership?
 Wait: Riders of dead cats, in this case...  )
## Post #10
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-12-29T03:30:25+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

> Reply from shakotay2 ↑Thu Dec 29, 2022 8:41 am at Thu Dec 29, 2022 8:41 am
>
> 
Script see repo of finale00 but the one for .skin doesn't apply (and is very basic).
 , that is not the .mdl file right? no more .skin files :'(.

Oh, it is! sorry retarded moment XD
## Post #11
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-01-05T07:46:22+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

Hello please someone could make a script to read the bones of the .act file? I was getting the meshes with hex2obj but most of the models are not in T-pose and is made complicated to make an armature for each mesh and reposition  it x.x 
[https://www.mediafire.com/file/34u3djeu ... es.7z/file](https://www.mediafire.com/file/34u3djeu4lw858y/yulgang_samples.7z/file)
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-01-05T14:57:28+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

> Reply from moonpaladin ↑Thu Jan 05, 2023 3:46 pm at Thu Jan 05, 2023 3:46 pm
>
> I was getting the meshes with hex2obj but most of the models are not in T-pose ...
You've done half the job already. Keep going!  
Using ASH plus AXE:
(bailang/body/skin/skin.mdl, manually linking the nodes)



skin.png (139.29 KiB) Viewed 160 times



Edit: there's a bone index mapping table at address 0x42 right after the bone count. The bone indices are corresponding to the "skip" field of the bone layout in the above ASH screenshot. The mapping indices used by that file are:

```
2,11,1,0,14,18,3,23,4,5,7,21,10,19,13,12,17,28,24,25,26,27,16,7,8,9,22,20,15
```

Edit 2: it should be:

```
2,11,1,0,14,18,3,23,4,5,6,21,10,19,13,12,17,28,24,25,26,27,16,7,8,9,22,20,15
```
## Post #13
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-01-05T17:29:03+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

> Reply from Bigchillghost ↑Thu Jan 05, 2023 10:57 pm at Thu Jan 05, 2023 10:57 pm
>
> 
Edit: there's a bone index mapping table at address 0x42 right after the bone count. The bone indices are corresponding to the "skip" field of the bone layout in the above ASH screenshot.
Thank you Bigchillghost, gonna try your method!!
## Post #14
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-01-06T02:04:57+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

> Reply from Bigchillghost ↑Thu Jan 05, 2023 10:57 pm at Thu Jan 05, 2023 10:57 pm
>
> 
there's a bone index mapping table at address 0x42 right after the bone count.
About bone count is ok, also there is the bone index mapping for the 29 bones. 

> Reply from Bigchillghost ↑Thu Jan 05, 2023 10:57 pm at Thu Jan 05, 2023 10:57 pm
>
> 
The bone indices are corresponding to the "skip" field of the bone layout in the above ASH screenshot. The mapping indices used by that file are:
How you interpret that bone index mapping into this?.

```
2,11,1,0,14,18,3,23,4,5,7,21,10,19,13,12,17,28,24,25,26,27,16,7,8,9,22,20,15
```

I saw that this info appears in the Data Interpretation into AXE, but there is another faster way to get these values? because is long list and need to check every value that doesn't have been repeat.

> Reply from Bigchillghost ↑Thu Jan 05, 2023 10:57 pm at Thu Jan 05, 2023 10:57 pm
>
> 
Using ASH plus AXE:
(bailang/body/skin/skin.mdl, manually linking the nodes)
If I understand correctly this one is used to link the bones with their parent bones, I was trying to achieve what you got in your image, but doesn't know  which bone is the parent bone of other and so on, it have something with the index mapping right?. 

btw! if you can show the correct way to get the uv values gonna be awesome, I was doing it trial and error, cause I had not clear that value like the others.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-01-06T04:27:49+00:00
- Post Title: Need help identify Yulgang files viewer/exporter

> Reply from moonpaladin ↑Fri Jan 06, 2023 10:04 am at Fri Jan 06, 2023 10:04 am
>
> 
How you interpret that bone index mapping into this?
The IDs of the first 12 bones in the bone data section are:

```
01: 54
02: 55
03: 56
04: 57
05: 58
06: 59
07: 5A
08: 5B
09: 5C
10: 5D
11: 5F

```

and the first 4 bone mapping IDs are:

```
55,5F,54,53
```

You need to find the subscript of the corresponding ID for each value in the bone mapping table.
So for 0x55, its subscript in the bone data list is 2, for 0x5F it's 11, for 0x54 it's 1, and for 0x53
it's 0, hence you get "2,11,1,0" for the first 4 mapping values. Indeed doing so manually is really tedious.
Here's a python helper script to create the literal string directly:


 mapLiteralGen.zip
(697 Bytes) Downloaded 15 times


Just supply the filename and the bone data address as arguments. For this file, run

```
python mapLiteralGen.py skin.mdl 0x203A6
```


For details about the full usage, simply run the script without arguments:

```
python mapLiteralGen.py
```


> Reply from moonpaladin ↑Fri Jan 06, 2023 10:04 am at Fri Jan 06, 2023 10:04 am
>
> I was trying to achieve what you got in your image, but doesn't know  which bone is the parent bone of other and so on, it have something with the index mapping right?.
Not really. You need to turn on the "Display Bone Node Names" option from AXE's Preference settings before previewing the skeleton. Then link the nodes according to their logical connections. You can even do that in your 3d app if possible.

> Reply from moonpaladin ↑Fri Jan 06, 2023 10:04 am at Fri Jan 06, 2023 10:04 am
>
> 
btw! if you can show the correct way to get the uv values gonna be awesome, I was doing it trial and error, cause I had not clear that value like the others.
The uv is right after the normal vector (12 bytes) in the first vertex data block. You just need to change the base address of that chunk and use the same relative offsets of normals/uvs/vertex colors. Or feel free to use absolute address mode for all attributes if you prefer it that way.
## Post #16
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-01-06T08:42:49+00:00
- Post Title: Re: Need help identify Yulgang files viewer/exporter

> Reply from Bigchillghost ↑Fri Jan 06, 2023 12:27 pm at Fri Jan 06, 2023 12:27 pm
>
> 
You need to find the subscript of the corresponding ID for each value in the bone mapping table.
So for 0x55, its subscript in the bone data list is 2, for 0x5F it's 11, for 0x54 it's 1, and for 0x53
it's 0, hence you get "2,11,1,0" for the first 4 mapping values.
Clear! thank you! the script works perfectly .

> Reply from Bigchillghost ↑Fri Jan 06, 2023 12:27 pm at Fri Jan 06, 2023 12:27 pm
>
> 
Not really. You need to turn on the "Display Bone Node Names" option from AXE's Preference settings before previewing the skeleton. Then link the nodes according to their logical connections. You can even do that in your 3d app if possible.
Well, I was thinking in something more than just visual, because not all models are like quadrupeds were are easy to track the bone names/ parents, are many models that have many bones in like the same place (really near), anyways my method was: see the bones in blender, and connect the nodes in AXE, bone 21--> bone 6 --> bone 5 --> bone 4, but at move the bones in blender it looks bad, so I did something wrong linking the bones? or I messed something about the weights.   


> Reply from Bigchillghost ↑Fri Jan 06, 2023 12:27 pm at Fri Jan 06, 2023 12:27 pm
>
> 
The uv is right after the normal vector (12 bytes) in the first vertex data block. You just need to change the base address of that chunk and use the same relative offsets of normals/uvs/vertex colors. Or feel free to use absolute address mode for all attributes if you prefer it that way.
Honestly didn't understad much the first part, I understand much better with an example     tried with the absolute address mode for all attributes but the uv looks messed up.

Thanks for your time
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-01-06T13:01:21+00:00
- Post Title: Re: Need help identify Yulgang files viewer/exporter

> Reply from moonpaladin ↑Fri Jan 06, 2023 4:42 pm at Fri Jan 06, 2023 4:42 pm
>
> 
but at move the bones in blender it looks bad, so I did something wrong linking the bones? or I messed something about the weights.
Well, it appeared that I miscalculated the 11th mapping 
index.  Instead of 7, it should be 6. You should use the script for literal generation to avoid that.

> Reply from moonpaladin ↑Fri Jan 06, 2023 4:42 pm at Fri Jan 06, 2023 4:42 pm
>
> 
Honestly didn't understad much the first part, I understand much better with an example     tried with the absolute address mode for all attributes but the uv looks messed up.
Did you copy the params from my previous screenshot and preview the uv? Looks fine at my end. Or do you mean the texture doesn't apply?
## Post #18
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-01-06T14:33:09+00:00
- Post Title: Re: Need help identify Yulgang files viewer/exporter

> Reply from Bigchillghost ↑Fri Jan 06, 2023 9:01 pm at Fri Jan 06, 2023 9:01 pm
>
> 
Well, it appeared that I miscalculated the 11th mapping 
index.  Instead of 7, it should be 6. You should use the script for literal generation to avoid that.
Thanks! I have seen that index mapping could give me any idea to interpret the bone inheritance   

> Reply from Bigchillghost ↑Fri Jan 06, 2023 9:01 pm at Fri Jan 06, 2023 9:01 pm
>
> 
Did you copy the params from my previous screenshot and preview the uv? Looks fine at my end. Or do you mean the texture doesn't apply?
I copy all your values and the uv looks empty
## Post #19
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-01-06T15:29:15+00:00
- Post Title: Re: Need help identify Yulgang files viewer/exporter

> Reply from moonpaladin ↑Fri Jan 06, 2023 10:33 pm at Fri Jan 06, 2023 10:33 pm
>
> 
I copy all your values and the uv looks empty
Perhaps you should show the actual params you used.



uv.png (88.46 KiB) Viewed 158 times
## Post #20
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-01-09T06:23:26+00:00
- Post Title: Re: Need help identify Yulgang files viewer/exporter

> Reply from Bigchillghost ↑Fri Jan 06, 2023 9:01 pm at Fri Jan 06, 2023 9:01 pm
>
> 
 You should use the script for literal generation to avoid that.
Hello Bigchillghost its me again   , well I was able to pull the model with their parent nodes, but dunno if your exporter model have the same problems as mine, because at move the bone 7 and 8, some vertices of the hind right leg moves too   
[https://www.mediafire.com/file/9fa8bn3z ... l.FBX/file](https://www.mediafire.com/file/9fa8bn3zutpp1i1/bailangfinal.FBX/file)
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-01-09T12:17:03+00:00
- Post Title: Re: Need help identify Yulgang files viewer/exporter

> Reply from moonpaladin ↑Mon Jan 09, 2023 2:23 pm at Mon Jan 09, 2023 2:23 pm
>
> 
well I was able to pull the model with their parent nodes, but dunno if your exporter model have the same problems as mine, because at move the bone 7 and 8, some vertices of the hind right leg moves too
Your FBX file contains invalid numbers (nan) in the vertex color data. If you didn't specify the params in AXE, then you should disable this attribute when adding the param set to list or when exporting the mesh. Though it's not related to this problem.   

The problematic vertex was vertex 680, which according to the blend indices/weights table is binded to bone 6 (with a weight of 0.901426) and bone 10 (with a weight of 0.09857404). While theoretically it should be binded to bone 6 only. So I guess it's just a weight-painting mistake made by the game artist.
## Post #22
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-01-09T15:18:45+00:00
- Post Title: Re: Need help identify Yulgang files viewer/exporter

> Reply from Bigchillghost ↑Mon Jan 09, 2023 8:17 pm at Mon Jan 09, 2023 8:17 pm
>
> 
Your FBX file contains invalid numbers (nan) in the vertex color data. If you didn't specify the params in AXE, then you should disable this attribute when adding the param set to list or when exporting the mesh. Though it's not related to this problem.
pointed   .

> Reply from Bigchillghost ↑Mon Jan 09, 2023 8:17 pm at Mon Jan 09, 2023 8:17 pm
>
> 
The problematic vertex was vertex 680, which according to the blend indices/weights table is binded to bone 6 (with a weight of 0.901426) and bone 10 (with a weight of 0.09857404). While theoretically it should be binded to bone 6 only. So I guess it's just a weight-painting mistake made by the game artist.
I do not consider that possibility XD! thanks Bigchillghost!
## Post #23
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-02-09T00:57:06+00:00
- Post Title: Re: Need help identify Yulgang files viewer/exporter

Hiiiii! I have been gathering the models with the bone info one by one and it worked nice with some models but having problems with others, bad values and also the problem from above, gonna be awesome if someone could make a plugin for this game please!   
re-posting the samples : [https://www.mediafire.com/file/34u3djeu ... es.7z/file](https://www.mediafire.com/file/34u3djeu4lw858y/yulgang_samples.7z/file)
## Post #24
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-14T09:57:56+00:00
- Post Title: Re: Need help identify Yulgang files viewer/exporter

> Reply from Bigchillghost ↑Thu Jan 05, 2023 10:57 pm at Thu Jan 05, 2023 10:57 pm
>
> 
Using ASH on bailang/default.act:



bailang.png (64.4 KiB) Viewed 56 times
