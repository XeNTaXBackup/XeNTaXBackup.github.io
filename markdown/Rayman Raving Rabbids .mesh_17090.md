## Post #1
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-09-30T10:43:26+00:00
- Post Title: Rayman Raving Rabbids .mesh

Hello! With a friend of me (Droolie) we extracted a model for Rayman Raving Rabbids. We got a mesh file but we have no idea about how to open it!
The model is named S_LapinPirate_Yeux, which should be eyes for a Pirate Rabbid.
So this a .mesh (format we named ourselves), and I think it doesn't contain anything about normals etc, probably only the mesh itself, but I'm not sure. Opening the mesh already is gonna be a good thing!
Here's the link to the file: [https://ufile.io/3dqyo](https://ufile.io/3dqyo)
Thanks everyone who tries to help!
Cya!
## Post #2
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-10-02T05:00:28+00:00
- Post Title: Rayman Raving Rabbids .mesh

bump
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-02T18:37:36+00:00
- Post Title: Rayman Raving Rabbids .mesh

You might try out hex2obj (view link in my sig) to get some point clouds:



mesh.jpg (93.38 KiB) Viewed 230 times


(Don't have the time to care for face indices, sry.)
## Post #4
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-10-07T07:31:15+00:00
- Post Title: Rayman Raving Rabbids .mesh

> Reply from shakotay2
>
> You might try out hex2obj (view link in my sig) to get some point clouds:
mesh.jpg
(Don't have the time to care for face indices, sry.)
Thanks, I actually got normals working with a friends, but we couldn't get face indices yet
## Post #5
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-10-10T17:03:23+00:00
- Post Title: Rayman Raving Rabbids .mesh

bump, any help for face indices?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-10T20:44:45+00:00
- Post Title: Rayman Raving Rabbids .mesh

a simpler .mesh file is required, such as a book, a chest, a plank or a box for example
## Post #7
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-10-13T20:21:09+00:00
- Post Title: Rayman Raving Rabbids .mesh

> Reply from shakotay2
>
> a simpler .mesh file is required, such as a book, a chest, a plank or a box for example
Here is it! A pair of sunglasses! 

[http://www.filedropper.com/ff001435bindec13872517](http://www.filedropper.com/ff001435bindec13872517)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-13T20:40:59+00:00
- Post Title: Rayman Raving Rabbids .mesh

thanks! The face indices are still a riddle, though.
I wouldn't know where the "trick" should be?

The sequence 0100000003001A00 for example is contained 120 times with an offset of 20
so might be a good idea to skip it.

yeah, seems I'm on the right track, but tired now:



sunglasses.jpg (71.28 KiB) Viewed 180 times
## Post #9
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-10-20T23:21:02+00:00
- Post Title: Rayman Raving Rabbids .mesh

> Reply from shakotay2
>
> thanks! The face indices are still a riddle, though.
I wouldn't know where the "trick" should be?

The sequence 0100000003001A00 for example is contained 120 times with an offset of 20
so might be a good idea to skip it.

yeah, seems I'm on the right track, but tired now:
sunglasses.jpg
Oh! Do you think you could explain how it works?
And so faces are starting at 0x193C?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-21T08:48:43+00:00
- Post Title: Rayman Raving Rabbids .mesh

> Reply from Got4n
>
> Oh! Do you think you could explain how it works?as I wrote: skip the sequence.
(As you can see from the right part of the pic there's another rule required but I'm too busy atm to search for it.)

> And so faces are starting at 0x193C?why? I used 0xFDC for the sunglasses, iirc (but not sure, at least it's the offset I used last time).
## Post #11
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-10-21T10:39:09+00:00
- Post Title: Rayman Raving Rabbids .mesh

> Reply from shakotay2
>
> Got4n wrote:Oh! Do you think you could explain how it works?as I wrote: skip the sequence.
(As you can see from the right part of the pic there's another rule required but I'm too busy atm to search for it.)
And so faces are starting at 0x193C?why? I used 0xFDC for the sunglasses, iirc (but not sure, at least it's the offset I used last time).
Because you said "the sequence 0100000003001A00 for example is contained 120 times with an offset of 20
so might be a good idea to skip it." so I thought I could skip it and it ends at 0x193C but I'll try!
Do you think you could screen your hex2obj settings?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-21T13:27:05+00:00
- Post Title: Rayman Raving Rabbids .mesh

sunglasses.jpg (78.47 KiB) Viewed 156 times


(you'll need a script for getting the face indices)
## Post #13
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-10-21T13:49:14+00:00
- Post Title: Rayman Raving Rabbids .mesh

> Reply from shakotay2
>
> sunglasses.jpg
(you'll need a script for getting the face indices)
Oh, that's why it wasn't working for me lol, I guess it's the .txt that indicates the faces?
## Post #14
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-11-04T20:28:48+00:00
- Post Title: Rayman Raving Rabbids .mesh

nvm so I got it working, but now I really have troubles understanding why half of the faces are fucking up haha.
Also, I don't know if you noticed but 0xFCC is the size block (that we use to divide the length of the face block). Also how would I do if it's 4 bytes instead of 2?
## Post #15
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-11-26T11:17:22+00:00
- Post Title: Rayman Raving Rabbids .mesh

bump
## Post #16
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-12-21T20:01:06+00:00
- Post Title: Re: Rayman Raving Rabbids .mesh

bump
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-12-22T18:42:37+00:00
- Post Title: Re: Rayman Raving Rabbids .mesh

guess bumpers will lead to nothing 
I erased the superfluous faces:



sunGlasses.jpg (105.4 KiB) Viewed 109 times


then saved in somewhat format to compare which face indices were the wrong ones.

But blender's obj export mixes everything up, no chance to do a simple comparison.
I remember having created a "render to vertex" exporter but it's lost somewhere on my dozens of partitions...

(I had another one for gmax on my old pc but don't have the time to dig it up.)

Blender's Directx-exporter produces a bigger x file from the above sunglasses than from the spoiled one, very funny.
## Post #18
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2017-12-23T11:56:41+00:00
- Post Title: Re: Rayman Raving Rabbids .mesh

> Reply from shakotay2
>
> guess bumpers will lead to nothing 
I erased the superfluous faces:
sunGlasses.jpg
then saved in somewhat format to compare which face indices were the wrong ones.

But blender's obj export mixes everything up, no chance to do a simple comparison.
I remember having created a "render to vertex" exporter but it's lost somewhere on my dozens of partitions...

(I had another one for gmax on my old pc but don't have the time to dig it up.)

Blender's Directx-exporter produces a bigger x file from the above sunglasses than from the spoiled one, very funny.
Oh okay LOL, good luck finding it
## Post #19
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2018-03-02T12:59:40+00:00
- Post Title: Re: Rayman Raving Rabbids .mesh

Bumping slightly to tell that I really still wonder why the format is different from file to file  
Managed to load the sunglasses perfectly thanks to a friend, but it's not working for teh r3st
## Post #20
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2018-03-02T16:12:09+00:00
- Post Title: Re: Rayman Raving Rabbids .mesh

I readed some topics here on Xentax and Zenhax about this game, but still  don't know how extract meshes from archive.
I have many decompressed files from *.bin files ( .bins are from bf archive )and what next ?
Sorry if something overlook
[screen.jpg](https://xentaxbackup.github.io/file/13989_screen.jpg)
## Post #21
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-03T00:19:15+00:00
- Post Title: Re: Rayman Raving Rabbids .mesh

Can you upload the file in the op again? It says it is expired.

Edit : Anyway downloaded the file thanks to a friend.

This is what I got : 


I am not sure how correct it is though. Don't know how these guys look ingame
## Post #22
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2018-03-09T09:53:43+00:00
- Post Title: Re: Rayman Raving Rabbids .mesh

> Reply from akderebur
>
> Can you upload the file in the op again? It says it is expired.

Edit : Anyway downloaded the file thanks to a friend.

This is what I got : 


I am not sure how correct it is though. Don't know how these guys look ingame

Oops, sorry dude 
Wow, dang already got it so fast! 
How have you got that? I'm really interested! GGs! :O
## Post #23
- Username: Got4n
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 12, 2014 2:38 am
- Post datetime: 2018-03-09T10:00:46+00:00
- Post Title: Re: Rayman Raving Rabbids .mesh

> Reply from Szkaradek123
>
> I readed some topics here on Xentax and Zenhax about this game, but still  don't know how extract meshes from archive.
I have many decompressed files from *.bin files ( .bins are from bf archive )and what next ?
Sorry if something overlook

You need to decode .bin files, and then extract the models from the decoded bin files
