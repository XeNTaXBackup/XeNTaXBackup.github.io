## Post #1
- Username: DJMD713
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 13, 2018 9:03 pm
- Post datetime: 2018-08-14T21:09:05+00:00
- Post Title: Astonia - Compressed Archives (.pak/zlib/libpng)

I have been working on figuring out Astonia's .pak files but have not had much success. The game is now open source (see Github below). So far I have determined the following:

- It takes folders with .png files and converts them to .pak files. (Examples - https://drive.google.com/open?id=1Ej6O0 ... 7zRcTq5jL1)
- The code for the .pak conversion process is here (Function - gfx_make_pak - https://github.com/AstoniaDev/Astonia-3 ... moac/gfx.c)
- The app is written in C++ and uses zlib and libpng.
- I have tried accessing the files using multiple applications with no luck (MultiEx Commander, Game Extractor, etc) 

I am trying to learn more about C++ to figure out a way to reverse the process but it is currently beyond what I am capable of. Does anyone have suggested guides or tutorials I can learn from? If anyone else is up to the task of deconstructing the files that would be much appreciated as well  

Edit: There is another thread on the forum ([viewtopic.php?f=15&t=2134](http://forum.xentax.com/viewtopic.php?f=15&t=2134)) but the MexScript did not yield any useful results.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-08-14T22:56:17+00:00
- Post Title: Astonia - Compressed Archives (.pak/zlib/libpng)

use offzip 
offzip.exe -a c:\file.pak c:\extractDir 0x0
## Post #3
- Username: DJMD713
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 13, 2018 9:03 pm
- Post datetime: 2018-08-15T01:49:40+00:00
- Post Title: Astonia - Compressed Archives (.pak/zlib/libpng)

> Reply from chrrox
>
> use offzip 
offzip.exe -a c:\file.pak c:\extractDir 0x0

Thanks for the suggestion. It seems to extract the correct number of files but does not get the correct data. Here is a screenshot with the extracted files (left) vs the expected output (right). Not sure what to make of this. Is it an offset issue or is there more to it?
## Post #4
- Username: honcheon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 16, 2017 1:03 pm
- Post datetime: 2018-08-21T08:16:22+00:00
- Post Title: Astonia - Compressed Archives (.pak/zlib/libpng)

[Google Translator]
The contents are very awkward using the translator.

Looking at line 288 of 'gfx.c', there are three types of pak files.
The structure of the pak file can be seen by looking at the 'pakdat' and 'gfxdata' directly below the type.

Let's go some more.
On line 804 we have the function 'gfx_save_pak'.
If you check this function, 'savetime', 'dat_cnt', 'offset', 'totsize', 'dat_id', 'dat_type' etc. exist with the size of the variable.

```
# dat_cnt,4
# offset,4 => 4+4 + dat_cnt*(4+4+4+4)
# totsize,4 => 4+4 + gfxdata[i].compsize +8
# gfxdata[i].dat_id,4
# gfxdata[i].dat_type,4
```


Let's take an example of this file. (00000000.pak)
The first 4 bytes 'B0 62 9A 46' is 'savetime'. The next 4 bytes '63 00 00 00' are 'dat_cnt'.
This is a separate value up to this point.
From this point, it is repeated by 'dat_cnt' until offset 638h.
The format is 'offset', 'totsize', 'dat_id', and 'dat_type', each of 4 bytes.

Now move to the 'offset' section. (638h)
Looking at the data in this next section, 697h.

The total size is 5F. This is 'totsize'.
This block is also the contents of the for statement on line 841.
If you look carefully at the content, you can see that this data has the following form:

```
# gfxdata[i].realsize,4
# gfxdata[i].data, gfxdata[i].compsize
# gfxdata[i].xres,2
# gfxdata[i].yres,2
# gfxdata[i].xoff,2
# gfxdata[i].yoff,2
```


Now, with 'compsize' and 'realsize', you can output the same result as using offzip.
So far, it's very easy, But what you see now is the most important issue.

This is followed by the image palette value. On line 860.
The last 4 bytes of sample file are '00 00 00 00 '.
In other words, this means that the first three types of data were palette-free.

To extract an image from a pak file, you need to figure out the palette value. (The last 36 bytes of the 00124000.pak file have the same value.)
That is, you have to distinguish the type of the file. 
Probably related functions are estimated to be 'gfx_load_image_pak', 'load_gfx_num', 'make_gfx_num' and so on.
And the variables 'xres', 'yres', 'xoff', and 'yoff' also seem to be related.

That's all I've analyzed.
It was beyond my ability to reverse this part.
I hope these contents will help you.

# This script is for a sample file. (same offzip output)

```
get dat_cnt long

for i=0 < dat_cnt
    if i == dat_cnt
        break
    endif

    get offset long
    get totsize long
    get dat_id long
    get dat_type long
    savepos nextoff

    goto offset
    get compsize long
    get realsize long
    xmath offset "offset + 8"
    clog "" offset compsize realsize

    goto nextoff
next i

```
