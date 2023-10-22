## Post #1
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-23T16:00:18+00:00
- Post Title: Help again! WWE WMXXI

Heres a file, all the others are too big. Its in WAD fomrat but not compatible with either extractor yet!

Heres the example file:

[http://lukereeve.co.uk/HD.wad](http://lukereeve.co.uk/HD.wad)
## Post #2
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-25T05:37:02+00:00
- Post Title: Help again! WWE WMXXI

I was just about 2 make this topic. I hope someone can get the .wad format 2 work cause wm21 has some sweet textures I could use for other wrestling games
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-25T11:51:28+00:00
- Post Title: Help again! WWE WMXXI

Thanks for the archive - we are downloading it now and will take a look at it soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-25T13:27:19+00:00
- Post Title: Help again! WWE WMXXI

Oh Hell yes! You guys rock!!
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T14:03:10+00:00
- Post Title: Help again! WWE WMXXI

I downloaded it and it does not seem to much of a problem, at first glance. WIll look into it.
## Post #6
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-25T15:03:23+00:00
- Post Title: Help again! WWE WMXXI

Sweet!

I cant wait you guys are simply amazing!
## Post #7
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-26T12:36:58+00:00
- Post Title: Help again! WWE WMXXI

looking forward to your findings guys
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-26T13:55:11+00:00
- Post Title: Help again! WWE WMXXI

This is it:

```
3-6 	32-bit		Unknown (01000000)
7-10	32-bit		Unknown (00000000)
11-14	32-bit		Number of files (N)

15-(15+N*12) All file entry-Offset info

This has the following (relative) format:

0-3	32-bit		Unknown
4-7	32-bit 		absolute offset of file entry
8-11	32-bit		Unknown (usually 0)

Each file entry has an info header and a data section. 

File Entry format:

0-1 	16-bit		Relative offset of (compressed) file data (ROCD)
2-5 	32-bit		Uncompressed Size of file
6-9	32-bit		Unknown
10	8-bit		The byte before the filename (0x01)
11-ROCD	String		Filename 
ROCD-??	DATA		Zlib Compressed file data. 


```


There's one problem. There's no (to my knowledge) a "Compressed Size" variable for easy extraction of the compressed data. 
Also, the file-entries are not in the same order as in the FIleentry-offset section, preventing easy calculation of compressed sizes. 

Well, it's possible though. Just load all entries, sort them (ascending) and then calculate the compressed sizes.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-26T14:21:13+00:00
- Post Title: Help again! WWE WMXXI

Oh wel, I could create a script anyhow. Zlib knows when to stop decompressing, so I just took the uncompressed size as a measure. May not work on all files, but most will probably. Use the Custom BMS option.  
Note: import does not work, even though MexCom might allow you to visit the Editor.

Also attached some examples. Jeez, never knew The Rock could take up such a gay position LOL.   

Anyway the script is below as a .BMS. 

```
IDString 0 WAD ;
Get DUM Long 0 ;
Get DUM Long 0 ;
Get FNUM Long 0 ;
For T = 1 To FNUM ;
Get DUM Long 0 ;
Get FEO Long 0 ;
Get DUM Long 0 ;
SavePos EO 0 ;
GoTo FEO 0 ;
Get JP Int 0 ;
SavePos SS 0 ;
Math SS += JP ;
Get UCS Long 0 ;
Get DUM Long 0 ;
Get B Byte 0 ;
SavePos S 0 ;
Math SS -= S ;
GetDString FN SS 0 ;
SavePos FO 0 ;
Set FSI Long UCS ;
CLog FN FO FSI 0 0 UCS 0 ;
GoTo EO 0 ;
Next T ;

```

[wad.zip](https://xentaxbackup.github.io/file/191_wad.zip)

[icon_cassuperstar.jpg](https://xentaxbackup.github.io/file/190_icon_cassuperstar.jpg)

[pose_rock copy.jpg](https://xentaxbackup.github.io/file/189_pose_rock copy.jpg)
## Post #10
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-26T15:46:42+00:00
- Post Title: Help again! WWE WMXXI

Wow thanks alot Im sure it will work great. But for some reason the MexBinderPlus App won't let me open the .mrf file so I can add the new wad.bms  It says run-time error 7. Maybe you could post your mrf file that has support for the new bms file you made or maybe you could suggest another fix. Thanks for all the hard work I really appreciate it. Ill keep messing around with it I can't wait 2 use it hehe
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-26T16:56:46+00:00
- Post Title: Help again! WWE WMXXI

The MRF is changed since the last version, the new Binder has not been released yet. Meanwhile, the Use Custom BMS in Tools is the way to go, I guess.
## Post #12
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-26T17:31:32+00:00
- Post Title: Help again! WWE WMXXI

I dont have that option!? please explain with more detail Im starting 2 think Im retarded lol
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-26T17:36:31+00:00
- Post Title: Help again! WWE WMXXI

Well, you DO..."Run custom script on..."   

See also info on that in Help.
## Post #14
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-26T18:38:50+00:00
- Post Title: Help again! WWE WMXXI

Works ok for me but I can only extract one thing at a time. Although is probably explained up if I remember correctly.

EDIT some don;t want to extract atall for me.
## Post #15
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-26T19:32:16+00:00
- Post Title: Help again! WWE WMXXI

...
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-26T21:44:40+00:00
- Post Title: 

> Reply from greendayduh
>
> Works ok for me but I can only extract one thing at a time. Although is probably explained up if I remember correctly.

EDIT some don;t want to extract atall for me.

Hmm, I can select and extract multiple files as normal. 

As for using older versions, themasterthree, you will understand that support for those is no longer available.
## Post #17
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-26T22:48:52+00:00
- Post Title: 

basiclly can't do ne thing with it till the new Mex Binder Plus is released or register the current version.....

wish I had the cash but don't
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-26T22:51:01+00:00
- Post Title: 

Well, ' cash ' is not the only way of support. There are various ways of supporting the MultiEx project.
## Post #19
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-27T01:55:38+00:00
- Post Title: 

Nevermind everything is working perfect I can extract everything just fine. Only thing now is the files I really need 2 view are in some extension called '.res' if anyone can tell me something that will let me view .res files I will worship you!!  

wait a second i just realized you guys are like really smart and could crack this format! At first I was thinking along the lines of a photoshop plugin or something. Since I noticed some games are in a .res format built into the app. Maybe you could also get the .res files inside the .wad file 2 work  

well if you are up 2 it some .res files are in the hd.wad file If I can get those wrestler textures out of the .res files a donation will be made!
## Post #20
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-27T03:34:24+00:00
- Post Title: 

well I noticed in the tdata folder of were other stuff is saved for the game that your Charactered wrestler has one of those files

soz I was thinking that this is the render of your caws face pic for the select screen so I think a photoshop plugin would be the way to go
## Post #21
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-04-27T03:35:03+00:00
- Post Title: 

damn wish I would have logged in...
## Post #22
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-27T05:56:30+00:00
- Post Title: 

I couldnt find such a photoshop plugin I guess Mr.Mouse is my only hope...
## Post #23
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-27T07:16:10+00:00
- Post Title: 

Mr Mouse and Watto are for extracting game archives so I doubt they have time to look into plugins for pictures.
## Post #24
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-04-27T08:01:00+00:00
- Post Title: 

hey can someone help me when i left click on something it brings up this mesage on a tga file and when i click extract it brings it up too on the TGa and dosent extract themaster tried helping
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-27T08:02:50+00:00
- Post Title: 

Well, I did warn you guys that some files wouldn't work. (see above).
## Post #26
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-04-27T08:04:09+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Well, I did warn you guys that some files wouldn't work. (see above).

can you help please
## Post #27
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-27T08:09:12+00:00
- Post Title: 

Sure. Go to Options and UNCHECK "Check file info ascending"
## Post #28
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-04-27T08:11:55+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Sure. Go to Options and UNCHECK "Check file info ascending"

thanks dude worked a million
## Post #29
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-27T10:44:39+00:00
- Post Title: 

So you can't do anything about the .res files? Atleast point me in the right direction if you know anything about it. The thing is the .res files extracts just fine but there is no way 2 view the insides of the res file so couldnt you make another bms plugin like you did for the .wad?

I need those textures   Thats it Im starting a petition about something!!
[JohnCena_DrOfThuganomics.zip](https://xentaxbackup.github.io/file/193_JohnCena_DrOfThuganomics.zip)
## Post #30
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-27T10:56:23+00:00
- Post Title: 

Well, it has a header of 22 bytes. But the data is in there in a raw format. I haven't figured out the data part yet, or how to extract the texture(s) from that.
## Post #31
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-27T11:01:42+00:00
- Post Title: 

You will figure it out keep @ it!

Mr.Mouse! Mr.Mouse! Mr.Mouse!

If you get the .res files extracted you can expect a $10 donation!
## Post #32
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-27T15:37:33+00:00
- Post Title: 

OK, so the status

1. The .res files are actually .xbx files, without the first part ot the header of an .xbx file. 

```
byte     Type (0 in this case)
32-bit    size of the xbx file 
32-bit   unknown (but 0x00000800 in this case, 2048)

```


2. The larger ones are actually archives (so it seems) of chunks of xbx data (without headers). So, they start with the second part of a normal .xbx file, and then comes the whole picture data. I could reconstruct part of one whole picture/mesh by creating smaller xbx files of max 128x16 and viewing them in XBX To Image Converter (google it): (perhaps another method can load such a picture as a whole, must know the format of the XBX files!). 



3. I read that .xbx files are deflated-compressed (Zlib) files.
## Post #33
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-27T20:32:06+00:00
- Post Title: 

Turns out the character model textures are not even .res files. Its in another fromat called .k I hope this is easier 2 get cracked open because these are the textures I really could use. I could still use the .res dont get me wrong but if you cant get the .res working take a look @ this new format. I provided 2 character models  in the rar.

[DOWNLOAD](http://s4.yousendit.com/d.aspx?id=3VNXFNU2TDJC93IPM7PA1UKWWI)
## Post #34
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-28T10:14:34+00:00
- Post Title: 

bump
## Post #35
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-28T10:17:36+00:00
- Post Title: 

Thanks, we'll take a look at those
## Post #36
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-28T10:45:22+00:00
- Post Title: 

awesome! 

Some more smaller .k files...
[.K Files.rar](https://xentaxbackup.github.io/file/198_.K Files.rar)
## Post #37
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-29T10:36:32+00:00
- Post Title: 

The .k files have the same type of images in there as the .res files. Thus, .xbx like images, this time only without the "XPR0" id string. The original textures are .tga , as original filenames are also saved in the .k files. 

The guys that created Image To XBX Converter obviously know what format this type of images are in. But there'no source code to be found anywhere. 

Perhaps people at [http://www.xbox-scene.com](http://www.xbox-scene.com) can help?
## Post #38
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-29T17:57:06+00:00
- Post Title: 

Ok Im sure someone over @ X-S will reveal the source. Maybe you could look @ the creator of the apps name and pm him on X-S forums?

Could you explain how you compiled that 1 texture though?
## Post #39
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-29T19:04:44+00:00
- Post Title: 

Okay, I'm making some progress. 

I now have found that the images in the .res and .xbx are actually .DDS files (without the DDS header and with their own header). 

The TitleImage.xbx stuff is in DXT1 format, but I think in the .res files they are in DXT5.
## Post #40
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-29T20:45:42+00:00
- Post Title: 

The .k files also contain DDS file data.  It's a bit of searching as for the width and heights, and the correct DXT format. You should get yourself a good DDSfile editor (or a plugin for Adobe Photoshop). 

Examples from the .res files:






The following came from the .K file Trunks_skintight_long_body.fat.k




Here's a modified neXgen logo in an .xbx file viewed in XBX Image Converter 3.0 (showing that it works, and the files are indeed modified DDS files). See the XNTX (XeNTaX) characters I put on top of it. 



When I used Photoshop to edit it I noticed the DDS plugin in saved it with loss of resolution, although XBX Image Converter did not care and loaded and showed it anyway. 

Perhaps a program such as BMP2XIP can help. The problem with XBX Image Converter is that it doesn't support big DDS files (.xbx files).
## Post #41
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-29T21:04:11+00:00
- Post Title: 

This is great I hope we can find out more!

But the 2 images you said that are from the .res files look like the tga files. Can you view the 2 player models I gave you yet? I dont understand how you viewing some of this. I have photoshop,dds plugin,xboximageconverter30, I want 2 see some of this stuff for myself but neither program will let me. How are you doing this? Great work you are the real master!

I never thought body fat would get me so excited lol
## Post #42
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-30T09:06:46+00:00
- Post Title: 

Ok, what I do is take the data part of the image and put a DDS file header in front of it. A DDS file (as many other files) has a header, which contains info about the image that a viewer should know, and a data part (the actual image data). 

Look at this .res file:


I have opened it in Hex Workshop. I have highlighted the header part (which is only about half of the header of a .xbx file). 

Now compare it with an actual .xbx file header (also highlighted) :


You can see where the similarity begins between the two. (Look at the part :

```
 0100  0400 
```


So this is when I thought they were actually .xbx files, without the first part of the header. 

Then I read something about DDS files and Xbox images. Look at this, from a DDS file (a DXT1 encoded DDS file).



The highlighted part is the DDS file header, followed by the actual image data. What I did was take such a header and let it be followed by image data from a .res or a .k file. Then I could open it in Photoshop and view it! 

Finally look at a .k file:



Once again, the highlighted part is part of the header we also see in .xbx fiels and .res files (notice the 
```
0100  0400 
```
 again).
You can also see that they saved the original file name (a .tga file). THe part that comes after the highlighted header is the image data. I also took that data and let it bepreceded by a DDS file header and could open it in Photoshop thereafter (as a DDS file). 

That's it.
## Post #43
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-30T16:48:06+00:00
- Post Title: 

Wow thank you so much M.m. Ill mess with this till I get it 2 work. So your saying I can view .k and .res files if I do all of that right? Will there be an sort of limitations and finnaly is this all you can do 2 get these files working or do you have a trick up your sleeve? If your done trying 2 "crack" what would I need 2 find out 2 get this project rolling?
## Post #44
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-30T17:17:49+00:00
- Post Title: 

Yes, and you should play with the "width" and "height" variables. These are in the DDS file at position (byte) 13. 

look at the DDS header above and notice the 
```
8000 0000 8000 0000
```


These are 0x80000000 (128) and 80000000 (128) in the example. But this will be known by the game and not saved in the .res or .k header, so you will have to experiment with these to find the correct width and heigth. You will notice that in Photoshop. 

I could of course, write a program that would merge DDS file headers with image data extracted by MultiEx Commander.
## Post #45
- Username: bdlou
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 01, 2005 1:21 am
- Post datetime: 2005-04-30T17:27:30+00:00
- Post Title: 

Sorry.  N00b question.  I need help getting started here.  I donated last night and got my key this morning.  If I understand correctly, is this the process I am supposed to use to attempt to open the DVD.WAD file?

1. Create a blank txt file.  Copy/Paste the data from Mr. Mouse:

```
IDString 0 WAD ; 
Get DUM Long 0 ; 
Get DUM Long 0 ; 
Get FNUM Long 0 ; 
For T = 1 To FNUM ; 
Get DUM Long 0 ; 
Get FEO Long 0 ; 
Get DUM Long 0 ; 
SavePos EO 0 ; 
GoTo FEO 0 ; 
Get JP Int 0 ; 
SavePos SS 0 ; 
Math SS += JP ; 
Get UCS Long 0 ; 
Get DUM Long 0 ; 
Get B Byte 0 ; 
SavePos S 0 ; 
Math SS -= S ; 
GetDString FN SS 0 ; 
SavePos FO 0 ; 
Set FSI Long UCS ; 
CLog FN FO FSI 0 0 UCS 0 ; 
GoTo EO 0 ; 
Next T ; 
```


2. Save the file as something.bms
3. In MultiEx Commander, go to Tools>Run custom script on
4. Select the BMS file you just created
5. Select the DVD.WAD file

When I follow this process, I get a Run-time error '7': Out of memory, so I feel that I am missing a step.  Any help would be greatly appreciated.
## Post #46
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-04-30T17:56:44+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> I could of course, write a program that would merge DDS file headers with image data extracted by MultiEx Commander.

Please do this anything that will make this process easier/quicker.

Sorry but I just cant figure out the basic steps your trying 2 tell me. When you get some free time can you do a little step by step tutorial for people like me that are not very smart with this kind of stuff.You dont have 2 use baby steps just make it a little more idiot friendly.  I couldn't really understand the process if you can try and make a for dummies version of what you said in your second 2 last post me and my friends would greatly appreciate it. Then we would be out of your way for good
## Post #47
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-30T18:21:22+00:00
- Post Title: 

> Reply from bdlou
>
> Sorry.  N00b question.  I need help getting started here.  I donated last night and got my key this morning.  If I understand correctly, is this the process I am supposed to use to attempt to open the DVD.WAD file?

1. Create a blank txt file.  Copy/Paste the data from Mr. Mouse:
Code: Select allComType ZLib1 ; 
IDString 0 WAD ; 
Get DUM Long 0 ; 
Get DUM Long 0 ; 
Get FNUM Long 0 ; 
For T = 1 To FNUM ; 
Get DUM Long 0 ; 
Get FEO Long 0 ; 
Get DUM Long 0 ; 
SavePos EO 0 ; 
GoTo FEO 0 ; 
Get JP Int 0 ; 
SavePos SS 0 ; 
Math SS += JP ; 
Get UCS Long 0 ; 
Get DUM Long 0 ; 
Get B Byte 0 ; 
SavePos S 0 ; 
Math SS -= S ; 
GetDString FN SS 0 ; 
SavePos FO 0 ; 
Set FSI Long UCS ; 
CLog FN FO FSI 0 0 UCS 0 ; 
GoTo EO 0 ; 
Next T ; 

2. Save the file as something.bms
3. In MultiEx Commander, go to Tools>Run custom script on
4. Select the BMS file you just created
5. Select the DVD.WAD file

When I follow this process, I get a Run-time error '7': Out of memory, so I feel that I am missing a step.  Any help would be greatly appreciated.

The steps are correct. Just make sure that when you copy/paste it from the board, you remove trailing spaces for each line. You should "ENTER" each line from the ';'. If you copy/paste it will add extra spaces.

And then the Scriptor fucks up.
## Post #48
- Username: bdlou
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 01, 2005 1:21 am
- Post datetime: 2005-04-30T18:31:23+00:00
- Post Title: 

Hmm...still getting the same error.  I even tried the one you uploaded (which I hadn't noticed before) and I am still receiving the same error.  Any other ideas?
## Post #49
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-30T21:14:39+00:00
- Post Title: 

Well, we should take this issue outside this thread, use the Troubleshooting forum instead.
## Post #50
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-30T21:21:41+00:00
- Post Title: 

> Reply from themasterthree
>
> Mr.Mouse wrote:I could of course, write a program that would merge DDS file headers with image data extracted by MultiEx Commander.

Please do this anything that will make this process easier/quicker.

Sorry but I just cant figure out the basic steps your trying 2 tell me. When you get some free time can you do a little step by step tutorial for people like me that are not very smart with this kind of stuff.You dont have 2 use baby steps just make it a little more idiot friendly.  I couldn't really understand the process if you can try and make a for dummies version of what you said in your second 2 last post me and my friends would greatly appreciate it. Then we would be out of your way for good

I will see what I can do. I have already spend considerable time on this.
## Post #51
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-05-01T07:05:57+00:00
- Post Title: 

yeah and Mr mouse we appreicate it!
## Post #52
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-01T15:04:16+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> themasterthree wrote:Mr.Mouse wrote:I could of course, write a program that would merge DDS file headers with image data extracted by MultiEx Commander.

Please do this anything that will make this process easier/quicker.

Sorry but I just cant figure out the basic steps your trying 2 tell me. When you get some free time can you do a little step by step tutorial for people like me that are not very smart with this kind of stuff.You dont have 2 use baby steps just make it a little more idiot friendly.  I couldn't really understand the process if you can try and make a for dummies version of what you said in your second 2 last post me and my friends would greatly appreciate it. Then we would be out of your way for good 

I will see what I can do. I have already spend considerable time on this.

Thanx alot! I hate bothering you like this but Im so desperate it seems like your the only guy that could ever make this possible (anytime soon atleast) Just a easy 2 understand guide and/or a app that makes the process easier and we wont use up anymore of your time. Your the best Mr. Mouse!
## Post #53
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-02T03:16:39+00:00
- Post Title: 

I tried
## Post #54
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-02T16:44:13+00:00
- Post Title: 

The developers left Goldberg's model and textures in the game. I figured out how to add him to the game as a CAS, as well as figure out some other save hacks. I have a video you might want to check out, and remember that I did ALL of it by hacking the game save, none of the actual game files were hacked. It requires resigning the save after hacking it though, and I won't be telling the resign info because you can give your CAS more than 10 in each category, and would let people cheat on XBL. I may however change people's saves for them for a small donation. BTW, notice that I also changed the selection icon for my CAS as well as the Goldberg CAS, as well as gave myself all 10 stats. Also, notice that my name is longer than 10 characters long, another benefit to being able to hack the game save. Ok, here is the link to my video that you will prolly want to check out. You will need the Xvid Codec to watch it too, and don't make fun of how poorly I was playing, the game was going at about 10 fps while I was capturing the video with the debug capture program and it was hard to time stuff. So, here's the link:

[http://tinyurl.com/79q24](http://tinyurl.com/79q24)

Enjoy, and feel free to leave any comments!!!
## Post #55
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-02T17:15:59+00:00
- Post Title: 

OR....WE would hack the save game, and post it here regardless of possible cheat breaches nonetheless.
## Post #56
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-02T17:16:22+00:00
- Post Title: 

Holy Crap I was just talking with Mr. Mouse about getting goldberg back into the game on msn. Please just pm the secret method your safe with me. I discovered the goldberg.k file weeks ago but I could never figure it out. I dont even have xbl please tell me
## Post #57
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-05-02T17:17:24+00:00
- Post Title: 

Brien you are the man!
## Post #58
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-02T17:20:24+00:00
- Post Title: 

> Reply from themasterthree
>
> Holy Crap I was just talking with Mr. Mouse about getting goldberg back into the game on msn. Please just pm the secret method your safe with me. I discovered the goldberg.k file weeks ago but I could never figure it out. I dont even have xbl please tell me

Hmm, that would not help out the "community" if only YOU could add him to the game ? What about the others then?
## Post #59
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-02T17:29:36+00:00
- Post Title: 

Im all 4 that but he doesn't want this 2 spread thats why I requested he only sends it 2 me. But yeah I dont see why you dont just make it public already nobody is going 2 give you donations.
## Post #60
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-02T17:36:46+00:00
- Post Title: 

Because the saves are resigned to your Xbox HD Key, so it will only work on my Xbox right now, unless I resign it to work on another.  I'm sorry, but if I reveal the resign info, then people can give their CAS ungodly high stats and cheat like hell on XBL.  Maybe I can work out a deal with Mr. Mouse and he can make a program that will automatically resign the saves for you, without revealing the resign info.  Can we work something out you think?
## Post #61
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-02T17:40:08+00:00
- Post Title: 

> Reply from brienj
>
> Because the saves are resigned to your Xbox HD Key, so it will only work on my Xbox right now, unless I resign it to work on another.  I'm sorry, but if I reveal the resign info, then people can give their CAS ungodly high stats and cheat like hell on XBL.  Maybe I can work out a deal with Mr. Mouse and he can make a program that will automatically resign the saves for you, without revealing the resign info.  Can we work something out you think?

That would be satisfactory    I don't actually play the game, but I can see what you mean.
## Post #62
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-02T23:24:07+00:00
- Post Title: 

Yeah, I made a CAS with the stats all at 20, but didn't try any higher, but I bet it can go pretty high and I'm sure people that play on XBL don't want to find out how high they can go.
## Post #63
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-03T06:06:16+00:00
- Post Title: 

Okay, well, let's work together on this one then, see if we can come up with a nice tool for the community.
## Post #64
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-03T17:23:52+00:00
- Post Title: 

So your saying you dont need a modded xbox, because Ive heard you cant get on live with a modded xbox.
## Post #65
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-03T17:41:32+00:00
- Post Title: 

> Reply from Anonymous
>
> So your saying you dont need a modded xbox, because Ive heard you cant get on live with a modded xbox.
No, but you have to be able to obtain your HD Key.  When I finally finish my program I'll be distributing it to everyone.
## Post #66
- Username: cfcrule
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 03, 2005 3:27 am
- Post datetime: 2005-05-03T21:09:27+00:00
- Post Title: 

Is it gonna be for people who donate to you though?.
## Post #67
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-03T22:23:29+00:00
- Post Title: 

> Reply from brienj
>
> Anonymous wrote:So your saying you dont need a modded xbox, because Ive heard you cant get on live with a modded xbox.
No, but you have to be able to obtain your HD Key.  When I finally finish my program I'll be distributing it to everyone.

Well, you do not want to work together then, you wish to get all the credit?
## Post #68
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-03T22:30:53+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> brienj wrote:Anonymous wrote:So your saying you dont need a modded xbox, because Ive heard you cant get on live with a modded xbox.
No, but you have to be able to obtain your HD Key.  When I finally finish my program I'll be distributing it to everyone.  

Well, you do not want to work together then, you wish to get all the credit?
Nothing against you, but there is some soure code that I have to keep a secret as well as the AuthKey a secret, but if I figure out a way to get around that, then you could help, especially by making a gui for it, because my app will more than likely be a command line tool.  

You could easily make the program to manipulate the files, and only need my program to resign it, but let me work it out some more, and I may have you help with that too, if you want.
## Post #69
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-03T22:34:29+00:00
- Post Title: 

I'll PM you about this.
## Post #70
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-03T23:15:31+00:00
- Post Title: 

Brienj how did you get your face in the game? You must know something about the .res format. I need 2 extract .res and .k files badly so I can use the  textures in other games (wwf no mercy) If you can be any help I would appreciate it.
## Post #71
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-04T02:26:39+00:00
- Post Title: 

Yes I finnaly got a texture out!! Only took me 100 tries but I got a wm21 texture out! Not 2 bad 4 someone with no knowledge of what they are doing. Ok now smart people figure out the .res and .k formats so I can get all the sweet textures out!!
## Post #72
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-04T06:58:40+00:00
- Post Title: 

Smart people have already figured out these formats.   

Was the Guide helpful ? Or did you do it along the lines I've shown above?
## Post #73
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-04T08:00:48+00:00
- Post Title: 

I know that the .res files, at least for the CAS icons, are 128 x 128 DXT4 images, but since the DDS plugin won't let you save a DXT4, you can save them as DXT5 after changing them, they will work in place of the DXT4 textures.  I haven't delved deeper into the actual textures on the body, but I ampretty sure they are more than likely the same format, but of a larger size, more like 256 x 256 or maybe 512 x 512 or something like that.  They could be DXT1, but I'm pretty sure that most hair texture is prolly DXT4, since it can have different degrees of Alpha transparency instead of a single bit Alpha, which is what the DXT1 textures have.

Of course you must take the game header off the file, if it has one, the save files do, then supply a good DDS header, edit the file, then take the header back off, and put the game header back on.  

The .res files the game uses do not have to be resigned, unless it's a CAS icon in the save folder, and I don't think they do have a header, so those should be easy to edit, as long as we can get an importer into the WAD files.  This would allow hacking of characters and other stuff in the actual game, but to actually add any new stuff to a CAS, you will still need to resign the files, which I will have a program soon that will do that.  

I haven't had a chance to totally figure out the .k file format, but hopefully Mr. Mouse already has.  I just haven't had the time to disect it yet, the other stuff I've done is easy compared to that.  I was one of the big pioneers in hacking WWE Raw for PC, and figured alot of file formats out for that game, so I could easily do it for this game if I take the time.  My only problem was the WAD files, because I am not good with compressed formats.  Once I found out that this program could extract them, I was happy, but sad that we can't import, at least yet.  

If you haven't seen my ultra new movie, go to the forum at Xbox Saves or GameFAQs and look for the new links.
## Post #74
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-04T08:25:51+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Smart people have already figured out these formats.   

Was the Guide helpful ? Or did you do it along the lines I've shown above?

Yeah thats why I did what Ive been asking you 2 do for the last week in about 1 hour. You didnt have 2 make it sound all technical either it was pretty simple. But its pretty much random which texture come out perfect. Its like a 1 in 25 chance.

Sounds good brienj hope you can make importing possible as well as getting textures out more easily.
## Post #75
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-04T08:43:45+00:00
- Post Title: 

OMG I can now get every texture!
## Post #76
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-04T09:01:55+00:00
- Post Title: 

> Reply from themasterthree
>
> Yeah thats why I did what Ive been asking you 2 do for the last week in about 1 hour. You didnt have 2 make it sound all technical either it was pretty simple. But its pretty much random which texture come out perfect. Its like a 1 in 25 chance.

Sounds good brienj hope you can make importing possible as well as getting textures out more easily.

1. It IS technical, you should know what you are doing
2. You make it sound like you've been asking me to do something, and I didn't comply. I was busy focusing on what the actual DDS format of the damn files were, as you tried to import an altered icon file (that will show up any face in the select screen) and it failed. That put me off track, as that might mean there's more to it that what I thought. Thus, the puzzle was the DDS files, not extracting textures. That's not my job. I don't need to mod the game, I just need to create a tool or update for MultiEx Commander to make it possible for other people to do whatever they think they need to do. I'm not here to grant every wish people have. Some people seem to forget that I'm doing this in my spare time, whenever *I* feel like it. 

Seems Brien has done the same I did though, so that approach should have worked. As for it being easy, yes it is easy. And I explained it previously.
## Post #77
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-04T13:39:25+00:00
- Post Title: 

> Reply from themasterthree
>
> 
Yeah thats why I did what Ive been asking you 2 do for the last week in about 1 hour. You didnt have 2 make it sound all technical either it was pretty simple. But its pretty much random which texture come out perfect. Its like a 1 in 25 chance.

Sounds good brienj hope you can make importing possible as well as getting textures out more easily.
I won't be making an importer, I don't know much about compression formats, as I stated before.  I am hoping that Mr. Mouse will be able to work on that, and you should be a little nicer to him, because he could say, screw you guys, and then it would be a lot longer to be able to import anything.

Figuring out file formats is a lot more technical than you think, just because you can extract a texture 1 in 25 times proves that point.  Also, wouldn't you rather be able to extract them 1 in 1 times, it seems you like to gamble a lot.

The reason you are having a low success rate is because each one of the textures for the .k model files is more than likely each a different size, especially the one for the head, which is prolly the biggest one.  Also, I know by quickly looking at the data, that the beginning of the model file has the textures, several of them, then near the end it has the actual 3d model structure of the file.  Just be patient and either have fun playing the game until somebody makes it easy for you to do it, or don't bitch about not be able to figure it out.
## Post #78
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-04T14:54:22+00:00
- Post Title: 

Well, anyway. I have done enough to support modding on this game I think. 

I'll try to post some specifications of the .k and .res files in the future, although I don't think it will be a problem for Brien or anyone else to figure it out. 

This project is too time consuming. And I don't have so much free time. I hope that enough info is available now.  

Good luck! Topic closed.
## Post #79
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-04T17:16:47+00:00
- Post Title: 

Okay well, it's open for anyone who has ideas to help out others. Consider me not actively busy with this subject, until further notice.
## Post #80
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-04T18:00:37+00:00
- Post Title: 

Well thanks for re-opening this thread, I thought I was going to have to hurt themasterthree for making you close it.  

I only wish we could eventually import stuff into the WAD files, it would allow people with a modded Xbox to do some really crazy shit to the game.  I'm happy though that at least I was able to extract the stuff that i did with your program, so thanks for at least supporting the game as far as that goes.  If I finally figure out the file formats, I'll gladly share the info with you, if you want to add them to your program.  I really want to show my appreciation for what you have done, because I know what it feels like to have people that you don't owe anything to, begging that you tell them everything, and begging that you do it for them right now.

I would love if you did some more work on the game, and you would have at least one person be thankful for it.
## Post #81
- Username: cfcrule
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 03, 2005 3:27 am
- Post datetime: 2005-05-04T18:07:12+00:00
- Post Title: 

Thanks for all your work Mr.Mouse

I know i'm not actually helping brienj with the programs but thanks for your help.


Brienj you said that goldberg had his model and textures does that mean the textures are seperate because i've just seen rikishis model is in there as well.
## Post #82
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-04T19:10:43+00:00
- Post Title: 

Brienj you got the wrong idea about everything me and mouse are cool we talk on msn sometimes I was being sarcastic. I figured out how 2 extract everytype of texture now maybe you should look back a page. Also I could care less about importing into this shitty game I just wanted 2 extract the textures so I can make texture mods for WWF No Mercy the greatest wrestling game ever made. Also Im pretty sure you wouldnt of even know about goldberg being in the game if I didnt inform everyone on gamefaqs about it over a week ago! Dont tell me lies cause I know for a fact you just heard about accessing the .wad files a couple days ago. So you should be giving me some credit Im the first 1 from the public 2 discover the goldberg.k file.

btw I will eventually figure out the resign info then I will tell everyone how they can cheat on live just 2 piss you off.
## Post #83
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-04T19:43:15+00:00
- Post Title: 

Okay, well, let's all just relax now. And work on the problems at hand. Without pissing the others off bit, okay?  

After all, I am also one of the mods here.
## Post #84
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-04T20:08:01+00:00
- Post Title: 

I've been following your progress here for the past few days and I want to say thank you to Mr Mouse and anyone who helped getting it as far is got until now.

It would be awesome if someday we'd be able to make updates to the game like it happend for WWE RAW on the PC.
## Post #85
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-05-04T21:13:59+00:00
- Post Title: 

There is a game extractor plugin that allows import functions. But no use for it as of yet and yeah thanks Mr Mouse and brienj. Nice to see brien helping me again!
## Post #86
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-05-05T14:04:14+00:00
- Post Title: 

> Reply from themasterthree
>
> btw I will eventually figure out the resign info then I will tell everyone how they can cheat on live just 2 piss you off.
Don't act like a dickhead or I will ban you.
## Post #87
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-05T15:10:57+00:00
- Post Title: 

Its weird. The DDS plugin for Photoschop can open a DXT4 file, but won't save it as a DXT4. Only options are DXT1, 3 and 5 and a bunch of others, but no DXT2 or DXT5.
## Post #88
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-05T15:46:51+00:00
- Post Title: 

Maybe they are secretly trying to steer people away from using the version 2 and 4 of DXT - forcing them to use the more common formats?

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #89
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-05T16:02:34+00:00
- Post Title: 

i found that:

> In case you're wondering, DXT2 and DXT4 assume colors are premultiplied by the alpha channel, and are not supported.

Its no help though
## Post #90
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-05T16:05:09+00:00
- Post Title: 

I have reason to believe the textures are in DXT5 format, not DXT4.

Brien, how did you come to the conclusion they are in DXT4 format? Am I missing something?
## Post #91
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-05T17:11:25+00:00
- Post Title: 

There is an update on the CAS icons.  If you have the patched version of the game, they are DXT1 1bit Alpha instead of DXT4.  They are still 128x128, but the filesize is half the size, because of the format.

> Reply from Mr.Mouse
>
> Brien, how did you come to the conclusion they are in DXT4 format? Am I missing something?
Every DDS file in every game for the Xbox has always been in DXT4 format, excepting of course, the ones that are DXT1 or DXT2.  I guess it is possible that they are really DXT5, but I really doubt it.  I've never seen a DXT5 texture file ever used in an Xbox game, and I believe it has something to do with programming on the Xbox.  In fact, there are some games, that if you don't give the texture a DXT4 header, it will say the file is damaged.  Also Tao Feng, the other game made by Studio Gigante, used DXT4 and DXT1 textures.  I can't prove 100% that they are DXT4 textures, but it really doesn't matter, because if you replace them with DXT5 textures they will work just fine, unlike some other Xbox games.
## Post #92
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-05T18:18:47+00:00
- Post Title: 

Okay...interesting. That part about the DXT1 I had figured out as well, for the icons. (And the .xbx files). 

But how do you go about editing the images then? Is it feasible to load them in Photoshop, save them as DX5 and replace the header with a DXT4 header?

I tried to edit the icon__.res file in a CAS (I got that from themasterthree), but it didn't work for some reason (here's a [link](http://www.xentax.com/taoc/pics/icon__.res)). Also, the .res/.k images don't actually have DDS headers, just the data. They do however have their own header, which resembles .xbx headers. Do you know the format of these .xbx headers?

Here's an example of one (the highlighted part):



The res/k files have part of this header before the image data comes, in the above example this part: 

```
 0008 0000 0100 0400 0000 0000 0000 0000 290C 6106 0000 0000
```


What do these values mean?
## Post #93
- Username: gameboy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 29, 2005 10:19 am
- Post datetime: 2005-05-06T02:59:16+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Okay...interesting. That part about the DXT1 I had figured out as well, for the icons. (And the .xbx files). 

But how do you go about editing the images then? Is it feasible to load them in Photoshop, save them as DX5 and replace the header with a DXT4 header?

I tried to edit the icon__.res file in a CAS (I got that from themasterthree), but it didn't work for some reason (here's a link). Also, the .res/.k images don't actually have DDS headers, just the data. They do however have their own header, which resembles .xbx headers. Do you know the format of these .xbx headers?

Here's an example of one (the highlighted part):



The res/k files have part of this header before the image data comes, in the above example this part: 
Code: Select all 0008 0000 0100 0400 0000 0000 0000 0000 290C 6106 0000 0000

What do these values mean?

You can extract the files with the xbx headers by renaming them to .xpr and extract them using xprextract, you might be able to add .xbx and use one of the many xbx tools. The ones without the header you could probably add the xbx/xpr header and extract it with xprextract.
## Post #94
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-06T06:28:05+00:00
- Post Title: 

I can extract the files myself, that's not the issue. 

My question is about the nature of the values in part of the the header that is equal to a part of the header of .xbx/.xpr files.   

Besides, as I said above the .k/.res files don't have a complete .xbx header, so what you're suggesting would not work anyway, I doubt xprextract would be so smart to guess half of the header itself.
## Post #95
- Username: gameboy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 29, 2005 10:19 am
- Post datetime: 2005-05-06T07:58:18+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> I can extract the files myself, that's not the issue. 

My question is about the nature of the values in part of the the header that is equal to a part of the header of .xbx/.xpr files.   

Besides, as I said above the .k/.res files don't have a complete .xbx header, so what you're suggesting would not work anyway, I doubt xprextract would be so smart to guess half of the header itself.

No it will not guess half of the header but if i add the first half of the header it will extract the dds file. I just now read through all the pages so I understand now and here is xprextract with the source maybe it will help.
[xprextract3.zip](https://xentaxbackup.github.io/file/212_xprextract3.zip)
## Post #96
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-06T13:07:03+00:00
- Post Title: 

Thanks! Will certainly take a look at it.
## Post #97
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-06T14:31:56+00:00
- Post Title: 

Okay good, so :

.XBX header :

```
string		Magic Value (XPR0 XPR1 etc)
uint32		Image data size
uint32 		Headersize (total)
uint32		Image type (see below)
uint32		Unknown
uint32		Unknown
uint32		Texture format (dimensions etc)
uint32		Unknown

[IMAGE DATA]
Data

There are image types:

0x80000000	D3DCOMMON_TYPE_VERTEXBUFFER 
0x00040001	D3DCOMMON_TYPE_TEXTURE
0x00800001	D3DCOMMON_TYPE_INDEXBUFFER

```


Check out Goldbergs textures. And yes, it's DXT4.
[test0.jpg](https://xentaxbackup.github.io/file/213_test0.jpg)
## Post #98
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-06T15:05:49+00:00
- Post Title: 

Great Job Mr Mouse!

But how do you do the conversion now, i'm not really experienced in this yet, so could u make a small guide when u have the time?   

Keep up the good work!
## Post #99
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-05-06T15:53:45+00:00
- Post Title: 

Not sure if any1 cares but the member XTC is telling people he is the one that worked out the Image compression/format headers.
## Post #100
- Username: XTC!
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-06T17:41:37+00:00
- Post Title: 

> Reply from greendayduh
>
> Not sure if any1 cares but the member XTC is telling people he is the one that worked out the Image compression/format headers.
no i aint am just saying that people can do it and i can show them
## Post #101
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-06T18:18:56+00:00
- Post Title: 

To all: look, this is not an Xbox forum, nor is it dedicated to Wrestlegames or whatever. 

Please, we ask you nicely, don't drag us (XeNTaX) into your specific discussions and debate. 

Many people could have figured out what was figured out here, look at Brienj, he also did. It's nothing special if you know what you are doing. 

It's here that I explained how I extracted textures to themasterthree, for those who need to know how to extract textures:

[viewtopic.php?p=8008#8008](http://forum.xentax.com/viewtopic.php?p=8008#8008)

As I said there, it's simple. 

Now let's close this debate. We wish to keep this forum clean. If it looks like a discussion on another forum spills over to this one, Captain and I will have to start modding the forum, which we usually never have to. 

So, keep it clean, folks.
## Post #102
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-05-07T08:32:24+00:00
- Post Title: 

Sorry just wanted to inform if any1 cared. But real nice work, I still don't understand how to open the files . But I'm interested where this goes.
## Post #103
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-07T09:09:05+00:00
- Post Title: 

> Reply from TheKidRocker
>
> Great Job Mr Mouse!

But how do you do the conversion now, i'm not really experienced in this yet, so could u make a small guide when u have the time?   

Keep up the good work!

I did it as Gameboy suggested, by creating a full XPR0 header and renaming the file to .XPR. Then XPREXTRACT did all the work. I have browsed through the source code of that program, and could easily identify what each value represents.
## Post #104
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-07T14:39:14+00:00
- Post Title: 

I have a new video:

[Lita Video](http://tinyurl.com/apo6f)

So I'm slowly getting the details of the .k files worked out, and when I am finished, I can share it with Mr. Mouse, although it looks like he may have already figured it out with the xprextract source code.  My only problem is getting the model files out, I can only get the textures.  Once that is done, CAS will be busted WIDE open.  BTW, I am 99% sure the models are .x files, my problem is supplying a good header to them and finding an application that will handle multiple meshes.
## Post #105
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-07T16:26:24+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> I did it as Gameboy suggested, by creating a full XPR0 header and renaming the file to .XPR. Then XPREXTRACT did all the work. I have browsed through the source code of that program, and could easily identify what each value represents.

Okay let me show you my try 

I took this file and opened in Hex Workshop[Civic Center Color.res](http://home.arcor.de/webspaceforme/stuff/wm21/Civic%20Center%20Color.res)

Here is what it showed:


Then I checked an XPR File and changed the Header to this:


Now I uses xprextract and got 2 files out of it, one that is totally blank and the other looks like that:


Did i do anything wrong?
## Post #106
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-07T18:17:51+00:00
- Post Title: 

Yeah, you don't have to give .res files a XPR header, just a DDS file header, but it must be the right size and type.
## Post #107
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-07T19:08:58+00:00
- Post Title: 

> Reply from brienj
>
> Yeah, you don't have to give .res files a XPR header, just a DDS file header, but it must be the right size and type.

Yeah i tried this before aswell and got other quite similar results
What do you mean by size? And the type you mean is probably DXT1 & DXT4, etc.
How do i find out? trial and error i guess   

Could u please give an example for the file I uploaded?

Thanks for ur help
## Post #108
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-07T19:41:54+00:00
- Post Title: 

First, remove the first 20 bytes, so it is 40000h bytes long, and this is the size of a 512x512 DXT4 dds file, but since you can't save as a DXT4 in Photoshop anyway, just give it a DXT5 header, which is:

```
0002 0000 0000 0400 0000 0000 0000 0000
0000 0000 0000 0000 0000 0000 0000 0000
0000 0000 0000 0000 0000 0000 0000 0000
0000 0000 0000 0000 0000 0000 2000 0000
0400 0000 4458 5435 0002 0000 0000 0000
0000 0000 0000 0000 0000 0000 0010 0000
0000 0000 4444 5358 FFFF FFFF FFFF FFFF
```

Then save it as a .dds file, and open it up in Photoshop and edit it if you like, then save it as a DXT5 w/no mipmaps, remove the 80h byte dds header, replace the header you removed in the first step, and then it will work in the game.

This is what the image looks like when converted to a DXT5 file correctly:
## Post #109
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-07T21:03:14+00:00
- Post Title: 

Okay, i got a step further now   
I deleted the first 20 bytes of the file and put ur code for the DXT5 Header in and what i got is this:

 

You sure that paintshop can open it correctly with the DXT5 header when its a DXT4 File?
## Post #110
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-07T21:26:10+00:00
- Post Title: 

Well, you can still try the other method, and let xprextract do it for you. What you forgot (or I think did not know) is that you have to have the correct size of the image data in the XPR header. 

So in your original you left the value 4096 there (0010 0000, see the highlighted part):


But your image data is larger: 262144 ! (or 0x40000 in hexadecimals). 

So replacing the 0010 0000 with 0000 0400 will work. 

This learns that the file is not DXT4, or DXT5, but DXT1. 
It's 1024*512. 



[Here are the xbx and DDS files](http://www.xentax.com/taoc/pics/examples.zip).
## Post #111
- Username: STG
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 08, 2005 5:07 am
- Post datetime: 2005-05-07T21:28:04+00:00
- Post Title: 

He said photoshop didn't he? Not sure if there would be any difference between Photoshop and Paintshop pro but maybe.
## Post #112
- Username: cfcrule
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 03, 2005 3:27 am
- Post datetime: 2005-05-07T21:45:03+00:00
- Post Title: 

[quote]First, remove the first 20 bytes[/quote]


I know i sound like a noob but how much of it is 20 bytes is 4 numbers the byte. Sorry
## Post #113
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-07T21:55:32+00:00
- Post Title: 

> Reply from cfcrule
>
> First, remove the first 20 bytes

I know i sound like a noob but how much of it is 20 bytes is 4 numbers the byte. Sorry

Every 2 Characters are 1 byte


Thanks for Mr Mouse for trying to help!
Your example files work fine for me.

But still couldnt do it myself, i changed the 0010 0000 to 0000 0400 and still get the same result as my first, but i noticed that the rest of your code there looks different too
## Post #114
- Username: cfcrule
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 03, 2005 3:27 am
- Post datetime: 2005-05-07T21:57:46+00:00
- Post Title: 

Thanks TheKidRocker.
## Post #115
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-07T21:59:18+00:00
- Post Title: 

> Reply from TheKidRocker
>
> cfcrule wrote:First, remove the first 20 bytes

I know i sound like a noob but how much of it is 20 bytes is 4 numbers the byte. Sorry

Every 2 Characters are 1 byte


Thanks for Mr Mouse for trying to help!
Your example files work fine for me.

But still couldnt do it myself, i changed the 0010 0000 to 0000 0400 and still get the same result as my first, but i noticed that the rest of your code there looks different too

Ah I see you have actually TWICE the header info in there. 
Notice how the 0100 0400 comes twice. I guess you inserted it instead of replacing the old?
## Post #116
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-07T22:00:17+00:00
- Post Title: 

Okay, here's what I got so far for the .k files, educated guesses:

```
string		Magic Value ('MF10')
uint32		Size of XBXX part 
string		Magic Value ('XBXX')
uint32		Unknown 
uint32		K file type (have seen 0 and 1)
ubyte		Unknown
uint32		type 0 k file: Offset of model/mesh data
		type 1 k file: number of files (excluding the model at the back)
uint32		type 0 k file: number of files (excluding the model at the back)
		type 1 k file: size of filename string (first entry already starts)

[FILE ENTRY]
uint32		Size of filename string
string		Filename (Original), null-terminated
uint32		Size of file (including header and image data in case of textures)
data		File data

In case of textures:

[TEXTURE]
uint32		Unknown 
uint32		Part of DDS file header (starting from 0x00040001 D3DCOMMON_TYPE_TEXTURE)
data		DDS image data

[At offset of model/mesh data]
uint32		Size of model file
data		Model file

[End-0x4d]
At the end of a k file that includes these model files is a tail.
0x4d in length, it probably also containing some Mesh vars. 

```
## Post #117
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-07T22:03:29+00:00
- Post Title: 

Hey! Thats it! 
Thanks a lot! 
Must have messed something up 
The double header explains why i always got two files out of it with one being empty 

Now i have the same result you got! 
Thanks so much!  

But are you sure about the  1024*512 ?
I think the images dont look right like that
## Post #118
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-08T11:14:06+00:00
- Post Title: 

Well, that one image of the Hall looks okay, nice perspective. It doesn't mean ALL have those dimensions. This is what xprextract made of it, and I think the program knows what to do.
## Post #119
- Username: themasterthree
- Rank: Banned
- Number of posts: 28
- Joined date: Wed Apr 20, 2005 3:55 pm
- Post datetime: 2005-05-10T12:46:02+00:00
- Post Title: 

So what I do is insert dds headers into the wm21 files and this makes it so I can view the images in Photoshop. Only thing I wanted 2 know was what header did you use for that .k goldberg? Also maybe brienj can answer this question does anyone know where the wm21 attires are located? Im guessing in the .k files but from that goldberg shot MM posted it seems its only the heads. Well if you would be kind of enough 2 help me with this 1 last thing.
## Post #120
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-10T13:22:04+00:00
- Post Title: 

> Reply from themasterthree
>
> So what I do is insert dds headers into the wm21 files and this makes it so I can view the images in Photoshop. Only thing I wanted 2 know was what header did you use for that .k goldberg? Also maybe brienj can answer this question does anyone know where the wm21 attires are located? Im guessing in the .k files but from that goldberg shot MM posted it seems its only the heads. Well if you would be kind of enough 2 help me with this 1 last thing.

As far as i understood things, the textures for the wrestlers and packed into the .k files so you have to extract them out there first
## Post #121
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-10T13:49:19+00:00
- Post Title: 

Themasterthree was banned. 

Reasons: 

- He was stealing wind from other people, not in the least from XeNTaX. 
- He was being a dickhead at these forums. 

Post from him at thenormercyforums. Here it started. Thinks he's cool:

[http://thenomercyzone.clicdev.com/f/ind ... topic=2715](http://thenomercyzone.clicdev.com/f/index.php?showtopic=2715)

> Reply from themasterthree
>
> Thanks 2 me and some other guy that requested the format for the MultiExCommander you can now extract textures from the brand new wm21 game! Im having trouble getting the plugin installed since Im

We were helping him out, by explaining how to rip textures from his files. 
It wasn't fast enough and he succeeded finally, after repeated explanation via MSN. Then he came with this post here:

> Reply from themasterthree
>
> Yeah thats why I did what Ive been asking you 2 do for the last week in about 1 hour. You didnt have 2 make it sound all technical either it was pretty simple. But its pretty much random which texture come out perfect. Its like a 1 in 25 chance.

Which was stupid. Brien J corrected his behaviour and themasterthree responded agressively. Also starting to claim HE figured the stuff out i had actually explained to him. 

> Reply from themasterthree
>
> Brienj you got the wrong idea about everything me and mouse are cool we talk on msn sometimes I was being sarcastic. I figured out how 2 extract everytype of texture now maybe you should look back a page. Also I could care less about importing into this shitty game I just wanted 2 extract the textures so I can make texture mods for WWF No Mercy the greatest wrestling game ever made. Also Im pretty sure you wouldnt of even know about goldberg being in the game if I didnt inform everyone on gamefaqs about it over a week ago! Dont tell me lies cause I know for a fact you just heard about accessing the .wad files a couple days ago. So you should be giving me some credit Im the first 1 from the public 2 discover the goldberg.k file.

btw I will eventually figure out the resign info then I will tell everyone how they can cheat on live just 2 piss you off.

Then he starts a post at The No Mercy forums, showing ripped textures and that he did it all by himself, when someone asked how he did it. 

[http://thenomercyzone.clicdev.com/f/ind ... =2856&st=0](http://thenomercyzone.clicdev.com/f/index.php?showtopic=2856&st=0)

> Reply from themasterthree
>
> Im not telling anyone my texture secrets since nobody helped me figure it out. Ill post some more textures soon also I will make some complete wrestlers sometime this week.

XTC pointed it out to him:

> Reply from XTC
>
> 
master how dare you say nobody helped you get them dam textures if it wasnt for me you wouldnt have gotten the help from mike ( Mouse who hacked it ) so dont say that i didnt help you

Yet, he refused to acknowledge any help from the outside:

> Reply from themasterthree
>
> If it wasnt for me you wouldnt even know who Mr Mouse is! Besides Mr.Mouse didnt help me with shit as far as extracting the textures go. He made it possible 2 extract the .wad files which has been possible for weeks now.

Then he comes back here, even after I have posted the whole story over there, for anyone to read. And he dares ask for more help. 

Captain and I decided a ban was the only reasonable thing to do.
## Post #122
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-10T15:48:50+00:00
- Post Title: 

I totally agree with you Mr.Mouse
I hate it when guys dont give credit to the people that deserve it
## Post #123
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-10T17:44:13+00:00
- Post Title: 

> Reply from TheKidRocker
>
> I totally agree with you Mr.Mouse
It's hate it when guys dont give credit to the people that deserve it

Thanks! Also for your support of the project!  Nice pictures by the way on the Lane site ! I play drums in a band myself  In the past I composed music for the Commodore 64
## Post #124
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-10T20:32:18+00:00
- Post Title: 

Hmm, no wonder he is apologizing to me on the GameFAQs board.  I just hope you don't think I am being a dick, because of holding out on the resigning stuff.  I've explained my reasons why, and when I do finish the program that will resign the stuff to be used in the save file, I will be putting your name in the thanks section of my readme file.  When I finish a working copy, if you want to beta test it, or some people from the forum here want to beta test it, let me know, and you can even host it too, if you'd like.  Having extra mirrors wouldn't hurt.  

Well, thanks for all you've done so far, and I'd just like to add that I successfully de-pantsed Lita, but she still has a bra, the texture for the top isn't as easy to modify, and I can post a link to a screenshot if it's allowed here.  

So I guess I am the first to make a nude character in this game, like I was the first to do it in Outlaw Volleyball.  Go me!!!
## Post #125
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-10T20:45:02+00:00
- Post Title: 

Yeah, great Job brienj!   

I'd love to betatest your proggy, so you choose me to, that would be cool
If not, that would be cool too, you dont owe me anything  

Keep up the good work

@MrMouse
Sure thing, good projects need to be supported and this is sure one of them
## Post #126
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-05-10T21:19:30+00:00
- Post Title: 

Hey dudes Im new to this whole mod thing. Can someone tell me how this works? I read some post over at gamefaqs that you can get goldberg or something I was wondering how you can get him??

~Thanks Dudes!
## Post #127
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-10T21:50:27+00:00
- Post Title: 

> Reply from brienj
>
> Hmm, no wonder he is apologizing to me on the GameFAQs board.  I just hope you don't think I am being a dick, because of holding out on the resigning stuff.  I've explained my reasons why, and when I do finish the program that will resign the stuff to be used in the save file, I will be putting your name in the thanks section of my readme file.  When I finish a working copy, if you want to beta test it, or some people from the forum here want to beta test it, let me know, and you can even host it too, if you'd like.  Having extra mirrors wouldn't hurt.  

Well, thanks for all you've done so far, and I'd just like to add that I successfully de-pantsed Lita, but she still has a bra, the texture for the top isn't as easy to modify, and I can post a link to a screenshot if it's allowed here.  

So I guess I am the first to make a nude character in this game, like I was the first to do it in Outlaw Volleyball.  Go me!!!

Thanks! I have no reason to think you're a dick, you haven't given me any.  

I'd love to beta-test it, but I don't have an XBox or the game. Other people can sign up here if they want, TheKidRocker already did! 

But hosting is no problem! I'll even advertise it if we do. We just keep the right to remove it should we get into bandwidth trouble, but then it would have to be *enormously* popular though. So, go go go!  

Also, post the screenshot, I'm sure there are fans that would like to see your progress and we're not that prudent.
## Post #128
- Username: cfcrule
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 03, 2005 3:27 am
- Post datetime: 2005-05-10T23:26:49+00:00
- Post Title: 

I can test the beta also, but are you using the old version or the new one out now, I've still got the old one because it works fine with the patch.

> I successfully de-pantsed Lita, but she still has a bra, the texture for the top isn't as easy to modify, and I can post a link to a screenshot if it's allowed here

You'll have kane after you now
## Post #129
- Username: gameboy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 29, 2005 10:19 am
- Post datetime: 2005-05-11T01:44:29+00:00
- Post Title: 

If I remove the checks from the xbe to allow modified saves would someone post the files needed to use a real wrestler for a CAS?
## Post #130
- Username: THE GAME
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 09, 2005 4:36 am
- Post datetime: 2005-05-12T14:40:25+00:00
- Post Title: 

> Reply from brienj
>
> if you want to beta test it, or some people from the forum here want to beta test it, let me know

hi

i see your progress in every forum i go and its realy great t see you finaly going to start the betatesting

i hope i be one of your betatester and i well be thankfull
if you chose not to take me i well stay thank full for at least helping usto have goldberg and i realy admier your reason and i find it fear that you think taht way
you know this kind of behave taht make the world beter plaese to live

thanks mr.brien for ever thing you did for us



ps:
i am realy sorry for my poor english "that why i only read  and didn't write before"
## Post #131
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-05-12T14:47:00+00:00
- Post Title: 

Ill help test also if ya need it brienj. Ill even mirror it if needed, unlim disk sopace and bandwidth!
## Post #132
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-05-12T17:18:05+00:00
- Post Title: 

I would love to beta test it, I also can host it for you also.

f you need a email address, mine is [KDRUMM2K6@gmail.com](mailto:KDRUMM2K6@gmail.com)
## Post #133
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-13T05:15:20+00:00
- Post Title: 

Actually, I won't need anybody to beta test it, I couldn't release it in the state it is in yet, I didn't expect to get so much finished this fast.  I should have it done within a day or so.  There are some certain loose ends I have to tie up, and then it will be finished.
## Post #134
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-05-13T05:17:20+00:00
- Post Title: 

Could you add textures. 

Like heads.
[stonecold.png](https://xentaxbackup.github.io/file/223_stonecold.png)
## Post #135
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-05-15T19:07:17+00:00
- Post Title: 

alright please can someone help me whenever i get the code i want from a file and put it in a blank dds file this is all i get what's the problem

sorry here is the pic
## Post #136
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-18T19:07:08+00:00
- Post Title: 

I released my resigning program finally, and I will give you a link to the GameFAQs thread that gives the download link, because I think you will get a great laugh reading about ThE MaSTeR 3's problems running the program.  

I almost peed my pants it's so funny.  

[http://boards.gamefaqs.com/gfaqs/genmes ... c=21041198](http://boards.gamefaqs.com/gfaqs/genmessage.php?board=920641&topic=21041198)
## Post #137
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-18T19:17:16+00:00
- Post Title: 

lol

> Reply from themasterthree
>
> 
just disabled the dep and your app still wont work. Now it appears for a second then closes.
---
It's good to play Alone!

> Reply from TheKidRocker
>
> 
From: TheKidRocka | Posted: 5/18/2005 11:07:36 AM | Message Detail
are you sure ur using it right, u gotta start it via command line not with a double click
## Post #138
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-05-19T01:11:44+00:00
- Post Title: 

I once tried to use CLI programs as if they were GUI... before I even knew what CLIs were or how to use them. I asked the author of the program via email politely how to use it, and he quickly filled me out... Doesn't take a computer geek at all, just somewhat of a brave soul...
## Post #139
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-19T06:24:59+00:00
- Post Title: 

Found some proof of nice mod.  Adults only please!  
[Thatsit1.jpg](https://xentaxbackup.github.io/file/238_Thatsit1.jpg)
## Post #140
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-19T07:02:27+00:00
- Post Title: 


## Post #141
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-05-19T23:15:01+00:00
- Post Title: 

> Reply from jasmine
>
> Found some proof of nice mod.  Adults only please!

Where did you find the picture at?  I think that would mean someone figured out how to import textures back into the dvd.wad which would be pretty cool to know how to do.
## Post #142
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-05-20T01:12:40+00:00
- Post Title: 

I can post a program that allows importing if it's okay with Mr. Mouse.  The file is about 300k.  I'll wait for his response.
## Post #143
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-05-20T05:24:23+00:00
- Post Title: 

brienj werent you doing the same thing.
## Post #144
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-20T05:25:37+00:00
- Post Title: 

> Reply from SuperSSonic
>
> jasmine wrote:Found some proof of nice mod.  Adults only please!  

Where did you find the picture at?  I think that would mean someone figured out how to import textures back into the dvd.wad which would be pretty cool to know how to do.
It's easier to do it with the CAS now with the resigner.
## Post #145
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-20T07:40:27+00:00
- Post Title: 

> Reply from jasmine
>
> I can post a program that allows importing if it's okay with Mr. Mouse.  The file is about 300k.  I'll wait for his response.

Yep, go ahead.
## Post #146
- Username: SuperSSonic
- Rank: n00b
- Number of posts: 18
- Joined date: Tue May 17, 2005 3:36 am
- Post datetime: 2005-05-20T18:29:51+00:00
- Post Title: 

> Reply from brienj
>
> 
It's easier to do it with the CAS now with the resigner.

Would the steps be to open the model.k file in a hex editor find the body part you want to edit.  Copy and paste from the start of 01 00 04 to the end of the data of that body part then create a blank file add the copied data and save it.  That would leave me with something similar to a .res file I believe but I'm not sure how to edit the .res files yet.  Probably need to add some sort of header to it but not sure which one.  After editing it I would then remove the Header and Copy and Paste the new edited data back into the .k file then resign it.  Not sure if this is the correct way to do it though.

Edit:  Looks like part of that worked.




Edit2:  Tried to edit a texture then put the data back into the .k file using the Hex Editor then resigned it but it only freezes after the game goes to load the entrance of the character so I did something wrong.
## Post #147
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-05-20T22:30:56+00:00
- Post Title: 

> Reply from XTC
>
> alright please can someone help me whenever i get the code i want from a file and put it in a blank dds file this is all i get what's the problem

sorry here is the pic

anyone please??
## Post #148
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-05-22T08:46:31+00:00
- Post Title: 

Wow I hope we get some good mods coming out soon!
## Post #149
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-05-23T14:13:17+00:00
- Post Title: 

brienj how do you open .res files I want to add a picture for Goldberg.
## Post #150
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-05-23T14:41:24+00:00
- Post Title: 

> Reply from brienj
>
> I released my resigning program finally, and I will give you a link to the GameFAQs thread that gives the download link, because I think you will get a great laugh reading about ThE MaSTeR 3's problems running the program.  

I almost peed my pants it's so funny.
I didn't see that thread had more than one page, but now I read the whole thing. I'm glad we got rid of that guy. What a clueless moron lol.

> From: ThE MaSTeR 3 | Posted: 5/18/2005 5:52:34 PM | Message Detail
>
> "Modified the engine so it won't work for "The Master 3"
>
> Thanks for publishing your HDD Key on the internet you moron."
>
> 
>
> damn looks like Ill have 2 play it on my other xbox lol Oh wait... I already got goldberg working in the game with the first version of the program looks like your little plan backfired.
Hahaha. Did you put that in the readme file?
## Post #151
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-23T14:44:29+00:00
- Post Title: 

LOL!

More funny bits: 

> From: SuperSSonic | Posted: 5/18/2005 2:08:57 PM | Message Detail
>
> ThE MaSTeR 3 have you changed to the directory the program is located at in DOS.
>
> 
>
> Using: cd "this is where the program is"
>
> 
>
> then just type resign and then space once and the file you want to resign.
>
> From: ThE MaSTeR 3 | Posted: 5/18/2005 2:10:29 PM | Message Detail
>
> hmm maybe I did maybe I didnt....
>
> ---
>
> It's good to play Alone!
>
> From: ThE MaSTeR 3 | Posted: 5/18/2005 2:16:28 PM | Message Detail
>
> ok Im an idiot that was the problem *walks away in shame*
>
> ---
>
> It's good to play Alone!

NO CLUE WHATSOEVER.
## Post #152
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-05-23T15:06:15+00:00
- Post Title: 

also does anybody know what the .lua file is?
[Goldberg.rar](https://xentaxbackup.github.io/file/251_Goldberg.rar)
## Post #153
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-23T18:32:03+00:00
- Post Title: 

That file is empty.
## Post #154
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-23T19:38:36+00:00
- Post Title: 

> Reply from Hammer
>
> also does anybody know what the .lua file is?
This game script ... using Notepad for view and edit
## Post #155
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-05-23T21:58:23+00:00
- Post Title: 

I guess they never put anything in Goldberg's .lua because the other wrestlers are not empty.

I guess its ai tendency.

This is in HBK's lua

```
EnemyStunned.RunAttack = 40;

Turnbuckle.Climb = 80;
Turnbuckle.EnemyKnocked = {};
Turnbuckle.EnemyStanding = {};

TurnbuckleEnemyKnockedAttack.Jump1 = 50;
TurnbuckleEnemyKnockedAttack.Jump2 = 50;

TurnbuckleEnemyStandingAttack.Jump1 = 50;
TurnbuckleEnemyStandingAttack.Jump2 = 50;

EnemyStunnedTaunt.Taunt1 = 60;
EnemyStunnedTaunt.Taunt2 = 40;

```


Edit:
Alot of the wrestlers are empty. So maybe its only for certain wrestlers.
## Post #156
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-23T22:04:43+00:00
- Post Title: 

Indeed. How weird. Thanks!
## Post #157
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-05T13:32:37+00:00
- Post Title: 

dont me to bump it but what do i save my dds file type as like what are the settings a box comes up its that nivida thing could someone help me out?
## Post #158
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-06-05T13:56:39+00:00
- Post Title: 

For the most Textures its DXT1 no Alpha with 4 MipMaps.
## Post #159
- Username: XTC
- Rank: Banned
- Number of posts: 23
- Joined date: Wed Apr 27, 2005 10:21 am
- Post datetime: 2005-06-05T17:27:56+00:00
- Post Title: 

erm how did you get to change your mipmaps thing do i need to download something if so anyone got a link
## Post #160
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-07-03T21:18:20+00:00
- Post Title: 

Listen up everybody, I have just released my ModPack v1 with 31 new Skins and many more!

You can get it here:

[http://www.wrestlinggamesboard.de/index ... opic=14470](http://www.wrestlinggamesboard.de/index.php?showtopic=14470)
