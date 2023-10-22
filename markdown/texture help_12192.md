## Post #1
- Username: Sammael666
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 21, 2010 12:23 am
- Post datetime: 2014-11-03T19:53:01+00:00
- Post Title: texture help

Hello, can someone help me this Spiderman model to texture? I do not understand not with the black pattern. 

Here's a photo: [http://theflickcast.com/wp-content/uplo ... sion-2.jpg](http://theflickcast.com/wp-content/uploads//Cosmic-Spider-Man-Ultimate-Version-2.jpg)

 I have no idea how this works. In the appendix you will find the mesh with the associated textures.

[https://www.sendspace.com/file/jnqn5k](https://www.sendspace.com/file/jnqn5k)
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-11-03T21:05:23+00:00
- Post Title: texture help

The .mtl file was completely messed up. Here's a fixed model:
[https://www.sendspace.com/file/gx1e6f](https://www.sendspace.com/file/gx1e6f)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-05T16:01:23+00:00
- Post Title: texture help

> Reply from Sammael666
>
> Hello, can someone help me this Spiderman model to texture? I do not understand not with the black pattern. 

Here's a photo: http://theflickcast.com/wp-content/uplo ... sion-2.jpg

 I have no idea how this works.It might be helpful if you told us how u created that obj file.
For example how it comes that it contains
usemtl wire_135006006_4e00c1e6.dds

Was it u who gave the material the name of a texture (.dds)?
Do u have an original dds for that model?

I tried to use the black.bmp as a kinda bump map.

That's the result but atm I don't know to make the pattern black:



spiderman_bump.JPG (29.98 KiB) Viewed 75 times



edit: upps, the pattern is z-flipped? - strange
## Post #4
- Username: Sammael666
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 21, 2010 12:23 am
- Post datetime: 2014-11-05T18:43:24+00:00
- Post Title: texture help

This is exactly what I mean that the black pattern is somehow mirrored. 
But if I do then reflects it looks still different. 
In Spiderman Shattered dimensions it looks like from the picture posted by me. 
And yes these are the original textures. I had just renamed.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-05T20:48:20+00:00
- Post Title: texture help

could you upload an ingame screenshot of spiderman's back
so that it can be compared to this one?



back.JPG (33.83 KiB) Viewed 61 times



btw: did you get the pattern black? If so, how?
## Post #6
- Username: Sammael666
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 21, 2010 12:23 am
- Post datetime: 2014-11-06T18:46:08+00:00
- Post Title: texture help

Here is a picture
[view.jpg](https://xentaxbackup.github.io/file/8044_view.jpg)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-06T22:36:28+00:00
- Post Title: texture help

thx.

I didn't solve the problem but I think I know how the wrong pattern "is built":



pattern_prob.jpg (81.41 KiB) Viewed 45 times



(that's a part of the y-flipped black-bmp, so it doesn't need to be mirrored - I was just too lazy to undo it again)

btw: I really would prefer some bump mapped pattern (maybe a little bit less than in my first pic and colored black) but imho it looks more "mystical" than the "painted" pattern from your picture.
