## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-02-06T07:50:17+00:00
- Post Title: The Punisher

hello

please unpack vpp files in game The Punisher

thanks
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-06T12:57:36+00:00
- Post Title: The Punisher

Hi there mate 

It looks like it is loosely on this format, but there are a few changes that need to be made, particularly in the File Size area.

```
| Red Faction *.vpp |
+-------------------+

// The archive is based on multiples of 2048

4	Header (206 10 137 81)
4	Version (1)
4	Number Of Files
4	Archive Size

2032	Filler (ie filled to position 2048 using nulls)

// for each file
60	Filename
4	File Size

// after the directory
X	padding to a multiple of 2048 bytes


// The file offsets start at (numFiles * 64) + 2048 + (2048-((numFiles*64) % 2048))
// Where % is the mod function (remainder)

// Also, each file is padded to a multiple of 2048, which must be taken into account when
// calculating the offset to each file.
```


I'm also not sure about the *.tga references further down in the file ( ~offset 4096? ) - I couldn't see any TGA images in there during the brief look that I had - so either it is a bunch of compressed or encrypted images, or it is most probably just an external reference.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-02-07T09:37:41+00:00
- Post Title: The Punisher

hello mr watto

please look this file

or download demo from site : 
[http://www.download.com/The-Punisher-de ... 45018.html](http://www.download.com/The-Punisher-demo/3000-7466_4-10345018.html)
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-09T10:44:41+00:00
- Post Title: The Punisher

Alright, here are the specs...

```
| The Punisher *.vpp |
+--------------------+

// The archive is based on multiples of 2048

4 - Header (206 10 137 81)
4 - Version (3)
4 - Number Of Files
4 - Archive Size
4 - Unknown (64)

2028 - Filler (ie filled to position 2048 using nulls)

// for each file
24 - Filename (null)
4 - File Size
4 - File Size

X - padding to a multiple of 2048 bytes

X - File Data


// The file offsets start at (numFiles * 32) + 2048 + (2048-((numFiles*32) % 2048))
// Where % is the mod function (remainder)

// Also, each file is padded to a multiple of 2048, which must be taken into account when
// calculating the offset to each file.
```


And I have also attached a GameExtractor plugin for you. I will check it against the Voice file above, and if there are any changes that need to be made then I will post here again.

Thanks, and enjoy.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_VPP_2.zip](https://xentaxbackup.github.io/file/113_Plugin_VPP_2.zip)
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-09T10:57:06+00:00
- Post Title: The Punisher

I just tried the plugin with the voice archive you attached - works fine  - assuming that this is only the start of a bigger archive.

Enjoy

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-02-09T22:23:24+00:00
- Post Title: The Punisher

hi mr watto

thank you

very good work plugin on all original arrchives

thanks again
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T02:39:37+00:00
- Post Title: The Punisher

Not a problem mate, glad I could help. Thanks for confirming that it works.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-05-01T09:18:38+00:00
- Post Title: The Punisher

It works for me too, but im' looking now, for the packer.
Any idea/plugin in command line?

Thanks
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-01T14:24:09+00:00
- Post Title: The Punisher

Hey,

Yeah, I did end up writing a packer for this game, but it will only work for the full version of Game Extractor. if you can afford $5 then you will be able to do it. [http://www.watto.org/extract](http://www.watto.org/extract)

Unfortunately, I improved the code in the Full Version so the plugins I write for the full version will not work fully in the basic version.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-05-21T12:28:42+00:00
- Post Title: The Punisher

Hi again  I unpacked the vpp files but...What's this format? the files .ceg and .leg look very compressed, and maybe are textures?

I attach the two files 
[AztecSign.zip](https://xentaxbackup.github.io/file/242_AztecSign.zip)
## Post #11
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-05-21T12:29:47+00:00
- Post Title: The Punisher

The second file
[wep_m16.zip](https://xentaxbackup.github.io/file/243_wep_m16.zip)
## Post #12
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2012-01-08T13:31:50+00:00
- Post Title: The Punisher

bump, i need help too
## Post #13
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2014-08-24T01:58:40+00:00
- Post Title: The Punisher

-
