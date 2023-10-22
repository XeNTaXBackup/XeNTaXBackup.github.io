## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-06T13:44:53+00:00
- Post Title: quickbms batch conversion

(Posted due to a user's request and because I couldn't find an appropriate batch - though I have a deja vue there's already a solution somewhere on xentax)

Usually quickbms is used for extracting a bunch of (compressed) files from archives (*.pak or such).

But there's bms scripts which handle one single (non-archive) file only for example for decompressing texture files.

In case you have a hundreds of such files this batch should come in handy:

@echo off
for %%f in (*.data) do (
  quickbms unity_36.bms %%f D:\test
)
REM no blanks in filenames, please

Copy above 5 lines into a *.txt file and rename it to whatever.cmd.
Replace the parameter "unity_36.bms" by a bms script of your choice and replace *.data by the suiting extension.
(D:\test is the output directory, as an example.)

Execute the cmd file where the *.data AND the bms script files reside.

I did a test in the quickbms directory.
In case you use another directory for .cmd/.bms/*.data you need to expand "quickbms" in the cmd file by the full path, "D:\QBMS\quickbms" for example.

(To make it work with filenames containing blanks you might try "%%f" in the script - didn't test it though.)

---------------------------------------
In case you just want to drag'n drop the file to be decompressed/converted use this batch:

@echo off
quickbms unity_36.bms %1 D:\test
REM no blanks in filenames, please
