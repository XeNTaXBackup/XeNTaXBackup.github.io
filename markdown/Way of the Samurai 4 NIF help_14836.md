## Post #1
- Username: outerstarz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 11, 2016 8:18 am
- Post datetime: 2016-08-11T00:34:07+00:00
- Post Title: Way of the Samurai 4 NIF help

Hello, I've been trying to work out a way with these nif files of WoTS4. They Noesis script works to an extent, but the textures dont show up and models re invisible until you export them

they dont work in nifskope, nor 3ds max

with blender they import with errors and only the bones are there

Can I have some help plz, reallly wanna start modding this game lol   

here's a sample of Sayo [http://www.mediafire.com/download/bu6iw ... Sayo01.rar](http://www.mediafire.com/download/bu6iw1z9zd2wdc2/DLCSayo01.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-12T07:49:39+00:00
- Post Title: Way of the Samurai 4 NIF help

> Reply from outerstarz
>
> They Noesis script works to an extent, but the textures dont show up and models re invisible until you export themFrom what I can see it's textured in Noesis. Exported as smd for example and reimported to blender I don't know what the problem should be:



Sayo.jpg (108.71 KiB) Viewed 240 times



btw: nifskope and blender nif support is nothing I would rely on.
I wouldn't rely on MrAdults nif script updates (  ), too, but Noesis seems to provide the most reliable nif support so far...
## Post #3
- Username: outerstarz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 11, 2016 8:18 am
- Post datetime: 2016-08-12T20:10:40+00:00
- Post Title: Way of the Samurai 4 NIF help

weird, i tried it with seveal models and certain work; but:



many models aren't texted and aren't visible until i cycle blend
## Post #4
- Username: Leo73
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Feb 18, 2019 5:06 am
- Post datetime: 2019-04-24T03:25:07+00:00
- Post Title: Way of the Samurai 4 NIF help

i can import the nif models in Noesis and export them via .fbx to Blender with Geometry and Armature plus all the Weights...but, Noesis seems to cannot import/open the game‘s .kf files with the Animations correctly. The Animation, once opened in Noesis, consists of a very very short movement, only three til four incomplete Frames with movement only on two Fingers, and i tried several .kf files, its always the same, either no movement or only a very short movement on two fingers...

when i ignore this, and import the nif and kf combo as fbx or smd, then its the same in Blender, only two fingers will move or even nothing move...  

can someone give me advice here?
## Post #5
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2019-04-24T14:17:55+00:00
- Post Title: Way of the Samurai 4 NIF help

> Reply from shakotay2 ↑Fri Aug 12, 2016 3:49 pm at Fri Aug 12, 2016 3:49 pm
>
> 
outerstarz wrote:They Noesis script works to an extent, but the textures dont show up and models re invisible until you export them
From what I can see it's textured in Noesis. Exported as smd for example and reimported to blender I don't know what the problem should be:
Sayo.jpg

btw: nifskope and blender nif support is nothing I would rely on.
I wouldn't rely on MrAdults nif script updates (  ), too, but Noesis seems to provide the most reliable nif support so far...

How did you get texture applied like that? I cant get it work
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-04-25T04:45:51+00:00
- Post Title: Way of the Samurai 4 NIF help

How should I remember after 3 years? Guess loaded the model into Noesis, then dragged and dropped the texture file, but not sure. (Be sure to try it with the same model as I did.)
## Post #7
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2019-04-25T18:20:03+00:00
- Post Title: Way of the Samurai 4 NIF help

> Reply from shakotay2 ↑Thu Apr 25, 2019 12:45 pm at Thu Apr 25, 2019 12:45 pm
>
> 
How should I remember after 3 years? Guess loaded the model into Noesis, then dragged and dropped the texture file, but not sure. (Be sure to try it with the same model as I did.)
  Its not working. Texture files are also NIF, drag and drop is not working
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-04-25T18:41:21+00:00
- Post Title: Way of the Samurai 4 NIF help

> Reply from ngovandang ↑Fri Apr 26, 2019 2:20 am at Fri Apr 26, 2019 2:20 am
>
>    Its not working. Texture files are also NIF, drag and drop is not workingwhat did you expect? It's working with genuine texture files only, afaik. 

But there's some texture handling in fmt_gambryo_nif.py by Rich. So you need to dig into it and learn how it works.
(Never cared for textures in nifs.)
## Post #9
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2019-04-29T21:40:28+00:00
- Post Title: Way of the Samurai 4 NIF help

> Reply from shakotay2 ↑Fri Apr 26, 2019 2:41 am at Fri Apr 26, 2019 2:41 am
>
> 
what did you expect? It's working with genuine texture files only, afaik. 

But there's some texture handling in fmt_gambryo_nif.py by Rich. So you need to dig into it and learn how it works.
(Never cared for textures in nifs.)
  No, I am just cant get how to export these textures from NIFs since Noesis cant export them
