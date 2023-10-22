## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-11T08:04:59+00:00
- Post Title: Dark Models

Hey guys, I'm working on ripping this one game... Magic The Gathering: Craptics. The skin for all models are really dark. Texture sheets are 1 sheet per model. Some kind of shading? Anyone got a clue what to do to the textures to create normal looking skin?

Here's a sample (it's a free game on Steam):
[http://www.mediafire.com/?6a4do5d1cbcw78r](http://www.mediafire.com/?6a4do5d1cbcw78r)

bad


bad


really bad
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-03-11T09:33:57+00:00
- Post Title: Dark Models

It looks like the diffuse shading color is set too dark judging by the sample provided, when set to white everything looks normal.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-11T10:23:49+00:00
- Post Title: Dark Models

Wow, thanks ha ha ha. Hmmm... though when I took those pics I had diffuse set to 100% already. I even tried a white diffuse map too. Man, I think it's cause I'm working from my parent's place where I only can work on this stuff on a 2006 laptop with only OpenGL 1.2 support ha ha ha. Will test on my dev machine when I get home in a few days. I see your model is mirrored so you took in into Blender then to 3DS max?

.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-03-11T19:39:17+00:00
- Post Title: Dark Models

> Reply from howfie
>
> I see your model is mirrored so you took in into Blender then to 3DS max?
I didn't alter any files from your sample, I just opened the aetheradept.lwo file in 3D Object Convertor and relinked the diffuse texture(file6.dds) and changed the diffuse color to white. Apparently 3DOC flipped it on the X axis after import but Unwrap 3d displays it just as your image does.
