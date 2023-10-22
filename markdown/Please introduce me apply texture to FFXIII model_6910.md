## Post #1
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-07-04T04:00:14+00:00
- Post Title: Please introduce me apply texture to FFXIII model

I know FFXIII ripping guide in the forum, i tried to read all 20 page of that topic but i cant find a way to appy texture to the model. (iam a newbie on 3D Max)
Each time i apply texture to the model, i always get "brown" model (like model only have 1 color")

This is my step to apply texture to the model (i used 3ds Max 2010)
1>Export model to .dae , .tga texture with "Flip UV" option (Noesis) (Odin model)
2>Import .dae to 3ds max.
3> Odin model have 7 texture (000 >> 0006)
4>Open "Material Editor" and drag "000" texture to the material box.
5>Choose all mesh of Odin model and apply texture.
6> And i got this picture :



Anything i did wrong ? Please help me.
## Post #2
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-07-04T07:00:42+00:00
- Post Title: Please introduce me apply texture to FFXIII model

I think the problem is that you are selecting all mesh parts and applying the texture. You need to apply each texture to the right parts of the mesh you are only applying one texture to the entire mesh the way you said.
## Post #3
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-07-04T09:34:44+00:00
- Post Title: Please introduce me apply texture to FFXIII model

> Reply from rexil
>
> I think the problem is that you are selecting all mesh parts and applying the texture. You need to apply each texture to the right parts of the mesh you are only applying one texture to the entire mesh the way you said.

Thank you for your comment but i tried to apply one texture one mesh but nothing change   
Always get "brown" ><
The Odin model only need 1 texture to apply. I think the problem is UV but i dont know how to fix UV.
I tried skin modifier -> IV Tile but nothing happen.
## Post #4
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2011-07-06T09:36:00+00:00
- Post Title: Please introduce me apply texture to FFXIII model

I found the way to solve this. Just use Unwrap UV and fit the coordiantes ^^
But i want to convert .dae to smd. I always get "big bone" and small mesh. Anyway to fix it ?
I want export to milkshape 3d , i tried to scale up to 5 but nothing happen (the mesh is so small, and the bone is so big)
Please help me 
Thank in advanced.
## Post #5
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-07-21T14:02:35+00:00
- Post Title: Please introduce me apply texture to FFXIII model

> Reply from goder2910
>
> I found the way to solve this. Just use Unwrap UV and fit the coordiantes ^^
But i want to convert .dae to smd. I always get "big bone" and small mesh. Anyway to fix it ?
I want export to milkshape 3d , i tried to scale up to 5 but nothing happen (the mesh is so small, and the bone is so big)
Please help me 
Thank in advanced.

Hey there, when you export from Noesis, in the you can select SMD for output and in the advanced options use "-scale 20.0"  I found that 20.0 made the model big enough to work with in 3DS, of  course the bones are scaled up as well, however they won't be as ridiculous looking as before.  Try it out, it should work.
## Post #6
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-07-22T01:12:04+00:00
- Post Title: Please introduce me apply texture to FFXIII model

I've run into an issue with textures as well, I'm trying to move a model from 3dsmax2010 into Sketchup and when I do, I get a weird "banded" looking effect on the model.  It's fairly disorienting to work with...

When I view the model in 3ds it looks normal, I export to .3ds and preserve max's texture coordinates,  but something is happening which makes the texture not appear as it does in 3DS. 

Upon looking at the texture in sketchup, it shows the file as a 'colored' image, but the preview is in 'black and white'.

I see in the folder that there are 3 files(trbtex000out, trbtex001out, and trbtex002out) that could have been applied to the model; in 3ds I just dragged and dropped the "colored file" onto the model to apply the textures.

Here's a a picture of what I'm facing with.

I'm in the learning process and would greatly apppreciate any pointers or direction.
## Post #7
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-07-24T03:44:55+00:00
- Post Title: Please introduce me apply texture to FFXIII model

> I've run into an issue with textures as well, I'm trying to move a model from 3dsmax2010 into Sketchup and when I do, I get a weird "banded" looking effect on the model.

Problem resolved, it turned out that the model and textures were exported at different scales.  3DS had the facilities to correct this, however Sketchup doesn't.



So in case anyone ever runs into this issue...
## Post #8
- Username: Hikarya
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 29, 2011 2:59 am
- Post datetime: 2011-10-28T19:12:33+00:00
- Post Title: Please introduce me apply texture to FFXIII model

I have a question. I displayed Lightning on 3DS Max but her eyes and hair are bulky. 





How can I refine these details so that her hair and eyes will be displayed like this, as they would appear on Lightning in the game?





I was able to refine the details on the preview window in Neosis, but I wanna know how to do it on 3DS Max.
## Post #9
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-10-29T00:45:28+00:00
- Post Title: Please introduce me apply texture to FFXIII model

> Reply from Hikarya
>
> I have a question. I displayed Lightning on 3DS Max but her eyes and hair are bulky. 





How can I refine these details so that her hair and eyes will be displayed like this, as they would appear on Lightning in the game?





I was able to refine the details on the preview window in Neosis, but I wanna know how to do it on 3DS Max.

With the aplha texture, check the original thread, there is the explanation on how to get the alpha texture and it can be allocated in an alpha channel with the diffuse texture.
## Post #10
- Username: Hikarya
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 29, 2011 2:59 am
- Post datetime: 2011-10-29T04:37:57+00:00
- Post Title: Please introduce me apply texture to FFXIII model

> Reply from Darko
>
> 
With the aplha texture, check the original thread, there is the explanation on how to get the alpha texture and it can be allocated in an alpha channel with the diffuse texture.
Can you give me the link to the thread?
## Post #11
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-10-29T10:59:59+00:00
- Post Title: Please introduce me apply texture to FFXIII model

> Reply from Hikarya
>
> Darko wrote:
With the aplha texture, check the original thread, there is the explanation on how to get the alpha texture and it can be allocated in an alpha channel with the diffuse texture.
Can you give me the link to the thread?

This question is related to 3dsmax knowledges not to ffxiii textures problem.
Try with google .."apply tga textures with alpha channel in 3ds max"
u can use the the diffuse texture and apply it in the opacity channel in the material editor of 3ds max.
Inside opacity channel select: Alpha source > Image alpha and mono channel output > alpha..now render and that is all.
## Post #12
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-10-29T15:42:27+00:00
- Post Title: Please introduce me apply texture to FFXIII model

> Reply from Ares722
>
> Hikarya wrote:Darko wrote:
With the aplha texture, check the original thread, there is the explanation on how to get the alpha texture and it can be allocated in an alpha channel with the diffuse texture.
Can you give me the link to the thread?

This question is related to 3dsmax knowledges not to ffxiii textures problem.
Try with google .."apply tga textures with alpha channel in 3ds max"
u can use the the diffuse texture and apply it in the opacity channel in the material editor of 3ds max.
Inside opacity channel select: Alpha source > Image alpha and mono channel output > alpha..now render and that is all.

I'm assuming if he's using 3dsmax, ke knows how to aply that kind of textures, but ok... my error.
## Post #13
- Username: Hikarya
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 29, 2011 2:59 am
- Post datetime: 2011-10-30T08:44:46+00:00
- Post Title: Please introduce me apply texture to FFXIII model

> Reply from Ares722
>
> 
This question is related to 3dsmax knowledges not to ffxiii textures problem.
Try with google .."apply tga textures with alpha channel in 3ds max"
u can use the the diffuse texture and apply it in the opacity channel in the material editor of 3ds max.
Inside opacity channel select: Alpha source > Image alpha and mono channel output > alpha..now render and that is all.

I tried that, but I'm getting the same results.  My Lightning model was exported from Noesis as a .dae file with its textures as .tga and.dds files, and I tried using both the .dds and .tga files of the textures on both the diffuse and opacity channels.

UPDATE: Okay, I found two textures for Lightning's hair. The "trbtex009" file is the main texture file to color her hair, and "trbtex008" file appears to be a mesh file that will refine her hair to the way it is suppose to be. So far, I only applied the "trbtex009.dds" texture to Lightning; all I need to do is find a way to apply the "trbtex008.dds" file onto her as well so it would refine her hair. Does anyone know how to do this?
