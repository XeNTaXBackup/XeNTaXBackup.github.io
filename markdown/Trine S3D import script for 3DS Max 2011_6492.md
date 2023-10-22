## Post #1
- Username: Nubblecakes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 25, 2011 8:12 am
- Post datetime: 2011-04-25T00:20:35+00:00
- Post Title: Trine S3D import script for 3DS Max 2011?

I was googling around for a way to get Trine models in to 3DS Max and I found a thread where a guy requested a Blender script for this file type (s3d). You can view the thread here:

[viewtopic.php?f=16&t=6465](http://forum.xentax.com/viewtopic.php?f=16&t=6465)

I don't have the first clue on how to use Blender since all I use is 3DS Max. Is it possible that someone could make a Maxscript to import Trine .S3D models (with their UV maps intact of course)? Textures aren't a problem since the .fbi format is unencrypted and can be renamed to .dds and such.

I've been wanting to mess with the Trine stuff ever since the game was released. I'd greatly appreciate it if anyone were to do this for me. I don't know how to make scripts or anything, otherwise I'd do it myself.


PS: I thought about posting this in that thread but I wasn't sure if it was the right move. The thread was basically said and done with so it seemed proper to let it die away naturally.
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-04-25T04:29:35+00:00
- Post Title: Trine S3D import script for 3DS Max 2011?

Wouldnt take much effort for you to import your model into blender, then export to FBX and import it back into max that way.
I know you said you don't have experience with blender.. but the import and export locations are pretty much the same as max under File > Export

Since there is already a blender script, making a maxscript port is easy. but blender is free to you, and its only a matter of you exploring the program. I respect that you still want a maxscript, but personally seems like a waste of effort in my opinion.

besides me, chrrox and fatduck, I don't think anyone else here does much with maxscript. you would have better luck posting this request at a maxscript forum. such a scriptspot.com
## Post #3
- Username: Nubblecakes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 25, 2011 8:12 am
- Post datetime: 2011-04-26T00:54:10+00:00
- Post Title: Trine S3D import script for 3DS Max 2011?

I see what you mean. I can certainly explore Blender some more, as I used the same process you mentioned to port Crysis models to Max. I tried using the script already but it spits out this error every time:

"struct.error: unpack requires a string argument of length 8"


EDIT: Well I think I figured out my issue here. The blender script only works for Jack Claw models. Same format but I guess there's some minor differences in the encryption or whatever you would call it that makes Trine models not work with the script.
