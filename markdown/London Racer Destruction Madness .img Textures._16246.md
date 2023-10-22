## Post #1
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-05-06T21:58:02+00:00
- Post Title: London Racer: Destruction Madness *.img Textures.

Hi all,i want to extract textures from this files.

Files: 

[https://mega.nz/#!NktmXKwL!tUlnUjCv7Ya9 ... 9JlDa_P94Y](https://mega.nz/#!NktmXKwL!tUlnUjCv7Ya9omAj7r-WAz3-NFkPt0zjI9JlDa_P94Y)

I hope someone can help.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-06T23:57:03+00:00
- Post Title: London Racer: Destruction Madness *.img Textures.

what platform did this sample come from? google say it was released on PS2 and Windows.

i could not get a clear image from the data but here is what i could see   
little endian
0x10 - 4bytes - data size
0x14 - 2bytes - width
0x16 - 2bytes - height
0x318 - image data starts
## Post #3
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-05-07T00:27:18+00:00
- Post Title: London Racer: Destruction Madness *.img Textures.

> Reply from AceWell
>
> what platform did this sample come from? google say it was released on PS2 and Windows.

i could not get a clear image from the data but here is what i could see   
little endian
0x10 - 4bytes - data size
0x14 - 2bytes - width
0x16 - 2bytes - height
0x318 - image data starts

This from pc,but this game also on ps2.
## Post #4
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-02-17T11:42:00+00:00
- Post Title: London Racer: Destruction Madness *.img Textures.

I want to bump this topic,i can extract textures with ninja ripper but its a bit complicated.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-17T12:10:11+00:00
- Post Title: London Racer: Destruction Madness *.img Textures.

looks like paletted image data with three distinct 256 byte palettes after the 24 byte header.   
maybe episoder will drop by and whip up something, this looks right up his alley.
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-17T14:29:17+00:00
- Post Title: London Racer: Destruction Madness *.img Textures.

ofc you shove that over here, @acewell. why? cause it's ps2 style? you certain i can crack those? 

yeh. i'm on it. as of right now a bunch of textures may remain on the floor. some sizes don't make sense. but i got lights and tyres. sick formats. some linear palettes (all reds, all greens, all blues). red channel monochromes. green + blue monochromes (technically this could possibly be computed as a 'specular angle bumpmap' - on the ps2). i may check 4-bit merged iterations too. do whip...
## Post #7
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-17T17:24:26+00:00
- Post Title: London Racer: Destruction Madness *.img Textures.

no thanks pls. i gotta throw it. nothing else to find. i can't figure out the compression either. only outputs the raw images. beware that all of this seem to really be just red channel greyscales. note that: you need a image viewer that can output palette tgas. every viewer out there should be able todo that tho. 
[img2tga.rar](https://xentaxbackup.github.io/file/13924_img2tga.rar)
