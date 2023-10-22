## Post #1
- Username: Fish013
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 07, 2014 4:17 am
- Post datetime: 2015-08-07T13:18:16+00:00
- Post Title: UDK assign right textures to model

Hey guys, 
first, I'm kind of new to materials in udk and textures in common so please be gracious.
I extracted some Life is Strange textures and models and am now trying to reimport those into udk.
As I could not manage to extract the materials I have to set them up again. 
Everything kind of works so far except I have some problems with the face.

This is what my face material looks like in udk right now:


And this is the face:


Obviously this looks not exactly as it should and maybe you noticed that I have two unconnected textures in the material editor.
I don't know where to put them. I assume the bottom one is to light up the cheeks or sth. and no idea at all where to put the other one.
I should also mention that TX_Max01_Head_RGB is a 16x16 completely blue filled texture.

Did I assign anything wrong or am I missing textures? Thanks for your help in advance.
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-08-08T18:51:59+00:00
- Post Title: UDK assign right textures to model

This is completely the wrong forum for this sort of thing, but I'll help you out with what I can since its here anyway.

The unconnected one thats a white version of the face, thats the occlusion texture, you'd have to multiply that ontop of the diffuse input, the other one, honestly I've no idea what that is.

Try looking at the model in the viewport with unlit mode to see if its still screwed up, if its not, then its just your lighting and normals, that specular map also looks wrong, its just solid black, doesn't seem right to me at all.
