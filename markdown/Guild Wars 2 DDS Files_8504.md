## Post #1
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-09T03:32:55+00:00
- Post Title: Guild Wars 2 DDS Files

So I have found ways to get all GW2 files directly from their CDN in uncompressed format.

I was looking through the files, and noticed the DDS files seem to have missing headers and other stuff going on. I am kinda going into territory that I am not familiar with so I would like some help figuring out how to view these.

The only information I got to distinguish these files are the first bit of the header that says

ATEXDXT1
ATEXDXT2
ATEX3DCX 
etc.

Here is an Archive with DXT1, DXT5 and a few Unknown DXTs. My script automatically adds extensions to them based on the header. normally they are just numbers. 
[http://www.mediafire.com/?j4kmw3021bxs7k1](http://www.mediafire.com/?j4kmw3021bxs7k1)

There might be similarities to the Guild Wars 1 files, but I am not sure of that.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-09T12:22:57+00:00
- Post Title: Guild Wars 2 DDS Files

can you post how to download the entire file directory so i can look at the files.
## Post #3
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-09T20:57:50+00:00
- Post Title: Guild Wars 2 DDS Files

[viewtopic.php?f=10&t=8499](http://forum.xentax.com/viewtopic.php?f=10&t=8499)

The problem is, everything is in a DAT file. I have spent time messing with the patcher and figured out how to download directly from ArenaNet. The instructions are near the bottom. I wrote myself a script that downloads the file, reads the first 250 characters. And based on a few if statements, adds extensions and puts them in folders to the best of my knowledge of what they are.

I can give you the script, but I would prefer to give it to you over PM or privately. I don't want to just post the script here for anyone to download, since I don't want people to just hammer the server. The script downloads Uncompressed files, so traffic would be high and they might figure it out if like 20-30 people are hammering their servers trying to get uncompressed files.

So tell me your preferred method for me to send you the script.

Just letting you know, it is a very simple and messy script in python. So its not perfect on sorting them (Ive had a few MP3 files go into the TEXTs section with a .TXT extension) but I believe most if not all DDS are properly sorted.

I have also no way of telling what kind of file any fileis until downloaded. So you might have to download lots of unwanted files. I have 23 gigs of files atm. My script died, so it stopped at 23 gigs, and the texture folder is 15 gigs.

So, anything I can help or provide you with to get you the files you want? A bigger sample of DDS files? the Game EXE/Patcher is in the thread I linked above.

But this was on the Xentax Wiki for GW1's DAT in the TALK section:

> So here is the image I extracted from one of the ATEX sections in my archive. It was the second ATEX section, which I used because the first had 'DXTA', which isn't an actual compression format. This one was 'DXT5', though it isn't exactly that anyway. For reference, the data is here: http://rep.undev.org/gw/07537E00.dat
>
> The image data starts at 0x1c. The only obvious element of the header is the width and height, which are the first two shorts after 'ATEXDXT5'. The image data works as normal DXT5 [3] with a few differences. First, only the alpha part is there. Normally, it is organized into 4x4 pixel blocks (texels) with eight bytes of alpha information and eight bytes of color information. Here, the color information is missing, so texels are only eight bytes. To view the image, I added a DDS header and put in eight byte blocks of zeros every eight bytes throughout the image data.
>
> With that done, the image still wasn't right, but it was obvious that it was missing several texels, which shift all the following texels left. The missing texels were the ones in the four corners of the image (all zero data, since they are completely black). I am pretty sure that for extra compression, they leave out these texels and give their offsets elsewhere (only about two bytes to store the offset, rather than keeping the eight bytes of empty image data). If I counted correctly, the offsets (in texels, not bytes) of zero texels for that image are 0, 7, 56, 63 or 0, 6, 54, 60, depending on whether you add one for each previous texel. I haven't examined the data very carefully for these values yet.
>
> I don't know how to get the right lower mipmap levels yet. What is interesting is that assuming normal DXT5 data (color included and no missing texels), the sizes work out perfectly for a 32x32 image with 6 mipmap levels if you start the image data at 0x14. Maybe GW needs to trick DirectX into thinking it's dealing with real DXT5 data at some point.
[http://wiki.xentax.com/index.php/Talk:Guild_Wars_DAT](http://wiki.xentax.com/index.php/Talk:Guild_Wars_DAT)

I hope this helps.
## Post #4
- Username: SUPERBOB
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-09T21:06:50+00:00
- Post Title: Guild Wars 2 DDS Files

sure pm me the script then mabee i can figure out how to uncompress the files for everyone.
## Post #5
- Username: SUPERBOB
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 24, 2014 1:41 am
- Post datetime: 2014-05-24T01:47:46+00:00
- Post Title: Guild Wars 2 DDS Files

> Reply from chrrox
>
> sure pm me the script then mabee i can figure out how to uncompress the files for everyone.

If this worked for GW1 also it would be awesome... I have a folder with over a Gb of .ATEX files I would love to get into...
