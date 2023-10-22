## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-22T14:37:03+00:00
- Post Title: dealing with unicode filenames

Is there any way to deal with non-english filenames with quickbms?
Suppose I knew what encoding the names used.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-22T14:51:32+00:00
- Post Title: dealing with unicode filenames

i have no issues with non english characters in quickbms.
what error / problem are you getting?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-22T15:12:43+00:00
- Post Title: dealing with unicode filenames

No error, I just don't know how to extract them properly.
Which commands do I use?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-22T15:14:53+00:00
- Post Title: dealing with unicode filenames

get name string
or 
getdstring name length
what is the problem?
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-22T15:20:32+00:00
- Post Title: dealing with unicode filenames

All of the non-english filenames are garbled when I extract the [launcherSkin.axp archive](http://www.mediafire.com/?5az1n33aoezcnt5) with [this](http://forum.xentax.com/viewtopic.php?p=56790#p56790) script.

The sample archives I posted only has a couple non-english names but all meshes are non-english.
My computer can read chinese korean and japanese fine so I think it is how I am getting the names.



encoding: GB2312
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-22T16:14:28+00:00
- Post Title: dealing with unicode filenames

i dont have any problem just logging normal file names i am not sure the problem you are having.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-22T17:18:07+00:00
- Post Title: dealing with unicode filenames

Do you remember any games that used non-english names that you wrote scripts for?
Could be my computer settings too lol
## Post #8
- Username: Mippithedork
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 20, 2012 10:47 am
- Post datetime: 2012-02-20T02:56:54+00:00
- Post Title: dealing with unicode filenames

It seems i'm having similar issues, the names are not coming out in chinese even tho i have chinese implemented on my PC. I need the file names to be correct according to what they are supposed to be within the packs. I only get garbled text for names and symbols, but no chinese, also it asks me to rename practically every single file in some of these axp's. 

One more thing, I'm also looking for information on how to recompile these files back into the axp pack format after i've made my changes. Any ideas?
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-20T14:37:17+00:00
- Post Title: dealing with unicode filenames

I'm enough interested on this point.

at the moment quickbms reads the strings till the reaching of a zero so any ascii/utf8 string gets read correctly.

then when writing the files it cleans the filename using the function src\utils.h->clean_filename which removes the carriage return/line feed, any of the following "?%*:|\"<>", removes all the spaces and dots at the end of the filename (for example "myname.txt   ") and obviously removes the absolute and directory traversal paths ("c:", "..").

so at a first look I don't see problems with "get NAME string".

instead the "unicode" type (16bit like bytes "61 00 61 00") is a different story and it's bugged for sure because it's written to work with english only chars so:
  getdstring NAME 0x20
  set NAME unicode NAME
will produce an invalid name if it's asian.
maybe I will find an universal solution in future but I doubt because looks like you must specify a charset for the unicode->utf8 conversion and so if you don't set it (if you do then it's no longer "universal") any other name that use a different charset will be converted in a wrong way.

so resuming:
- get NAME string: should be 99% correct for asian names
- set NAME unicode NAME: correct only for english chars
