## Post #1
- Username: Kastoplex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 23, 2022 2:04 am
- Post datetime: 2022-01-22T18:16:53+00:00
- Post Title: Soulbringer - B16 and BIN textures

Hi there!
I was trying to figure out the resource format of the classic "Soulbringer" recently. I figured the files with extensions .b16 and .bin in the data folder should be the resource files containing the textures. I tried several tools like the resource detection of quickbms, but it doesn't recognize anything usable. I tried tools like Ravioli that scans files for bitmap resources, but it didn't help either. Did someone stumble over these kind of files or did some research in this game already who could give me a hint?
If this sounds like a "noob question", then probably because i am exactly this: totally new in this    Thanks!
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-22T19:29:26+00:00
- Post Title: Soulbringer - B16 and BIN textures

> files with extensions .b16 and .bin in the data folder
Can you upload few samples of B16 and BIN files to some hosting site like mega.nz or google drive and share a link with us?

> i am exactly this: totally new in this
If you're looking for some knowledge sources, 
you can check this topic [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #3
- Username: Kastoplex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 23, 2022 2:04 am
- Post datetime: 2022-01-22T19:45:28+00:00
- Post Title: Soulbringer - B16 and BIN textures

Thanks for the link with the Reverse Engineering Tutorial, I'll check it out! I'll update if I find a solution
## Post #4
- Username: Kastoplex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 23, 2022 2:04 am
- Post datetime: 2022-01-23T08:07:25+00:00
- Post Title: Soulbringer - B16 and BIN textures

Attached you'll find a link to one of the resource directories (data folder) of Soulbringer:

[https://mega.nz/file/wVhwGDjJ#YCujDZlhD ... YbSIB3IpPc](https://mega.nz/file/wVhwGDjJ#YCujDZlhDpUY2Zx0LF6GKUqHqVnlK6ThuYbSIB3IpPc)

I checked the other resource directories, too, and the B16 files always have a size of 128KB, while the BIN files always have a size of 64KB.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-23T12:03:42+00:00
- Post Title: Soulbringer - B16 and BIN textures

Those files contain raw texture data. 

You can open them in texture finder
[https://i.imgur.com/qJFqGqa.png](https://i.imgur.com/qJFqGqa.png)
[https://i.imgur.com/Vd0zSVp.png](https://i.imgur.com/Vd0zSVp.png)

All the files I have checked are 256x256 and 16 bit or 8 bit images.
Someone could create a script for Noesis to handle them automatically.
## Post #6
- Username: Kastoplex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 23, 2022 2:04 am
- Post datetime: 2022-01-23T13:03:30+00:00
- Post Title: Soulbringer - B16 and BIN textures

Thanks, that's helpful! I didn't know neither TextureFinder nor Noesis, i will have to read about them! For now, thanks for your time! I'll post if I make any progress
## Post #7
- Username: Kastoplex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 23, 2022 2:04 am
- Post datetime: 2022-01-24T13:09:40+00:00
- Post Title: Soulbringer - B16 and BIN textures

With TextureFinder I can easily export the file as a bitmap, that's quite nice. Is there a tool that does the job backwards, like converting the a bitmap back to the RAW bitmap data file? IrfanView could import the files but doesn't allow me to set the correct pixelformat.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-24T21:10:46+00:00
- Post Title: Soulbringer - B16 and BIN textures

> Is there a tool that does the job backwards, like converting the a bitmap back to the RAW bitmap data file?

So I was able to create a Noesis plugin for you [https://i.imgur.com/n33nRVO.gif](https://i.imgur.com/n33nRVO.gif)
But I couldn't figure out BIN format, so let's say this script is "experimental". 

Here is the code:
[https://github.com/bartlomiejduda/Tools ... _script.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Soulbringer/Soulbringer_b16_bin_Noesis_script.py)

So first you need to install it. Just move the script to \noesisv4459\plugins\python directory.

Then you can export/import like this:

1. Load B16/BIN file in Noesis
2. Export it to PNG
3. Edit PNG in GIMP
4. Import PNG to Noesis and export it to B16/BIN.
## Post #9
- Username: Kastoplex
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 23, 2022 2:04 am
- Post datetime: 2022-01-24T21:38:52+00:00
- Post Title: Soulbringer - B16 and BIN textures

Wow, thanks, I'll check it tomorrow! I really appreciate your help!
