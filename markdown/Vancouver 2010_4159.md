## Post #1
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-02-21T17:53:25+00:00
- Post Title: Vancouver 2010

Need help extracting this format.

all resource files used by game are in 3 files at GameDir\data\

File_COM.000 - 947mb header: MUSX
FILELIST.000 - 2.3Gb header: MOEGe
File_USA.000 - 5.5mb header: MUSX

If anyone really gonna help me, I'l upload examples, or my be u've already
Thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-07T23:30:27+00:00
- Post Title: Vancouver 2010

upload one of these smallest 000 files
## Post #3
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-03-10T19:25:56+00:00
- Post Title: Vancouver 2010

[http://www.sendspace.com/file/q03sui](http://www.sendspace.com/file/q03sui) here ure

There are all main files except File_COM.000

As I noticed files i need for translation are in FILELIST

Thanks u Aluigi for your try
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-10T23:21:22+00:00
- Post Title: Vancouver 2010

the last part of the bin files is for sure encrypted but I don't know the method (no one-byte xor/rot), so in the meantime the following script should work extracting nameless files:

```
string BLAH += "0"
string BLAH += "0"
open FDDE "bin" 0
open FDDE BLAH 1

get DUMMY long
get BIN_SIZE long
get FILES long
get DUMMY long
get DUMMY long
for i = 0 < FILES
    get DUMMY1 long
    get DUMMY2 long
    get DUMMY3 long
    get DUMMY4 long
    get SIZE long
    get DUMMY6 long
    get DUMMY7 long
    get OFFSET long
    get OFFSET64 long
    if OFFSET64 != 0
        print "Error: QuickBMS doesn't support 64bit numbers"
        cleanexit
    endif
    log "" OFFSET SIZE 1
next i
```
## Post #5
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-03-11T05:59:55+00:00
- Post Title: Vancouver 2010

Yes, you are right. It extracted nameless *.dat files with MOEGx headers
Some of them: [http://www.sendspace.com/file/mgoay3](http://www.sendspace.com/file/mgoay3)
This result is useless if it woudnt be researched too. Thanks anyway
