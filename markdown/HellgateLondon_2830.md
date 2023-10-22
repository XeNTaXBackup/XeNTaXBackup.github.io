## Post #1
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-10-22T08:28:13+00:00
- Post Title: Hellgate:London

Did someone tried to decrypt hellgate? The Demo of this Game is already available.

Download Mirrors:
[http://www.fileplanet.com/176044/170000 ... ondon-Demo](http://www.fileplanet.com/176044/170000/fileinfo/Hellgate:-London-Demo)
[http://www.gamedaily.com/games/hellgate ... 4251/7197/](http://www.gamedaily.com/games/hellgate-london/pc/game-downloads/hellgate-london-demo/4251/7197/)
[http://www.4players.de/4players.php/dow ... 46470.html](http://www.4players.de/4players.php/download_info/PC-CDROM/Download/46470.html)
[http://www.gamedemos.de/index.php?show= ... ls&did=960](http://www.gamedemos.de/index.php?show=demos&action=details&did=960)
## Post #2
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-10-25T12:01:46+00:00
- Post Title: Hellgate:London

Yes, I tried and succeeded 
The unpacker still hot 'n steaming fresh out of the compiler.
It's a simple command-line based unpacker.

You can download the Exe from [http://www.xentax.com/uploads/author/johndoe/unhell.zip](http://www.xentax.com/uploads/author/johndoe/unhell.zip)
and the source code for the interested from [http://www.xentax.com/uploads/author/jo ... ll-src.zip](http://www.xentax.com/uploads/author/johndoe/unhell-src.zip) (needs Dev-Cpp and zlib).

I only tested it with the demo (obviously) so I don't know if it will work with the full version, but I guess they'll change the encryption keys for that.
## Post #3
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-10-25T12:14:53+00:00
- Post Title: Hellgate:London

oh great.

i should test it with the beta. how do you got the enc. keys?
## Post #4
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-10-25T12:16:29+00:00
- Post Title: Hellgate:London

By looking inside the Exe 
If it doesn't work I'll think of something.
## Post #5
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-10-25T21:24:16+00:00
- Post Title: Hellgate:London

i tested it with the beta release and it worked for ~4 files for every .*dat *.idx . After 4-5 files it crashs with an exception.

So i think keys are working. The extracted dds files look good. But maybe they changed something in their fileformat or structure.
## Post #6
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-10-25T21:42:12+00:00
- Post Title: Hellgate:London

Can you send me the idx files to [john_doe@techie.com](mailto:john_doe@techie.com)?
Either they really changed something or it's just a bug
## Post #7
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-11-01T11:15:43+00:00
- Post Title: Hellgate:London

ok it works with the beta. but you have to choose the right zlib1.dll. I found an old one. better you add it to unhell.
## Post #8
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-11-01T13:15:56+00:00
- Post Title: Hellgate:London

Ok, I recompiled the Exe using the static zlib library. It should have used the static one before, somehow it didn't...
## Post #9
- Username: rood_boy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 23, 2006 6:23 pm
- Post datetime: 2007-11-02T11:15:30+00:00
- Post Title: Hellgate:London

fantastic work!, but one question:can a .idx/dat repacker be created?
## Post #10
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-11-14T07:41:53+00:00
- Post Title: Hellgate:London

There are still unknown values which are probably important, so at the moment it's not possible to create/modify the archives.
Also, I won't do any further research on the files and won't make packer.
## Post #11
- Username: rood_boy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 23, 2006 6:23 pm
- Post datetime: 2007-11-15T05:17:11+00:00
- Post Title: Hellgate:London

k tnx for the response
## Post #12
- Username: Fyren
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 10, 2007 2:59 pm
- Post datetime: 2007-12-10T11:21:24+00:00
- Post Title: Hellgate:London

I was poking around the Hellgate archives and noticed a lot of the files are named similar to "strings_skills.xls.uni.cooked".  It's not actually an Excel file (as it is), though it is in a directory named "excel" inside the archive's directory structure.  I suppose it's been encoded/processed/somethinged as suggested by the .cooked.  Some strings in it look like they might be Unicode, so I guess that's the uni.

There are some other files that are .txt.uni.cooked or .xml.uni.cooked, too.  You can find some text if you look in them, but there's a lot of padding, non-text, and repeated series of bytes.  

It seems like image or audio files aren't cooked, though.

Anyone have any ideas about what's been done to these cooked files?
## Post #13
- Username: YellowBiccies
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 20, 2007 10:13 pm
- Post datetime: 2007-12-18T16:27:49+00:00
- Post Title: Hellgate:London

cooked files are files encrypted in the build process. you need to find the encryption key again, decrypt the files into their excel format for some, straight xml for others, then they can be edited.

what would be good is a tool to read those files in the packed state, and edit them, or extract, decrypt, re-encrypt and then pack again.

but i cant see that happening
## Post #14
- Username: Fyren
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 10, 2007 2:59 pm
- Post datetime: 2007-12-19T07:04:50+00:00
- Post Title: Hellgate:London

I don't think they're "encrypted" since there's plaintext that remains in them.  That text would get hidden if they were encrypted.  Unfortunately I don't have the knowledge to poke around in the EXE to see what it's doing, like john_doe did.
## Post #15
- Username: YellowBiccies
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 20, 2007 10:13 pm
- Post datetime: 2008-01-07T06:09:53+00:00
- Post Title: Hellgate:London

not sure, ive had a bit of a look through, but i dont have a lot of time on my hands atm

hopefully someone does, and can lend a hand though
## Post #16
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-07T12:10:17+00:00
- Post Title: 

this is not encrypted. those files are somehow encoded differently.
Strangely there's no common format, cokked xls txt and xml files all have different formats.
But compare a cooked xls with a normal one (e.g. the install strings table)

EDIT: Here's the unpacked version of "Hellgate: London Patch 0.6 SP [MULTI8] Fixed EXE" if someone wants to disassemble the file.
[http://uploaded.to/?id=y69l0u](http://uploaded.to/?id=y69l0u)
## Post #17
- Username: etherdemon
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 05, 2008 2:11 pm
- Post datetime: 2008-03-02T15:44:42+00:00
- Post Title: 

i was wondering if someone knew a way to repack the dat files? unhell is awesome and there have been a couple of retexture mods made using it (thank you) but i was wondering if there was a way to repack some of the more sensitive .dat files like sp_hellgate001 which will crash you client if you leave it sitting uncompressed


thank you

-E
