## Post #1
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-04-29T22:25:50+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

Hi all i made this tread a few months ago i was wondering if someone could help me make a script for blender or 3dsmax for exporting this stadiums models with uv and texture data 
its from a game called  winning eleven 2010 its a japanese ps2 game it has around 30 - 40 stadiums but i guess if you guys make an exporter for the samples it should work with the rest 
 here is some sample files
[http://www.mediafire.com/download/ixizw ... adiums.rar](http://www.mediafire.com/download/ixizwl8bm8xb5jt/PS2+Stadiums.rar)
in the rar file there is 2 files that are in .bin format each file is a different stadium im just sending 2 just in case,
 inside each bin file there is textures and 3d mesh data for the stadiums
i also included a folder for each stadium this are the files that are inside the bin file i use a zlib editor
to extract them just in case you might need them, please let me know if there is something else that
you might guys may need THANKS in advance
please read all the post here and contact me if interested
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-30T05:53:13+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

use TextureFinder on unknow[n]_001.str:



Toyo_stadium_11103.JPG (93.91 KiB) Viewed 254 times
## Post #3
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-04-30T07:11:09+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

Thank you for the help but what i really really need is the 3d Data is there a way to extract to 3dsmax or blender?
Someone tried to help but he was to busy to continue he sent this note maybe it might help if you can help me 

Here are notes I made about the vertexes:
XX 00 08 00 04 01 00 01 04 80 XX 68
Where XX is the number of vertexes in that subsection.
Subsection format:
{2ByteSignedIntegerVertexes,2ByteSignedIntegerNormalMaps}
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-30T10:03:41+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

you could try to find some point clouds:



unknown_002_str.JPG (38.42 KiB) Viewed 245 times


(or wait for that "someone"  )

(From your formulae the vertex count should be 78 for this scetion but I ignored that.)

byte dump (guess that's no vertex section):
0x474
01 40  FF FF  67 66  FF FF  00 00  00 00  
01 40  FF FF  67 66  FF FF  00 00  00 00  
01 40  FF FF  67 66  FF FF  00 00  00 00  
BA 59  FF FF  67 66  FF FF  01 A0  FF FF  
BA 59  FF FF  67 66  FF FF  01 A0  FF FF  
BA 59  FF FF  67 66  FF FF  FF 5F  00 00  
BA 59  FF FF  67 66  FF FF  FF 5F  00 00  
BA 59  FF FF  00 00  00 00  01 A0  FF FF  
BA 59  FF FF  00 00  00 00  01 A0  FF FF  
BA 59  FF FF  00 00  00 00  01 A0  FF FF  
BA 59  FF FF  00 00  00 00  01 A0  FF FF  
BA 59  FF FF  00 00  00 00  01 A0  FF FF  
BA 59  FF FF  00 00  00 00  01 A0  FF FF  
BA 59  FF FF  00 00  00 00  FF 5F  00 00  
BA 59  FF FF  00 00  00 00  FF 5F  00 00  
BA 59  FF FF  00 00  00 00  FF 5F  00 00  
BA 59  FF FF  00 00  00 00  FF 5F  00 00  
BA 59  FF FF  00 00  00 00  FF 5F  00 00  
BA 59  FF FF  00 00  00 00  FF 5F  00 00  
BA 59  FF FF  CC 4C  00 00  01 A0  FF FF  
BA 59  FF FF  CC 4C  00 00  01 A0  FF FF  
BA 59  FF FF  CC 4C  00 00  FF 5F  00 00  
BA 59  FF FF  CC 4C  00 00  FF 5F  00 00  
00 A0  FF FF  67 66  FF FF  BA 59  FF FF  
00 A0  FF FF  67 66  FF FF  BA 59  FF FF  
00 A0  FF FF  67 66  FF FF  BA 59  FF FF  
01 A0  FF FF  67 66  FF FF  46 A6  00 00  
01 A0  FF FF  67 66  FF FF  46 A6  00 00  
01 A0  FF FF  67 66  FF FF  46 A6  00 00  
00 00  00 00  67 66  FF FF  01 40  FF FF  
00 00  00 00  67 66  FF FF  01 40  FF FF  
00 00  00 00  67 66  FF FF  FF BF  00 00  
00 00  00 00  67 66  FF FF  FF BF  00 00  
00 00  00 00  00 00  00 00  01 40  FF FF  
00 00  00 00  00 00  00 00  01 40  FF FF  
00 00  00 00  00 00  00 00  01 40  FF FF  
00 00  00 00  00 00  00 00  01 40  FF FF  
00 00  00 00  00 00  00 00  01 40  FF FF  
00 00  00 00  00 00  00 00  01 40  FF FF  
00 00  00 00  00 00  00 00  FF BF  00 00  
00 00  00 00  00 00  00 00  FF BF  00 00  
00 00  00 00  00 00  00 00  FF BF  00 00  
00 00  00 00  00 00  00 00  FF BF  00 00  
00 00  00 00  00 00  00 00  FF BF  00 00  
00 00  00 00  00 00  00 00  FF BF  00 00  
00 00  00 00  CC 4C  00 00  01 40  FF FF  
00 00  00 00  CC 4C  00 00  01 40  FF FF  
00 00  00 00  CC 4C  00 00  FF BF  00 00  
00 00  00 00  CC 4C  00 00  FF BF  00 00  
FF 5F  00 00  67 66  FF FF  BA 59  FF FF  
FF 5F  00 00  67 66  FF FF  BA 59  FF FF  
FF 5F  00 00  67 66  FF FF  BA 59  FF FF  
00 60  00 00  67 66  FF FF  46 A6  00 00  
00 60  00 00  67 66  FF FF  46 A6  00 00  
00 60  00 00  67 66  FF FF  46 A6  00 00  
46 A6  00 00  67 66  FF FF  00 A0  FF FF  
46 A6  00 00  67 66  FF FF  00 A0  FF FF  
46 A6  00 00  67 66  FF FF  FF 5F  00 00  
46 A6  00 00  67 66  FF FF  FF 5F  00 00  
46 A6  00 00  00 00  00 00  00 A0  FF FF  
46 A6  00 00  00 00  00 00  00 A0  FF FF  
46 A6  00 00  00 00  00 00  00 A0  FF FF  
46 A6  00 00  00 00  00 00  00 A0  FF FF  
46 A6  00 00  00 00  00 00  00 A0  FF FF  
46 A6  00 00  00 00  00 00  00 A0  FF FF  
46 A6  00 00  00 00  00 00  FF 5F  00 00  
46 A6  00 00  00 00  00 00  FF 5F  00 00  
46 A6  00 00  00 00  00 00  FF 5F  00 00  
46 A6  00 00  00 00  00 00  FF 5F  00 00  
46 A6  00 00  00 00  00 00  FF 5F  00 00  
46 A6  00 00  00 00  00 00  FF 5F  00 00  
46 A6  00 00  CC 4C  00 00  00 A0  FF FF  
46 A6  00 00  CC 4C  00 00  00 A0  FF FF  
46 A6  00 00  CC 4C  00 00  FF 5F  00 00  
46 A6  00 00  CC 4C  00 00  FF 5F  00 00  
00 C0  00 00  67 66  FF FF  00 00  00 00  
00 C0  00 00  67 66  FF FF  00 00  00 00  
00 C0  00 00  67 66  FF FF  00 00  00 00  
05 80  4E 69  3E F0  C1 02  00 00  8C F0  
00 00  DC FB  8C F0  00 00  24 04  8C F0  
00 00  DC FB  B0 F4  00 00  B0 F4  8C F0  
00 00  24 04  B0 F4  00 00  50 0B  00 F0  
00 00  00 00  3E F0  C1 02  00 00  8C F0  
00 00  DC FB  B0 F4  00 00  B0 F4  00 F8  
00 00  25 F2  1F F8  C1 02  5A F2  00 F0  
00 00  00 00  3E F0  C1 02  00 00  8C F0  
00 00  24 04  B0 F4  00 00  50 0B  00 F8  
00 00  DB 0D  1F F8  C1 02  A6 0D  00 F0  
00 00  00 00  00 F8  00 00  25 F2  00 F0  
00 00  00 00  00 F8  00 00  DB 0D  B0 F4  
00 00  B0 F4  1F F8  C1 02  5A F2  DC FB  
00 00  8C F0  B0 F4  00 00  50 0B  1F F8  
C1 02  A6 0D  DC FB  00 00  74 0F  DC FB
## Post #5
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-04-30T12:31:25+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

i have no idea where to even start 
do you think you can help me make a script for 3dsmax or blender or even export them to obj or 3ds whatever is easier for you 
i can make a small donation for you help i need the 3d an uv data 
Please and thanks in advance
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-30T15:31:15+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

> Reply from Joserod1980
>
> do you think you can help me make a script for 3dsmax or blender or even export them to obj or 3ds whatever is easier for youWhat does that exactly mean: "help me make a script"?
Do you know max script or blender python?

I can help people to help themselves but I don't perfom tasks/jobs.

Before you can write a script you need more infos about the model format.

You could ask the "someone" where the vertices to start because it's a little bit tedious to search for
in PS2 model files.

There's 186 findings of "000800 040100 010480" in unknow[n]_002.str.
That doesn't mean that there's 186 vertex blocks contained, does it?
## Post #7
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-04-30T21:55:02+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

I hope you read the part when i said that i can pay for your help i didnt mean to sound like im giving you a task
i will start learning i really hate to bother people its just that i have 0 experience i dont even know where to start
i tried before but it doesnt even start to make sense all of the hexadecimal and all the numbers
if anyone can help please let me know Thank you
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-30T22:28:30+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

> Reply from Joserod1980
>
> I hope you read the part when i said that i can pay for your help i didnt mean to sound like im giving you a taskyeah, I know. I didn't want to sound rude.  
But that's just a relaxing hobby for me so I don't work for money here.

> i will start learninggood news. 

> its just that i have 0 experience i dont even know where to start
>
> i tried before but it doesnt even start to make sense all of the hexadecimal and all the numbers
You could try out the tutorial (button 'tut') of hex2obj (view link in my sig).

(Maybe you can request the above mentioned vertex start addresses?)
## Post #9
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-04-30T23:47:01+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

this is the message he sent me 



vertexes start at every occurence of \x00\x08\x00\x04\x01\x00\x01\x04\x80
There will be multiple ones in a file.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-01T09:11:55+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

I get something similar when loading the obj files (without face indices):



Toyota_map.JPG (37.11 KiB) Viewed 208 times



It's a plane, yes. But this shall be a map? Really?
## Post #11
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-05-01T10:33:00+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

this is yamaha stadium i think it looks a little like the pic i posted but it looks imcomplete

i think you are doing toyota this is what it look in the game 


in the pc game the stadium was divided in parts up down left and right to hide the part when it was not visible
during gameplay im not sure if maybe its divided in more of the unknow files
Thank again for your help
## Post #12
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-05-01T10:48:51+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

i almost forgot let me show you this i use the export obj function on the pcsx2 emulator but the model come really stretch out with perspective thats why i couldnt use it
maybe this pic might help visualize the points you extracted i think its so many points because of all the meshes use for the crowd textures in this pics the yellow lines
are the stadium and all the other triangles are the crowd meshes
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-01T11:33:10+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

not sure whether "someone's" suggested format is correct.
I tried it like this (one obj file only) and it looks more interesting (not flat, 3 dimensions):



mesh_format.JPG (37.22 KiB) Viewed 202 times


Sadly I don't have the time to do further investigations.
## Post #14
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-05-01T18:45:28+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

WOW thats really great but this is what happen last time the guy helping me he didnt have time anymore
and like this time when i was getting really excited to finally have this stadiums 
can you please share what you use to transfer the complete stadium to blender even just the points
maybe i can still do something from them 
hopefully if you later have time you can help me finish please Thank you for everything
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-02T06:52:50+00:00
- Post Title: $40 for Help Exporting Stadiums from a ps2 game

> Reply from Joserod1980
>
> WOW thats really greatwell, it's not better than before:



Yamaha_notBetterThanBefore.JPG (45 KiB) Viewed 184 times



> can you please share what you use to transfer the complete stadium(as you can see above it doesn't look like a stadium) I used plain "c" such like this:

```
		fprintf( stream, "v ") ;
		for (k=0;k<3;k++) {
			for (i=0;i<2;i++) {									// 1x Word
				nValue[i] = (*pFBuf & 255) ; pFBuf++ ; j++ ;							
			}			
            lPosXYZ= nValue[0] + nValue[1]*256 ;
            if (lPosXYZ>32767) lPosXYZ -= 65536;
			fprintf( stream, "%f ", lPosXYZ/32767.0) ;
			pFBuf += 2 ; j += 2 ;
		}				
		fprintf( stream, "\n") ;
	}
```


I could include it into the Make_H2O project ([viewtopic.php?f=29&t=12756](http://forum.xentax.com/viewtopic.php?f=29&t=12756)).
It's not required to read/understand the crash course
but you'll need to know "C" to make senseful use of the above code.
## Post #16
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-05-02T07:16:05+00:00
- Post Title: Re: Please Help Exporting Stadiums

what do you mean include it into the project you mean the stadium files?
if so yes please perhaps during that phase you will find something new to fix it
and one question i was reading the hex2obj tutorial sorry for this stupid question
but i have 0 experience with this can u please tell me what hex editor u use on the tutorial and stadium files 
i tried the ones you suggested but it seem different from the pics you posted even the offset are different 
i see japanese letters on the right its totally different from the pics theres a lot of settings legacy unfiltered
defaul ansi default ascii unicode and a lot of other stuff and i have no idea
how to make it look the same i just want to follow the tutorials easier thanks
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-02T07:46:27+00:00
- Post Title: Re: Please Help Exporting Stadiums

> Reply from Joserod1980
>
> what do you mean include it into the project you mean the stadium files?
I meant to include the shown "C" code which allows to print out some pixels which don't appear to be a stadium.

> if so yes please perhaps during that phase you will find something new to fix itI would do if you knew "C".
I won't waste time on it if you don't.
And I surely won't find something new during the phase of copying a code snippet from one project to the other.

My hopes were to motivate you to help yourself. I'm too busy with other projects.

> can u please tell me what hex editor u use on the tutorial and stadium files 
>
> i tried the ones you suggested but it seem different from the pics you posted even the offset are different
It's an evaluation copy of WinHex. But any hex editor should do. The offsets are a matter of the entered start address and the count of bytes per row. (Seems you'll have to start from the very, very beginning.  )

> i see japanese letters on the right its totally different from the pics theres a lot of settings legacy unfiltered
>
> defaul ansi default ascii unicode and a lot of other stuff and i have no idea
>
> how to make it look the sameThat's a matter of localization. You can completely ignore the hex code's ASCII representation on the right. (It is just helpful to find strings and patterns easier.)
The font is WinHex Big (Options/General).
## Post #18
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-05-03T07:34:16+00:00
- Post Title: Re: Please Help Exporting Stadiums

Yes i will learn im already reading everything i can find 
it will take long as you can see from my questions i have 0 skills in hex and programming
but im really interested in all of this i think its amazing what you guys do 
do you think C is the best for a person as stupid as me to try to learn first?
and thank you for your patience
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-03T11:27:54+00:00
- Post Title: Re: Please Help Exporting Stadiums

> Reply from Joserod1980
>
> do you think C is the best for a person as stupid as me to try to learn first?First of all:
change your attitude.  
You're NOT stupid.

"C" is feared by some people because of its use of pointers. They prefer C# (C sharp) or java.

You could check for QBasic (QB64 for newer windows versions):
[http://www.schoolfreeware.com/Freeware_ ... nload.html](http://www.schoolfreeware.com/Freeware_QB64_Download.html)
There's a link to Visual Basic (Express, free), too.

But maybe you'd try out java:



java-Drawlines.JPG (35.67 KiB) Viewed 297 times



Get the java code from here:

[http://stackoverflow.com/questions/5801 ... es-in-java](http://stackoverflow.com/questions/5801734/how-to-draw-lines-in-java)
post from Andrew Thompson as of Apr 27 '11, "DrawLines.java"

copy it to DrawLines.java

create a manifest.txt file with this contents:

```
Main-Class: DrawLines
```

(Don't forget to press ENTER after "Main-Class: DrawLines" before saving the manifest.txt)

Copy the java and the txt file into a folder of your choice.

With java installed do a build on the command line (in the folder the java file is contained in):
javac DrawLines.java

Then create a jar file:
jar cvfm drawl.jar manifest.txt *.class

c: create a JAR file, v: verbose, f: out to a file (here: drawl.jar), m: use manifest file

in the command line type
drawl.jar [ENTER]

(You could doublelick the jar file in an explorer window, too.)
Then learn java if you think that's something you could deal with. 

btw: you wouldn't use the command line. (That's reserved to nerds like me.  )
I would suggest using a java IDE like NetBeans for example.
## Post #20
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-05-06T16:16:59+00:00
- Post Title: Re: Please Help Exporting Stadiums

Hi shakotay i started reading tutorials do me a favor i saw on other post that you are really fast and good with hex2obj
can you please take a look at this file and tell me if you can open it there and please tell me if this would be a good
first model for me to try to open thank you for all your help
[http://www4.zippyshare.com/v/nqJ7gMic/file.html](http://www4.zippyshare.com/v/nqJ7gMic/file.html)
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-06T18:02:29+00:00
- Post Title: Re: Please Help Exporting Stadiums

> Reply from Joserod1980
>
> can you please take a look at this file and tell me if you can open itfrom a first glance it seems to be compressed. (Maybe try offzip on it.)

> there and please tell me if this would be a good first model for me to try to openthere are dozens of simpler model examples hex2obj was used on. Maybe try out one of them?
## Post #22
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2015-11-07T07:33:27+00:00
- Post Title: Re: Please Help Exporting Stadiums

Hey guys please i hope someone can help
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-26T11:23:46+00:00
- Post Title: Re: Please Help Exporting Stadiums

yeah, this forum is full of posts like this one: "please someone can help me?"

But what do you guys do once you've being helped?
Why not use the infos you were given to proceed for yourself?

This is what the helpers (me at least) expect in a research forum.

Try to gain some basic coding skills to at least be able to read bytes from a binary file, for example.

Anyway, I used the code snippet from my post as of Sat May 02, 2015 7:52 am to get Toyota stadium.

Something is still wrong but the approach seems to make sense:



Toyota_stadium.jpg (230.52 KiB) Viewed 256 times


(836 submeshes)

Face indices still missing; maybe they have to be autocreated.
## Post #24
- Username: Acewell
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-26T16:35:24+00:00
- Post Title: Re: Please Help Exporting Stadiums

> Reply from shakotay2
>
> 
Face indices still missing; maybe they have to be autocreated.

It's a PS2 game so that's very likely. There might be a flag within each vertex specifying the draw direction etc. I'd take a look but the provided model files are too large.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-26T21:31:06+00:00
- Post Title: Re: Please Help Exporting Stadiums

Autocreated face indices such as f 1 2 3, f 4 5 6 don't produce good results:



autoFIs.jpg (86 KiB) Viewed 240 times


(using tri strips it looks even worse)

(I could try something like f 1 2 4
f 3 5 6
or something like that but to be honest, I'm lacking in some motivation for such.)
## Post #26
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-26T22:00:28+00:00
- Post Title: Re: Please Help Exporting Stadiums

How are you generating the face indices? Can I see the code?
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-26T23:12:15+00:00
- Post Title: Re: Please Help Exporting Stadiums

```
{	
	int faceDir, startDir= -1 ;
	WORD a=0, b=1, cnt=0, f1,f2,f3 ;

	f1 = a + 1 ;
	f2 = b + 1 ;
	faceDir = startDir ;
	do {
		cnt++ ;	f3 = cnt ;
		faceDir *= -1 ;
		if ((f1!=f2)&&(f2!=f3)&&(f3!=f1)) {
			if (faceDir > 0) fprintf( stream, "f %d %d %d\n", f1, f2, f3 ) ;
			else fprintf( stream, "f %d %d %d\n", f1, f3, f2 ) ;
		}
		f1 = f2 ;
		f2 = f3 ;
	} while (cnt < VertexCount) ;
}
```


But it looks like it were a problem of duplicate vertices:

g sm_225
v -0.609699 -0.965056 0.000000 
v -0.609699 -0.965056 0.000000 

v -0.603565 -0.960631 -0.161901 
v -0.603565 -0.960631 -0.161901 

v -0.603565 -0.960631 0.161962 
v -0.603565 -0.960631 0.161962 

v -0.597461 -0.956236 -0.323862 
v -0.597461 -0.956236 -0.323862 

v -0.597461 -0.956236 0.323893 
v -0.597461 -0.956236 0.323893 

v -0.585192 -0.947386 -0.485794 
v -0.585192 -0.947386 -0.485794 

v -0.585192 -0.947386 0.485824 
v -0.585192 -0.947386 0.485824 

v -0.578448 -0.932279 0.000000 
v -0.578448 -0.932279 0.000000
[...]

well, removing the duplicate vertices did the trick (more or less and for one submesh only):



duplicateVerts_removed.jpg (117.64 KiB) Viewed 226 times
## Post #28
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-03-15T01:58:45+00:00
- Post Title: Re: Please Help Exporting Stadiums

thanks for everything
i have ask for some guidance from other people here on the forums and none of them even answer
thats why its a bit harder for someone like me to understand very basic stuff ,i feels like im bothering 
and i dont feel comfortable asking more stuff thats why i just let it die of course im interested specially in getting the 3d models
but i guess i have to do it on my own you are the only one that have really answer any of the stuff i asked and i really appreciated 
i even asked a simple question about ripping stuff from google earth a couple of months a go and no one even notice on the ninja ripper post.
thanks for everything
## Post #29
- Username: metalex
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 18, 2016 2:48 pm
- Post datetime: 2018-04-05T06:25:05+00:00
- Post Title: Re: Please Help Exporting Stadiums

> Reply from shakotay2
>
> Code: Select allvoid build_TriList (WORD VertexCount)
{	
	int faceDir, startDir= -1 ;
	WORD a=0, b=1, cnt=0, f1,f2,f3 ;

	f1 = a + 1 ;
	f2 = b + 1 ;
	faceDir = startDir ;
	do {
		cnt++ ;	f3 = cnt ;
		faceDir *= -1 ;
		if ((f1!=f2)&&(f2!=f3)&&(f3!=f1)) {
			if (faceDir > 0) fprintf( stream, "f %d %d %d\n", f1, f2, f3 ) ;
			else fprintf( stream, "f %d %d %d\n", f1, f3, f2 ) ;
		}
		f1 = f2 ;
		f2 = f3 ;
	} while (cnt < VertexCount) ;
}

But it looks like it were a problem of duplicate vertices:

g sm_225
v -0.609699 -0.965056 0.000000 
v -0.609699 -0.965056 0.000000 

v -0.603565 -0.960631 -0.161901 
v -0.603565 -0.960631 -0.161901 

v -0.603565 -0.960631 0.161962 
v -0.603565 -0.960631 0.161962 

v -0.597461 -0.956236 -0.323862 
v -0.597461 -0.956236 -0.323862 

v -0.597461 -0.956236 0.323893 
v -0.597461 -0.956236 0.323893 

v -0.585192 -0.947386 -0.485794 
v -0.585192 -0.947386 -0.485794 

v -0.585192 -0.947386 0.485824 
v -0.585192 -0.947386 0.485824 

v -0.578448 -0.932279 0.000000 
v -0.578448 -0.932279 0.000000
[...]

well, removing the duplicate vertices did the trick (more or less and for one submesh only):
duplicateVerts_removed.jpg
hi dude 
How is this going on the export of stadiums from ps2 to blender?

Can one doubt export them backwards?
As in pc it could be in ps2?
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-05T16:03:30+00:00
- Post Title: Re: Please Help Exporting Stadiums

> Reply from metalex
>
> Can one doubt export them backwards?We'd need a proper export to obj first.
## Post #31
- Username: fabvitor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 29, 2020 12:30 am
- Post datetime: 2020-02-28T17:09:43+00:00
- Post Title: Re: $40 for Help Exporting Stadiums from a ps2 game

Hello friend, can you send me what you got?  I extract faces and hair from the feet of PS2, now I will try stadiums
## Post #32
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2020-04-08T02:46:29+00:00
- Post Title: Re: $40 for Help Exporting Stadiums from a ps2 game

On the first post the link still works for the files please tell me if you need something else
