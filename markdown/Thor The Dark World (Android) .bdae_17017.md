## Post #1
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-09-14T04:26:45+00:00
- Post Title: Thor: The Dark World (Android) .bdae

These bdae files have different structure and other bdae tools doesn't work. 
Samples: [https://mega.nz/#!P1gRSTgR!9qNWBaNFanEE ... 6IGa8xdGIM](https://mega.nz/#!P1gRSTgR!9qNWBaNFanEEdd8aLxIJok3QMKgrk2gYH6IGa8xdGIM) 
Thanks in advance! 
P.S don't forget to rename .bdae to .zip or .rar to get little_endian_not_quantiazied.bdae file.This file contains all information what you might need
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-14T10:14:11+00:00
- Post Title: Thor: The Dark World (Android) .bdae

when using hex2obj you don't need to unzip the bdae files:



Thor.jpg (175.06 KiB) Viewed 255 times
## Post #3
- Username: JulioCabral
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 28, 2015 7:14 am
- Post datetime: 2018-09-30T15:35:02+00:00
- Post Title: Thor: The Dark World (Android) .bdae

For everything that's worth, I found a program that for what it looks like could open the .bdae from this game. It's called Ultimate Unwrap 3D. The demo versions can't save anything or load new plugins but the web page have a free .bdae plugin there...then again I couldn't test it since I don't have credit to buy it.
EDIT: I'm determinated to get the models via hex2obj. Is not magic, is logic.
I've followed the tutorial and I'm trying to make use of reason here; so, using the values provided for the Thor example I'm trying to replicate a logic metod.
Howerever, in the tutorial said that the start of the faces can be located searching for the value 00010002, wich fits with the example (2230E) but I'm having a hard time locating the end of the faces following the tutorial since there's written that the end should be before the value "09000000". So, is this a constant formula or I'm missing more knowledge?.
Please be patient with me.
## Post #4
- Username: JulioCabral
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 28, 2015 7:14 am
- Post datetime: 2018-10-07T21:32:40+00:00
- Post Title: Thor: The Dark World (Android) .bdae

YES!! I did it!Please someone help me with Odin
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-07T22:12:12+00:00
- Post Title: Thor: The Dark World (Android) .bdae

> Reply from JulioCabral
>
> Howerever, in the tutorial said that the start of the faces can be located searching for the value 00010002, wich fits with the example (2230E) but I'm having a hard time locating the end of the faces following the tutorial since there's written that the end should be before the value "09000000". So, is this a constant formula or I'm missing more knowledge?no, that's the length dword of a string, strings vary from file to file, so it's not constant. It's also an example only, where the face indices block was followed by a string; you can't seriously think that this has to be true for any other 3D format like this one here?

You need to understand data formats; the values in rectangles are assumed to be floats. The thick line marks the end of the face indices block; you can see the following values have too many zeroes than to give faces that make sense.



EndOfFIsBlock.png (39.42 KiB) Viewed 154 times



> Reply from JulioCabral
>
> YES!! I did it!Please someone help me with OdinSample file?
## Post #6
- Username: JulioCabral
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 28, 2015 7:14 am
- Post datetime: 2018-10-07T22:32:59+00:00
- Post Title: Thor: The Dark World (Android) .bdae

> you can't seriously think that this has to be true for any other 3D format like this one here?
That was noob talk there lol
Right now I've foun a pattern in the weapons models for the face start and end, it begins with 00 00 01 00 02 00 and end in 50 4B, after that the vertices start is easy to find.

> Sample file?
Here you got my friend: [http://www.mediafire.com/file/pug3ce2bd ... .bdae/file](http://www.mediafire.com/file/pug3ce2bdh6vtpu/odin.bdae/file)
So far I found the face star at 11BC6 but I'm having trouble finding the end.
Thanks in advance.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-07T22:46:51+00:00
- Post Title: Thor: The Dark World (Android) .bdae

see picture in my previous post.

H2O file (copy the 6 lines into a text file and name  it Odin.H2O, load model and H2O file, then File/SaveAs mesh to create the obj file):

0x11BC6 4542
Vb1
56 24
0x2656 1122
020000
0x0 255
## Post #8
- Username: JulioCabral
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 28, 2015 7:14 am
- Post datetime: 2018-10-07T23:25:24+00:00
- Post Title: Thor: The Dark World (Android) .bdae

Thanks!
For your help and the guidance. I'll study each step.
EDIT: I've manage to get all the support characters and almost every Thor costume. I'm so happy because I started the search for this models 5 years ago.
