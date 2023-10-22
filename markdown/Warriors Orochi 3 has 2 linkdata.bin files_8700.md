## Post #1
- Username: mogbee
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 01, 2012 9:09 am
- Post datetime: 2012-04-06T05:56:03+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

Hello.  I'm a little new to all this stuff, but I was finally able to extract DW7's linkdata file with the help of Chrrox's post: [viewtopic.php?f=16&t=6252](http://forum.xentax.com/viewtopic.php?f=16&t=6252)  (Thank you!!)

So now I extracted Warriors Orochi 3's disc and among all the files, I found a linkdata.bin and a linkdata2.bin
Using offzip, i extracted the first one with several errors, and chroxx's maxscript will not import the g1m files. "Unable to convert: undefined to type: float"  so no meshes. The textures don't convert correctly either.
Using offzip on linkdata2.bin file only gives me a big g1t archive.

Can anyone give me a hand??  Basically my big question is why there are 2 linkdata.bin files and what should I do with them.

Thank you, kindly!
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-06T06:03:35+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

Every time a new DW game comes out, they make a number of changes (sometimes small, sometimes large). The old extractor cannot be used; you will have to wait and see if someone is interested in updating it. Unless of course, you want to try to code an extractor yourself; in that case, you can use my DW Gundam code or my One Piece code that's posted somewhere around here and modify that. So best advice is to just sit back and wait for a while since it's a fairly new game (I don't have it yet, it's still $60 so fuck that for now).

If you know how to extract and post samples, you can use a hex editor and post some of the G1M_0034 sections for people to look at. I forget what the texture sections where named... G1TG5000 and G1TG6000 or something like that.
## Post #3
- Username: mogbee
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 01, 2012 9:09 am
- Post datetime: 2012-04-06T06:09:53+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

Gah... should've known! I'll take a look at it and post it if I can figure it out. My coding experience is limited, but what can't one do with the internet?

Thank you 

EDIT: It's really good, btw.  Love the cameo's like DOA's Ayane and friggin Achilles.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-06T06:14:55+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

really? are you serious? in Orochi 3? LOL, you are making me want to walk over to the redbox and see if they have it yet (they won't, redbox sucks).

EDIT: Good news, gamefly has xbox360 version (but not ps3).
## Post #5
- Username: mogbee
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 01, 2012 9:09 am
- Post datetime: 2012-04-06T08:02:05+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

Oh man you GOTTA see the roster. So.Many.Characters! o_o

The PS3 version is download only via PSN.  It's also $10 cheaper than the 360 version.  Idk if this might turn you away from the game, but there isn't an English dub. Doesn't bother me, but it bothers some.  But WOO! Gamefly saves the day.

EDIT:
I don't really know what the G1M_0034 section is in the hex editor... Heh. If you just lemme know what block you need copied, I will be happy to get a sample.
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-06T10:59:32+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

I am japanese. No worries lol. You don't have to post samples; it should take a few days for me to get the game.
## Post #7
- Username: mogbee
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 01, 2012 9:09 am
- Post datetime: 2012-04-06T12:57:01+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

Oh  

And yay! Looking forward to good news!....maybe -fingers crosses-
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-12T11:10:53+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

Almost done with One Piece... then I can move onto Orochi. Hopefully Orochi won't be that hard. One texture in One Piece is swizzled and they added a bunch of new vertex formats. In fact, some of the vertex formats overlap, and there are now different N-byte formats for both static models and animated models. There are also some huge 0x68 byte vertex structures! Seems like with every new DW, Musou, Orochi game that comes out the extraction gets more and more complex. With any luck it should be a similar format to One Piece.

BTW, in general there are multiple linkdata files because one typically stores the sounds and the others store models and textures. However, One Piece kind of stores data all over place and since all their offsets are 32-bit, they can't have a single linkdata file that is likely to one day exceed the 4GB mark.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-12T11:47:08+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

dynasty warriors 7 also had that huge vertex buffer size.
all their games have had it for a while. its some kind of pysics data or cloth simulation or something. I could never get the verts to look correct. Did you get them to look right?
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-13T11:00:17+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

No, most of them look like arches, paths, or crooked lines.
## Post #11
- Username: mogbee
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 01, 2012 9:09 am
- Post datetime: 2012-04-15T15:47:49+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

The One Piece extraction is lookin' gooood.
I like how hard they're trying to make extraction more difficult. No obstacle to you brilliant people!
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-16T17:32:06+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

man, there are all kinds of new chunks in WO3 lol. COLK0000 chunks, OSOG chunks, O2O chunks, ha ha ha chunks up the wazoo.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-16T17:52:31+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

Makes your life easier.
Unless they re-defined existing chunks as well.
## Post #14
- Username: mogbee
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 01, 2012 9:09 am
- Post datetime: 2012-04-16T18:52:30+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

Can I ask what the chunks mean and how it makes life easier?  I'm trying to learn this stuff! Unless there's a post already on it somewhere on Xentax -searches-
## Post #15
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-17T13:04:13+00:00
- Post Title: Warriors Orochi 3 has 2 linkdata.bin files

[The wiki article](http://en.wikipedia.org/wiki/Chunk_%28information%29) is somewhat OK with the definition of chunk (I've seen worse when it comes to CS topics on the wiki like [this](http://en.wikipedia.org/w/index.php?title=Database_model&diff=395717357&oldid=395498749) lol it was like that for years before somebody fixed it ha ha ha took them a year after I complained about it before somebody had the balls to fix it). Love it how they referenced a department of transportation article (rather than a CS book on databases) to get the definition of a database model lol!

But a chunk typically is a fixed-length string identifier, called the chunk identifier (like FORM chunk is used in lightwave), followed by a fixed-length number indicating the size of the chunk in bytes, followed by chunk properties, which can be any length and of any type but not chunks themselves, followed by data, which my also be composed of chunks. Chunk files can be represented by a k-ary tree.

```
 4 + 4 + 4 + 4 + 256*256*4 (4 bytes chunk size)
 256 (width) (4 bytes)
 256 (height) (4 bytes)
 data (256*256*4 bytes)

```
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-17T16:55:40+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

Chunk-based format makes life easier because you can skip all the chunks you don't know or don't care about.
Only problem is trying to handle nested chunks and stuff.

I still haven't come up with a good way to recurse through a chunk-based format even though it's really a matter of writing down all of the cases and then calling itself...
## Post #17
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-17T17:29:38+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

if there are explicit rules governing what types child chunks can be, and what the first chunk must be, you can just write processing functions like

processFORM(...)
processLAYR(...)

and so on and then those function can call more process functions and so on and so on.

```
{
 uint32 bytes_remaining = size;
 while(bytes_remaining) {
     uint32 chunktype = ReadChunkType();
     uint32 chunksize = ReadChunkSize();
     if(chunktype == PNTS) return processPNTS(chunksize);
     if(chunktype == POLS) return processPOLS(chunksize);
     // etc.
     bytes_remaining -= (8 + chunksize);
    }
}

```


But when shit is arbitrary the best way is to parse the whole thing and build a tree and then do a preorder traversal. This is why I loathe thinking about redoing Neptunia MK2 and my PSSG ripper.
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-17T17:32:51+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

I refuse to write the same while loop twice for grabbing a chunk.
I want at most one chunk parser function and no more!
## Post #19
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-17T17:36:11+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

If some other chunk can contain PNTS and POLS then yeah, there is going to be code repetition, but it really is the easy way to do it. There will be only one chunk parser function per chunk. It can also be a nightmare if you have to keep track of several parent nodes up the hierarchy. Like for PSSG:

* TEXTUREIMAGE
**  TEXTUREIMAGEDATA
***    TEXTUREIMAGEDATABLOCK

The width and height and stuff are in TEXTUREIMAGE, nothing is in TEXTUREIMAGEDATA, and the data is actually in TEXTUREIMAGEDATABLOCK. So you have to save all the width and height and stuff and keep it around for a few levels until you hit the TEXTUREIMAGEDATABLOCK so you can save all data when you hit the BLOCK. Sucks it requires a lot of bookkeeping.
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-17T17:47:27+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

I refuse to have repetitive code in my code.
It is not beautiful.
## Post #21
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-17T17:49:41+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

You probably have nightmares looking at my code then huh ?

But repetition is a good thing. We all go to the same job everyday, we all fuck the same GF/wife everyday, visit the same forums, and so on and so on.
## Post #22
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-19T13:47:15+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

The following is just a file extractor; it goes a little further than the one by AlphaTwenty in that it doesn't stop at just processing the files listed in the IDX files. I'm not going to work on the models or extracting textures yet, as I think chrrox is going to help me out on this one. The output of the extract is the following:

LINKDATA directory
 * ANIM directory (contains g1a and g2a files, I think these are animation files)
 * BIN directory (contains mainly useless crap like localization files)
 * GEM directory (contains static models and textures for these models)
 * MODELS directory (contains g1m files)
 * SOUNDS directory (contains wav files)
 * TEXTURES directory (contains g1t files)
 * UNK directory (contains more useless crap)
 * WBD directory (contains WBD and WBH files, I have no idea what these files are for, maybe music and dialog)

It takes a long time to extract all files (30 to 60 minutes) since most of the files are zlib compressed and I spend a lot of time processing archive files and renaming them (there are three types of archive files, first one stores animations, second one stores static models and third one stores those WBD files). Instructions are the same as my other extractors: place binaries in game root directory (where the LINKDATA files are) and run.

In the IDX files, there is a list of 9,000 or so files. When you see a folder like GEM/3872, that's file #3872 in the IDX file, which was an archive file that contains static models, textures, and effects data. In this folder you will find the model's GEM, GFX, and G1T files.

Also for example, if a folder is named MODELS/8721, its textures are most likely stored in TEXTURES/8722 and animations in ANIM/WTFGKW.
[orochi3_extract.7z](https://xentaxbackup.github.io/file/5330_orochi3_extract.7z)
## Post #23
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-20T00:39:38+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

BTW finale, you ever read that book "Beautiful Code?" It's funny cuz after reading that book I came away with one thing... that "Beautiful code is still ugly."
## Post #24
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-20T16:13:40+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

EDIT: thanks! got what i needed!
## Post #25
- Username: mogbee
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 01, 2012 9:09 am
- Post datetime: 2012-04-23T20:49:38+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

Woo! Gonna check it out when I get home. Thank you!
## Post #26
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-23T20:51:27+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

> (30 to 60 minutes)

Lol can you add a simple GUI allows users to choose what they want to extract.

Though, while I say simple, I don't actually know how simple it is to actually display a list of files in a ListView or something cause you'd probably have to store all of the offsets and sizes somewhere. Guess that's something to while aimlessly reading snippets of C++ and C#.

But if you already have something like that then it's a matter of grabbing the GUI and referencing a different set of functions.
## Post #27
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-23T21:13:07+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

Remember, all it is so far is just an unpacker. Doesn't extract models yet. This is going to be a doozy lol. There is a lot of cloth in these games and no one's been able to figure out the vertex format for cloth geometry. I still haven't gotten full character geometry from one piece. Only partial.
## Post #28
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-23T21:21:44+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

In fact, I'm taking a day or two break from working on this to work on something else... something I'd thought would be easier... and even that's fighting me   ha ha ha.

What I get:


What it should look like:
## Post #29
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-04-30T21:38:37+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

Any news?
## Post #30
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-30T21:47:25+00:00
- Post Title: Re: Warriors Orochi 3 has 2 linkdata.bin files

still working on it. cloth vertex formats remain a problem. for example, half of Monkey's shirt (one piece) i cannot decode. without it he looks like some guy getting ready to hit a gay bar lol. also taking a break from it to work on another game. hopefully will come back to it soon with fresher eyes. if anyone else wants to work on the extracted files in the meantime, be my guest...
