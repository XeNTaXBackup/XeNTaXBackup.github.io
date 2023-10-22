## Post #1
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-08-06T23:53:36+00:00
- Post Title: Davidson & Associates .res files

I'm at it again: I'm looking at files from old educational computer games I played as a kid. Files that end in .res can be found with several games by Davidson & Associates, but here I will be looking at one file from Math Blaster Episode 2: Secret of the Lost City, Version 1.2 C, as well as a file from Davidson's Learning Center Series: 3rd Grade (also known as Learning Voyage: Sand Trapped!). There's a reason I'm looking at two .res files, which I will get to. Feel free to follow along at home. A ZIP file containing both files can be downloaded from my Dropbox here: [https://www.dropbox.com/s/p872xcdsf38gx ... s.zip?dl=0](https://www.dropbox.com/s/p872xcdsf38gxzk/davidson%20res%20examples.zip?dl=0)

So, here's the structure for the Math Blaster Episode 2 file (E2CD.RES):

```
uint64 {8}      - null padding (all 0)
uint32 {4}      - tail 1 offset
uint32 {4}      - tail 1 length
uint32 {4}      - tail 2 offset
uint32 {4}      - tail 2 length
byte {44}       - null padding (all 0)
// all data, until tail 1 offset
   // begin tail 1
   uint64 {8}      - null padding (all 0)
   // for each file
   uint32 {4}      - file offset
   uint32 {4}      - file size
   // tail 2 begins at tail 2 offset; exactly the same as tail 1

```


There are a few oddities with this. For one thing, as mentioned, both tails are exactly the same; why they bothered putting it in there twice is beyond me. Second, the offsets are not in order, so in this case, the first file (at offset 0x44) is actually listed much later on down the list. Third, and most unfortunately for me, there are no file names. An accompanying file, E2CD.BAP, seems to contain file directory names, but not the names of the files themselves. I'll take a look at a later release also, to see if its .res file might be structured differently.

Now for the Learning Voyage file (LVG3.RES):

```
byte {16}       - null padding (all 0)
uint32 {4}      - file info A offset
uint32 {4}      - file info A length
byte {32}       - null padding (all 0)
uint32 {4}      - tail offset
uint32 {4}      - tail length
// all data, until file info A offset
   uint64 {8}      - null padding (all 0)
   // for each file
   uint32 {4}      - file offset
   uint32 {4}      - file size
   // continues until file info B offset (defined in tail)
      // for each file
      uint32 {4}      - file number
      uint32 {4}      - file size (+2 for RCB files)
      uint32 {4}      - unknown (see below for guess)
      uint32 {4}      - file type ID (0x2 for WAV files, 0x4 for BMP files, 0x7 for RCB files, 0xA for BAP files)
      uint32 {4}      - length of file name
      char {length}   - file name, complete with drive letter or "./"
      // continues until tail offset
         uint32 {4}      - file info B offset
         uint32 {4}      - file info B length
         // for each file
         uint32 {4}      - starting offset of detailed file info
         uint32 {4}      - length of detailed file info

```


Whew! Now, that is what I call a complex archive! Hence why I probably won't write a MultiEx script for these types of files; there's too much jumping back and forth from offset to offset. Why did they do that, rather than just put everything in the header, or in the tail?

But despite the complexities compared to what I call the "version 2" .res files, these "version 3" .res files actually have some major advantages, such as actually having the file names, as well as having the file offsets and sizes be in the actual order of the files. But then, why is it that the sizes are still reported twice, except for RCB files they're listed incorrectly the one time, and correctly the other? And what the heck is an RCB file, anyway? What is it there for? Also, what's with those file names? Why do they start with a drive letter or a "./"? (Yes, I do know that ./ means the root, but... of what, in this case?)

Now, onto the one "unknown" element in the detailed info/"Info B" section (I'm sorry, I really don't know what else to call it). It's clearly not an offset or a length. However, with Hex Workshop, I can actually highlight it and it gives me a value that seems to make sense: the "time_t" value seems to match up with when the files were actually created. I've highlighted those strange values at random points in each file, as well as for other files, and it seems to consistently match up. So, my theory is that these values are actually the dates when the individual files were created. Now that's great and all, but is there a way to make it so that, when I eventually make some way to extract it, I can have that be the date modified/created?

I'm sorry that this is such a long post, but I really wanted to let everyone know what I've figured out so far, and what I have yet to figure out. I'm just thankful that there's no compression or encoding that I have to deal with this time.

-Johnny
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-08-08T20:59:02+00:00
- Post Title: Davidson & Associates .res files

It's a shame version two of the *.res files don't hold any filenames :/. (If there's another file it's supposed to match up to, just post it here and I'll add in support for those in version 2). For version 3, you were right about the "unknown" value being the file's date and time (given the game seems to be released around '98 and that is when the files were created). I wrote a QuickBMS implementation for both of the versions you've supplied as samples. If you happen to find anymore versions, post them here and I'll take a look (even much better if you would like to identify the structure beforehand ). Anyways, here's the QuickBMS script for RES version's 2 + 3:

```
# Writen By Anex For QuickBMS

get VER long

if VER == 0x2
	get PADDING longlong
	get TB1OFF long
	get TB1SIZE long
	get TB2OFF long
	get TB2SIZE long
	goto TB1OFF 
	get PADDING longlong
	xmath FCOUNT "(TB1SIZE - 0x8) / 0x8"
	callfunction VER2EXTRACT
	goto TB2OFF
	get PADDING longlong
	xmath FCOUNT "(TB1SIZE - 0x8) / 0x8"
	callfunction VER2EXTRACT
elif VER == 0x3
	callfunction SKIP
	get FTBA long
	get FTBASZ long
	callfunction SKIP
	get FTBB long
	get FTBSZ long
	goto FTBB 
	get FNAMETB long
	get FNAMETBSZ long
	goto FTBA
	get PADDING longlong
	savepos OFFTABLE
	xmath FCOUNT "(FTBASZ - 0x8) / 0x8"
	for i = 0 < FCOUNT
		get OFFSET long
		get SIZE long
		savepos OFFTABLE
		goto FNAMETB
		get FNUM long
		get NULLSZ long //Sizes also stored here, but not accurate
		get FILEDATE long
		get FILEID long
		get FNSZ long
		getdstring NAME FNSZ
		savepos FNAMETB
		goto OFFTABLE
		log NAME OFFSET SIZE
	next i
endif

startfunction VER2EXTRACT
	for i = 0 < FCOUNT
		get OFFSET long
		get SIZE long
		log "" OFFSET SIZE
	next i
endfunction

startfunction SKIP
	do
		get ADVANCE byte
	while ADVANCE == 0x0
	savepos CUR_OFF
	math CUR_OFF - 0x1
	goto CUR_OFF
endfunction

```


I'm interested in these formats too (hopefully there's more RES versions ).
## Post #3
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-09-01T15:14:41+00:00
- Post Title: Davidson & Associates .res files

Thank you so much for the script, and sorry for the late reply.

> Reply from Anexenaumoon
>
> (If there's another file it's supposed to match up to, just post it here and I'll add in support for those in version 2).

I'm in the process of looking into this; it's possible that the name data may be contained within some other files (the extension is .bap), but I need to analyze them a little more before I can determine this for sure. There are .bap files associated with version 3 .res files also, but the strings contained in those files seem to only be directories or... other stuff. Once I have a little more info, I can post about them too. There aren't any resource files within the .bap files, though.

> Reply from Anexenaumoon
>
> For version 3, you were right about the "unknown" value being the file's date and time (given the game seems to be released around '98 and that is when the files were created).

Sweet! Thank you for confirming. Is there some way to implement this into some other script? I'm sure QuickBMS/MultiEx wouldn't support it (not yet anyway), but it would be nice to have that option there; rip the files and have the date and time when they were actually created, rather than just the date and time that they were placed on my hard drive.

> Reply from Anexenaumoon
>
> I'm interested in these formats too (hopefully there's more RES versions ).

You know, I could have sworn I saw a version 4 somewhere also, but I can't seem to find it. I definitely could have been wrong, of course. I'll have to check my collection again. Anyway, good to know someone other than me is interested in this.

Also, I had mentioned that I had a newer version of Math Blaster Episode 2, and yes, it does use version 3 .res files. If you'd like, I can attach them; even though we already know the structure, it might be good to have a version 2 and a version 3 file for the same game, just to make it easier to compare the differences.

-Johnny
## Post #4
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-09-01T17:43:30+00:00
- Post Title: Davidson & Associates .res files

Sure go for it . I don't think QuickBMS support Date and Time options sorry :/. If you find the version 4 file, post it here!
## Post #5
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-09-02T04:16:04+00:00
- Post Title: Davidson & Associates .res files

Dropbox link: [https://www.dropbox.com/s/0qx9g96j2vok0 ... s.zip?dl=0](https://www.dropbox.com/s/0qx9g96j2vok0sq/more%20res%20examples.zip?dl=0)

This zip file contains an updated version of E2CD.RES (version 3 with names), as well as SBJR.RES and SBJRMMX.RES, which are version 4, but... the structure is almost exactly the same as version 2, with one annoying difference. Tables A and B are different from each other (thankfully), but Table A makes no sense! It contains a hex value that doesn't seem to be an offset or size (although it looks like it should be), and then alternates between 0x44 and 0x0.
## Post #6
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-09-02T04:51:47+00:00
- Post Title: Davidson & Associates .res files

I think you dropped in the wrong E2CD.res, it's still version 2 on my end 


EDIT: Transferred all of this over to a Noesis python script. Easier to read. Can be found here:
[fmt_davidsonassoc_res.py](https://github.com/TheDeverEric/noesis-importers/blob/master/Eric%20Van%20Hoven/fmt_davidsonassoc_res.py)

-Added support for version 4. if you can get the proper "E2CD.res" updated file that would be awesome. Table A in version 4 is useless, so no point in reading it. 

Just in case you don't have it:

Grab noesis from [here](http://richwhitehouse.com/index.php?content=inc_projects.php), download, and just drop the python file into the "plugins" folder .

Once we confirm that we have all of the res versions figured out, i'm going to add in a function to guess file extension to make identifying slightly easier for the future
## Post #7
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-09-02T13:27:57+00:00
- Post Title: Davidson & Associates .res files

> Reply from Anexenaumoon
>
> I think you dropped in the wrong E2CD.res, it's still version 2 on my end

Son of a...

Here: [https://www.dropbox.com/s/noyhqs77gf61s ... 9.zip?dl=0](https://www.dropbox.com/s/noyhqs77gf61sqe/more%20res%20examples%20%28fixed%29.zip?dl=0)

Thanks for the Python script. I love Python.
## Post #8
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-09-02T15:27:30+00:00
- Post Title: Davidson & Associates .res files

> Reply from HeadsetGuy
>
> Anexenaumoon wrote:I think you dropped in the wrong E2CD.res, it's still version 2 on my end 

Son of a...

Here: https://www.dropbox.com/s/noyhqs77gf61s ... 9.zip?dl=0

Thanks for the Python script. I love Python.

Still version 2 xD. But regardless, version 3 should extract fine since it's supported. I'll start working on an extension guesser function for the ones without names so they don't just spit out ".dat" files.
## Post #9
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-09-02T20:24:50+00:00
- Post Title: Davidson & Associates .res files

> Reply from Anexenaumoon
>
> Still version 2 xD.
Are you sure? I just tried extracting the zip files; you were right about the first one still being version 2, but the second time I'm 100% positive I put the version 3 file in.

Screw it, I'll just link to the .res file directly: [https://www.dropbox.com/s/dv2rbzdlh3f1l ... 3.RES?dl=0](https://www.dropbox.com/s/dv2rbzdlh3f1lxk/i%20looked%20in%20a%20hex%20editor%20and%20this%20is%20definitely%20version%203.RES?dl=0)

(Yes, I know the file name is long; you can change it back to E2CD.RES if you want  )
## Post #10
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-09-03T01:41:29+00:00
- Post Title: Davidson & Associates .res files

> Reply from HeadsetGuy
>
> Anexenaumoon wrote:Still version 2 xD.
Are you sure? I just tried extracting the zip files; you were right about the first one still being version 2, but the second time I'm 100% positive I put the version 3 file in.

Screw it, I'll just link to the .res file directly: https://www.dropbox.com/s/dv2rbzdlh3f1l ... 3.RES?dl=0

(Yes, I know the file name is long; you can change it back to E2CD.RES if you want  )

The script I provided still extracts it fine. Names provided, too
## Post #11
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2021-01-02T15:28:17+00:00
- Post Title: Davidson & Associates .res files

Well, it's been a long time since I've added anything of substance to this post. But, I now know what the "Rectlist" files are, and why they are shown to be two bytes larger than they really are in the version 3 Info header.

I'll start with what they are. "Rect" is short for "Rectangle". A rectlist is a list of rectangles based on the sprites' bitmap files. It's an array of 16-bit signed integers in the form of X1, Y1, X2, and Y2 for each rectangle in the relevant BMP file.

As for why there are two sizes, with one being two bytes larger than the other... That's because the original files were two bytes larger. I discovered this in another Davidson program called Kid Works Deluxe, which, while it doesn't use RES archives, it does have several RCB files on the disc. But once I discovered what the structure of the rectlists was, I noticed that the Kid Works Deluxe files didn't match up; they were two bytes larger than they should have been, and the width and height that I calculated didn't add up.

That's when it hit me: After doing some calculations, I determined that this extra 16-bit int at the beginning is the number of rectangles in the list. Why they cut this number out when they stored it in the archive, I have no idea.

Anyway, it's not much, but it's something!

-Johnny
