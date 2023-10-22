## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-04T22:44:48+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

I pulled up this PSX game yesterday wondering how it stored data and found out that each data files was accompanied by a table that tells where everything is and as well gives information on what each file is. Here's an example: [http://download.yousendit.com/2C7A503177D85F75](http://download.yousendit.com/2C7A503177D85F75)

Now I'm not sure entirely how a table file is used but it seems it tells where and what each file is in the archive (extensions). Basically I'm centering in on the graphics and figuring those out because I've found out that some of the music is just Microsoft RIFF WAVE as opposed to XA audio and are unarchived with a *.DA extension as if that changes what it is XD. Odd eh?

Edit, just another realization: Also they had a BIN called "SECRET.BIN" and it was just a blank dummy file and the "DUMMY.BIN" was another music RIFF WAVE. I have no clue what they were thinking there. O_o
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-04T23:10:56+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

> Reply from Darkfox
>
> it seems it tells where and what each file is in the archive (extensions).

Your assumption is quite correct. In formal notation, the format of the TBL files looks like

```
  char {8}     - file name prefix // terminated by 0x20
  char {3}     - file name suffix
  uint32 {4}   - offset
  uint32 {4}   - size

```

All integers are big-endian, by the way.

> Reply from Darkfox
>
> Basically I'm centering in on the graphics and figuring those out because I've found out that some of the music is just Microsoft RIFF WAVE as opposed to XA audio and are unarchived with a *.DA extension as if that changes what it is XD. Odd eh?
Programmers work in mysterious ways. 

Anyway, extracting files from this archive should be pretty easy. Let's see if I can take this as an example to learn writing BMS ...

Do you already know the type of the files you are looking for?

> Reply from Darkfox
>
> Edit, just another realization: Also they had a BIN called "SECRET.BIN" and it was just a blank dummy file and the "DUMMY.BIN" was another music RIFF WAVE. I have no clue what they were thinking there. O_o
Maybe some odd form of copy protection?
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-05T00:45:44+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

Contained in there are an image format (or image formats), I'm not 100% sure the name that they go by because as far as I see they are not a standard format. I saw the images using Texture Finder while looking for the sprites so I'll assume that the images and sprites are the same format but don't hold me to it.

It seems there are two types of image files but both have an associate PAL (pallette) file.

Image Type 1: 256 (256 colors?)
Image Type 2: B8 (not certain)

Both have a PAL file of the same name.

There seems to be a third type: B16 but these don't seem to have a PAL file, possibly having a built-in palette?
## Post #4
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-05T09:47:26+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

Currently, I cannot see the difference between the 256 and the B8 type, they both look like palettized images at the first glance. Also, the PAL files are 512 bytes in size for both image types, indicating 16 bit colour values -- now one would have to find out how many bits are reserved for each colour.

Judging from their appearance, B16 files are probably raw colour data, using the same colour encoding as the PAL files -- a 16 bit value for each pixel.

What strikes me as odd, though, is that I cannot seem to find any kind of size information. The images might be fixed-width (or -height) or the image dimensions might be stored somewhere else.

By the way, if someone fluent in MexScript is reading this: Is there any way to get the file size of a currently opened file or alternatively check for EOF? Also, can certain characters (such as spaces) be removed from strings?
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-05T12:28:56+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

Okay, the B16 images seem to be always 320 pixels wide, only the colours are still off. Let's see ...

[Edit: The colour format of each 16 bit big endian (!) value is GBR, each with 5 bits, ignoring out the first bit: 0GGGGGBBBBBRRRRR.
Some of the pictures still look weird, though ...]

[Edit #2: I was mistaken. There are at least two images which are 480 pixels wide. There does not seem to be a way to determine the image dimensions from the file alone.]
[ED_JUS  .jpg](https://xentaxbackup.github.io/file/1250_ED_JUS  .jpg)
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-05T18:30:49+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

Thats one of the leader selection screens and it looks perfect.  

> [Edit #2: I was mistaken. There are at least two images which are 480 pixels wide. There does not seem to be a way to determine the image dimensions from the file alone.]

Hm, do you have any thoughts of a way to work through that? Don't know why there are no dimensions.

[Edit: Fixing the title, it's not "Masumon Kids" but "Master of Monsters - Akatsuki no Kenja Tachi" which is different from Masumon Kids which featured chibi characters.]
## Post #7
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-05T21:31:59+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

> Reply from Darkfox
>
> Hm, do you have any thoughts of a way to work through that?
Unfortunately, no. The dimensions are probably buried somewhere in the script which loads the images (or at least implied by it). I wouldn't know where to start searching for this particular bit of information.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-05T21:44:06+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

> Reply from Deniz Oezmen
>
> 
By the way, if someone fluent in MexScript is reading this: Is there any way to get the file size of a currently opened file or alternatively check for EOF? Also, can certain characters (such as spaces) be removed from strings?

Well, there are a number of options. The current implementation of MexScript is not that flexible. Rahly is working on a much improved MexScript. For now, you'll have to make do with mine.  

There is no way to remove unwanted characters from an already loaded string. However, there's a dirty work-around: 

```
Do ;
SavePos A 0 ;
GetDString C 1 0 ;
GoTo A 0 ;
Get B Byte 0 ;
If B <> 32 ;
String NAME += C ;
EndIf ;
While B <> 0 ;
Log NAME B B 0 0 ;

```


Okay, the Do While loop is the key here. It assumes a new string will start from the current file pointer. It then loads the bytes there as a STRING and then again as a BYTE (there's no type conversion!). The value of the BYTE is checked, if NOT 32 then the 1 character string will be appended to the string NAME. This is repeated until B is 0 (thus assuming a null-terminated string, you'll have to adapt the code if you're dealing with strings of predetermined size. After the "function" you will have a string NAME consisting of no spaces. 

Similarly, to get the archive size: 

```
GoTo EOF 0 ;
SavePos END 0 ;
GoTo S 0 ;

```


EOF is a preset variable you can use. The example code first saves the current position in S, then goes to the end of the file, and saves that position there in END. Then returns to where it came from. You may need to add 1 to the value for your needs as position 1 in a file is 0 (offset 0). 

Another dirty method would be : 

```
Get C Byte 0 ;
While NotEOF <> 0 ;

```


This would get bytes and store each of them in C until the end of the file is reached. NotEOF is preset, but the MexScript does not allow the rest of the arguments omitted in the While statement.   
So that's why there's the *ignored* "<> 0"
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-05T22:26:57+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

> Reply from Mr.Mouse
>
> For now, you'll have to make do with mine.
I can work with whatever is available. 

> Reply from Mr.Mouse
>
> There is no way to remove unwanted characters from an already loaded string. However, there's a dirty work-around:
Crazy minds work alike. 
I thought this might be a solution, but wanted to ask first. Thanks for the explanation!

As for the archive size/EOF stuff, thanks for pointing me to the EOF/NotEOF values. I believe I will want to use the first solution, since I need to test for the end of a secondary opened file, not the main archive (0), which I assume NotEOF tests for. Did I get that right?

So, this would be my current script (which I wrote just now but didn't test yet):

```
ImpType Standard ;
Set Dot String . ;

# open directory table
Open FDDE TBL 1 ;

# find terminal file offset
GoTo EOF 1 ;
SavePos FileEnd 1 ;
GoTo 0 1 ;

# read directory entries until EOF
Do ;

# read prefix (8 characters, padded with 0x20)
Set FileNamePrefix String "" ;
Set I Long 8 ;
Do ;
SavePos StrPos 1 ;
GetDString Char 1 1 ;
GoTo StrPos 1 ;
Get CharVal Byte 1 ;
If CharVal <> 32 ;
String FileNamePrefix += Char ;
EndIf ;
Math I -= 1 ;
While I > 0 ;

# read suffix (3 characters, padded with 0x20)
Set FileNameSuffix String "" ;
Set I Long 3 ;
Do ;
SavePos StrPos 1 ;
GetDString Char 1 1 ;
GoTo StrPos 1 ;
Get CharVal Byte 1 ;
If CharVal <> 32 ;
String FileNameSuffix += Char ;
EndIf ;
Math I -= 1 ;
While I > 0 ;

# read offset (big endian longword)
Get Offset Long 1 ;
ReverseLong Offset ;

# read size (big endian longword)
Get Size Long 1 ;
ReverseLong Size ;

# construct file name and output
Set FileName String FileNamePrefix ;
String FileName += Dot ;
String FileName += FileNameSuffix ;
Log FileName Offset Size 0 0 ;

SavePos CurrentPos 1 ;

While CurrentPos < FileEnd;
```

I'll first sleep over this. 

Thanks again!

[Edit: Removed SizeOffset/OffsetOffset references from script]
[Edit #2: Replaced "for" by "do" loops]
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-05T23:28:52+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

Oh my god ! You're amazing! It works first time around!

But I noticed a stupid stupid bug in multiex.dll that will crash MultiEx Commander. . . . This is not due to your MexScript however! But my own sloppy coding. This will need a fix. I hope to get round to that soon. 

But here's proof that you got it right (in my current build of MultiEx Commander). Brilliant!
[deniz_did_it.jpg](https://xentaxbackup.github.io/file/1253_deniz_did_it.jpg)
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-05T23:43:51+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

Nice.  But what bug is this you speak of?
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-06T06:40:12+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

Well, there are two problems, one of them a bug, another a lacking feature. 

First, the progress window of multiex.dll does a strang calculation once more than one For...Next loop is used and this results in an error after which multiex.dll decides it cannot finish the job. Once I had removed that, Deniz's script worked perfectly as you can see in the screenshot. 

The other problem is with file importation. Deniz has nicely included support for replacement of files by adding the offsets of the resource sizes and resource offsets in the Log statement. The irritating problem here is that MexCom is not written to change values in files other than the main archive (file 0). If you'd try to replace files in the archive, this would probably crash the program or in any event corrupt the main archive. Beat me with a stick for this.
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-06T17:43:01+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

Nice to see that it actually works. 
I just followed the instructions on the Wiki and your help, Mr.Mouse, so kudos to you.

> Reply from Mr.Mouse
>
> The irritating problem here is that MexCom is not written to change values in files other than the main archive (file 0).
Of course. I should have concluded that myself (from a semantical point of view). Ah, just remove the lines then ...
## Post #14
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-06T22:38:41+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

Almost forgot ... the current version of the converters I used is attached. As the B8/B16/256 files are basically unstructured, I do not see much room for improvement (at least until the image dimensions suddenly appear from somewhere).

Usage:

```
B82BMP <B8/256Files> <Width> [<PaletteFile>]
```

Both programs need the desired image width as a mandatory parameter. In the case of B82BMP, an external palette file can be given. If it is not specifiec, the .PAL file of the same name as the current image file will be used. If that does not exist, a standard grayscale palette will be used.

The tools will probably not work on all image files -- but I do not see much I could do about that at the moment.
[B16B8.zip](https://xentaxbackup.github.io/file/1256_B16B8.zip)
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-07T02:57:37+00:00
- Post Title: Master of Monsters-Akatsuki no Kenja Tachi (PSX) DAT+TBL

So which lines does one remove from the script that would make it work properly? This loop is what causes the crash correct and to fix it Mr. Mouse removed it but where is this loop?

Edit: Okay I figured out what this loop was but I'm just fumbling in the dark here.  One fix leading to another error is all that I'm doing. 

Also, with Texture Finder I think finding the width of an image will not be too hard. So do not worry about that any. I could still look for the dimensions though, there's a file that may contain it I intend to investigate.
## Post #16
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-07T09:46:29+00:00
- Post Title: 

> Reply from Darkfox
>
> So which lines does one remove from the script that would make it work properly? This loop is what causes the crash correct and to fix it Mr. Mouse removed it but where is this loop?
The lines I was referring to were the ones handling the values SizeOffset and OffsetOffset, which are not useful due to the reasons Mr.Mouse gave earlier. I've edited the post above accordingly.

As far as I understand, the looping bug cannot be fixed within the script itself (or maybe it could via some work-around?), but needs a patch to MultiEx Commander.
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-07T12:12:10+00:00
- Post Title: 

Well, the work around could be to replace the rest of the for loops with Do; While loops. 

I hope to release a new version some time later this year, with some added features, but also some bug fixes.
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-07T18:59:25+00:00
- Post Title: 

Yeah, still doesn't seem to work.
## Post #19
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-07T22:54:32+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Well, the work around could be to replace the rest of the for loops with Do; While loops.
Of course, thanks for the reminder.

> Reply from Darkfox
>
> Yeah, still doesn't seem to work.
Try the current version; I replaced the loops as Mike suggested. (Once again a "dry" edit, i.e. not tested yet.)
## Post #20
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-08T03:22:56+00:00
- Post Title: 

Dunno if it is me or MultiEX but now it just freezes up. But at least there is no error now. XD Ah... That was the first test of the new revision. I dunno if it's my PC's current state or not but I think I'll wait for a second opinion. XD
## Post #21
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-08T09:06:08+00:00
- Post Title: 

You're right, it freezes. Odd stuff ... if I replace the outer "Do" Loop by some "For J = 1 To 10" loop, it correctly loads up the first 10 entries.

Does MexScript allow for nested Do loops?
## Post #22
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-08T23:14:04+00:00
- Post Title: 

Ahhhh, just let me take the time to look at this. It's what I doubted. I doubted my suggestion would work, but thought: let's see. 

I will still have to see.
## Post #23
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-09T00:59:36+00:00
- Post Title: 

Good luck. It's got me baffled already. XD
## Post #24
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-14T18:27:58+00:00
- Post Title: 

Any news or is the script still a mystery on why it is freezing MultiEx?
## Post #25
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-19T23:33:29+00:00
- Post Title: 

I think Mike will take a look at it as soon as he has time to do so. We probably can't do anything from here ...
## Post #26
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-20T02:26:41+00:00
- Post Title: 

I suppose you are right. I tried several things that seemed to work but crashed at the end. Hopefully he can find a fix for it. Odd that this has been the only time I've had a problem with a script.
