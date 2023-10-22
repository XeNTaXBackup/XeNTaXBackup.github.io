## Post #1
- Username: stuntpenguin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2016 1:52 pm
- Post datetime: 2016-02-08T06:02:48+00:00
- Post Title: [XBOX] The Godfather .viv archives

I'm trying to figure out how to extract the contents of .viv archive for the game "The Godfather".  The game contains all of it's files other that the executable in these archives names "godfath0.viv" through "godfath4.viv".  It seems like some variant of BIGF.  Each one starts with the "ÂIGH" or "C2 49 47 48" in hex.  The next four bytes indicate the size of the archive.  After that I'd assume to see the offset of the first file,  but the next four bytes don't really point anywhere useful.

I'm able to find a few SCHl .str sound files in the archives.  I've tried taking the address of where those files are found in an effort to search for their offset in hopes of finding some kind of file table but I'm having no luck there either.

I'm willing to bet that the PS2 and PC versions of this game have the same types of archives.

Has anyone encountered this type of archive before?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-02-08T21:20:24+00:00
- Post Title: [XBOX] The Godfather .viv archives

Post a sample, or a chunk of the first few mb and we can take a look
## Post #3
- Username: stuntpenguin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2016 1:52 pm
- Post datetime: 2016-03-08T23:03:12+00:00
- Post Title: [XBOX] The Godfather .viv archives

I think I'm on the right track.  The viv file contains a list of entries in a "file table".  Each entry is three words long.  The words represent: size, offset, and filename hash.  The first few file names (whole path eg "frontend/frontend.str") are hard coded into the xbox executable.

The game starts by hashing the hardcoded string "frontend/frontend.str" and looking for the matching hash in the viv archive file table.

Here is where I'm starting to get stumped.  I believe that once frontend.str has been loaded, it looks for the next file path to load from somewhere within frontend.str.  I've done some debugging and found that the file that loads after frontend.str is frontend_global.str.  If you look at 0x53 in frontend.str, you'll see "frontend_global".

In frontend_global.str at about 0x800 there is a "StreamTOC".  This area of the file lists the directory paths of several other files.  Unfortunately, not all StreamTOC's are as clear.  For example, the StreamTOC in a file called "wb_mobface_final_global.str" is seemingly filled with random bytes and occasionally the broken remnants of a file directory.

Here's an example of a file directory remnant:
Folder\n.%pcådels\nm_newsstandowner_0..0˜.2â

From my experience debugging this game, I know that it should probably be something like:
GlobalFolder\npc_models\nm_newsstandowner_00_model.str

Do you guys think the StreamTOC's could be compressed or encoded in some way?

Here are a few .str files to look at:
[https://mega.nz/#!7MpzDAbK!NoZcvFabxy-W ... 7dWU1sy4LY](https://mega.nz/#!7MpzDAbK!NoZcvFabxy-WQ4jxWbnYFtiJD2HQxng4_7dWU1sy4LY)

Thanks!
## Post #4
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-09T10:30:56+00:00
- Post Title: [XBOX] The Godfather .viv archives

I discussed this format with someone on another forum very recently. I know how the .VIV format works, however the problem is the file names are hashed so there's no point in extracting them unless the location for the filenames are found. A quick way of dumping the names would be to set a breakpoint on the hashing algorithm then dump the string.
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-03-10T00:38:18+00:00
- Post Title: [XBOX] The Godfather .viv archives

how are you debugging this on xbox? is this 360 (so xenia?)
## Post #6
- Username: stuntpenguin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2016 1:52 pm
- Post datetime: 2016-03-10T01:01:03+00:00
- Post Title: [XBOX] The Godfather .viv archives

I'm debugging it on an (original not 360) DVT4 xbox development kit through visual studio 2003.  I have the symbols so it's relatively easy for me to find functions and put breakpoints at them.

I could just make a hook to dump out the file names when they pass through the hashing function, however, I'd like to figure out how this format actually works.  Filenames only pass through the hash function when they are needed, so I'd have to adventure every part of the game and hope I've collected all of the directories.

Think I'm making a little progress by debugging this function
Framework.StreamTOC.InplaceFixup()

Could be searching in the wrong places but I guess I'll find out eventually.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-10T20:39:55+00:00
- Post Title: [XBOX] The Godfather .viv archives

You are wasting your time. This is Visceral Games formats, and these were all reversed long time ago for Dead space 1/2/3. RickVisceral tools are available with source codes included. I bet all the names can also be found with the techniques used for Dead Space. You don't have to play the whole game to do it, you don't have to debug it either.

p.s. yes, some files are compressed.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-11T16:38:19+00:00
- Post Title: [XBOX] The Godfather .viv archives

Full filelist, if you need it.
[gf.rar](https://xentaxbackup.github.io/file/10577_gf.rar)
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-15T16:52:17+00:00
- Post Title: [XBOX] The Godfather .viv archives

So was it helpful? Do you need any more info on this game or engine format?
