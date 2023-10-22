## Post #1
- Username: jayande
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 03, 2015 12:48 pm
- Post datetime: 2015-07-05T16:20:22+00:00
- Post Title: Madden 12 PSP .msh file format - any help

Hello.  I'm trying to view the textures within the .msh graphic format correctly, found in the PSP version of Madden.  I've included compressed and decompressed versions of the .msh file and the  original.viv which serves as the container for them. I tried using the Console Texture Explorer for PSP, but all I got was the image below. Ideally I would like to be able to import and export textures.  If there is a tool that I'm missing to be able to accomplish this, please let me know.  I've attached the texture files below.  Any help would really be appreciated.


[Madden12PSPtexturefiles.zip](https://xentaxbackup.github.io/file/9386_Madden12PSPtexturefiles.zip)
## Post #2
- Username: jayande
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 03, 2015 12:48 pm
- Post datetime: 2015-07-05T16:22:34+00:00
- Post Title: Madden 12 PSP .msh file format - any help

Here is the viv file that contains the .msh texture files mentioned above.  Attached below.
[Madden12PSP_VIVFile.zip](https://xentaxbackup.github.io/file/9387_Madden12PSP_VIVFile.zip)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-05T17:55:57+00:00
- Post Title: Madden 12 PSP .msh file format - any help

did you notice "torso" starts amidst of the msh file?



SEA2_decomp_msh.JPG (51.81 KiB) Viewed 270 times
## Post #4
- Username: jayande
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 03, 2015 12:48 pm
- Post datetime: 2015-07-05T18:56:28+00:00
- Post Title: Madden 12 PSP .msh file format - any help

[quote=hakotay2"]did you notice "torso" starts amidst of the msh file?
SEA2_decomp_msh.JPG[/quote]

No, I didn't notice, but I guess that would make sense.  This is all fairly new to me.  Is there any way to get the image to display correctly?  Do you think editing the texture file (editing then adding it back to the .msh  file) is a possibility?  You added a jpg extension, How does that effect the file?  Thank you for your help thus far.  I really appreciate it.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-05T19:59:51+00:00
- Post Title: Madden 12 PSP .msh file format - any help

> Reply from jayande
>
> Is there any way to get the image to display correctly?Dunno - I'm not a console user so I don't care too much for those formats. I just wanted to give you a hint.

> Do you think editing the texture file (editing then adding it back to the .msh  file) is a possibility?That's what the Console Texture Explorer was made for I guess.
"Export" (as TM2), import changed tim texture, then "Save"

> You added a jpg extension, How does that effect the file?That's just a screenshot of the explorer, nothing more. You should check out some tim viewers for loading the exported TM2 file.
## Post #6
- Username: jayande
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 03, 2015 12:48 pm
- Post datetime: 2015-07-06T17:41:31+00:00
- Post Title: Madden 12 PSP .msh file format - any help

Why the number 28016 as the graphic offset?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-07T06:28:18+00:00
- Post Title: Madden 12 PSP .msh file format - any help

Just the first senseful address after "torso".
Feel free to de- or increase it to improve the displayed picture.
## Post #8
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-07-08T08:17:34+00:00
- Post Title: Madden 12 PSP .msh file format - any help

Here's what I got from the first part of the file:
SHPM - some kind of identifier
32bit long - total file size
23bit long - number of textures in file
G359 - no idea what this is

Then for each texture:
4-byte texture name
32bit long - offset to that texture

Each texture starts with a 16-byte header:
32bit long - unknown
16bit short - texture width
16bit short - texture height
32bit long - unknown

multiply the texture width by texture height and you get image data size
go forward by that size, and you get the pallette, with a 16-byte header.
Afterwards you get the colors (32-bit longs, noticable columns of FFs).

So you fill out Console Texture Explorer accordingly and you get a texture
## Post #9
- Username: jayande
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 03, 2015 12:48 pm
- Post datetime: 2015-07-08T12:14:38+00:00
- Post Title: Madden 12 PSP .msh file format - any help

> Reply from barti
>
> Here's what I got from the first part of the file:
SHPM - some kind of identifier
32bit long - total file size
23bit long - number of textures in file
G359 - no idea what this is

Then for each texture:
4-byte texture name
32bit long - offset to that texture

Each texture starts with a 16-byte header:
32bit long - unknown
16bit short - texture width
16bit short - texture height
32bit long - unknown

multiply the texture width by texture height and you get image data size
go forward by that size, and you get the pallette, with a 16-byte header.
Afterwards you get the colors (32-bit longs, noticable columns of FFs).

So you fill out Console Texture Explorer accordingly and you get a texture

Wow!  Thanks so much to both you and shakotay2!    But please tell me, how exactly did you arrive at 224 for the Graphics offset and 4336 for the Palette offset?  A bit more detail would really be appreciated.  I want to learn as much as possible.  Do these 2 settings apply for the other texture?  Thanks again, for your time and assistance.  Your awesome!
## Post #10
- Username: jayande
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 03, 2015 12:48 pm
- Post datetime: 2015-07-09T11:50:40+00:00
- Post Title: Madden 12 PSP .msh file format - any help

I've been trying to figure out how to come up with the Graphic and Palette offset for different textures for the last day or so with no luck.  Others textures that I have found include:

Jersey: 128x128
Sleeve: 128x32
Thigh: 64x64

Where in the hex editor do I look to find the offsets?  Is there a formula?  If so, how is it calculated?  Or is it trial and error after multiplying the texture width by texture height and you get image data size?  I just need a bit more help.  Again, I would really appreciate it.
## Post #11
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-07-09T15:38:38+00:00
- Post Title: Madden 12 PSP .msh file format - any help

As I mentioned before, the first part of .msh file is kind of a header. So you have the texture names there and also the offsets:


As you can see, the offset for "mask" is 42432. So we go to offset 42432.

Here we can ignore the first 4 bytes, and next there is the image width (as uint16, 2 bytes) and image height (same parameters). So you type that into CTE.
Then you move to offset 42448 (where the image header starts + 16 bytes) and put that as the bitmap offset.


Now whip out your calculator and multiply the image width by the image height. Next go forward by that offset in the file. Make sure you go by that offset from the current position, not the beginning of file:


Now you should be at offset 42704. The palette header is not useful in this case so add 16 to 42704 = 42720 and put that as the Palette offset. Also remember to set Type to Texture + PaletteOffset and BPP to 8 in CTE.



Well, this wasn't the best example for this method but you get the idea 
I hope this post cleared up the process for you.
## Post #12
- Username: jayande
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 03, 2015 12:48 pm
- Post datetime: 2015-07-09T16:03:56+00:00
- Post Title: Madden 12 PSP .msh file format - any help

Thanks! That clears up a few things   What Hex editor are you using?  I'm using HxD and I don't have the option for a data offset  info window like your examples.
## Post #13
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-07-09T16:40:06+00:00
- Post Title: Madden 12 PSP .msh file format - any help

I'm using Hex Workshop. Unfortunately it's not free, but there is a free trial.
## Post #14
- Username: jayande
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jul 03, 2015 12:48 pm
- Post datetime: 2015-07-12T02:38:06+00:00
- Post Title: Madden 12 PSP .msh file format - any help

I'm still not getting good results.  Seems like I'm close, but the images aren't displaying correctly.  Using your method, could you try the helmet, torso and thigh and post your results please?  Even working backwards using the correct hip offset values doesn't give the same result.
## Post #15
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-07-12T07:49:11+00:00
- Post Title: Madden 12 PSP .msh file format - any help

Helmet:


Torso:


Thigh:
## Post #16
- Username: metalex
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 18, 2016 2:48 pm
- Post datetime: 2017-04-06T05:10:47+00:00
- Post Title: Re: Madden 12 PSP .msh file format - any help

hi help me too with this file

is a scoreboard of fifa 07 of ps2
[to23_s.zip](https://xentaxbackup.github.io/file/12748_to23_s.zip)
## Post #17
- Username: reeshmd23
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 22, 2017 3:43 am
- Post datetime: 2017-12-21T20:55:42+00:00
- Post Title: Re: Madden 12 PSP .msh file format - any help

Any easy way to edit these msh files ever been found?  Would love to texture mod psp ea sports games
