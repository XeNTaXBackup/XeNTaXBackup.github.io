## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-10-13T19:41:44+00:00
- Post Title: Driver San Francisco PC ???

I want to rip the cars from DRIVER SF , it seem like people have done it before but I am confused. I googled but there's only threads that didn't get far or did get far, but it's a maxscript, for a program that costs too much  

I need to extract file : SP file. this contains vehicle.   

I use the program Blender and I am on Windows 11.                

file ( dng vehicles.sp ) [https://drive.google.com/file/d/1IDogyq ... sp=sharing](https://drive.google.com/file/d/1IDogyqo720XbHkFBlmllbKf6FKdf1TMF/view?usp=sharing)
## Post #2
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-12-22T19:53:14+00:00
- Post Title: Driver San Francisco PC ???

im still trying to find a way to extract the car models..
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-23T11:05:58+00:00
- Post Title: Driver San Francisco PC ???

> Reply from ReVolt ↑Thu Oct 14, 2021 3:41 am at Thu Oct 14, 2021 3:41 am
>
> 
but it's a maxscript, for a program that costs too muchIf you were a student you could get it for free, afaik.
And if you have a maxscript then it should be simple (usually, with some basic understanding) to use the info in it for creating H2O files.
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-12-23T20:56:37+00:00
- Post Title: Driver San Francisco PC ???

maxscript original and decompiled. using it you can make a plugin for blender
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-23T21:03:12+00:00
- Post Title: Driver San Francisco PC ???

> Reply from Durik256 ↑Fri Dec 24, 2021 4:56 am at Fri Dec 24, 2021 4:56 am
>
> maxscript original and decompiled. using it you can make a plugin for blender... and don't forget to mention the original authors. Will spare you some troubles. 

(Plus, this decompiling is legal, is it?  ) Because, if they provided the mse only they obviously didn't want the source (ms script) to be public. Just my two cents.
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-12-23T22:00:07+00:00
- Post Title: Driver San Francisco PC ???

"for academic purpose"
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-24T00:06:37+00:00
- Post Title: Driver San Francisco PC ???

Hey, I didn't want to interrupt your research "for academic purpose", really.  

I merely didn't want you to get into troubles, if any.

Merry Christmas
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-03T13:15:00+00:00
- Post Title: Driver San Francisco PC ???

original max script from :

> Reply from Chipicao ↑Wed Jan 01, 2014 12:19 am at Wed Jan 01, 2014 12:19 am
>
> 
Vehicle importer for Driver San Francisco.
there will be no updates

> Reply from ReVolt ↑Thu Dec 23, 2021 3:53 am at Thu Dec 23, 2021 3:53 am
>
> 
im still trying to find a way to extract the car models..
load .sp, export all cars or one.
load .VEHC file (model car) works very slowly

('load selected' dont work)
how to load a model from the tool panel when the file is already loaded?
[fmt_vehc.zip](https://xentaxbackup.github.io/file/21499_fmt_vehc.zip)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-03T15:39:32+00:00
- Post Title: Driver San Francisco PC ???

> Reply from Durik256 ↑Mon Jan 03, 2022 9:15 pm at Mon Jan 03, 2022 9:15 pm
>
> 
load .VEHC file (model car) works very slowlyyeah, that's strange. Seems there's a delay before
"Detected file type: driver sf file"
(Even with a "fresh" start of Noesis without loading the .sp file before.)

> how to load a model from the tool panel when the file is already loaded?what?
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-03T16:00:30+00:00
- Post Title: Driver San Francisco PC ???

> Reply from shakotay2 ↑Mon Jan 03, 2022 11:39 pm at Mon Jan 03, 2022 11:39 pm
>
> 
what?
when the "noepyLoadModel" method is complete and I add the model to the mdlList from toolbar(button "load selected">method importVHEC), nothing happens
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-03T16:12:07+00:00
- Post Title: Driver San Francisco PC ???

maybe an indexing problem? It displays 445 VW_Camper_1965_LOD1.VEHC for me when I select 259 VW_Camper_1965_LOD1.VEHC
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-03T17:13:06+00:00
- Post Title: Driver San Francisco PC ???

> Reply from shakotay2 ↑Tue Jan 04, 2022 12:12 am at Tue Jan 04, 2022 12:12 am
>
> 
maybe an indexing problem?
it's just a name   
in list its (id and name), and in console (index and name)

that's what I mean. how to load the model from the toolbox. adding to the mdlList gives nothing  

[fmt_test.zip](https://xentaxbackup.github.io/file/21502_fmt_test.zip)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-03T18:16:19+00:00
- Post Title: Driver San Francisco PC ???

Ok, from what I see the data is loaded from the BitStream object but not displayed.
It stops after
...
2d74b254653913c0
2d74b2545f3913c0

(So createMesh() is called several times after LoadSelected.)

Funny: when you log the positions in importVEHC() once directly loading a .vehc file, and then by "Load selected" the first ones are identical, but the ladder creates a 50 times bigger log. What?
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-04T02:27:52+00:00
- Post Title: Driver San Francisco PC ???

> Reply from shakotay2 ↑Tue Jan 04, 2022 2:16 am at Tue Jan 04, 2022 2:16 am
>
> 
but not displayed.
when method "noepyLoadModel" stop(return 1) then dont load model  

new script
if load model as one mesh then very fast
[fmt_%.zip](https://xentaxbackup.github.io/file/21503_fmt_%.zip)
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T07:31:26+00:00
- Post Title: Driver San Francisco PC ???

yeah, that's a workaround for the memory problem not loading the .sp at the same time. 

Comparing face indices for both "runs", loading .VEHC separately or with "Load selected".
edit: correction, logged ind1, 2 and 3 now and they are identical. (Seems there was an error with my formatting of the face array.)
## Post #16
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-04T17:30:54+00:00
- Post Title: Re: Driver San Francisco PC ???

> Reply from shakotay2 ↑Tue Jan 04, 2022 3:31 pm at Tue Jan 04, 2022 3:31 pm
>
> 
the data is corrupted:

maybe the data is corrupted
but i can't load empty model (NoeModel()) from button click.

```
    mdlList.append(NoeModel())#dont work
    return True
```


I tried through rapi.toolLoadGData(mList)

```
rapi.toolLoadGData(mList)

```

I get an error "RuntimeError: Called rapi function in uninitialized state!"
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T17:45:50+00:00
- Post Title: Re: Driver San Francisco PC ???

I'll have a look at it asap! Your using very interesting ("windows") features from Noesis, btw.  

So there's not many .py scrips as a reference. In fact I don't have any other samples which (for example) use getControlById (from noewin.py).
You're (one of) the first to use it, congratz. 

Reason is that most scripts deal with seperate model files only, not with an archiv.
## Post #18
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-04T18:01:38+00:00
- Post Title: Re: Driver San Francisco PC ???

> Reply from shakotay2 ↑Wed Jan 05, 2022 1:45 am at Wed Jan 05, 2022 1:45 am
>
> 
congratz.
thank  

I solved the "load Selected" issue. saving to a temporary file and opening it. 

```
exportVEHC(listIndex)
noesis.openAndRemoveTempFile(tempPath)
```


But I still want to load the model into the previewer via the toolbar without opening the file 
[fmt_vehc.zip](https://xentaxbackup.github.io/file/21519_fmt_vehc.zip)
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-04T18:34:24+00:00
- Post Title: Re: Driver San Francisco PC ???

> Reply from Durik256 ↑Wed Jan 05, 2022 2:01 am at Wed Jan 05, 2022 2:01 am
>
> But I still want to load the model into the previewer via the toolbar without opening the fileI know.   You'd need a debugger for such to find the cause of the problem. (Checking object addresses using the integrated "Universal debugger", from Noesis/Tools gave me no clues.)

edit: I logged some offsets:

thinking...
(they had to be different because they were from a specific .VEHC versa it's corresponding data block in the .sp)
Search for string "Pooled vertex dependencies>>>" in .VEHC file. After that the mentioned offsets start.

This is totally strange, I logged vertices and face indices into a file when using "Load selected" and this is the result (why the heck doesn't noesis display the model then?  )
.



strange_ok.png (58.96 KiB) Viewed 115 times
## Post #20
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-05T02:15:24+00:00
- Post Title: Re: Driver San Francisco PC ???

> Reply from shakotay2 ↑Wed Jan 05, 2022 2:34 am at Wed Jan 05, 2022 2:34 am
>
> 
This is totally strange, I logged vertices and face indices into a file when using "Load selected" and this is the result (why the heck doesn't noesis display the model then?  )
it loads the models only once the first time the method is called "noesis.setHandlerLoadModel(handle, noepyLoadModel)" when we  open registered file.   

works here: 

> Reply from Durik256 ↑Wed Jan 05, 2022 2:01 am at Wed Jan 05, 2022 2:01 am
>
> 
saving to a temporary file and opening it.
I think we've had enough, let the author of this topic figure it out
## Post #21
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-05T18:08:37+00:00
- Post Title: Re: Driver San Francisco PC ???

new .sp file extractor 
[fmt_sp.zip](https://xentaxbackup.github.io/file/21531_fmt_sp.zip)
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-05T19:02:26+00:00
- Post Title: Re: Driver San Francisco PC ???

Very quick .sp unpacking!

(And some day   we will know why it takes so long between noepyCheckType(data) and "Detected file type: driver sf file" when loading one  VEHC file (about 1 MB). Maybe that message is in the windows queue earlier, I dunno.  )
## Post #23
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2022-01-09T21:23:00+00:00
- Post Title: Re: Driver San Francisco PC ???

this is cool...but the wheels are not positioned and no textures.
## Post #24
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2022-01-09T23:54:56+00:00
- Post Title: Re: Driver San Francisco PC ???

I got textures using DragonUnPACKer but I have an issue

some of the textures are wrong color 



How do I fix this?
## Post #25
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2022-01-10T00:11:55+00:00
- Post Title: Re: Driver San Francisco PC ???

AHA, the trick was...these textures weren't even supposed to have color! I grayscaled them and it looks correct now.
for the wheels I just seperated the brake models from the model, set origin on them, and positioned the wheels from there.
