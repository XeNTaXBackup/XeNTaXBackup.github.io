## Post #1
- Username: Hunter
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 17, 2006 12:52 pm
- Post datetime: 2006-04-21T06:26:59+00:00
- Post Title: String Finding Proggy

I wrote a little proggy to find strings inside of a file.  Just want to see what you guys think.  Maybe it might even help someone out with reversing, who knows.

To inspect an file just click on "Open and Inspect", select your file and you're good to go.

I should probably warn you though, currently it loads the entire file into memory while its doing its searching, so becareful if you don't have alot of RAM.  If it works well I might add paging for large files later.

Most of the output is self explanatory, except for maybe the %'s and the PString and CString labels.  
The %'s are a number I come up with that the program uses to determine the likely-hood of what its looking at being a string.  To allow it to display more potential strings, change the "Cut-Off Threshold" value then inspect the file again.
PString, 2PString and 4PString mean that the string was read as a pascal-style string.  This just means that the string length was before the string.  PString is a byte length, 2PString is 2 byte length, 4PString is 4 byte length.
CString means that the string was read as a standard C-style null-terminated string.

Oh, and this was made with .NET 2.0 so you'll need it to run this proggy.

Let me know what you think guys. 
[Inspector.zip](https://xentaxbackup.github.io/file/713_Inspector.zip)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-21T07:16:25+00:00
- Post Title: String Finding Proggy

Could be useful to some. It reminds me of a command line program I wrote 6 years ago, called MEXSCAN, that had the option to scan for possible headers/string repetitions. 

Here's the docs: 

```
                         -===================-

                       Author :  Mr.Mouse/XeNTaX
                             Done in 2000

                   This file has the following content:

                           1. Introduction
                           2. Advanced Information
                           3. Interpretation
                           4. About



                            1. Introduction
                            -=============-

With MEXSCAN you can scan a datafile with an unknown format.
It will search for format ID tags that MultiEx already knows, it will
scan for specific files, like WAVE (*.WAV) tags among others and it will
scan for a header or tail. All the info it can get from the datafile
it will log in a textfile named after your file.
If you let it scan pak0.pak from quake2 for instance then the log file
that is created will be named pak0.txt.

COMMANDLINE:
============

MEXSCAN <filename>

                         2. Advanced information
                         -=====================-

In essence, MEXSCAN uses the delivered MEXSCAN.MSS (MSS = Mex Scan Script)
to retrieve commands. You can alter the MEXSCAN.MSS to suit your needs.
The default MEXSCAN.MSS makes sure the file is completely scanned.
With large files this may take a while. If you just want to see if
MULTIEX already understands the format, you should create a script file
that only executes SCAN4IDS.MSS. If you open the MEXSCAN.MSS you will
see that the commands there are 'msEXECUTE "scan4ids.mss"' and more.
So all you need to do is backup the original MEXSCAN.MSS and alter
the MEXCAN.MSS. In the present example you would delete all other commands
except 'msEXECUTE "scan4ids.mss"'. Now if you start mexscan, it will
only scan for ids (already supported formats).

At present there are only four commands at your disposal:

msEXECUTE "<filename>"
----------------------

This will execute a script file of your choice, named <filename>.
Example: msEXECUTE "scan4ids.mss"


msSCFILEHEADER ""
-----------------

This will scan for any information that could point to a header or tail
that includes filenames. It is important that you use the "" after you 
have given the command.
(A header or tail usually contains information regarding the files in the
datafile. e.g. FILENAME, FILE OFFSET and FILE SIZE.)


msIDREAD "<identification>" "<text explaining format>"
------------------------------------------------------

This will scan the first bytes of a file for a certain identity string. 
And you must specify what text will be logged if the string you give 
is indeed found.
Example:
msIDREAD "IWAD" "iD Software WAD format"


msSIGREAD "<signature>"
-----------------------

This will scan the datafile for a give signature, and as with the other
commands, report it in the log file. It will give the position it finds
it, and the number of bytes until the next occasion is found. 
Example:
msSIGREAD "RIFF"

                     3. Interpretation of the log
                     -==========================-

I will talk about this command by command. 

msSIGREAD
--------

Example Log text:

;*** Signature Scan Initiated ***
;RIFF
;144348 : lenght of file to scan
;408 : POSITION FOUND SIGNATURE
;3884 : SIZE OF FOUND SIGNATURE
;Signature: RIFF Found 1 times !
;*=- Signature Scan Ended -=*

The log states that the SIGSCAN has been started.
It then gives the SIG it will scan for and the length of the file to scan. 
It reports the offset of the signature found and the size of the signature
(or rather the number of bytes until it found the next). 
When all of the file has been scanned it reports the number of sigs it has
found and declares the scan to be finished. 

msIDREAD
--------

Example log text

;*** ID Scan Initiated ***
;SadComLtdat
;++IDScan Complete! SadCom Ltd. SAD format implied.
;*=- ID Scan Ended -=*

The log states that the IDSCAN has been started.
It then gives the ID it will scan for.
If the identity if found, it will state the text comment that you use in
the initial command. 
(Here the command used in the script was:
msIDREAD "SadComLtdat" "SadCom Ltd. SAD format"


msSCFILEHEADER
--------------

Example log text:

;**** Header Scan Initiated ****
;17 >> C:\TOOLS\MC\BREAD.EXE >> DELTA 17 >> AL 20 >> F 15
;281 >> C:\TOOLS\MC\EDITOR.MCT >> DELTA 264 >> AL 19 >> F 14
;545 >> C:\TOOLS\MC\FILE.MKD >> DELTA 264 >> AL 21 >> F 5
;809 >> C:\TOOLS\MC\LFE.EXE >> DELTA 264 >> AL 22 >> F 16
;1073 >> C:\TOOLS\MC\MC.BAT >> DELTA 264 >> AL 23 >> F 11
;1337 >> C:\TOOLS\MC\MC.INI >> DELTA 264 >> AL 23 >> F 11
;1601 >> C:\TOOLS\MC\MC.PIF >> DELTA 264 >> AL 23 >> F 5
;1865 >> C:\TOOLS\MC\MCMAIN.EXE >> DELTA 264 >> AL 19 >> F 9
;2129 >> C:\TOOLS\MC\MCVIEW.EXE >> DELTA 264 >> AL 19 >> F 14
;2393 >> C:\TOOLS\MC\MULTIAD.EXE >> DELTA 264 >> AL 18 >> F 9
;2657 >> C:\TOOLS\MC\MULTIEX.EXE >> DELTA 264 >> AL 18 >> F 13
;2921 >> C:\TOOLS\MC\multiex.imp >> DELTA 264 >> AL 18 >> F 4
;3185 >> C:\TOOLS\MC\MULTIEX.INI >> DELTA 264 >> AL 18 >> F 13
;3449 >> C:\TOOLS\MC\multiex.lst >> DELTA 264 >> AL 18 >> F 9
;3713 >> C:\TOOLS\MC\README.1ST >> DELTA 264 >> AL 19 >> F 9
;3977 >> C:\TOOLS\MC\selected.mkd >> DELTA 264 >> AL 17 >> F 8
;4241 >> C:\TOOLS\MC\TREAD.EXE >> DELTA 264 >> AL 20 >> F 15
;!! Possible HEADER at approx. 17, 16 files 264 spacing !!
;Most probable header : offset 374456, at least 48 files.
;=-*** Header Scan Ended ***-=

The log said it initiated the header scan and then reports any 
filename found: this has the following format:

<offset> >>
<text> >>
DELTA <number of bytes distance from previous reported filename> >>
AL <percentage of non-letter character>
F <average frequency of all the different characters in the text>

When MEXSCAN sees that the DELTA is the same it counts this as a
possible header, and counts the number of possible files in the 
datafile, until it finds a possible filename that has a different 
DELTA. It then gives a summary of the previous header:
;!! Possible HEADER at approx. 17, 16 files 264 spacing !!
When the whole file has been scanned it will give the most probable
header(containing filenames) found and ends by saying that the scan 
is done. 

msEXECUTE
---------

Whenever an external script file is called and ended it will say 
in the log
;=-*** Process Script File Initiated ***-= and
;=-*** Process Script File Ended ***-= respectively.


**!! IMPORTANT !!**

The headerscan just gives A VERY ROUGH ESTIMATE. You will have to look at the 
file positions it reports yourself with a decent HEX editor
(such as HEX WORKSHOP) to unravel the other fileinformation
(e.g. FILEOFFSET FILESIZE etc..)

                              4. About
                              -=======-

MEXSCAN v1.0 was coded by Mr.Mouse/XeNTaX in 2000
No rights reserved. The author is NOT responsible for anything that
might happen to your computer that may be regarded as malicious. 
By using the program you have agreed to these terms. 

This file was made as a personal tool for quickly scanning newly
encountered datafiles to readily gain as much information as 
possible before diving into the file in question with a HEX editor. 


```


And the prog itself. 
[Mexscan.zip](https://xentaxbackup.github.io/file/714_Mexscan.zip)
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-21T10:10:06+00:00
- Post Title: String Finding Proggy

Both programs could be usefull ! =D

and to Mr.Mouse, thats exactly what i have developed now into jaeder naub :X , i have made functions similiar to your old tool.
currently some of the internal rippers is using it with built-in scripts,
which will later be able to be read from outside the program as plugin
scripts. (some might have noticed the JNCR Plugins on the
option screen. thats just what it is.)

current functions as in the source code, you can see it has been
around for awhile, since 1.8.1e. not yet utilized to its full potential.
i really hope to get it finished, cause the it will be just to write
scripts for any filetype and save it in a plugin folder, so anyone could
add filetypes to the program.


```
  ' custom blockread added v1.8.1e
  Public BlockReadLength As Long
  Public BlockLength As Long
  Public BlockAddLength As Long
  Public BlockIntegrityOffset As Long
  Public BlockIntegrity As Long
  Public BlockAbsoluteEnd As Long
  Public OperationBlock As String
  Public InformationBlock As String
  Public ActionBlock As String
  Public ExtensionBlock As String
  Public PrefixBlock As String
  Public BlockLengthMotorola As Long
  Public BlockStartOffsetSaving As Long
  Public BlockFindEndTimes As Long

```
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-21T10:13:12+00:00
- Post Title: String Finding Proggy

Gaargrhrghrghghghghyhhgaghhfghgfhfdhgdfghdfg DOT NET!! >8(

thats why it crashed on my comp :/
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-04-22T02:00:06+00:00
- Post Title: String Finding Proggy

ummm have you tried looking at the source for the unix "strings" command?
