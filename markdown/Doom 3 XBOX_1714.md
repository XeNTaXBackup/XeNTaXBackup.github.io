## Post #1
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2006-01-26T05:36:39+00:00
- Post Title: Doom 3 XBOX

Hey guys I'd like you to take a look at the XBOX version of Doom 3.

Here are sample files:
[http://unhandledexceptions.com/~agret/assets.rar](http://unhandledexceptions.com/~agret/assets.rar)
[http://unhandledexceptions.com/~agret/g ... ll_cut.rar](http://unhandledexceptions.com/~agret/global.d3tfull_cut.rar)

Here is a post from XBOX-Scene:

> Reply from Iron_Forge
>
> 
I had a look at the Doom3 files for xbox over the last few hours...Hit some snags, so I thought I'd post what I have so far...

The GFC files (I assume Game File Collection?), is the index for their respective GOB files (Game Object?)...The GFC files are in big endian...
Code: Select all/* GFC files */
struct mainHeader {
  uint unknown;
  uint gobSize;
  uint indexCount;
  uint fileCount;
}
struct index {
  uint size;
  uint offset;
  uint nextPiece;
}
struct indexThing {
  uint unknown; // CRC maybe?..
}
struct fileThing {
  uint unknown;
  uint unknown;
  uint file;
}
struct fileIndex {
  char[256] path;
  uint unknown;
  uint unknown;
}

The main header is followed by the index (has indexCount elements), followed by the indexThing (also indexCount elements)...These are followed by fileThing (has fileCount elements), and fileIndex (also has fileIndex elements)...

The GOB files just contain the data in blocks (padded to 2048 I believe)...You can get the offset/size from the index...Each block of data starts with STBL and ends with ENBL (start block/end block)...I believe the data between is compressed, but I haven't the foggiest with what...

I also had a look at the d3tfull file...Unlike the GFC, it's little endian...
Code: Select all/* d3tfull file */
struct mainHeader {
  uint unknown;
  uint indexCount;
  uint unknown
}

struct index {
  uint unknown
  uint unknown
  uint unknown
  uint unknown
  uint unknown
  uint unknown
  uint offset;
  uint size;
}


For this file, the offset points to further in the file itself...Your guess is as good at mine what any of this is...It's also possible the mainHeader is larger, and offset/size isn't the last elements in the index...But this seems to fit...
It's not much, and doesn't let you do anything...But hopefully it'll be a start for anyone else who's interested...

Just in case you missed the sample file links, here they are again:
[http://unhandledexceptions.com/~agret/assets.rar](http://unhandledexceptions.com/~agret/assets.rar)
[http://unhandledexceptions.com/~agret/g ... ll_cut.rar](http://unhandledexceptions.com/~agret/global.d3tfull_cut.rar)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-26T09:56:10+00:00
- Post Title: Doom 3 XBOX

Check the link to my Filecutter (follow the Request Rules), its not in java.
## Post #3
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2006-01-27T06:42:49+00:00
- Post Title: Doom 3 XBOX

I get this:

> Reply from fcutter
>
> 
---------------------------
cutter
---------------------------
429 MexZip ActiveX component can't create object
---------------------------
OK   
---------------------------

Running your one.

I found another program that will split the file though so I've used that. Here is the sample for the d3tfull format:

[http://unhandledexceptions.com/~agret/g ... ll_cut.rar](http://unhandledexceptions.com/~agret/global.d3tfull_cut.rar)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-27T07:56:55+00:00
- Post Title: Doom 3 XBOX

Hmm. Seems that error is more frequent. Oh well. You got it done.
## Post #5
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2006-01-30T05:51:05+00:00
- Post Title: Doom 3 XBOX

So any takers for having a look at this file format?
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-02-12T04:52:45+00:00
- Post Title: Doom 3 XBOX

Hmm I would have looked at the files, but obviously I am too late - it just keeps saying that the files are no longer available 

> the splitter provided by this site was coded in java so I obviously need another program seeing how java is the uber sux and all.

Your loss, not mine. If you don't want to use java, thats fine by me, just don't go complaining if I'm the only one who writes a program to do what you want and you can't use it cause you don't want to use Java. Like I said - your loss 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2006-02-12T09:02:37+00:00
- Post Title: Doom 3 XBOX

Yea well it's not so much that java is terribly slow and resource hungry but more the fact that I can't actually run java on this computer, it doesn't like running after you install the japanese language packs.

```
Error occurred during initialization of VM
java.lang.Error: java.io.UnsupportedEncodingException: MS932

C:\Documents and Settings\Agret.PHANTOM.000>

```


I've put the files on a better host now:

[http://unhandledexceptions.com/~agret/assets.rar](http://unhandledexceptions.com/~agret/assets.rar)

[http://unhandledexceptions.com/~agret/g ... ll_cut.rar](http://unhandledexceptions.com/~agret/global.d3tfull_cut.rar)
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-02-23T10:41:51+00:00
- Post Title: Doom 3 XBOX

OK well the files are the same as used in the game Star Wars Jedi Academy (XBox), but I havn't been able to write any plugins for them yet - I need to find something a bit more solid about the archives, like a better directory or something.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
