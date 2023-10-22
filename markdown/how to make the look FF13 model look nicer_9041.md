## Post #1
- Username: YouMe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 06, 2012 6:14 pm
- Post datetime: 2012-06-06T10:25:20+00:00
- Post Title: how to make the look FF13 model look nicer?

This is the pic using Neosis Software..the preview section..I have problem to use in Maya and 3ds max because i'm still beginner

This is the before using the toggle transparency.THe character look kinda square
[](http://imageshack.us/photo/my-images/607/oriy.png/)

This is after using the toggle transparency.The character look kinda nicer and beautiful
[](http://imageshack.us/photo/my-images/171/ori2.png/)

How i want to make it look like the after image...now i'm still on the before image using Maya or 3ds max..can someone teach me how.Thank you
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-06-06T14:06:09+00:00
- Post Title: how to make the look FF13 model look nicer?

> Reply from YouMe
>
> This is the pic using Neosis Software..the preview section..I have problem to use in Maya and 3ds max because i'm still beginner

This is the before using the toggle transparency.THe character look kinda square


This is after using the toggle transparency.The character look kinda nicer and beautiful


How i want to make it look like the after image...now i'm still on the before image using Maya or 3ds max..can someone teach me how.Thank you

Are you trying to do a cell shaded render?? You're turning on the selfillumination function in noesis.

You just need to apply correctly the textures in your model in order to make it look better. Just open your textures in Photohsop or Gimp, a check the channels and you'll get the correct shaders.

See ya.
## Post #3
- Username: YouMe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 06, 2012 6:14 pm
- Post datetime: 2012-06-07T10:41:08+00:00
- Post Title: how to make the look FF13 model look nicer?

Ok so i have to turn on self illumination, but the texture is in .dds format because i extracted the model from the game..how i can change it in photoshop while it's not support .dds format..
## Post #4
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-06-07T14:08:10+00:00
- Post Title: how to make the look FF13 model look nicer?

> Reply from YouMe
>
> Ok so i have to turn on self illumination, but the texture is in .dds format because i extracted the model from the game..how i can change it in photoshop while it's not support .dds format..

Lol, your question is a little bit noobish, but you have to start with something and nobody knows everything when they start:

[http://developer.nvidia.com/nvidia-text ... -photoshop](http://developer.nvidia.com/nvidia-texture-tools-adobe-photoshop)

The textures are multichannel, It mean's that also the normal bump and the specular textures are in the same texture but different channels or in the case of the hair, the alpha texture and the specular texture are in the same texture in the same way.

See ya.
## Post #5
- Username: YouMe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 06, 2012 6:14 pm
- Post datetime: 2012-06-07T17:46:47+00:00
- Post Title: how to make the look FF13 model look nicer?

ok thank you, i will try it
## Post #6
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-06-09T15:45:09+00:00
- Post Title: how to make the look FF13 model look nicer?

> Reply from YouMe
>
> This is the pic using Neosis Software..the preview section..I have problem to use in Maya and 3ds max because i'm still beginner

This is the before using the toggle transparency.THe character look kinda square


This is after using the toggle transparency.The character look kinda nicer and beautiful


How i want to make it look like the after image...now i'm still on the before image using Maya or 3ds max..can someone teach me how.Thank you

You need to render it in something with a decent lightning and material setup support. Something like marmoset toolbag or even somewhere insideo f a game engine. The alternatively is some decent render in a 3d modelling program.

But you'll need to at least somewhat learn how to set up materials.
