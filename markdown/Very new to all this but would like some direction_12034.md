## Post #1
- Username: SeductiveJelly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 17, 2014 11:57 pm
- Post datetime: 2014-10-01T18:43:39+00:00
- Post Title: Very new to all this but would like some direction

So I am very new to all of this and do not know much. I know that this is probably a noob question but I have been trying to mess around with graphics files and recently found a file in Trials Fusion that contains tons of files that end in *png.tex. So I assume they were originally .png files. 

    Anyways I was experimented with the "Texture Finder" tool. I found the correct format, shift, and widths. I then saved it a BMP image. I then altered the picture to my liking but, the problem is I don't know how to but it back into the original .tex for use again. What can I do? Any help in right direction would be great. Thanks!
## Post #2
- Username: SeductiveJelly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 17, 2014 11:57 pm
- Post datetime: 2014-10-03T17:03:54+00:00
- Post Title: Very new to all this but would like some direction

I know that someone here can help me. I am aware that I am new and you probably don't care enough to respond, but, it would be extremely helpful to me in so many ways. Any replies at all would be greatly appreciated. Even if you don't know for sure.
## Post #3
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-10-03T22:53:03+00:00
- Post Title: Very new to all this but would like some direction

You need to provide files and code. Get us up to speed.
## Post #4
- Username: SeductiveJelly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 17, 2014 11:57 pm
- Post datetime: 2014-10-03T23:06:29+00:00
- Post Title: Very new to all this but would like some direction

> Reply from JohnHudeski
>
> You need to provide files and code. Get us up to speed.

Okay, the game is Trials Fusion. Once you have unpacked the data_misc.pak there is a folder called images. In there are all(as far as I know) the static images used by the game.

Here is a link the the files so you can look at them for yourself: [http://www.mediafire.com/download/qofiv ... _Files.zip](http://www.mediafire.com/download/qofivb5cicpruyd/Trials_Fusion_tex_Files.zip)
## Post #5
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-10-25T21:31:29+00:00
- Post Title: Very new to all this but would like some direction

Here's one way to edit the images (probably not the best way though).

First of all you'll need three things:
a) A Hex Editor (I'm usinig [HxD](http://mh-nexus.de/en/downloads.php?product=HxD))
b) [GIMP](http://www.gimp.org/downloads/) (or Photoshop)
c) A png.tex file (I chose medal_64_4.png.tex)

Follow these steps:
1) Open the *.png.tex file with a hex editor (see screenshot below, left image)
#Header: 0x1D or 0x1F bytes (file starts with T5X or T8X)
#DXT5 compressed image (no mipmaps)

2) Get the width and height
0x80 = 128
0x40 = 64

3) Open GIMP:
File > New > Width:128, Height: 64 > OK
File > Export As... > Name: texture.dds > Export > Compression: BC3 / DXT5 > OK

4) Open the *.dds file with the hex editor (see screenshot, right image)
Select width*height bytes starting from offset 0x80
Copy width*height bytes (offset = 0x1D in T5X files, 0x1F in T8X) from the *.png.tex file and paste them into the .dds
Save the file and open it with the GIMP

5) Now you can edit the image, export it to dds (don't forget to set the compression to DXT5 again) and use the technique from above to copy the data from the dds to the png.tex



screenshots.png (118.58 KiB) Viewed 56 times
