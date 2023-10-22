## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-05-30T12:41:03+00:00
- Post Title: Darkness Within 2 - BIN files

Hi there,

This file contains the strings and texts for the game. However I couldn't find anything to edit it with. Anyone have any ideas?

[http://www.speedyshare.com/files/226980 ... nglish.rar](http://www.speedyshare.com/files/22698062/local_english.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-30T13:35:55+00:00
- Post Title: Darkness Within 2 - BIN files

script for quickbms for extracting the files:

```
get DUMMY long
get FILES long
get DATA_SIZE long
for i = 0 < FILES
    get DUMMY long
    get OFFSET long
    get SIZE long
    get DUMMY long
    getdstring NAME 0x30
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-05-30T15:25:34+00:00
- Post Title: Darkness Within 2 - BIN files

I think there is a problem. When the file has been uncompressed, and the changes have been done it's neccesary to include these files into BIN file again, due to the game not recognize the uncompressed files, like in Darkness Within. I tried to use DarkUpdater.exe but it doesn't work because I have not the ID of the files. Is There any way to get those ID, or recompress again this files using BMS?

Thanks.
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-05-30T15:38:34+00:00
- Post Title: Darkness Within 2 - BIN files

darkUpdater works only with the 1st part of the game.
Here are the programs for the 2nd part: dark2eXtr and dark2Updater!!!

The structure of the 'local_english.bin' file:

```
         ID : Array[0..3] Of Char; // 'CP11'
         Version : DWORD; // $200
         NrOfFiles : DWORD;
         DataSize : DWORD; // size of the FILE DATA
  -> Directory: (NrOfFiles * 64 bytes)
       for each file:
        -> FileID : DWORD;
        -> FileStartPos : DWORD;
        -> FileSize : DWORD;
        -> CRC32 : DWORD; // the CRC32 value of the data
        -> FileName : Array[0..47] Of Char; // with padding zeroes to fill the space
  -> Padding Zeroes: to align the FILE DATA to $8010 starting position
  -> FILE DATA...

```
## Post #5
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-05-31T13:56:57+00:00
- Post Title: Darkness Within 2 - BIN files

Thanks a lot bacter!

Regards.
## Post #6
- Username: Farflame
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Nov 11, 2009 12:11 am
- Post datetime: 2010-06-09T13:36:04+00:00
- Post Title: Darkness Within 2 - BIN files

Thanks bacter for great work. Thumbs up!

Can I ask you about one thing? I have one more "local.bin" file containing ingame texts and need some way to unpack/pack it to edit it. It seems to be similar to bin in DWithin, but its not packed, text is visible, so it may be even easier task. I assume you already worked with similar files. Please could you take a look at it? 

You can download it here - [http://www.volny.cz/farflame/eng.rar](http://www.volny.cz/farflame/eng.rar)

Thanks.
## Post #7
- Username: SergioKool
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 29, 2010 10:48 pm
- Post datetime: 2010-06-30T16:41:59+00:00
- Post Title: Darkness Within 2 - BIN files

hi mates i be able to extract the files of the texts with the quickbms    But after editing the texts how can i manage to pack again to same file   i try too the dark2updater but i cant work or dont know how to work with it    Please help guys
## Post #8
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-30T21:01:18+00:00
- Post Title: Darkness Within 2 - BIN files

Hi! I created a GUI version of the eXtractor/Updater. It works with the 1st and the 2nd part of the game.
#1: Select the correct game from the combobox
#2: Select the bin file
#3: Select the target directory
#4: Extract the contents of the bin file;
#5: Modify your extracted files;
#6: Use the "Replace" function.
I hope it is not too complicated.
## Post #9
- Username: SergioKool
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 29, 2010 10:48 pm
- Post datetime: 2010-07-01T20:28:06+00:00
- Post Title: Darkness Within 2 - BIN files

it works simple and usefull thanks a lot mate bacter you rule
## Post #10
- Username: kiratta
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 01, 2015 8:21 pm
- Post datetime: 2015-12-01T12:34:41+00:00
- Post Title: Darkness Within 2 - BIN files

But where can I find this eXtractor/Updater to download?
