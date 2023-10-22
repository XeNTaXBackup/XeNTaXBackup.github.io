## Post #1
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-11-25T13:06:31+00:00
- Post Title: Def Jam Bitmap and .colours files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-12-06T08:05:06+00:00
- Post Title: Def Jam Bitmap and .colours files

Any progress?
## Post #3
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-12-13T22:06:47+00:00
- Post Title: Def Jam Bitmap and .colours files

Well no.

Nobody actually replied here so (

Hope i still could get helped


Ty
## Post #4
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-12-23T20:54:33+00:00
- Post Title: Def Jam Bitmap and .colours files

Still I want these files are decoded. You can see that they are not encrypted in any way. The image is clearly visible, only to have something to do with the palette. Maybe endianess or sth? Once again, please work on these files. I guess it's not that difficult? Thank you again.
Sorry for my poor English possible, I used google tanslate.
## Post #5
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-12-26T23:06:40+00:00
- Post Title: Def Jam Bitmap and .colours files

Yes... but... the problems is... when i try to open em in PS i get nothing or wrong file.... and the pallette does not show anything good too... :S
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-28T19:01:05+00:00
- Post Title: Def Jam Bitmap and .colours files

Can you upload them again, thx?
## Post #7
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-12-29T09:02:57+00:00
- Post Title: Def Jam Bitmap and .colours files

Some files from the FIFA street.

[http://www.filefront.com/15240337/files.rar](http://www.filefront.com/15240337/files.rar)

I hope these files can be opened.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-29T19:35:37+00:00
- Post Title: Def Jam Bitmap and .colours files

How did you get the image right?
## Post #9
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-12-29T20:46:28+00:00
- Post Title: Def Jam Bitmap and .colours files

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-29T23:34:24+00:00
- Post Title: Def Jam Bitmap and .colours files

I see your point. There's somethinh going on with the palette. The 4th byte of each colour goes up only to 128 and not 256 as a "true" alpha channel.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-30T08:15:59+00:00
- Post Title: Def Jam Bitmap and .colours files

Also, it would help if you have a screenshot of textures in action, so we can compare the real colours. Is that possible?
## Post #12
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-12-30T08:28:43+00:00
- Post Title: Def Jam Bitmap and .colours files

Unfortunately, no. Sorry, but this image comes from the GUI. I do not remember how was called *. big file from which came the file, because I had to rename the file. The file had a "/" and could not be saved to disk. Maybe you understand?
## Post #13
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-12-31T08:57:39+00:00
- Post Title: Def Jam Bitmap and .colours files

Here is an another file: 
It shows flags while selecting language in game. First should look like flag of england.
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-31T09:22:01+00:00
- Post Title: Def Jam Bitmap and .colours files

There is no attachment
## Post #15
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2009-12-31T09:50:31+00:00
- Post Title: Def Jam Bitmap and .colours files

[http://www.filefront.com/15257567/flags.ssh](http://www.filefront.com/15257567/flags.ssh)
## Post #16
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2009-12-31T19:40:00+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-01T18:08:23+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

I've borrowed the game now and it sort of works on thepcsx2 emulator, so I can check some in-game textures and compare with the files. Using PT Explorer I could at least confirm that the 4th byte is an alpha (tranparency) value, but I'm unsure what the colours are. I see that each ssh file is accompanied by other files. ONe of those a .o file (ELF) has this text in it: 

```
__Model:::2 
__EAGL::TAR:::RUNTIME_ALLOC::UID=3000;SHAPENAME=1,1;PS2EXTOBJ_SetClampH=EAGL::PS2CM_CLAMP;PS2EXTOBJ_SetClampV=EAGL::PS2CM_CLAMP;
__BBOX:::2 __COORD4:::ColourModulator __EAGL::GeoPrimState:::RUNTIME_ALLOC::UID=3000;;SetTextureEnable=true;SetAlphaCompareValue=1;SetAlphaBlendMode=EAGL::ABM_BLEND;SetDepthTestMethod=EAGL::DTM_GEQUAL;;SetPrimitiveType=EAGL::PT_TRIANGLESTRIP;
__const MATRIX4:::EAGL::ViewPort::gpModelViewProjectionMatrix TextureApt0__EAGLMicroCode
__EAGL_TOOLLIB_VERSION:::EAGL_TOOLLIB_VERSION-4
TextureApt 
```


This seems to mean as much as Electronic Arts Graphics Library (EAGL) 
It then sets an alpha compare value of 1 and a blend mode of EAGL (standard I assume) But it also tests Depth.
## Post #18
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-01T23:09:59+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Okay, a little progress. 

1. I used MultiEx Commander to extract compressed BIG files from the non-compressed ASSETCMN.BIG file. 
2. It gave me the tr1.big file that I opened with BigGUI and extracted the tr1.ssh file from. 
3. I wrote a little program that created a test palette and picture to replace the tr1.ssh contents with (it is the trophy picture of the Danish SAS league). 
4. I used BigGUI to replace the contents of the tr1.big file with my test picture and palette (my altered tr1.ssh). 
5. I reimported the new tr1.big file into ASSETCMN.BIG with MultiEx Commander
6. I used UltraISO to delete the old ASSETCMN.BIG in the games's ISO and replaced it with my new one. 
7. I mount the new iso using Virtual Clonedrive
8. I fire up PCSX2 and point to the new virtual drive to boot from and start the game

In the tournament selection screen I switch to the Danish league and look at my test picture. Here's the result:

First my test picture. It will show Blue Green and Red in ever increasing alpha up to 255 (0 transparency) at the end. You can't see the alpha here.



The test picture my program generated (alpha not visible) tr1_SAS_trophy_test.bmp (65.05 KiB) Viewed 530 times

 

Here's my PTExplorer showing off the alpha variable. You notice it is a smooth transition to solid. 



PTExplorer generated alpha increasingalpha_alternatingRGB_ptexplorer.jpg (47.68 KiB) Viewed 529 times



Now here's the in-game view. 



My test picture in the game increasingalpha_alternatingRGB_PS2.jpg (53.92 KiB) Viewed 530 times



You'll notice two things. First, the game has RGB the other way around in the palette (I suspected as much, but this confirmed it). Second, the 4th byte (the alpha variable), is not a smooth one. It is indeed also giving rise to transparency, but in a jumpy way, and there's more to it. SOme values give less transparence than others, I think this may mean something about Depth as well.
## Post #19
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-01-02T12:30:29+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Many thanks. Waiting for more. 
Maybe there would be a tool for editing these files without unnecessary cases from other files, such as BIG.
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-03T00:05:37+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

I don't know about that. Could be, but not for sure. At least the above method succesfully mods the game.
## Post #21
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-04T12:18:59+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

I think these textures are colour modulated in a way. This technique would enable an original image to be stored in less bytes, while retaining a sufficient resolution if you need to show the texture larger on screen. When plotted on screen the source cell colour is taken and put in an algorithm to obtain the actual colour based from a predetermined palette (in three dimensions : red, green and blue as axis), depending on size of the texture. Even with a palette of 256 colours, each taken from a prism of red, green and blue, one can create higher colour images. 

I will need to keep experimenting to see what happens if I change certain aspects of images. 

I've written a program that will extract a folder full of *.big files to another folder, and then extracts all .ssh files it finds, automatically creating *.bmp images as well of the images. This made it easier to find images that appear in the boot of the game, so I can alter those for testing purposes (and don't have to go through the game each time). 

From what I saw, I can copy a part of the original image and duplicate it elsewhere in the original image without problem: it will show the same. So there is no underlying invisible colour map at work. I've also created some squares next to each other and that does not result in distortion at the edges of the squares. However, the squares were solid in one colour. I've also tried to import a new image using the palette of the original image, but that showed incorrectly in-game.
## Post #22
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2010-01-05T21:44:20+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

What a progress...

Does this work for Def Jam FFNY too??

how much u ask for the program?:P

very nice man keep it up

and thnx
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-11T08:45:48+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Ok, just a small update so I don't forget. 

I've been working with the 47_legal.ssh file, the first picture is the one with all the logo's of the national competitions that you see during boot of the game. 

I created a test picture that showed the complete palette of the picture as squares of 14x14, 16 columns with rows of 16 (thus making 256 colours of the palette) and set the alpha to 128 (0% transparency) for each. I wanted to see which colours would be exact in the game and which would be altered somehow. 

I then made a screenshot and used the original testpicture as overlay in Photoshop and set the blending option to "Difference". This way I could see which colours were exact and which were modulated (example : a black result would mean no difference, any other would indicate some difference).  

It turns out that the palette started with 8 colours that were exact, followed by 16 colours that were modulated, followed by 16 colours that were exact, followed by 16 colours that were modulated and this repeated for the whole palette. So colours 0-7 were unchanged by the game, 8-23 were modulated somehow, 24-39 were unchanged,  40-15 were modulated etc. So there is a definite pattern there. I have yet to check if this is the same pattern for other pictures. 

I then tried to create a picture with only the unchanced colours (I call them 'primary colours'), and did so using a palette that only left the primary colours and the modulated ones I made black. Using that palette in Photoshop I could simply copy and paste another picture there, Photoshop would choose the right colours (and had only the primaries to chose from). 

Interestingly, the game did not like this, as it hung when trying to show the picture. I will have to confirm that as well, when I left the picture alone, but used that trimmed palette instead, the picture showed up, so it seems that the game expects or needs certain colours at specific locations in the palette to be used in the image.
## Post #24
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-12T22:49:34+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Interesting, I got a picture in, using only the primaries. 

It shows as intended. Note I edited the picture's palette to have only the primaries remain and all other colours I made black. Note how the rest of the picture is now as "corrupted" as we see it in a paintprogram. The colour modulation depends on the non-primaries.



primary picture.jpg (260.35 KiB) Viewed 380 times
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-17T21:01:31+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

I've noticed something interesting. Those modulated palette entries (16 bytes in lenght) are actually two sets of 8 entries that are switched position in game. So the first set becomes second and the second becomes first.
## Post #26
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-17T21:41:25+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Yes, hehe, that looks a lot better doesn't it:



47_legal_ssh_file1.jpg (208.4 KiB) Viewed 346 times



That's the logo bit at the start. I've extracted the bitmap and palette from 47_legal.ssh and converted the palette to my idea. Notice how the colours now match !
## Post #27
- Username: grzesiek
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-17T21:51:08+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Yes, and here's a part of the picture in PT Explorer with active alpha (transparency), it works 100%.



47_legal_ssh_file1_pt_alpha.jpg (138.97 KiB) Viewed 326 times



It's half as bright, because the game uses 128 as max opacity (0 transparency) instead of 256 assumed by PT Explorer. So you see it as 50% transparent against a black background.

Check out this picture as well, I extracted the bitmap and palette, converted the palette and voila!



backPS22.ssh.png (179.47 KiB) Viewed 321 times
## Post #28
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-01-18T07:13:29+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Wow, nice! Can you make a program to view or convert these files? Ex bmp to ssh and vice versa?
## Post #29
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-18T07:28:53+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

In time yes. There is still some unanswered question: why is this palette modification being done? I tried importing a new image instead of the logos, with exactly the same size and pre-converted the palette. However, the game hung when the image was about to come up. So, there is more to the palette than just the switching of colours. Perhaps the game expects certain colours to be present at certain locations, or certain colours with 0 alpha at certain location, it can be anything. This requires even more research. 

For now, if you want to thank me, press the "thank you" button below my previous post for figuring out a way to properly show the textures outside the game.  It is common courtesy at these forums . 

I will release the tool when I'm satisfied I've covered most or enough of the format. It would be interesting to see if this method also applies to other games than FIFA2009. A universal tool to modifiy these PS2 Electronic Arts games could then be created. 

A viewer to at least browse and view the files is also an option to release first.
## Post #30
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-01-18T07:55:24+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Can you get out something from this compressed ssh? From FIFA Street.

[http://www.speedyshare.com/files/20405464/splash.ssh](http://www.speedyshare.com/files/20405464/splash.ssh)

It should look like this but with no load bar:
[image.JPG](https://xentaxbackup.github.io/file/2734_image.JPG)
## Post #31
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-18T08:11:54+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

That file is compressed. Do you have a decompressor?
## Post #32
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-01-18T08:18:03+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Try FSH Tool:

1. Change header from SHPS to SHPI (in hex editor)
2. Drag and drop ssh to fshtool
3. You should get 0000.BIN file
4. In multi image ssh each BIN is one image
5. BIN starts with width or height or sth (i dont remember). Rest should be the same as regular ssh.
Offset of image is probably 16 (in dec). And size is 512x512.

EDIT - Probably the image is 16 bit
## Post #33
- Username: grzesiek
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-18T15:20:42+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Works perfectly. Converted the palette:



1.JPG (78.78 KiB) Viewed 418 times
## Post #34
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-01-18T16:03:02+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Colours are a bit different  - red channel is replaced with blue
THX, waiting for tool
## Post #35
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-18T17:06:28+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Ah yes, I see now. Corrected for this one:



Kopie van 1.png (228.64 KiB) Viewed 394 times
## Post #36
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-01-27T11:30:18+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Could you write a little program for only viewing ssh files?
## Post #37
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-27T16:10:25+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Yeah, I'm already doing that.  It already works.
## Post #38
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-03-13T09:10:33+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Progress?
## Post #39
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-03-31T17:00:09+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

When the viewing tool will be relased?
## Post #40
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-31T21:00:11+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Hopefully soon. The code is still a mess.
## Post #41
- Username: grzesiek
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Oct 24, 2009 1:59 am
- Post datetime: 2010-05-28T18:36:32+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

How to quickly replace colors in the palette that the order was good? Some special command in the hex editor? And what about the creation of a program to look at these textures?
## Post #42
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-03T09:24:33+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Sorry for the late response, but I've worked on the first release of the tool yesterday since months. I now hope to release a first version this week. It will extract *.bmp from SSH files with the correct palette for viewing.
## Post #43
- Username: absarhegde
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-03T21:45:32+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Here is the tool. use 7Zip to unpack it. EA Graphics Tools. 



eagt.jpg (370.73 KiB) Viewed 179 times


[EAGT_0_1_0.7z](https://xentaxbackup.github.io/file/3104_EAGT_0_1_0.7z)
## Post #44
- Username: absarhegde
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 21, 2008 2:52 am
- Post datetime: 2010-06-04T06:26:37+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

thanks for the wonderful software..

i was waiting for this since long...

have couple of questions..

how can we import a bitmap in SSH file ? will it support in your next update ?

and this SSH file shows some error in your tool...
it opens in EAgraphic editor(released by someone else)
have attached this file
## Post #45
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-04T07:42:03+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

There is no attachment. 

As for importation, yes, that may be in a later version. However, you should be aware that the palette can be converted to standard, but to create a picture in the palette format that this Electronic Arts playstation software uses back into the SSH file is another issue. I can convert the colours from EA to standard, but I have yet to determine exactly what imaging algorithm was used to create the EA palette.
## Post #46
- Username: absarhegde
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 21, 2008 2:52 am
- Post datetime: 2010-06-04T20:11:50+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

sorry here is the attached file
[tops0907.rar](https://xentaxbackup.github.io/file/3111_tops0907.rar)
## Post #47
- Username: absarhegde
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 21, 2008 2:52 am
- Post datetime: 2010-06-20T10:29:55+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

any news for update ?/
## Post #48
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-21T08:24:12+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

I need to restrict myself to complete one project at a time. Currently I'm working on my HOMM1 Converter to finish it more properly. Then I will return to this one.
## Post #49
- Username: absarhegde
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 21, 2008 2:52 am
- Post datetime: 2010-06-22T01:07:05+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

oohk thanks 
i ll wait
## Post #50
- Username: adam35
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 02, 2010 1:43 am
- Post datetime: 2010-07-05T03:33:40+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Great breakthrough on this file...if the project is completed, all EA Sports games should be able to be modded on PS2.
## Post #51
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2010-07-15T21:29:13+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Mr. Mouse,

Thank you for responding to my topic once again, the program you made is great!!!! I hope I can work on with it and make my dream come true.

Im also back on the forums now.

Thank you so much!
## Post #52
- Username: Fatal
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 17, 2009 5:10 am
- Post datetime: 2010-07-16T12:28:20+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Sorry for double posting but when i want to open an SSH it goes all ok but when i want to open another one the program crashes.. Im using windows 7.

Is this a problem from my computer or,,??

Thank you in advance
## Post #53
- Username: absarhegde
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Aug 21, 2008 2:52 am
- Post datetime: 2010-10-28T00:30:50+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Hey! Mr. Mouse 
its really been long... can we get the update of tool now ?
please can you start working on this project ....   
need this tool to work with EA games...please help us
## Post #54
- Username: NightHawkFur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 10, 2019 1:05 am
- Post datetime: 2019-01-09T17:07:13+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Whenever I try to open an .ssh file from ssx tricky (apart from the splashscreen, wich actually works and doesn't crash the program):



Unbenannt.bmp (96.28 KiB) Viewed 46 times



I actually managed to mod the game so it uses the beta boards featured in the winter 2001 "jampack" demo. however some of them use a placeholder texture that i'd like to change with the final ones, you know.
## Post #55
- Username: NightHawkFur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 10, 2019 1:05 am
- Post datetime: 2019-01-14T08:51:03+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

bump
## Post #56
- Username: NightHawkFur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 10, 2019 1:05 am
- Post datetime: 2019-01-21T19:33:24+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

bump
## Post #57
- Username: NightHawkFur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 10, 2019 1:05 am
- Post datetime: 2019-01-28T01:49:35+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

bump
## Post #58
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-28T08:15:45+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

> Reply from NightHawkFur
>
> bump

You should probably make a topic about it instead and provide both the files you want modified and the tools are using so people can troubleshoot. 
If nobody can get the tools to work, then I bet there is people who know how to do it manually.

/GHFear
## Post #59
- Username: NightHawkFur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 10, 2019 1:05 am
- Post datetime: 2019-01-30T18:06:27+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

I'd love to provide the files, however for some reason when I try to rip the .ssh texture files using the program "finalbig", They end up being around 500MB to 1Gb.
In total around 60Gb. Now that can't be real. (If it is, tell me where I would upload 60gigs...) Also, when I try to open these huge .ssh files in eagt, the program crashes.

Now, when I try to extract the .big archive using EAGT instead of finalbig, I end up with an empty file with the extension ".lst"
## Post #60
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-31T08:09:07+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

> Reply from NightHawkFur
>
> I'd love to provide the files, however for some reason when I try to rip the .ssh texture files using the program "finalbig", They end up being around 500MB to 1Gb.
In total around 60Gb. Now that can't be real. (If it is, tell me where I would upload 60gigs...) Also, when I try to open these huge .ssh files in eagt, the program crashes.

Now, when I try to extract the .big archive using EAGT instead of finalbig, I end up with an empty file with the extension ".lst"

You could try to use QuickBMS to extract the files instead. Try both the big4 script and the EB script.
Big4: [https://aluigi.altervista.org/bms/ea_big4.bms](https://aluigi.altervista.org/bms/ea_big4.bms)
EB: [https://aluigi.altervista.org/bms/fightnight.bms](https://aluigi.altervista.org/bms/fightnight.bms)

QuickBMS download: [https://aluigi.altervista.org/papers/quickbms.zip](https://aluigi.altervista.org/papers/quickbms.zip)
## Post #61
- Username: NightHawkFur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 10, 2019 1:05 am
- Post datetime: 2019-01-31T11:41:02+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Big4 Script:
- signature of 3 bytes at offset 0x0000000000000000 doesn't match the one
  expected by the script:

  this one: "'"
  c0 fb 27                                          ..'

  expected: "BIG"
  42 49 47                                          BIG

- 0 files found in 0 seconds
  coverage file 0     0%   3          5247378    . offset 0000000000000003


EB Script:
Error: the uncompressed data (-1) is bigger than the allocated buffer (2594305)

Last script line before the error or that produced the error:
  227 clog NAME OFFSET ZSIZE SIZE
## Post #62
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-31T12:10:26+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

> Reply from NightHawkFur
>
> Big4 Script:
- signature of 3 bytes at offset 0x0000000000000000 doesn't match the one
  expected by the script:

  this one: "'"
  c0 fb 27                                          ..'

  expected: "BIG"
  42 49 47                                          BIG

- 0 files found in 0 seconds
  coverage file 0     0%   3          5247378    . offset 0000000000000003


EB Script:
Error: the uncompressed data (-1) is bigger than the allocated buffer (2594305)

Last script line before the error or that produced the error:
  227 clog NAME OFFSET ZSIZE SIZE

from searching around a little, I can't seem to find any actual good tools that work for SSX. I think you'd have to go over to ZenHax forum and ask aluigi nicely if he could make a script for the SSX tricky .big file.
## Post #63
- Username: JovoHolmes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 10, 2020 10:23 pm
- Post datetime: 2020-07-12T01:38:46+00:00
- Post Title: Re: Def Jam Bitmap and .colours files

Did anyone manage to extract any models/textures from Fifa Street? I've been trying but not had much luck unfortunately.
