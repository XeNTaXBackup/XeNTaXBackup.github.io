## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-10-31T06:07:22+00:00
- Post Title: DDS Format Help - Mr Mouse your skills are needed!!!

I'm trying to inject textures into the pain tool of smackdown 2011. The texture format is dds dxt5 with no mip maps. Wehn I save the file with paint.net or dxt bmp, the image looks the same as the one created in game but the game reports it as corrupt.  

When I open both the images in a hex editor, the hex values are completely different. I think the game uses a special way to compress the dds file. Can anybody suggest a way to create the dds file exactly like the attachment?
[382024.rar](https://xentaxbackup.github.io/file/3570_382024.rar)
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-11-01T09:04:40+00:00
- Post Title: DDS Format Help - Mr Mouse your skills are needed!!!

Need the original and your edited dds file too.
## Post #3
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-11-01T10:44:40+00:00
- Post Title: DDS Format Help - Mr Mouse your skills are needed!!!

Here's the edited files. I've included the original file, the one labelled "copy" is the file generated by paint.net, the one labelled copy(2) is the file generated by dxtbmp and the last is the dds file I wish to inject (picture of a face). 

I have saved all the files as dds dxt 5 with no mip maps.
[files.rar](https://xentaxbackup.github.io/file/3574_files.rar)
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-11-01T20:24:00+00:00
- Post Title: DDS Format Help - Mr Mouse your skills are needed!!!

Well, because I can't testing it, try to use Photoshop (if you can) with Nvidia DDS plugin. Or try to save the edited dds with dxt5 and mipmap1 compression.
And for first sight, all dds files are looks fine.

And what if the injection not working well?
## Post #5
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-11-02T06:30:14+00:00
- Post Title: DDS Format Help - Mr Mouse your skills are needed!!!

The injection is working fine. The paint tool file in the game has 20 slots which each stores a dds file. If I inject for example slot 1 dds into slot 2, the game loads it fine. 

It only stops working when I save the file with a graphics editor on my pc. 

I don't have photoshop but I have tried using the nvidia plugin with dds converter. It still doesn't work. I also can't save it with mip maps as the resulting filesize becomes bigger than the original. 

Can you please save the file with photoshop and upload it for me? I'll try it in game and see what happens.

Thanks for your help thus far.
## Post #6
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-11-02T07:31:57+00:00
- Post Title: DDS Format Help - Mr Mouse your skills are needed!!!

Attached.
[dxt5_mip1.zip](https://xentaxbackup.github.io/file/3575_dxt5_mip1.zip)
## Post #7
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-11-03T21:50:06+00:00
- Post Title: DDS Format Help - Mr Mouse your skills are needed!!!

Thanks evin. I'm traveling at the moment but will test soon.
## Post #8
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2010-11-14T16:18:41+00:00
- Post Title: DDS Format Help - Mr Mouse your skills are needed!!!

@evin, the file doesn't work. Getting the same result as the files I am saving. 

On further inspection, the format doesn't have an alpha channel and seems to store the alpha information in the image itself. I seems to use black to indicate to the game what is transparent. 

I'm not certain how it distinguishes between black which should be visible though. I've attached two files, the first is meant to be transparent outside the white box but black inside the white box. The second is meant to be completly transparent except for the white lightning design. 

Anybody have any idea how to save the file in same format?
[pt.rar](https://xentaxbackup.github.io/file/3606_pt.rar)
