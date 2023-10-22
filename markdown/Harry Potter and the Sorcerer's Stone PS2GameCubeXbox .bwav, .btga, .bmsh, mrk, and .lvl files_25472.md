## Post #1
- Username: avifors
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 29, 2017 1:08 am
- Post datetime: 2022-05-31T22:47:31+00:00
- Post Title: Harry Potter and the Sorcerer's Stone PS2/GameCube/Xbox .bwav, .btga, .bmsh, mrk, and .lvl files

Hi. I am looking to view/convert the .bwav, btga, .bmsh, .mrk, and lvl files for Harry Potter and the Sorcerer's Stone PS2/GameCube/Xbox but I am not having any luck so far. Any ideas are appreciated. Here are some samples. Thanks.

[https://www.mediafire.com/file/38aavwg5 ... s.rar/file](https://www.mediafire.com/file/38aavwg56yds6e5/Samples.rar/file)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-31T23:24:07+00:00
- Post Title: Harry Potter and the Sorcerer's Stone PS2/GameCube/Xbox .bwav, .btga, .bmsh, mrk, and .lvl files

I've checked your samples.

BTGA is some kind of custom image container. File format looks like this:

```
{
   160 bytes - header
   x bytes - image data
   1024 bytes - palette data
}
```

You can try to get some results with TextureFinder.

BWAV is some compressed audio.

LVL is a text file. You can open it in Notepad++.

BMSH looks like some kind of model data?

MRK file is empty.
## Post #3
- Username: avifors
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 29, 2017 1:08 am
- Post datetime: 2022-06-01T02:36:27+00:00
- Post Title: Harry Potter and the Sorcerer's Stone PS2/GameCube/Xbox .bwav, .btga, .bmsh, mrk, and .lvl files

Hey thanks. For the bwav do you have any suggestions on how I can decompress it as I can't find anything that tells me how to so far? I did just try using TextureFinders but the colors don't display properly and I did change the quad and pixel formats but no luck.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-01T19:32:24+00:00
- Post Title: Harry Potter and the Sorcerer's Stone PS2/GameCube/Xbox .bwav, .btga, .bmsh, mrk, and .lvl files

> Hey thanks. For the bwav do you have any suggestions on how I can decompress it
Hi, BWAV files are compressed audio files.
There are multiple audio entries for each file, first one is always PlayStation 4-bit ADPCM, other ones are currently unknown.

To extract them you can create ".bwav.txth" file 
and put these lines inside:

```
start_offset = 0x44
channels = 1
sample_rate = 22050
num_samples = @0x30
```


Then you should put all your BWAV samples to the same directory.
Final result should look like this --> [https://imgur.com/a/HbIvOBH](https://imgur.com/a/HbIvOBH)

Then install foobar2000 with vgmstream plugin.
Now you can just drag and drop bwav files to foobar's window and play them.
## Post #5
- Username: avifors
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 29, 2017 1:08 am
- Post datetime: 2022-06-02T22:35:07+00:00
- Post Title: Harry Potter and the Sorcerer's Stone PS2/GameCube/Xbox .bwav, .btga, .bmsh, mrk, and .lvl files

Thank you so much! How did you manage to figure that out? When I researched I came up with nothing.
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-03T21:52:27+00:00
- Post Title: Harry Potter and the Sorcerer's Stone PS2/GameCube/Xbox .bwav, .btga, .bmsh, mrk, and .lvl files

> Reply from avifors ↑Fri Jun 03, 2022 6:35 am at Fri Jun 03, 2022 6:35 am
>
> 
Thank you so much! How did you manage to figure that out? When I researched I came up with nothing.

It's just a lot of knowledge and experience from researching other games on this forum   

If you want to learn this as well, you can read some tutorials from this topic [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
