## Post #1
- Username: headrift
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 27, 2005 11:19 am
- Post datetime: 2005-11-27T03:38:57+00:00
- Post Title: Metal Heart, .pkg format, and file table encoding?

Hey.  I'm new here.  I'll try not to troll.  

So...  the problem.  A friend of mine (no, really, it's not me) has a copy of Metal Heart that he'd like to mod a little, so we've been trying to crack the .pkg format.

The wiki here was invaluable for the first part of the process.  I've got my little perl script unpacking archives made by the pkg.exe that comes with the game.  The problem I'm up against is the .pkg files that come with the game.  They have the same structure, but the file table, and maybe file data, seems to be encoded.

Best way I have to explain it is this image:

(For image see attachment to post (free registration needed))

The top window is the file table of an archive made with pkg.exe, and the bottom window is from a pkg that came with the game.  Both packages had only one file in them, and the hex in the view is the complete isolated file table from each package.  The top one should be fairly easy to read once you're familiar with [the wiki](http://wiki.xentax.com/index.php/Metal_Heart_-_Replicants_Rampage).

As you can see, the file in the second window doesn't make near as much sense.  I marked out where are the important values should be, as well as the decimal values that should be there, as figured out with a little math.

It's not anything simple.  Bit shifting would leave more 0x00 values, bit masks would leave the same values behind them where the 0x00's are supposed to be at.  It's not anything easy and mathematic that I could find.

So, I've come here hoping for help.  What have they done to my file indices?

TIA,

- head
[notes.png](https://xentaxbackup.github.io/file/477_notes.png)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-11-27T08:34:09+00:00
- Post Title: Metal Heart, .pkg format, and file table encoding?

Welcome! This is the right place to come with those questions. 
I have edited your post so to show the actual image (your host didn't allow direct linking).

What would help is to be able to look at these files ourselves. Can you attach both of these files to a post ? Or, if they are too big, you can use my cutter to provide us with the first and last 1mb part of these files. (See Game Request rules in my sig).
## Post #3
- Username: headrift
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 27, 2005 11:19 am
- Post datetime: 2005-11-27T16:31:25+00:00
- Post Title: Metal Heart, .pkg format, and file table encoding?

Thanks for the reply.  Sorry about the image thing, worked fine here, but I guess I have the right cookie.  

I'll attach the complete pkg files I'm looking at, since the file table for each one is already in that image.  'onefile.pkg' is the source file for the 'selfmade.dat' file visible in the pic.  Again, it's a single-file archive made by pkg.exe.

'load_screens.pkg' is a single-file archive that comes with the game.  It's the one I'm having trouble reading.  The headers on both files are not encoded, and I'm guessing the file data is also not encoded.  The file table on this file is the only portion that seems to be encoded.

I had to put both files into a zip to get them through the file extension screen.  You'll want to unzip before looking at them.  

Hope it helps.
[pkgs.zip](https://xentaxbackup.github.io/file/478_pkgs.zip)
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-11-28T07:47:17+00:00
- Post Title: Metal Heart, .pkg format, and file table encoding?

It certainly looks hashed in some way. The tail part is 0x36 long and should contain unknown, date and time, compressed size, uncompressed size, filename (unicode) string size, filename size, filename string size, filename string. 

As the info is there, I suggest that the authors used some kind of XOR method to XOR the original bytes with a mask/seed byte, that is generated through some (unknown) algorithm for each of the original bytes. 

I haven't figured out what this algorithm is.
## Post #5
- Username: headrift
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 27, 2005 11:19 am
- Post datetime: 2005-11-28T16:29:11+00:00
- Post Title: Metal Heart, .pkg format, and file table encoding?

Thanks for looking at it.  I've been looking at it too, and it seems that there's a different value in every file where the '.' should be in the filenames, or where 0x00 should appear in sizes.  Makes me think that there's a key or digest in one of those 'unknown' areas, since anything stored statically in the program would probably result in similar output values.

That's just a wild guess, though.  I don't know enough about encryption to even start trying to decode these files.    :-/ 

Do you know of any good documents on reversing encryption, or even encryption principles?  Something to bring me up to speed on this?  I'm holding onto the hope that it is reversible in some way.
## Post #6
- Username: headrift
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 27, 2005 11:19 am
- Post datetime: 2005-12-01T18:43:08+00:00
- Post Title: Metal Heart, .pkg format, and file table encoding?

Hey.  Still working on this, read the Definitive Guide to Exploring File Formats, especially the encryption part.

After that, I decided that I'd be crazy to try to brute force this thing by hand, so I wrote some python (switched form Perl, Python has a file.seek() function) that checks for basic shifting and masking.  I've attached it in case anybody has any suggestions for it, since it's not finding anything right now.   :-/

As warning, it's an ugly script.  Only been working in Python for a week or less.
[crack.py.zip](https://xentaxbackup.github.io/file/484_crack.py.zip)
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-03T09:06:51+00:00
- Post Title: Metal Heart, .pkg format, and file table encoding?

OK, I haven't any experience in Python, perhaps Rahly or Captain can take a look at it. 

Your best bet would be to hack the executable. Load it up in some DASM and locate the ASM hash method.
