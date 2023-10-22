## Post #1
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2005-07-11T04:38:35+00:00
- Post Title: Manhattan Chase

Hey ppl
Its possible to make a pluggin to this game Manhattan Chase
I have uploaded one file from textures directory they use this format for almost all files they have in the game if you can plz take a look on it.
Thx
[timesqb.rar](https://xentaxbackup.github.io/file/349_timesqb.rar)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-11T06:25:29+00:00
- Post Title: Manhattan Chase

Thanks! I'm on it. Let you know what I find.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-11T07:45:32+00:00
- Post Title: Manhattan Chase

This is a file that contains increasingly smaller textures for the same item (like MIP maps in DDS). I haven't quite figured out the format of the images yet. They do not look compressed really, as the image data matches the height*width variables in there. So it should be an 8-bit image format. 

Do you have more examples? There are still some variables in the 0x24 header that I don't understand.
## Post #4
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2005-07-11T11:57:30+00:00
- Post Title: Manhattan Chase

Sure mate i have included other file from the folder textures/ and other file from the folder Menu/ i hope this help you.
Thx
[pave08.rar](https://xentaxbackup.github.io/file/351_pave08.rar)
## Post #5
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2005-07-11T11:58:45+00:00
- Post Title: Manhattan Chase

this one if from the Menu/ folder
[E1M9.rar](https://xentaxbackup.github.io/file/352_E1M9.rar)
## Post #6
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2005-07-12T00:02:36+00:00
- Post Title: Manhattan Chase

mr. mouse if you can resolve this i wanna ask if is possible to make a convertor for the images inside the paks in case they are not standart.
Thx
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-12T07:55:12+00:00
- Post Title: Manhattan Chase

I will take a look at them at get back asap.
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-13T13:59:38+00:00
- Post Title: Manhattan Chase

Demo Version 
[http://www.gamershell.com/download_8664.shtml](http://www.gamershell.com/download_8664.shtml)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-13T14:16:43+00:00
- Post Title: Manhattan Chase

Thanks. I will see what I can do, when I have time.
## Post #10
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2005-07-16T19:38:43+00:00
- Post Title: Manhattan Chase

The DCT texture file format is indeed a DDS file with mips. The DCT header is 48 bytes and contains all the information including the width and height. All that I looked at were DXT3 format which may mean that modders can utilize the alpha channel. 


Marvey:
Since I'm on the road and using this old laptop I don't think I have enough resources available to write and test a Perl conversion script but if you want to convert by hand I can tell you how with Photoshop and a HEX editor.
## Post #11
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-18T23:21:53+00:00
- Post Title: Manhattan Chase

Strange but I sat understood with formats of all files this game and have come to conclusion what not what there DXT3 even does not smell as a format... At all files with expansions DCT, DCW, DCM, DCA, CAM , MCS, DCV, DCL, dcShadow, dcScript heading DC2 and further on all file almost one zero...   What think in this occasion?  

This example CAM file format
DC2...........?....i...k.
.?...=...:...B...?....2?

This example DCT file format
DC2.......................................
.................................................
.................................................
..................................................
...................................................
..................................................
..................................................
....................................................
.....................................................
........................................................
..................................
## Post #12
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2005-07-19T00:16:13+00:00
- Post Title: Manhattan Chase

If I read your translation correctly, you do not understand how I concluded the DCT files are DXT3. 

 The DC2 header is 48 bytes long. If you remove this header the remaining data is a raw DXT3 with mips. It is not readable as a DXT3 because there is no DDS header. I looked at some other textures and there are both DXT1 and DXT3

 To make it a DDS you will need to add a DDS header. This can be done by creating a DDS DXT3 file in the size needed with mips. Then remove the 128 byte header from your newly created DDS and attach it to the top of the raw DDS. The same for DXT1

 To get the correct file size look at the original DC2 header. The 2 byte word at byte 19 is the width and the 2 byte word at byte 23 is the height. I also noticed the file size height and width at byte 36 and 38

For instance this Perl script would work for the DXT3

```
      	print "found a DCT file named $name\n";
        open(INPUT, "< $name") or die "can't open $input file: $!\n";
	binmode(INPUT);
	$FileLength = (-s INPUT);
	print "filelength = $FileLength\n";
	read(INPUT,$c,$FileLength,0) or die "can't read $FileLength bytes.\n";
       	($Width,$Height)= unpack "Sx[S]S", substr $c, 36, 128;
        print "width = $Width\n";
	print "height = $Height\n";
	$Size = ($Width * $Height);
	print "size = $Size\n";
	$DDSL1 = pack "SSSSSSSS", 17476, 8275, 124, 0, 4103, 10, $Height, 0;
	$DDSL2 = pack "SSSSSSSS",$Width,0,0,4,0,0,0,0;
	$DDSL345 = pack "LLLLLLLLLLLL", 0,0,0,0,0,0,0,0,0,0,0,0;
	$DDSL6 = pack "LCCCCLL", 0,68,88,84,51,0,0;
	$DDSL78 = pack "LLLLLLLL", 0,0,0,0,0,0,0,0;
	
	
   	
	seek INPUT, 48, SEEK_SET or die "can't seek Header length. \n";
	read (INPUT,$b,$Size,0) or die "can't read File Size.\n";
	$name =~ s/DCT/dds/;
	print "name = $name\n"; 
    	open(DDSFILE, "> $name") or die "can't open DDSFILE: $!\n";
   	binmode(DDSFILE);
   	print(DDSFILE $DDSL1);
	print(DDSFILE $DDSL2);
	print(DDSFILE $DDSL345);
	print(DDSFILE $DDSL6);
	print(DDSFILE $DDSL78);
	print(DDSFILE $b);
  }
```


 Basically the script reads the 48 byte header , gets the size of the graphic, removes the 48 byte header , puts the DDS header on the file using the size from the original header. Just a time saver since it will read every DCT file in the folder and convert to DXT3. I tried it on a few and the actual DXT3 files came out ok.
## Post #13
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-19T08:37:01+00:00
- Post Title: Manhattan Chase

I wish to know you what version use? Full or the Demo? In the full version files differ from a demo !
## Post #14
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2005-07-19T17:26:45+00:00
- Post Title: Manhattan Chase

the files i posted here are from the full game not the demo.
Mate is possible to compile this code ? 
thx
## Post #15
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2005-07-20T03:24:35+00:00
- Post Title: Manhattan Chase

> Mate is possible to compile this code ?

 I have heard of Perl compilers but the code is smaller and easier to manipulate in script form. For instance to get this to work on DXT1 only requires text editing a couple values. 

 Perl is a free download, I used ActiveState Perl to test the script. It runs at the command prompt and requires no Perl knowledge to run the script.
## Post #16
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-04T23:54:14+00:00
- Post Title: 

Game Taxi3 eXtreme Rush has the same formats of archives
## Post #17
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2005-08-05T14:21:12+00:00
- Post Title: 

yeah same engine
## Post #18
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-10-11T08:53:38+00:00
- Post Title: 

I'm trying to open the file MONSTER JAM (IOS)
seem to be the usual file you mentioned here
which software can I use to open these files?
the DCT file should be the texture, while the DCM file 3d model
thanks so much

[https://drive.google.com/file/d/0Bxt-hU ... sp=sharing](https://drive.google.com/file/d/0Bxt-hUWDTtoGY3M1b2hHZzcwVW8/edit?usp=sharing)
[https://drive.google.com/file/d/0Bxt-hU ... sp=sharing](https://drive.google.com/file/d/0Bxt-hUWDTtoGZjJ1ZHVFX1VIck0/edit?usp=sharing)
## Post #19
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-10-13T16:32:42+00:00
- Post Title: 

I tried to use the method you mentioned, but the result has been disastrous.
can someone give me a hand?
