## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-05-12T20:10:32+00:00
- Post Title: Question abouth Alpha view in 3DS Max

How try see tranparence textures with alpha channels (TGA) in 3ds max, but every time i make a render or i put a model with the textures right i see only black areas in the alpha area, in milkshape an other programs i not have this problem, anyone know why this happend and how to fix?
## Post #2
- Username: KFK
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 06, 2010 4:46 am
- Post datetime: 2011-05-15T11:01:00+00:00
- Post Title: Question abouth Alpha view in 3DS Max

I assume your opacity maps are properly applied in the first place.

Make sure "Show standard map in view port" is checked at the TOP level of the material - not in Diffuse, not in Opacity. Max is unbelievably thick-headed about this.
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-05-21T00:48:31+00:00
- Post Title: Question abouth Alpha view in 3DS Max

Sorry doens work too i try all, and the texture have alpha right, here the files sample. thanks and regards.

[http://www.megaupload.com/?d=0K7CRAD4](http://www.megaupload.com/?d=0K7CRAD4)
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-05-21T10:15:01+00:00
- Post Title: Question abouth Alpha view in 3DS Max

Ok, first copy the diffuse to opacity slot. Don't choose instance but copy

Next, go into the opacity slot and you will have alot of options.

Tick off PREMULTIPLIED ALPHA. In the MONO CHANNEL OUTPUT choose ALPHA

VOILA, done

This works almost everytime if the texture has an alpha baked inside. Some games have a separate alpha texture file but same procedure there.

edit:

Ok tried to import the dds file in photoshop and it gave me error, wrong filetype. I am guessing that the dds is corrupt in some way. At least I know that max is very sensitive when it comes to dds so make sure you convert it properly and try again.
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-15T19:46:40+00:00
- Post Title: Question abouth Alpha view in 3DS Max

> Reply from pixellegolas
>
> Ok, first copy the diffuse to opacity slot. Don't choose instance but copy

Next, go into the opacity slot and you will have alot of options.

Tick off PREMULTIPLIED ALPHA. In the MONO CHANNEL OUTPUT choose ALPHA

VOILA, done

This works almost everytime if the texture has an alpha baked inside. Some games have a separate alpha texture file but same procedure there.

edit:

Ok tried to import the dds file in photoshop and it gave me error, wrong filetype. I am guessing that the dds is corrupt in some way. At least I know that max is very sensitive when it comes to dds so make sure you convert it properly and try again.first of all thanks a lot, I try before with it and get again again and again same error.
