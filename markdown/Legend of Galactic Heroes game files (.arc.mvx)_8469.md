## Post #1
- Username: Axem
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 04, 2012 11:32 pm
- Post datetime: 2012-03-04T16:25:36+00:00
- Post Title: Legend of Galactic Heroes game files (*.arc/*.mvx)

Hey guys, I was wondering if I could get some help trying to decode these files. I've nearly torn my hair out trying to make heads or tails of these.

All I've been able to find out is that there's some kind of file manifest near the beginning. There's also some kind of compression since trying to pull out a dds file just results in an invalid file.

Sample files:
[http://www.sendspace.com/file/sufikq](http://www.sendspace.com/file/sufikq) (fortressmodel_mdx.arc + fortressmodel_tex.arc)

Thanks in advance!
## Post #2
- Username: Axem
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 04, 2012 11:32 pm
- Post datetime: 2012-03-10T23:24:10+00:00
- Post Title: Legend of Galactic Heroes game files (*.arc/*.mvx)

Hate to bump this without looking like a needy newbie, so I did some reading around the forum to see if I could gain any more insight.

It looks like there's 4 parts to one of the arc files. The header (which always seems to be 0x80 long), file information (containing file offsets, sizes and other info), file names, and then the actual files.

I looked at 4 different files and tried to find commonalities between the 4's headers. The only thing I was able to for sure recognize was the file counts (at 0x0D - 0E). Others I think I see what they are, but they don't always match up. Sometimes just the last short matches or things are out by 0x80.

I also looked at the file info, the only thing I could see was an indication where a file name will begin and how long it is. I thought I found something that points to the file offset, but it seems to depend on if the arc is carrying textures or models. Same with the file size...

I was able to extract a fully intact TGA from atmospheremodel_tex.arc, but the dds files from say, distantview_tex.arc, seem to resemble DDS files, but won't load in any viewer. Not sure if they're compressed or they need to get read in a special way.

(I'm a complete noob at this file reading stuff, so take my observations with a grain of salt)

I've uploaded the files I looked at and the notes I made while looking at the files. 
[http://www.sendspace.com/file/uq48oh](http://www.sendspace.com/file/uq48oh)
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-11T04:11:49+00:00
- Post Title: Legend of Galactic Heroes game files (*.arc/*.mvx)

I have already seen these files recently and spent some time on them.
if I remember correctly, the problem is the compression algorithm which is simple but I don't remember to have found what's it exactly.
I don't remember the thread I followed here on xentax regarding these files
