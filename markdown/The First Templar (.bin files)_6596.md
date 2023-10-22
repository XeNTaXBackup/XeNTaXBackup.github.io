## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-11T11:30:39+00:00
- Post Title: The First Templar (*.bin files)

In searching of meshes i found an interesting mention about granny format in binassets.hpk, but all files are in archives with bin extension and looks like they are not encrypted. [Here](http://www.mediafire.com/?ipralx0bsqmmjp3) all files from binassets.hpk except animations.bin.

can someone handle those bins?
## Post #2
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-11T15:16:05+00:00
- Post Title: The First Templar (*.bin files)

It seems they contain files "GR2".
## Post #3
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-12T00:23:35+00:00
- Post Title: The First Templar (*.bin files)

Based on just looking at the files, none of this has yet been fully tested.

"report.csv"

Most important part of this file is the last bit of each line.  The number at the end of each line is the byte size of the vertex data block contained in "meshes.vb.bin"
Secondly important is the section prior to that number.  This includes the name of the model.

"meshes.gr2.bin"

Contains blocks of granny information for each model.  Each block appears to follow this structure:

```
Count
0000 -- Int32     -- Block size
0548 -- Float (6) -- Bounding Box
0572 -- Int32     -- Number of Verts
0576 -- Int32     -- Number of Indices

```

"meshes.ib.bin"

Contains blocks of face information.  Starting from the beginning of each block read a number of UInt16 equal to the Number of Indices from the gr2 file.  What is hard for me to explain is the variable amount of 00 byte padding at the end of each block.

"meshes.vb.bin"

Contains blocks of vertex information.  Starting from the beginning of each block read a number 24 byte blocks equal to the Number of Verts from the gr2 file.  Inside that 24 byte block is the vert position and tvert position for each vertex.  Once again there is a variable amount of 00 byte padding at the end of each block.  However, because of the "report.csv" file, we know the exact size of each block.

At this time, I can only assume that vert and tvert positions are being stored as Int16s somewhere in that 24 byte block, but I don't have a lot of time right now to do further testing.

HTH,
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-13T10:13:29+00:00
- Post Title: The First Templar (*.bin files)

> Reply from MichaelDarkAngel
>
> Based on just looking at the files, none of this has yet been fully tested...
Thanks for your researches.
I check out  this files too, very interesting storing of date  so, any chance you have a time to help me with converting those files?
## Post #5
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-15T00:54:07+00:00
- Post Title: The First Templar (*.bin files)

I generally don't do anything for games I don't own...  So I bought it this morning 

I'll be looking at it a little more intently over the next few days.  Keep a watchful eye for something in the near future.
## Post #6
- Username: mesnik88
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-21T22:17:32+00:00
- Post Title: The First Templar (*.bin files)

Think I've finally gotten the file structure under control.  And of course the easiest thing to pick out are the image files

[](http://www.tbotr.net/albums/tbotr_g3/ftX_0001.png)

Click for larger image

Continuing on...
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-22T05:41:56+00:00
- Post Title: The First Templar (*.bin files)

> Reply from MichaelDarkAngel
>
> Think I've finally gotten the file structure under control.  And of course the easiest thing to pick out are the image files
Continuing on...
Oh wow  even with file names 
this game have very quality texture of characters, will be nice to see the models too

thanks for your work
## Post #8
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-24T05:04:31+00:00
- Post Title: The First Templar (*.bin files)

Now that I've gotten into this a little deeper, I've discovered that the model files are a little more complicated than my first glance led me to believe.

The report.csv file references both static meshes and animations.  The last column of the csv file is still a block size, however, when referencing a static mesh its a block size in the meshes.vb.bin file, when referencing an animation its a block size in the animations.bin file.

That apparently makes the first column of the csv file more important now.  If the text in that column starts with a drive letter as opposed to just a folder name that means we are looking at an animation.

I'm getting there, hopefully only a day or two more.
## Post #9
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-30T01:22:34+00:00
- Post Title: The First Templar (*.bin files)

First model files exported from game files and imported into 3DSMax.

[](http://www.tbotr.net/albums/tbotr_g3/ftX_0005.png)
Click image for larger view

More images will be in my gallery soon.  Still working out some bugs in the export process.  Still looking for material information.
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-30T14:09:28+00:00
- Post Title: The First Templar (*.bin files)

> Reply from MichaelDarkAngel
>
> First model files exported from game files and imported into 3DSMax.


Click image for larger view

More images will be in my gallery soon.  Still working out some bugs in the export process.  Still looking for material information.
Nice work MichaelDarkAngel,
i see you already implemented possibility of model converting and this is great i think. Tell me please, is there a way to convert character models with their bones and weight data?
## Post #11
- Username: Privateer
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-05-30T14:30:16+00:00
- Post Title: The First Templar (*.bin files)

> Reply from Tosyk
>
> Nice work MichaelDarkAngel,
i see you already implemented possibility of model converting and this is great i think. Tell me please, is there a way to convert character models with their bones and weight data?

This should be a possibility, all the important information is stored in the gr2 file.  I just haven't made it that far yet.
## Post #12
- Username: bruno021
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 02, 2011 6:50 am
- Post datetime: 2011-12-08T13:15:51+00:00
- Post Title: The First Templar (*.bin files)

Any news?With explorer for First templar
## Post #13
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-12-25T00:19:08+00:00
- Post Title: The First Templar (*.bin files)

@MichaelDarkAngel,
This thread is what brought me to Xentax.
I did extract a few files and took a quick look at them but other projects never gave me the time to follow up.
I'd be interested in any knowledge you may have as I go back to looking at the files again here soon.
Thanks!
## Post #14
- Username: bruno021
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 02, 2011 6:50 am
- Post datetime: 2012-05-06T18:22:46+00:00
- Post Title: The First Templar (*.bin files)

Still waiting extractor from MichaelDarkAngel.
## Post #15
- Username: SkyeFish
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 10, 2011 6:49 am
- Post datetime: 2014-04-26T08:25:29+00:00
- Post Title: The First Templar (*.bin files)

This looks like a dead thread but I wanted to necro it because I am interested in the progress that was made here and if it might be applicable to the Tropico games. I've been looking at Tropico 4 and have been able to extract textures but not any mesh data.

If any tools for working with such exist I would be interested in them.
## Post #16
- Username: bruno88
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 06, 2023 5:04 pm
- Post datetime: 2023-02-18T10:55:13+00:00
- Post Title: Re: The First Templar (*.bin files)

Hey everyone, i will bump this dead topic. Who already make expoler/converter for this game?
