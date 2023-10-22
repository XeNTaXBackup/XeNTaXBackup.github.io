## Post #1
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-10T16:36:06+00:00
- Post Title: Immortal Fenyx Rising

Since these are just a bunch of raw files. Im hoping I can find a way to process these. 
[](https://ibb.co/2KhngFq)

SAMPLE
[https://drive.google.com/file/d/1gOxYVr ... sp=sharing](https://drive.google.com/file/d/1gOxYVraillX2_UDge8-GWuD8T_nyit-4/view?usp=sharing)
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2021-12-18T14:47:15+00:00
- Post Title: Immortal Fenyx Rising

I'm sure it is doable but how conveniently is another thing given custom header, unfortunately the google drive file is trash binned to check.
## Post #3
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-18T19:31:19+00:00
- Post Title: Immortal Fenyx Rising

Sorry about that moving files around. Here are some samples hard to tell what is what so i uploaded the original files. Maybe the information i cut could  be used to parse data better.  I think i found a few sizes here 2048, 1024, 512, 256

[https://drive.google.com/file/d/1cOsUBr ... sp=sharing](https://drive.google.com/file/d/1cOsUBrjm1kNZdTz-dSCmxlDFMT-4P75x/view?usp=sharing)
## Post #4
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-19T08:09:49+00:00
- Post Title: Immortal Fenyx Rising

Using this script made by Edness helps in seeing filenames to .dats
[forge_cut.zip](https://xentaxbackup.github.io/file/21420_forge_cut.zip)
## Post #5
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2021-12-19T13:19:44+00:00
- Post Title: Immortal Fenyx Rising

Unfortunately from my 'quick look' it looks far more tricky than expected. 
The texture data is swizzled seemingly as else it gives total mess what I tried and that naming script is a good start but it works incorrectly on the bigger files as gets a wrong string instead of precise texture string given presence of multiple string headers along some random data prior to texture data.

Someone (other than me with lots of time) would have to determine the fields from header that also define the format per texture and other settings like lenght prior to data besides figure out the exact swizzle used else can't really write a handy script for these.
