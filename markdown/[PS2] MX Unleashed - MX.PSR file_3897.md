## Post #1
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-11-27T17:45:13+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

Hi all,

in the forum I have found a post with something about *.res files in the MX Unleashed game for XBox and PS2.
I've looked at my games DVD and found only a really big file (2GB), called MX.PSR. Opened in Hex Workshop I saw the *.res files in the MX.PSR file.


Here is a small sample of the file:

* edit *


Can anyone help and create an BMS-script for the .PSR file, please?


Thanks a lot,

Andreas
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-27T21:45:23+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

Try this:

```
Get HEADER_UNK1 long # Version?
Get NUM_FILES long
Get HEADER_UNK2 long
Get HEADER_UNK3 long
Get FILE_TABLE_SIZE long
Get HEADER_UNK4 long

For I = 0 < NUM_FILES
	# File entry
	Get NAME_LEN long
	GetDString NAME NAME_LEN
	Get SIZE long
	Get OFFSET long
	Math OFFSET *= 0x800

	Log NAME OFFSET SIZE
Next I

```
## Post #3
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-12-01T18:15:47+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

Hi,

the script works fine, but quickbms brings some errors (attached) during extraction.

Thanks a lot,
Andreas
[error_mx_psr.jpg](https://xentaxbackup.github.io/file/2581_error_mx_psr.jpg)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-01T18:56:29+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

are you using the latest version of quickbms?
because that error reminds me a bug which was corrected some versions ago:
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #5
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-12-01T19:44:03+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

I want to try it again with the latest version.
## Post #6
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-12-02T17:16:48+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

@ aluigi
With version 0.3.9a (I think it's the latest version) the "specified offset can't be reached" error I don't get again. Only the "overwriting file" questions occurs. 

@ all
Why I do get the "overwriting file" questions? I can't believe that there are double files in same folders in the archive.

Thanks once more,
Andreas
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-02T17:19:55+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

sometime can happens that 2 files have the same name because they are stored as resources in the archive so it's possible that they are an older and more recent version of the same resource.

other times 2 or more files can have the same name if the archive has been not handled to parse also the folders but this one doesn't seem the case
## Post #8
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2010-05-02T10:10:06+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

I want to compile the textfile into an bmsfile with Mex Binder + (1.6.0.24) but I get error messages like e.g. not enough variables. I've tried it also with Game Extractor's Script builder (v2.01) and it was the same. Only when I use the script (textfile) with quickbms - it works. 

Can someone check the script for errors again or compile it anyway?

Thank's for your help,

Andreas.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-02T13:25:49+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

because multiex and game extractor support only the original bms syntax, so you need only to add a ';' after each line and a 0 for all the input and output file operations.
the following modification "should" work:

```
Get NUM_FILES long 0 ;
Get HEADER_UNK2 long 0 ;
Get HEADER_UNK3 long 0 ;
Get FILE_TABLE_SIZE long 0 ;
Get HEADER_UNK4 long 0 ;
For I = 0 < NUM_FILES ;
Get NAME_LEN long 0 ;
GetDString NAME NAME_LEN 0 ;
Get SIZE long 0 ;
Get OFFSET long 0 ;
Math OFFSET *= 0x800 ;
Log NAME OFFSET SIZE 0 ;
Next I ;
```
## Post #10
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2010-05-02T16:33:40+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

I've tried it again with the specified changes (Mex Binder +). What I get is this:

ErrorLog
Error in line 0: Wrong Data Type specified
Error in line 0: Cannot save, still errors in Script
Error in line 0: Wrong Data Type specified
Error in line 0: Cannot save, still errors in Script

Anyone another idea?

Bye Andreas
## Post #11
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2010-05-08T20:45:45+00:00
- Post Title: [PS2] MX Unleashed - MX.PSR file

First of all, here is another link to the MX.PSR file. This link is working.

* snip *

Here is my own script:

```
Get NUM_FILES long 0 ;
Get HEADER_UNK2 long 0 ;
Get HEADER_UNK3 long 0 ;
Get FILE_TABLE_SIZE long 0 ;
Get HEADER_UNK4 long 0 ;
For I = 0 To NUM_FILES ;
Get NAME_LEN long 0 ;
GetDString NAME NAME_LEN 0 ;
Get SIZE long 0 ;
Get OFFSET long 0 ;
Math OFFSET *= 2048 ;
Log NAME OFFSET SIZE 0 0 ;
Next I ;
```


But I can't get it to work:

Game Extractor's Script Builder find no errors and create an BMS file. If I want to use it with the archive, GE gets an "Cannot open the archive with the script" or something like that error message.

With Mex Script I can't compile the script with the "error in line 0 - wrong data type" message.

If I want to use the BMS file, created by Game Extractor in MexCom I get runtime error 7 (not enough memory). With the textfile MexCom gives me an "MexScript 3 cannot proceed" message.

Can anyone help me again and check the code or create an working BMS file?

Thank you,

Andreas.
