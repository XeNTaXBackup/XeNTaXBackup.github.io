## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2016-12-25T13:54:03+00:00
- Post Title: [QBMS] Bionic Commando Unpacked FCL files extractor

A script that extracts all files from unpacked FCL files.
Pretty late huh?

You will need to know a few things before you start extracting.
1st - use FCL_Grin.exe to decompress FCL file
2nd optional - remember or write down block number when "--skip" appears, if not you're fine.
3rd - make sure that "game.lhd" is in same folder as .fcl_unp file
4th optional - in script find line "set SKIPPEDBLOCK 0" and chage 0 into block number from 2nd optional

Note: script will skip files with 0 size

Now after you extracted file and did NOT set SKIPPEDBLOCK  in script, some files will be unreadable by any program, you will need to add 4 missing bytes at begining of file. For example if you want to view dds texture and cannot due to missing bytes at start of file, you just add "DDS " (0x44445320) and file will be readable. Everyone familiar with file formats should know without this note.

So I recommend you to watch for "--skip" while using FCL_Grin.exe and writing block number into script, saves a lot of trouble and time.
[grin fcl_unp.zip](https://xentaxbackup.github.io/file/12121_grin fcl_unp.zip)
## Post #2
- Username: KoRaG
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 01, 2015 10:48 am
- Post datetime: 2019-06-19T17:24:30+00:00
- Post Title: [QBMS] Bionic Commando Unpacked FCL files extractor

PredatorCZ, hello and thank you for the script. 
But I have a problem with script:
I am trying to extract the Terminator Salvation game level 1 fcl file and nothing happens
I have a lot of -skip and I do not know how to deal with your script... As I understand it, only one set SKIPPEDBLOCK is inserted into your script. What should I do if I have as many as 11 pieces -skip (in the fcl file of the 1st game level)
Thanks in advance for the answer



[https://drive.google.com/file/d/1QahiGb ... sp=sharing](https://drive.google.com/file/d/1QahiGbnl5HoSBKsx7URIiqWHBNE3XM10/view?usp=sharing)
## Post #3
- Username: kuiks
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 13, 2014 2:31 am
- Post datetime: 2019-12-14T16:12:09+00:00
- Post Title: [QBMS] Bionic Commando Unpacked FCL files extractor

hello help me Terminator Salvation strings translate problem
[Adsız.jpg](https://xentaxbackup.github.io/file/17189_Adsız.jpg)
## Post #4
- Username: Controller
- Rank: n00b
- Number of posts: 11
- Joined date: Mon May 25, 2009 8:44 am
- Post datetime: 2021-07-29T11:20:33+00:00
- Post Title: [QBMS] Bionic Commando Unpacked FCL files extractor

For some reason, this script restarts exporting again and again. (QuickBMS 0.10.1)
Had to add a "CleanExit" at the end of it.
