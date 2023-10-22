## Post #1
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-04-22T11:57:43+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

I've been working on extracting various files from Lucas Arts Gladius game (for PS2,XBox and GameCube). With the help of game extractor I've managed to turn the large BEC archives into indidividual files, and then with various zlib decompressors I've managed to turn those files into 'meaningful' data. 

I have been struggling to get the texture data out though. The various code files seem to refer to the textures as TGA files, but they don't have a standard TGA Header, instead the data (on the ps2 version at least) seems to be raw 16bit per pixel rgb data after a given offset. I've extracted that (sample enclosed), but the colour data is wrong.  The aspect ratio of the image also seems a little odd, this one came out at 256x392 to get the 'full' image, but as you can see it definitely looks stretched vertically.

Has anyone come across this sort of colour 'corruption' before and could offer some advice on where to start looking to fix it? I've tried changing texture order from rgb to grb and other combinations. I've tried looking for palette data but couldn't see anything particuarly appropriate in my sample files. I've also tried inverting the colours and so on in Paint.Net but am a little stumped now.

I've also been trying to compare the data differences between the xbox and ps2 versions for a hint as to how it might be structured but they seem pretty different as well. Thats probably a post for another day though.

Thanks in advance.



GladiusPS2Image1.png (65.49 KiB) Viewed 351 times
## Post #2
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-04-27T12:14:51+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

I've now included the file the image data was taken from in case anyone can unpick the palette data.

thanks
[File_000066.zip](https://xentaxbackup.github.io/file/7266_File_000066.zip)
## Post #3
- Username: xexuxjy
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-04-27T14:56:23+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

You should take a better look inside those files. The image data is a bitmap, per pixel, up to 256 colours. The palette is right in front of the image data. The PS usually has images like that. The palette is RGBA, I would say. So that's 4 bytes per colour, 256 times = 0x400h (1024) bytes. The rest of the bytes is header stuff. This image is 512x512 (check out the location of this in the file).
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-04-27T21:01:07+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

Don't mind the misalignment, but this seems to be the palette in there. I doubt it will be right, as I see others on the net look like the other one. Do you have a snapshot of the original colours?



image_data.bmp (257.05 KiB) Viewed 320 times





2024658-cyclops.png (148.25 KiB) Viewed 320 times
## Post #5
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-04-28T09:12:39+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

Thankyou very much. Guess I need to learn more about palette structures rather than trusting a tool that says it's extracting the palette data for me.
## Post #6
- Username: xexuxjy
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-04-28T16:53:36+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

Actually, I just remembered I worked on SSH files textures in Def Jam and FIFA street back in 2009/2010:
[viewtopic.php?f=18&t=3894&hilit=eagt](http://forum.xentax.com/viewtopic.php?f=18&t=3894&hilit=eagt) (you may want to read that whole thread to get the gist of it all). 

Bottom line, the Electronic Arts Graphics Tool I wrote helps out here too. 

1. The file you uploaded is a sort of texture file,with magic word "R2D2psx2". Harhar. 
2. At location 0x10 (16) you see 'tmap' as an identifier for a "texture map" (?) Anyway, you will find some header info there. I won't bother to figure out all that.
3. At location 0x90 the palette starts. As said, this is a 256 colour palette , of the BGRA format, A being the alpha (translucency) value up to 0c7f (128) max. 0 is fully transparent (background shines completely through), 0x7F is full colour. The size of this palette is thus 0x400 (1024) bytes. However, this is a PS2 specific format. Read the thread above what is going on. 
4. At 0x04b0 the actual bitmap (one byte per pixel) starts. Before that, right after the palette is a small subheader of 0x20 (32) bytes long. There you will also find the width and height integers (words) showing 512 x 512. The total image bitmap is therefore 512x512 long. After the image data there seems to be a tail of 0x40 (64) bytes. 

Now, get to using EAGT. 

5. Get the palette data and image data as separate files using any hex-editor. 
6. Open the palette data in EAGT and select Convert PS2 EA Palette... from the correct menu. Choose the palette you created and give a filename for the new one. Go. 
7. Open up the raw image data in a good paint program, like Photoshop (in this case: Open As..." .RAW) and select 512x512. 
8. Change the image to Indexed Colour mode (8 bit, 256 colours) and save as 8 bit Windows bitmap. 
9. Open the image (.BMP) with the Hex Editor and replace the 0x400 bytes from location 0x36 with the new palette data. Save it. 
10. Open the .BMP image, now with correct palette. 

See below for the result that I got.  This looks spot on now.  

Get the Electronic Arts Graphics Tool here:
[viewtopic.php?f=18&t=3894&p=39092&hilit=eagt#p39092](http://forum.xentax.com/viewtopic.php?f=18&t=3894&p=39092&hilit=eagt#p39092)
Or here: [blog/?p=155](http://forum.xentax.com/blog/?p=155)



correct.bmp (257.05 KiB) Viewed 301 times
## Post #7
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-04-28T23:08:25+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

Thanks again, have spent a useful couple of hours updating my converters to write out a bunch of the files, just working on the palette converter based on your EAGT tool, but in general all those class images are coming out well now, next step is to make things more general based off the image size info and see what else I can find in the archives.
Gladius seems to be full of fun file headers, though that R2D2 one only appears in the ps2 version, xbox and GCN seem to have their own different formats, which if I'm feeling particlarly masochistic i'll try and extract as well.....
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-04-29T07:47:20+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

Okay, be sure to share your final tools.  Also,what're you going to do with the images?
## Post #9
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-04-29T07:56:08+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

What am I going to do with them? Hadn't really thought it through that far.....  Original goal was to get some textures, models and so on for a unity version of Gladius I'm writing as a fun project. This had me digging around in the files and extracted a lot of text based shop,item,character data . Then I used the Dolphin emulator and a GCN version of the game to get some ripped models of arenas, but a lot of the textures didn't come out particularly well so I wanted to find a way of getting the raw images. I'd also like to try and get the model and animation data out at a later stage, but got plenty to be going on with.
## Post #10
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-05-21T17:26:35+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

Ok, I've mostly got this working now, extracts single and multiple images from the PS2 files. Handles 8bpp indexed and rgba files. Also makes use of image names in the files where available to provide 'sensible' output. Theres still a few odd files I need to look at , and there also seems to be some texture atlas data for some files as well which might be nice to extract. c# vs2010 solution attached.

Thanks again to MrMouse for the help with this.

Now onto the model files. yay....
[GladiusPS2ImageExtractor.7z](https://xentaxbackup.github.io/file/7356_GladiusPS2ImageExtractor.7z)
## Post #11
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2015-01-27T12:03:29+00:00
- Post Title: Gladius PS2 extracted texture , colour help.

In case anyone's interested I've updated my Gladius unpacking project to extract xbox textures, as well as lots more model data :

[https://code.google.com/p/xexuxjy-xna-g ... ModelNamer](https://code.google.com/p/xexuxjy-xna-games/source/browse/#svn%2Ftrunk%2FGladius%2FUnpacking%2FModelNamer)

The difference between the xbox  (higher res 16/24bit dxt1,dx5 )and ps2 (8 bit paletted) textures is quite pronounced in a lot of cases.....
