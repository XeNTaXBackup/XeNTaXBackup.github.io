## Post #1
- Username: skyo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 19, 2008 1:13 am
- Post datetime: 2009-01-25T04:12:32+00:00
- Post Title: Help with a new weird .dat bigfile game

Hi, im new here, i have tried to open&handle this bigfile .dat but doest matter the tool,
this bigfile is not supported yet. Only dragon unpacker can extract a bit using hyperRipper
and only .669 files.

Can someone try, look and add support to this new file?

Download Sample :

```
http://www.mediafire.com/file/gyudzoymhnm/sample.dat.rar
```


Thanks.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-30T12:04:37+00:00
- Post Title: Help with a new weird .dat bigfile game

Where's this file from? What program or game?
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-30T21:09:15+00:00
- Post Title: Help with a new weird .dat bigfile game

They've gone to great lengths to create an algorithm to XOR encrypt the header of this file. Each entry in the header that probably refers to information about a specific file in the archive is 0x100 (256 bytes) in length. 

However, they have divided each 256 byte section of the file up into a grid of 0x20 (32 bytes) columns of 8 bytes. 

Each column has its own logical pattern of XOR bytes that are used to encrypt, some of them a pattern of 8 rows, but some have patterns of 32 rows for instance. 

By simple deduction it is possible to find approx. half of all patterns, because 64 bit (4 byte) values are used as variables, and many of them (especially the third and fourth byte) are 0's. If you XOR 0 with a value, the result is the value you used to XOR with. So 0's in an original file reveal the encryption code right away.  

Of course, the executable calculates this algorithm run-time. 

So, what program uses this file? Some Playstation 2 game?

[EDIT] It also looks like some colums use the same value (so it could be patterns that affect two or more columns pairs)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-01T21:18:38+00:00
- Post Title: Help with a new weird .dat bigfile game

I've got about 60% of algorithms used I think.  It's a pity I don't know the game we are talking about.
## Post #5
- Username: skyo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 19, 2008 1:13 am
- Post datetime: 2009-03-04T00:29:14+00:00
- Post Title: Help with a new weird .dat bigfile game

Sorry and thanks for the help, i been very busy with work and travels.

The game is pyroblazer [http://www.pyroblazer.com](http://www.pyroblazer.com)
You can found a demo on the website.

Thanks anyways, i dont need anymore help with this game.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-03-10T02:24:59+00:00
- Post Title: Help with a new weird .dat bigfile game

for completness in case someone was interested (to the game or to the algorithm, which is interesting imho) the extractor is available at [http://aluigi.org/papers.htm#pyroblazerext](http://aluigi.org/papers.htm#pyroblazerext)
## Post #7
- Username: Entory
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 07, 2011 5:04 am
- Post datetime: 2012-01-27T16:59:19+00:00
- Post Title: Help with a new weird .dat bigfile game

Help me please. How to use this program?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-27T17:37:05+00:00
- Post Title: Help with a new weird .dat bigfile game

it works from the command-line:
create c:\output_folder and then:
pyroblazerext.exe c:\file.dat c:\output_folder

more informations about how to use command-line tools:
[http://aluigi.org/about.htm#howuse](http://aluigi.org/about.htm#howuse)
