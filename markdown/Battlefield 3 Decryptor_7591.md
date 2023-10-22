## Post #1
- Username: mojobojo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 26, 2011 3:25 am
- Post datetime: 2011-10-30T01:31:38+00:00
- Post Title: Battlefield 3 Decryptor

Probably not good for a first post but there is no introduction forum so might as well get posting instead of lurking. I reversed the game and figured out the encryption used on the BF3 resources with the 0x00D1CE00 header magic. Just run it once on the file to decrypt it, and once again to re-encrypt it. The crypto is just a simple XOR encryption with a per-file key and a constant.

Source is included. Compile for linux with "gcc -Os bf3decrypt.c -o bf3decrypt"

Source
[https://github.com/mojobojo/PublicXboxS ... 3decrypt.c](https://github.com/mojobojo/PublicXboxStuff/blob/master/Applications/CrossPlatform/BF3/bf3decrypt.c)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-30T01:39:00+00:00
- Post Title: Battlefield 3 Decryptor

cool, thanks! will give it a try when the game comes down in price! got any sample model files for the guys to work with?
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2011-10-30T19:56:55+00:00
- Post Title: Battlefield 3 Decryptor

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: panz0r
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 31, 2011 8:32 am
- Post datetime: 2011-10-31T00:37:37+00:00
- Post Title: Battlefield 3 Decryptor

> Reply from mojobojo
>
> Probably not good for a first post but there is no introduction forum so might as well get posting instead of lurking. I reversed the game and figured out the encryption used on the BF3 resources with the 0x00D1CE00 header magic. Just run it once on the file to decrypt it, and once again to re-encrypt it. The crypto is just a simple XOR encryption with a per-file key and a constant.

Source is included. Compile for linux with "gcc -Os bf3decrypt.c -o bf3decrypt"
http://dl.dropbox.com/u/45861203/bf3decrypt.zip
I have no idea what about these files and whatnot. I just want to know the weapon files, so I have a noob question. What did it do, me clicking on the bf3decrypt.exe? A cmd window popped up and then disappeared right away. =S Also, could you post the numbers? Thanks!
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-31T02:10:41+00:00
- Post Title: Battlefield 3 Decryptor

Works great decrypting the toc files, what about using these to extract the sb files contents?
## Post #6
- Username: RGGZOR
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 30, 2011 5:38 pm
- Post datetime: 2011-11-02T04:29:25+00:00
- Post Title: Battlefield 3 Decryptor

How do I use this tool? I want to translate the game and I'm running after opening the files from BF3.
## Post #7
- Username: General Shepherd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 03, 2011 5:21 am
- Post datetime: 2011-11-02T21:26:46+00:00
- Post Title: Battlefield 3 Decryptor

> Reply from panz0r
>
> 
I have no idea what about these files and whatnot. I just want to know the weapon files, so I have a noob question. What did it do, me clicking on the bf3decrypt.exe? A cmd window popped up and then disappeared right away. =S Also, could you post the numbers? Thanks!

You can't run it just clicking on the exe file. Open the console, go to the folder where is the bf3decrypt.exe, then type:

bf3decrypt [input file] [output file]

Obviously, change the [input file] and [output file] for the correct names of the files that you're trying to open.
## Post #8
- Username: mitsuhiko
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 29, 2011 9:30 pm
- Post datetime: 2011-11-03T22:29:13+00:00
- Post Title: Battlefield 3 Decryptor

> Reply from OrangeC
>
> Works great decrypting the toc files, what about using these to extract the sb files contents?
The toc and sb files are not too useful. They basically just group things together and have some payload. However the general format is used in more places.  I outlined the basic file format here: [https://github.com/mitsuhiko/frostbite2 ... ter/README](https://github.com/mitsuhiko/frostbite2-stuff/blob/master/README)

The same repository has a parser for these files and the code for decrypting and some other things we already found.
## Post #9
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-11-08T08:24:16+00:00
- Post Title: Battlefield 3 Decryptor

could you provide an executable for these. Because, I have never compiled a python project.
## Post #10
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-11-08T10:11:00+00:00
- Post Title: Battlefield 3 Decryptor

If you install the Python, you can run the .py files. No compiled .py file.
## Post #11
- Username: seanpual123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 10, 2011 6:52 pm
- Post datetime: 2011-11-10T10:59:04+00:00
- Post Title: Battlefield 3 Decryptor

This part of battlefield is looking awesome i will buy it soon.
