## Post #1
- Username: Golokopitenko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 07, 2018 5:42 pm
- Post datetime: 2018-03-07T09:56:27+00:00
- Post Title: Mission: Humanity, an extremely hard case

I have been trying to rip the files of this game (an RTS from 2001 by Techland) for literal years with no success. I will try to make it short, do not hesitate to ask for more information if needed.

The game directory looks like this: 


The files I suspect contain the 2D/audio files are the .rsr ones. The .nam folders, when opened with a hex editor (HxD) they look like this:



These directories are not in the game's folder (which only contain some videos used in the game), so I suspect the .nam files act as a some sort of guide for the .exe to pull resources from the .rsr files.
I have also browsed the game's memory (when running) with Cheat Engine and found other files (like .txt, and also .sam and .gfx) that the game would presumably load during gameplay.

Now, I have tried most if not all of the extractors in the Xentax wiki. None work for any of the files (wrong format, and other errors pop up). I have also tried programs like IDA Pro, Poser and Blend. None work.

So this is a tough nut to crack, and I'm out of ideas at this point. How can I extract this game's files?
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-07T21:24:02+00:00
- Post Title: Mission: Humanity, an extremely hard case

upload those .nam (name) and .rsr (resource) pairs, or at least the smallest size pair and we'll have a look.
## Post #3
- Username: Golokopitenko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 07, 2018 5:42 pm
- Post datetime: 2018-03-07T22:49:30+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from AceWell
>
> upload those .nam (name) and .rsr (resource) pairs, or at least the smallest size pair and we'll have a look.

Really?? Thank you very much! Here they are:

[http://www.mediafire.com/folder/tuaws99 ... 82w/shared](http://www.mediafire.com/folder/tuaws99bk3rjs6c,ghjebml1h06h3ez,2dndzq7cm04tkjn,2iy656jz9ebm6gk,b4tz61zq3bu042v,sdo92ktpd4bb1o2,m2desqe0pzkeqyo,edf3qrmvmosr7h5,508p2s36i1j682w/shared)

I uploaded a few other files in case they are needed.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-08T02:00:19+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from Golokopitenko
>
> Now, I have tried most if not all of the extractors in the Xentax wiki. None work for any of the files (wrong format, and other errors pop up). I have also tried programs like IDA Pro, Poser and Blend. None work.

So this is a tough nut to crack, and I'm out of ideas at this point

Just because you'd tried all existing tools without success doesn't mean it's "an extremely hard case".  
The archive structure is rather simple. Structure of the .nam files:

```
	Struct Entry
	{
		Size					Data Type				Name	
		
		0x2F					Char[]					Filename
		0x05					String					"NONE\0"
		0x04					UINT32					FileOffset(to its corresponding .rsr file)
		0x04					UINT32					FileSize
		0x04					UINT32					FileUnzipSize(LZW compression)
	}

```

Now it should be simple to write an BMS script for unpacking.
## Post #5
- Username: Golokopitenko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 07, 2018 5:42 pm
- Post datetime: 2018-03-08T08:48:06+00:00
- Post Title: Mission: Humanity, an extremely hard case

Wow... I eh... I am speechless!

The problem is I don't know much about coding. I don't really understand the code you posted. If it's as simple as you said, would it be feasible that I (with 0 initial knowledge) learn how to do it?

Another thing I'd like to know, the .nam files are just... a list? With a BMS script, would it be using the .nam files to extract the sprites/sounds/etc from the .rsr files?

Again, thank you so much for this! I am extremely excited about all of these good news!
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-08T09:52:45+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from Golokopitenko
>
> 
The problem is I don't know much about coding. I don't really understand the code you posted. If it's as simple as you said, would it be feasible that I (with 0 initial knowledge) learn how to do it?
Well it does require some knowledge of programming. But fortunately you don't have to learn everything to reach your goal.
The first step is to gain a basic understanding towards data types. Maybe this would be a good start: [Terms, Definitions, and Data Structures](http://wiki.xentax.com/index.php/DGTEFF#Terms.2C_Definitions.2C_and_Data_Structures)

Then you can have a look at the QuickBMS document for the scripting part. Also you don't need to master all the commands, but some frequently-used ones will be enough for most tasks. 
However, even though QuickBMS is convenient and powerful for archives unpacking, when you're trying to convert some assets like models to a common format, you'll still feel it weak. 
So I suggest you to learn also a real programming language, like C for example.

> Reply from Golokopitenko
>
> Another thing I'd like to know, the .nam files are just... a list? With a BMS script, would it be using the .nam files to extract the sprites/sounds/etc from the .rsr files?
I can assure you that you'll find the answer after you've read the passage from the link above. But I'll just put it here: 

The .nam files are just index files containing necessary info for reading data from its corresponding .rsr(resource for short) file with the same name. 
This should be referred as one of the most simple archive structures. You can handle such cases within a BMS script using the "open" command.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-09T00:35:21+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from Golokopitenko
>
> Here they are:
http://www.mediafire.com/folder/tuaws99 ... 82w/shared
thanks! this is not a archive i would start learning with, there are simpler ones 
that have all info in a single file and are not compressed which are far easier.   

anyway here is bms script but the output files look incorrect, compression logging is disabled until solution is found.   
open the nam file and the script will find the rsr file if they are next to each other.

```

open FDDE "rsr" 1
comtype unlzw //?? unlzwx
get NAM_SIZE asize
get FOLDER basename
xmath FILES "NAM_SIZE / 0x40"
for i = 0 < FILES
    getdstring NAME 0x2f 
    get NONE string
    get OFFSET long
    //math OFFSET + 12 //???
    get ZSIZE long
    //math ZSIZE - 12  //???
    get SIZE long //??
    string NAME p "%s\%s" FOLDER NAME
    //clog NAME OFFSET ZSIZE SIZE 1
    log NAME OFFSET ZSIZE 1
next i
```


i think the files are not lzw compressed, it tried many different offsets and variations of lzw
implemented in QuickBMS, maybe there is another layer of compression or they are encrypted
or maybe i'm just not doing it right, you should have aluigi on Zenhax take a look, he is a
compression expert.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-09T03:48:13+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from AceWell
>
> anyway here is bms script but the output files look incorrect.
You shouldn't decompress the data like that. There's still a 0xC-byte header which contains the magic "LZW\x20", the unzip size, and the total size of the file. 
So you need to subtract 0xC bytes from the ZSIZE and add 0xC bytes to the OFFSET.

> Reply from AceWell
>
> i think the files are not lzw compressed, it tried many different offsets and variations of lzw implemented in QuickBMS, 
maybe there is another layer of compression or they are encrypted or maybe i'm just not doing it right
As for the compression, some can get the correct results with unlzwx, CREDITS.TXT from mh_ex.rsr for example, while others will not.
So it's possible that they're using a different compression, or something that QuickBMS doesn't support at the moment.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-09T04:54:44+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from Bigchillghost
>
> You shouldn't decompress the data like that. There's still a 0xC-byte header which contains the magic "LZW\x20", the unzip size, and the total size of the file. 
So you need to subtract 0xC bytes from the ZSIZE and add 0xC bytes to the OFFSET.
yep, like i said, 

> Reply from AceWell
>
> .... tried many different offsetsalready tried that with 4,8,12,16 etc just to be sure, and i just posted here the original script i started with and not 
the one with all the debug, comp types and offset/size shifts so the next guy at least have something to start with.   
it won't output correctly anyway until the compression stuff is sorted out.
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-09T05:40:49+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from AceWell
>
> 
yep, like i said, 
AceWell wrote:.... tried many different offsets
I didn't ignore that though. Just wanted to say that if you use unlzwx to decompress CREDITS.TXT from mh_ex.rsr, the output will be a correct one, which'll match the unzip size in the 0xC-byte header. So the header should be handled separately.
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-09T06:27:14+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from Bigchillghost
>
> I didn't ignore that though. Just wanted to say that if you use unlzwx to decompress CREDITS.TXT from mh_ex.rsr, the output will be a correct one, which'll match the unzip size in the 0xC-byte header. So the header should be handled separately.
there is more to it than unlzwx though, it doesn't work for all, best to let aluigi look it over.   
the header info is already being read by the script in the nam file, can just skip the header bytes in the rsr file.
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-09T06:37:34+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from AceWell
>
> can just skip the header bytes in the rsr file.
That's exactly what I mean.
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-09T07:03:24+00:00
- Post Title: Mission: Humanity, an extremely hard case

yes and i said i already tried that, this brings us back to this

> Reply from AceWell
>
> .... tried many different offsets
the script i posted doesn't show that because it was the original draft i 
had and not the debug version because it wasn't 100% functional anyway.   
guess i will edit back into it some things so we can end this unproductive discussion.  

edit
i'm changing it back to what i had because i posted it like that for a reason, i will disable compression logging too.
## Post #14
- Username: Golokopitenko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 07, 2018 5:42 pm
- Post datetime: 2018-03-09T14:22:07+00:00
- Post Title: Mission: Humanity, an extremely hard case

So many replies!

I started making my own code from [this tutorial](https://www.vg-resource.com/thread-28180.html) and I got this thus far:

> endian big
>
> idstring "KYP\x20

But I guess the .rsr and .nam are a different case, since I see the code Acewell posted is telling the .nam file to open the .rsr resource and do a bunch of stuff.

The code he posted extracts part of the files, two folders of the whole directory, which contain .fnt (font files I am sure) and two .flc files, which can be opened with VLC and similars, and are animated sprites.

Honestly I can't quite contain my enthusiasm! How can we make it so the code extracts the whole thing? You guys were saying the compression was the culprit?
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-09T15:42:01+00:00
- Post Title: Mission: Humanity, an extremely hard case

> Reply from Golokopitenko
>
> But I guess the .rsr and .nam are a different case, since I see the code Acewell posted is telling the .nam file to open the .rsr resource and do a bunch of stuff.
They're very similar though. The main difference in this case is that you need to open the resource files (.rsr) additionally. Thus you'll need to handle two files in one script.

> Reply from Golokopitenko
>
> The code he posted extracts part of the files
How can we make it so the code extracts the whole thing?
Actually it extracts all assets with records in the .nam file so there should be nothing unhandled.

> Reply from Golokopitenko
>
> You guys were saying the compression was the culprit?
Yeah, the compression is the key to get the correct output. Weird thing is that some files seem to use different compression algorithms other than unlzwx though they have the same header structure, and there're no other fields specifying the compression types. So you'd better ask aluigi for help on the compression at [ZenHAX](http://zenhax.com/).
