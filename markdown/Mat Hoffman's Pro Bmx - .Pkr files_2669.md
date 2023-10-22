## Post #1
- Username: homezO
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 28, 2007 12:52 am
- Post datetime: 2007-06-28T12:33:36+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

Sup guys i am new here, a friend told me i might could get help here.

I am looking for a program that is able to open the mat hoffman format: .pkr, its a 240mb big file in which music and movies of the game are located..so basically its like a .rar file (i just want the music, cant find all songs seperately and theres no soundtrack).
I tried alot of game-unpackers and some tony hawk's pro skater 2 (same game engine i think) .pkr tools aswell but nothing worked.
Only things i got so far are the vids (.bik), got them with a program called dragon unpacker.
One of the thps2 .pkr unpackers at least is able to read it..kind of..

but as u can see it just shows crappy stuff and wont export anything
I'm looking for this soundtrack/a way to extract it for quite some time now..any help is appreciated =)

Just for the fact that there's no demo and the file itself is too big i used that filecutter thingy to attach a part of the file here, hope that helps, otherwise please tell me how i could help with getting this done.
edit: just noticed that i cant cut it down to 256kb so i just ul'ed it to my funpic ftp: [http://hom3boy.ho.funpic.de/media.pkr](http://hom3boy.ho.funpic.de/media.pkr)

And i'll post 3 programs for thps2 which partly or fully unpack the thps .pkr, but as i said..they dont really work with the mat hoffman's .pkr

> Allpkr is the best program yet to import and export textures and other data into thps2. In our Tutorials we will point to this program a lot of times. Please download it here.
>
> http://members.lycos.nl/thpscenter/thps ... kredit.zip

> Repkr is a DOS program that lets you import bigger files into the all.pkr. This program is very good but command line based so you have to type everything in which is quite anoying please use Allpkr for some real editing.
>
> http://members.lycos.nl/thpscenter/thps ... /unpkr.zip

> The first program for viewing the files in all.pkr. This is a great program for unpacking whole directories out of the all.pkr but this program can't import them!
>
> http://members.lycos.nl/thpscenter/thps ... /unpkr.zip

I think thats all i can tell you about this.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-02T20:54:58+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

Okay, it would be cool to have a large (whole) file of this, but can you tell the size in bytes of media.pkr? 

Here's what I can gather so far:

```

00 	byte{4}		Magic Word ("PKR3")
03	uint32{4}	Offset of tail

// Data

07	data		Start of first resource


//Tail (the virtual offset I guessed from the snippets)

00	uint32{4}	Number of folders
03	uint32{4}	Number of resources

	// for each folder

	byte{32}	Folder name
	uint32{4}	Sum of resources in previous folders
	uint32{4}	Number of resources in current folder

	// for each resource

	byte{32}	Resource name
	uint32{4}	Unknown
	uint32{4}	Unkown, probably a separator
	uint32{4}	Resource absolute offset in archive
	uint32{4}	Resource size (OR COMPRESSED SIZE!!)
	uint32{4}	Resource size (OR UNCOMPRESSED SIZE!!)

Notes:

The resources are listed in the order of the folders. 
So if the first folder contained 4 files, then the first 4
resources in the resource list will be those, etc. 

Also, the size of the resources were listed twice in my example, 
this probably means that compression may be used
on other resources in other archives. 

```
## Post #3
- Username: homezO
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 28, 2007 12:52 am
- Post datetime: 2007-07-03T00:19:21+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

Hm, okay..i'll upload the media.pkr but will take some time, i'll edit later.
The exact size is 247.121.944 Bytes, and thx for your effort so far :p
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-03T05:44:15+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

Ok, and could you also cut other PKR files, that might contain other types of data? In the media.pkr file there are only BIK movie files that are not compressed. I'd like to see if the format does take into account compression. Thanks!
## Post #5
- Username: homezO
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 28, 2007 12:52 am
- Post datetime: 2007-07-03T08:55:12+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-03T22:12:29+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

Okay, exactly like I thought. And the files are either compressed using Zlib or not. 

Due to MexScript not being all too flexible, I have to create two scripts, one to extract the compressed ones and one to extract the uncompressed ones. 

There are attached here. I used it on the media.pkr file (uncompressed) and extracted the BINK Video files in there that played neatly with 
[http://www.radgametools.com/bnkdown.htm](http://www.radgametools.com/bnkdown.htm)

The GRAF then is:

```
// Header

00    byte{4}      Magic Word ("PKR3")
03   uint32{4}   Offset of tail

// Data

07   data      Start of first resource


//Tail 

00   uint32{4}   Unknown
00   uint32{4}   Number of folders
03   uint32{4}   Number of resources

   // for each folder

   byte{32}   Folder name
   uint32{4}   Sum of resources in previous folders
   uint32{4}   Number of resources in current folder

   // for each resource

   byte{32}   Resource name
   uint32{4}   Unknown
   uint32{4}   If -2 then the resource is uncompressed, if 2 then it's compressed
   uint32{4}   Resource absolute offset in archive
   uint32{4}   Uncompressed Size
   uint32{4}   Compressed size

Notes:

The resources are listed in the order of the folders.
So if the first folder contained 4 files, then the first 4
resources in the resource list will be those, etc.

```

[pkr_mexscripts.zip](https://xentaxbackup.github.io/file/1245_pkr_mexscripts.zip)
## Post #7
- Username: homezO
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 28, 2007 12:52 am
- Post datetime: 2007-07-04T01:11:07+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

Good work =) thanks alot.

Edit: I can open the data.pkr with the pkr_compressed.txt but cant open the media.pkr with none of both txt's, with the uncompressed.txt it loads 1/8 and then says "Process listfile failed: 13-Type mismatch", compressed.txt just says "MEX Empty list file".
Well the Media.pkr is the main thing to me because the music files must be located there, so do i do anything wrong?
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-04T13:27:09+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

1. Check you have the right version of MultiEx Commander (4.3.0) and open with the MexScript option. First point to the .txt file and then choose the pkr file. 
2. I tried it at another computer and I could open media.pkr with no problems
3. There's no music in the media.pkr file, only Bink video files. 
4. If it still fails, hit CTRL-L after it does and sent me the text of the debug.log. 

Thanks.
## Post #9
- Username: homezO
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 28, 2007 12:52 am
- Post datetime: 2007-07-04T15:14:27+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

Okay i ran the files from CD and now it works, and you are right the music files are not in media.pkr, so thank you very much for your help   
Finally i can extract the music :>
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-04T16:12:08+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

No problem. That's what we do .
## Post #11
- Username: bAstimc
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 23, 2007 4:33 am
- Post datetime: 2007-07-05T14:31:18+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

nice homeb0
## Post #12
- Username: PowerofNOS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 26, 2008 12:58 am
- Post datetime: 2008-01-27T16:59:32+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

Hi 

I'm also interested in the music of MH Pro BMX. 
at the end homezO had written, that he had extracted the music of Mat Hoffmanns Bro BMX but i don't really know how he had done this!!
can anyone give me a small description, how i can extract the music???

Thanks 
Power of NOS
## Post #13
- Username: homezO
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 28, 2007 12:52 am
- Post datetime: 2008-06-03T14:11:10+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

Sorry for the bump and that I haven't checked back earlier, but to answer your question PowerofNOS:
If you want to extract them, use the multiex commander thingy BMS->run mexscript on...->pick the pkr_uncompressed.txt and then pick the data.pkr, as I mentioned, it didn't work when I tried to extract it from my hdd but it worked when I ran it off the CD.

PM me if you still can't get it to work, maybe we should talk in MSN or some other messenger.
## Post #14
- Username: PowerofNOS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 26, 2008 12:58 am
- Post datetime: 2008-09-16T13:37:28+00:00
- Post Title: Mat Hoffman's Pro Bmx - .Pkr files

He homezO

everything worked perfect - i extracted it to .bik files
then i used Rad Video Tools to convert it into .wav files
and then i just use db poweramp for mp3 files

thanks a lot homezO

greetz Power of NOS
