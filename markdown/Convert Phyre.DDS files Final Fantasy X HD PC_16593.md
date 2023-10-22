## Post #1
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2017-07-25T22:56:20+00:00
- Post Title: Convert Phyre.DDS files Final Fantasy X HD PC

I need some help converting phyre.dds files from the PC version of Final Fantasy X HD

dtester1 already made a converter but it only works for a limited amount of files here's his post ([viewtopic.php?f=16&t=11107&p=126978#p126978](http://forum.xentax.com/viewtopic.php?f=16&t=11107&p=126978#p126978))

Here are some samples: [https://mega.nz/#!w2h30IAb!7vntFo4G8UtX ... u0v8JawYBk](https://mega.nz/#!w2h30IAb!7vntFo4G8UtXE7BfaGzPsurif0oIklDjXu0v8JawYBk)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-26T07:31:02+00:00
- Post Title: Convert Phyre.DDS files Final Fantasy X HD PC

here is a Noesis python script to open all of your dds.phyre samples except the cubemap image (reflection3.dds.phyre)  


 tex_FinalFantasyXHD_PC_phyre.zip
(924 Bytes) Downloaded 496 times


supports dxt1, dxt5, bgra8

the cubemap image has something else going on and needs more time
to research but you can decode it with TextureFinder in the mean time.
## Post #3
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2017-07-26T14:17:37+00:00
- Post Title: Convert Phyre.DDS files Final Fantasy X HD PC

Thank you very much, you're a real life saver. Some ARGB textures have wrong colors but it doesn't matter.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-27T01:42:34+00:00
- Post Title: Convert Phyre.DDS files Final Fantasy X HD PC

> Reply from Beyond69
>
> Some ARGB textures have wrong colors but it doesn't matter.
script updated in previous post, had to reverse the channels
## Post #5
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2017-07-27T13:42:43+00:00
- Post Title: Convert Phyre.DDS files Final Fantasy X HD PC

Thanks again
## Post #6
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2017-08-07T19:02:44+00:00
- Post Title: Convert Phyre.DDS files Final Fantasy X HD PC

There is an easy way to edit (or, for example, translate) DDS textures in "dds.phyre" files. I have translated all needed textures in this way:

1. Download Nvidia plugin to Photoshop to get "D3D/DDS" format in PS.
2. Download Texture Finder 2.1.
3. Open the same file in hexeditor, to check the type (near 0xA30-0xA40) - PTexture2D DXT1, DXT3 or DXT5.
4. Open .dds.phyre file in Texture Finder.
5. Set the correct setting (DXT1, 3 or 5), check vertical flipping and change width to correct. This is to get the correct width and height of the texture.
6. Create new file in Photoshop, with width and height of the DDS you want to extract. Save as DDS with correct settings (DXT5, DXT3 etc), with checked "Save Flipped Vertically", "No MIP Maps", and "2DTexture".
7. Copy body of graphic from phyre file (starting from 53 byte after offset of PTexture2D) and paste into the DDS file, starting from 0x80. Save the file.
8. Open the file in Photoshop, remember to check "Load Flipped Vertically".
9. After editing, you have to put the content of DDS file back to the dds.phyre file.
## Post #7
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2017-12-21T09:27:35+00:00
- Post Title: Convert Phyre.DDS files Final Fantasy X HD PC

> Reply from AceWell
>
> here is a Noesis python script to open all of your dds.phyre samples except the cubemap image (reflection3.dds.phyre)  
tex_FinalFantasyXHD_PC_phyre.zip
supports dxt1, dxt5, bgra8

the cubemap image has something else going on and needs more time
to research but you can decode it with TextureFinder in the mean time.
the python script doesn't really work for me in Noesis, nothing shows up at all .-.
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-21T10:48:23+00:00
- Post Title: Convert Phyre.DDS files Final Fantasy X HD PC

> Reply from demonslayerx8
>
> the python script doesn't really work for me in Noesis, nothing shows up at all
are your samples from the same game and platform the script was written for?
how many samples did you try?
is there an error?
if no error, is it just appearing invisible in viewport because of alpha channel?
can you provide not-working samples for investigation into the problem?
you gotta give me more to go on, nothing i can do without at least some samples. 


> Reply from Robin
>
> 3. Open the same file in hexeditor, to check the type (near 0xA30-0xA40) - PTexture2D DXT1, DXT3 or DXT5.
4. Open .dds.phyre file in Texture Finder.
5. Set the correct setting (DXT1, 3 or 5), check vertical flipping and change width to correct. This is to get the correct width and height of the texture.
6. Create new file in Photoshop, with width and height of the DDS you want to extract. Save as DDS with correct settings (DXT5, DXT3 etc), with checked "Save Flipped Vertically", "No MIP Maps", and "2DTexture".
7. Copy body of graphic from phyre file (starting from 53 byte after offset of PTexture2D) and paste into the DDS file, starting from 0x80. Save the file.
you do realize my script makes these steps obsolete?
## Post #9
- Username: mami11x
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 24, 2018 11:54 am
- Post datetime: 2018-02-25T09:09:55+00:00
- Post Title: Convert Phyre.DDS files Final Fantasy X HD PC

> Reply from Robin
>
> There is an easy way to edit (or, for example, translate) DDS textures in "dds.phyre" files. I have translated all needed textures in this way:

1. Download Nvidia plugin to Photoshop to get "D3D/DDS" format in PS.
2. Download Texture Finder 2.1.
3. Open the same file in hexeditor, to check the type (near 0xA30-0xA40) - PTexture2D DXT1, DXT3 or DXT5.
4. Open .dds.phyre file in Texture Finder.
5. Set the correct setting (DXT1, 3 or 5), check vertical flipping and change width to correct. This is to get the correct width and height of the texture.
6. Create new file in Photoshop, with width and height of the DDS you want to extract. Save as DDS with correct settings (DXT5, DXT3 etc), with checked "Save Flipped Vertically", "No MIP Maps", and "2DTexture".
7. Copy body of graphic from phyre file (starting from 53 byte after offset of PTexture2D) and paste into the DDS file, starting from 0x80. Save the file.
8. Open the file in Photoshop, remember to check "Load Flipped Vertically".
9. After editing, you have to put the content of DDS file back to the dds.phyre file.

Where is file "sub"? Help
