## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-06-17T18:04:56+00:00
- Post Title: swizzled texture dds

Hello everyone! 
Could someone experienced with 2d image formats take a look at this texture sample? I'm kinda lost, tried some things but couldn't get it to look correct. Any help will be much appreciated. Thanks in advance!
Here's sample texture:
[https://www.mediafire.com/file/3mi8ib8b ... atlas_0.7z](https://www.mediafire.com/file/3mi8ib8btmfjocy/atlas_0.7z)
## Post #2
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2019-06-18T15:48:55+00:00
- Post Title: swizzled texture dds

Looks like there are blocks of RGB splitted data (32x32 pixel per block). Some blocks looks omitted.

Is this image a converted image or original file?
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-06-18T16:41:26+00:00
- Post Title: swizzled texture dds

Originally extracted, it's texture "atlas" used for character customization all other textures are okay (just ordinary .dds), so I'm almost sure extraction process was correct, game engine somehow making this texture correct lol On this textures should be a bunch of other smaller textures for different face details like scars, wrinkles, eyebrows and so on.
## Post #4
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2019-06-18T17:06:50+00:00
- Post Title: swizzled texture dds

OK, so there must be additional information for atlas.

I'm think that it must be palette (or what color tile represents: R/G/B/A) and ID of tiles.
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-06-18T18:19:05+00:00
- Post Title: swizzled texture dds

Yeah, looks like that! It's very sad, there's some index .dds files in same folder after extraction. Here's one of them, but seriously I have no idea how it might help lol
[index_0.7z](https://xentaxbackup.github.io/file/16368_index_0.7z)
## Post #6
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2019-06-18T20:23:04+00:00
- Post Title: swizzled texture dds

Hm, interesting - looks like there are index information, stored as 32x32 chunks by 3 in group. And if we look at index (0-255) it might be index in atlas's line (256 * 32 = 8192, equal to width of atlas; 32 * 32 = 1024, equal to height of atlas).

I'll check it tomorrow.

UPD: It works! First chunk from three is X index of atlas, second is Y index. This is the only first image (first two chunks).
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-06-18T21:39:32+00:00
- Post Title: swizzled texture dds

Ты большой молодец, я бы точно не додумался бы сам! Я с 2д форматами чаще всего мучаюсь, особенно если что-то сильно замороченное.
Well done! Thanks for your time and efforts
## Post #8
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2019-06-19T17:26:12+00:00
- Post Title: swizzled texture dds

OK, there some information:

there are 2 types of data: atlases and indices.
Atlas store information in tiles 32x32 with 16 levels of grey.
Indices store information in chuncks 32x32 as index (0-255).

Three chunks of indices describe 1 color plane (channel) as: X index in atlas, Y index in atlas, atlas index. Four channels forms RGBA image.
Resulted image is 1024x1024, RGBA.
[decoder.zip](https://xentaxbackup.github.io/file/16376_decoder.zip)
