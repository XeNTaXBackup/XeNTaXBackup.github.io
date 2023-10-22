## Post #1
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-02-09T09:06:54+00:00
- Post Title: Genesis Rising [Solved]

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-02-09T13:22:03+00:00
- Post Title: Genesis Rising [Solved]

Thanks for posting this AceAngel, I too would like to get more information on these models. I tried OGLE and 3d ripper dx with no luck.
## Post #3
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-02-09T15:40:30+00:00
- Post Title: Genesis Rising [Solved]

So far it seems the models are reliant on the animation files to work properly. Everytime I delete an animation file, the model is loaded in T-Pose, however it crashes after a few milliseconds after you see the model. Not enough time to start the ripper and get it working properly.

OpenGL rippers...I'm not sure which one I tried, but the one I tried didn't rip anything viable...mish mash of useless data.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-10T17:31:48+00:00
- Post Title: Genesis Rising [Solved]

Well the .geomb format is roughly as follows:
It starts with a 64 Byte header starting with the magic, version and the mesh name (has a fixed size but I don't know what size)
It is then made up of chunks:

```
char datatype[8];
// data
```


chunk types are: pos, nrml, tangent, binorm, tex0, tex1, tex2, tex3, wght, boneId
## Post #5
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-02-11T19:50:35+00:00
- Post Title: Genesis Rising [Solved]

Excellent, Thanks for the information Rheini!
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-11T19:53:37+00:00
- Post Title: Genesis Rising [Solved]

Don't know the format of those chunks though.
Guess fatduck would figure it out in a minute
## Post #7
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-02-11T21:02:19+00:00
- Post Title: Genesis Rising [Solved]

Well, at least the format now has it's feet wet...that's a start, right? RIGHT?
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-02-15T19:47:31+00:00
- Post Title: Genesis Rising [Solved]

AceAngel,

You can download the converted ship objects (in .obj/mtl format) using the following link:
[http://web.t-online.hu/karpo/ship_geomb_to_obj.zip](http://web.t-online.hu/karpo/ship_geomb_to_obj.zip)
## Post #9
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-02-15T22:58:32+00:00
- Post Title: Genesis Rising [Solved]

Amazing! Are you willing to share the tool that you used to do this? GR has dozens more ships that I would like to convert.
## Post #10
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-02-16T12:40:19+00:00
- Post Title: Genesis Rising [Solved]

3DVIA Printscreen may be useful for you !
[viewtopic.php?f=18&t=3313](http://forum.xentax.com/viewtopic.php?f=18&t=3313)
## Post #11
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-02-16T12:45:39+00:00
- Post Title: Genesis Rising [Solved]

Thanks Karpati,

I just searched 3DOC, but I couldn't find the format supported. Also, I'm not sure if I can buy your program for now...

Could you tell me how your were able to convert the format? A CMD would be fine for me...

Also, PrintScreen doesn't work for me since the UV's are lost. If anyone knows of a importer that doesn't lose the UV's please do tell.
## Post #12
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-02-16T14:24:31+00:00
- Post Title: Genesis Rising [Solved]

I added this module to my developer version of the 3D O.C only.
When I will release that I will inform you (I must finish this module totally).
## Post #13
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-02-16T15:21:06+00:00
- Post Title: Genesis Rising [Solved]

So no hopes for a free CMD version?
## Post #14
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-02-16T18:48:57+00:00
- Post Title: Genesis Rising [Solved]

> Reply from Karpati
>
> I added this module to my developer version of the 3D O.C only.
When I will release that I will inform you (I must finish this module totally).

That's great news Karpati, looking forward to it
## Post #15
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-02-19T16:18:06+00:00
- Post Title: Genesis Rising [Solved]

Today I released the 3D Object Converter v4.221 update at 17:10.

You can update your installed application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates).


My program currently supports 8 different uncompressed types of the DirectDraw Surface *.dds texture format. The Genesis Rising uses the compressed .dds format.

When I wrote and tested my .geomb/gobj loader module I used the following procedure to get the texture shaded view (in my program):

- Convert the .dds files into .jpg files using the Irfanview's batch converter module.
- Run the 3D O.C.
- Check out the Options/Import/Default texture file extension (.jpg)
- Turn on the 'Options/Import/Set the default texture file extension in the material table after load'
  (This will replace the .dds file extension to .jpg automatically after load your object)

  (Or you can use the 'Tools/Set the default texture file extension in the material table after every load if you would like...)

- Save settings.
- Apply settings.
- Load the .geomb file.


[http://web.t-online.hu/karpo](http://web.t-online.hu/karpo)
## Post #16
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-02-22T07:32:32+00:00
- Post Title: Re: Genesis Rising

AceAngel,

I don't plane to create a free CMD version, because I am developing one version only.
## Post #17
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-02-23T12:36:18+00:00
- Post Title: Re: Genesis Rising

So basically, I have to buy a 50$ program only to use 1 importation format...out of the 500 that I don't need.

Le sigh?
## Post #18
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-02-23T16:16:53+00:00
- Post Title: Re: Genesis Rising

Have a good day and send only 30$ to me (using the PayPal system) with the codename: 'AceAngel'.
## Post #19
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-03-21T09:48:32+00:00
- Post Title: Re: Genesis Rising

I added the compressed .dds (DXT1, DXT2, DXT3, DXT4, DXT5) texture loader module to V4.40 and today I released the 3D Object Converter v4.40 update at 19:00.

You can update your installed application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates).
## Post #20
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-10-17T14:02:16+00:00
- Post Title: Re: Genesis Rising

I added the Generis Rising to my gallery:

[http://web.t-online.hu/karpo/gallery_ge ... ising.html](http://web.t-online.hu/karpo/gallery_genesis_rising.html)
