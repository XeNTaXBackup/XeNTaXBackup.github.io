## Post #1
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-06-14T14:56:57+00:00
- Post Title: South Park Rally PC texture files

Hello,


I'm trying to figure out for years how can I open the textures files for South Park Rally.

They are all in .vram file format and they are with the company of .rbh files which I think they are for 3D models or also for sound format.

Any help for this thread will be appreciated, thanks!


Here is the files:
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-18T18:41:15+00:00
- Post Title: South Park Rally PC texture files

In the words of aluigi

> No sample, no party
## Post #3
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-06-19T03:26:53+00:00
- Post Title: South Park Rally PC texture files

> Reply from AceWell
>
> In the words of aluigi
No sample, no party

You're saying that I need to send a file?

 Here I send one of them!
[cartman.zip](https://xentaxbackup.github.io/file/11076_cartman.zip)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-19T04:17:55+00:00
- Post Title: South Park Rally PC texture files

Sorry man i have no clue what kind of image this is, it kind of looks like an archive of some sort.   
4 bytes - BODY
4 bytes - data length
data
next sub header


since this is a PC game have you tried ripping the textures with Ninjaripper or something?
## Post #5
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-06-21T21:36:08+00:00
- Post Title: South Park Rally PC texture files

Yes I tried, even with 3D Ripper DX too!!


  But doesn't work on this game.
## Post #6
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-06-22T06:27:57+00:00
- Post Title: South Park Rally PC texture files

The .vram file contains multiple 256-color bitmaps.
With this information it should be possible to extract all the images:

char[4] | "PIFF"
uint32 | file size
char[4] | "VVTP"

while (!EOF) {

char[4] | "BODY"
uint32 | chunk_size
uint32 | header_size
uint32 | image id
uint16 | bitmap_width
uint16 | bitmap_height
uint16 | flags (see below)
uint16 | color_depth (4, 8, 16, 24, 32)
byte[0x10] | bit_fields (ARGB, 4 bytes each)
uint32 | image_data_offset (= size of header + color table)
uint32 | unknown (0 or 0x40)
uint32 | number of mipmaps
byte[0x14] | unknown data (usually all 0)
byte[2^color_depth * 4] | color table, 4 bytes per pixel = [blue, green, red, alpha] (if color_depth <= 8)
byte[width * height * color_depth / 8] | bitmap (top to bottom order)

// mipmaps (if number of mipmaps > 0)

}

/*
 * flags:
 * bit 1 (1)	hasNoColortable (16,24,32)
 * bit 2 (2) 	hasTransparency (16,32)
 * bit 3 (4) 	hasColorDepth4
 * bit 4 (8) 	hasColorDepth8
 * bit 5 (16) 	hasNoTransparency (16,32)
 * bit 8 (128)	hasMipmaps
*/

Edit: File format updated
## Post #7
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-06-25T18:04:36+00:00
- Post Title: South Park Rally PC texture files

What do I do to really extract the images so I can edit them?
## Post #8
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-06-25T22:23:40+00:00
- Post Title: South Park Rally PC texture files

Ok, here's a tool that extracts the images.
Do you also need to repack the edited images?

Download and extract this zip archive:


 VramExtractor1.0.zip
(6.18 KiB) Downloaded 46 times

copy both files to the location of your .vram files
Run 'Extract VRAM.bat' and enter the .vram filename

Requires a Java Runtime Environment ([http://www.java.com](http://www.java.com)).
## Post #9
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-06-26T12:53:07+00:00
- Post Title: South Park Rally PC texture files

Yes, I want to repack back the edited files.


Thank you so much for this!!



Edit: But there's also another problem, the extractor doesn't work with all the other vram files because maybe the files doesn't have "bitmap" as a name. Here I let the art folder for you.   Here's the link [https://drive.google.com/open?id=0By_Xs ... m1FdWpGcGs](https://drive.google.com/open?id=0By_Xs884e-hxUUZvdm1FdWpGcGs)
## Post #10
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-06-27T06:38:51+00:00
- Post Title: South Park Rally PC texture files

Ok, the first sample file only had indexed color bitmaps (color depth 4 or 8). But there are also vram files with a color depth of 16, 24 or 32 bits/pixel. The updated extractor supports these files.


 VramExtractor1.1.zip
(6.93 KiB) Downloaded 36 times


The number in curved brackets in the filename is the color dpeth - e.g. "Bitmap_1 (8).bmp"

Note that inferior image viewers/editor (like Windows Photo Viewer or Microsoft Paint) can't display transparent bitmaps (= bitmaps with a color depth of 16 or 32). GIMP for instance can display those files correctly.

I'll start to create the repacker soon.


By the way, you can also extract all .vram files by entering this as the filename: 
```
*.vram
```
## Post #11
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-06-27T08:37:05+00:00
- Post Title: South Park Rally PC texture files

It really works!!!

Thank you so much.


I'll be waiting for the vram packer so then I can test the edits in-game.


   So many thanks!!
## Post #12
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-06-28T01:37:41+00:00
- Post Title: South Park Rally PC texture files

Please check if the bitmaps of the repacked vram files are displayed correctly in the game. The repacked files don't match the original files 100%, for example I skipped the mipmaps.


 VramTools1.2.zip
(13.31 KiB) Downloaded 42 times

Usage: Just run the BAT file and enter the name of the VRAM file to extract it or enter the name of an extracted folder to repack it.
## Post #13
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-06-28T14:38:17+00:00
- Post Title: South Park Rally PC texture files

I gotta say it, pal.. 


   It really works!!! You did it 100% perfect, there's one or such where I have to convert 24 bit bmp formats to 8 bit but that's no problem for me because I've been testing everything one by one and see the problems in each character.

  I'll might create a gui for this code so it can be easier to use it and the special thanks goes to you!!



Just one more thing, you that know a lot about encrypted extensions and files it would be possible for you to figure about the rbh extension?

  It might be an archive I think but in one folder I think it contains the 3D model and in the other folder contains audio files:


[viewtopic.php?f=17&t=14571](http://forum.xentax.com/viewtopic.php?f=17&t=14571)

[viewtopic.php?f=16&t=14579](http://forum.xentax.com/viewtopic.php?f=16&t=14579)



The rbh with the audio files can be possible to open in audacity as a raw file and then change the hz and such but I would like to edit as well I did with the .vram.


And the rbh with model files I would like to know what format of the 3D model and changes somethings if possible.
## Post #14
- Username: QOTSANINSOADKORN
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 01, 2016 7:26 pm
- Post datetime: 2016-07-01T12:23:52+00:00
- Post Title: South Park Rally PC texture files

What About Stick Of Truth and it's Sequel...
After all this luck above...
I Expected some simple mods for SoT months after it's launch...
is it unusually complicated?
the PS3 Files i remember looking at when i first got them... 3 days before the official launch... it at least had all the uncut scenes... a movie extracter would be nice for eg...
## Post #15
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-07-09T16:40:55+00:00
- Post Title: South Park Rally PC texture files

The file formats of South Park Rally and The Stick of Truth have nothing in common, they games were developed by different game studios.

Btw, here's the latest version of the Vram utility:
[viewtopic.php?f=32&t=14623](http://forum.xentax.com/viewtopic.php?f=32&t=14623)
