## Post #1
- Username: johncarterthe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 29, 2017 10:25 pm
- Post datetime: 2017-06-29T14:43:51+00:00
- Post Title: Help convert .mesh to .obj from Cars Lightning League

Hi , So in recent weeks disney released the android game Cars : Lightning League.

I tried ripping the models using ninja ripper and nox app player/bluestacks but the game wont even start up.

So I then extracted the .assets file and tried to convert the mesh to obj and only 2 worked and that was lightning and mater.

I tried to extract the rest of the models but kept getting the "cant convert compressed meshes" in UAEB

So now I got all the .mesh files of all the character bodies but don't how to open or convert to obj.

Please if anyone can help thanks 


 Unity Mesh Models.zip
(246.47 KiB) Downloaded 32 times
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-30T09:31:16+00:00
- Post Title: Help convert .mesh to .obj from Cars Lightning League

> Reply from johncarterthe
>
> So now I got all the .mesh files of all the character bodiesHi,
where/how did you get them from?



Disney_Cars-Lightning-League-APK.JPG (248.03 KiB) Viewed 121 times
## Post #3
- Username: johncarterthe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 29, 2017 10:25 pm
- Post datetime: 2017-06-30T10:39:16+00:00
- Post Title: Help convert .mesh to .obj from Cars Lightning League

> Reply from shakotay2
>
> johncarterthe wrote:So now I got all the .mesh files of all the character bodiesHi,
where/how did you get them from?
Disney_Cars-Lightning-League-APK.JPG

I got it by opening the shareassets1.assets with UnityEX but I found a better method to get the 3d models using AceWell method : [viewtopic.php?p=125969#p125969](http://forum.xentax.com/viewtopic.php?p=125969#p125969)

Only thing now is that I don't know how to open/convert .tex to actually texture it , there is also .pvr files.

Files : [http://www.datafilehost.com/d/0fa4cbfd](http://www.datafilehost.com/d/0fa4cbfd)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-01T05:56:28+00:00
- Post Title: Help convert .mesh to .obj from Cars Lightning League

> Reply from johncarterthe
>
> Only thing now is that I don't know how to open/convert .tex to actually texture it , there is also .pvr files.
it is best to just convert the textures directly using UABE so you never have to deal with *.tex conversion afterward, so
go ahead and delete those pvr and tex files then select the textures from the list in UABE then click Plugins and choose a
format.
## Post #5
- Username: johncarterthe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 29, 2017 10:25 pm
- Post datetime: 2017-07-01T11:41:08+00:00
- Post Title: Help convert .mesh to .obj from Cars Lightning League

> Reply from AceWell
>
> johncarterthe wrote:Only thing now is that I don't know how to open/convert .tex to actually texture it , there is also .pvr files.
it is best to just convert the textures directly using UABE so you never have to deal with *.tex conversion afterward, so
go ahead and delete those pvr and tex files then select the textures from the list in UABE then click Plugins and choose a
format.

Hi AceWell 

The thing is I didnt take the .tex from the the assets file because it was like a low quality not detailed texture , so I decided to get it from the cache folder from my android device , the file size of the .tex is much higher than the one in the assets file leading me to think its the much more detailed , so is there a way to import .tex into UABE to convert it.

Thanks in advance
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-02T00:03:19+00:00
- Post Title: Help convert .mesh to .obj from Cars Lightning League

> Reply from johncarterthe
>
> is there a way to import .tex into UABE to convert it.
yeah sometimes you can open a unity file and import raw the tex file into an existing texture
slot then save it to new asset and open that and convert to usable texture with UABE "Plugins".   

before you import raw the tex file insert (NOT overwrite) this to the beginning of it:

```
04 00 00 00 41 42 43 44
```

this will give it the name ABCD in the list so you can identify it easy  

this is trial and error and may or may not work with your tex files though but the pvr files should
easily be converted with PvrTexTool, heck maybe try to convert the tex files with that tool also.
## Post #7
- Username: meff1091
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 01, 2016 8:34 pm
- Post datetime: 2018-03-26T19:23:33+00:00
- Post Title: Help convert .mesh to .obj from Cars Lightning League

I have all the models extracted from the game. No need hex editing. Unity studio is enough
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-26T23:26:27+00:00
- Post Title: Help convert .mesh to .obj from Cars Lightning League

> Reply from meff1091
>
> I have all the models extracted from the game. No need hex editing. Unity studio is enough
for models now yes, 9 months ago not so much i guess, don't know, johncarterthe didn't share the .assets file.
the hex editing advice was optional and for adding a identifying name to the highres .tex file he got from cache
folder so he could import into and convert with UABE and see it clearly listed, this had nothing to do with models.   
all is explained in the thread, thank you for reading (or not) and the bump!
