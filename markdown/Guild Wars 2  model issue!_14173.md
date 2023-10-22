## Post #1
- Username: annaquick
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 26, 2015 8:56 am
- Post datetime: 2016-04-01T18:18:55+00:00
- Post Title: Guild Wars 2 > model issue!

I'm trying to extract a specific hair from Guild Wars 2. I've tried using both 3D Ripper DX and GW2Browser. The problem I encountered with GW2Browser is that I can't find the hair in the list of thousands upon thousands of files. I managed to find other hairs, but not the one I'm after. Although all the other hairs work perfectly fine in Milkshape.

The problem I'm in need of help with came with 3D Ripper DX(I also tried using ninjaripper, same issue).
When importing the ripped model into Milkshape(pref. program) the model is completely black. Normally to fix this, I either Align Normals or Smooth All faces. Both of those options leaves me with the hair having black spots all over, see image below.

This ONLY happens to the hair and not the rest of the model for some reason.
I've included a zip file with the MS3D of the full model inside, as well as the .obj if anyone would be so kind to take a look, here: [http://www.mediafire.com/download/7gep3 ... _model.zip](http://www.mediafire.com/download/7gep3tydp23u02u/gw2_model.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-02T10:19:53+00:00
- Post Title: Guild Wars 2 > model issue!

From your picture I don't see what you mean with "black spots all over".

For the "to-obj-converted/blender imported ms3d" file it seems there's a problem with the hair when smoothing the mesh.

So I imported to Noesis - does it look fine for you?



Sylvari_hair.jpg (62.47 KiB) Viewed 164 times


If so try out the dae file in the appended zip.
(Based on an obj without normals created with bkenwright's code.)

[http://www.uploadmb.com/dw.php?id=1459592339](http://www.uploadmb.com/dw.php?id=1459592339)
## Post #3
- Username: annaquick
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 26, 2015 8:56 am
- Post datetime: 2016-04-02T18:57:06+00:00
- Post Title: Guild Wars 2 > model issue!

Well maybe black spots wasn't the right words, sorry  - english isn't my first language!
If you compare the hair part to the face you can see that the hair has some awful shading issues, compared to the rest of the model which is plain smooth gray without the black "spots".

I looked at both of your files and it's the same issue unfortunately.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-02T19:22:16+00:00
- Post Title: Guild Wars 2 > model issue!

just to be sure: this does affect the textured model, doesn't it?
(if it didn't, we wouldn't talk about it, would we?)

Just for testing purposes: did you toggle the direction of the normals?

(Interestingly toggeling the back face culling in Noesis affects the eye lids (and some lower faces) only
while in blender the mesh shows holes then, especially the hair mesh.)

edit: try flipping normals of darker shaded hair regions:



FlipMe.jpg (77.1 KiB) Viewed 144 times
