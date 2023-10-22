## Post #1
- Username: blabla88
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 20, 2017 6:42 pm
- Post datetime: 2017-10-21T11:10:15+00:00
- Post Title: South Park The Fractured But whole SDF archive

Hello. Im a translator, who helped to translate first South Park game (South Park Stick of Truth) in to Czech language. In first game, developers used OAF system, which was really easy to extract, edit and put it back. 

But this time, they used SDF system. Same system, that used Tom Clancy The Division, due to usage of Snowdrop engine.

I think you see the problem now. Single player game with Multiplayer type archives. Thanks to [viewtopic.php?f=10&t=13882&p=134645#p134645](http://forum.xentax.com/viewtopic.php?f=10&t=13882&p=134645#p134645) and rouge_sdf, i managed to mine all files, but now i have no idea how to put it back. The archive looks like this [https://imgur.com/a/CH9v7](https://imgur.com/a/CH9v7) (Without rouge_sdf obviously). Many of SDFDATA files are 1kb text files, with word "dummy" written in it. 

Would be anyone able, to reverse engineer files, back to this type of archive, thus allowing us translate this game, or the only way is contact developers?

Thank you for response.

(Here is explanation of those files from mentioned topic)

SDFVER

sdfver files are text based files. They contain a numeric key value pair separated by spaces.
Each pair is for a different section in the sdfdata files (0 = A, 1 = B, 2 = C, etc.)
The key and value are separated by a colon. Each value consists of 5 numbers divided by a space.

Currently do not know what the numbers mean, I think it has something to do patching / version info.

SDFTOC

sdftoc files are binary based files with the header magic of "WEST". All sdftoc files have a separator(?).
The separator starts with "massive " and end with "ubisoft " (spaces being 0x00) in between there are 20
random characters, this separator is repeated multiple times in a file, and is always at the beginning
of the file at offset 0x1C and at the very end of the file.

Looking at the name I'm assuming the sdftoc files are Table of Content files, the actual content isn't
readable directly.

SDFDATA

sdfdata files are also in a binary format and have the header magic of "BERG". They have the same separator
as sdftoc files but starting separator is at offset 0x08 and also end with it.

I have come across sdfdata files that have plain text in them and bnk files.

A lot of the sdfdata files only contain the word "dummy".
## Post #2
- Username: wlscks7
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 17, 2017 11:18 pm
- Post datetime: 2017-10-21T13:16:58+00:00
- Post Title: South Park The Fractured But whole SDF archive

I'm watching this page : [https://zenhax.com/viewtopic.php?f=9&t=5114&p=27495](https://zenhax.com/viewtopic.php?f=9&t=5114&p=27495)
And trying quickbms something but it's not working that i want to do.
Anyone can show how to successfully reimport files to sdfdata?
I'm sorry for my terrible English... but I'm not good at it
## Post #3
- Username: r2856628
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 11, 2017 6:46 am
- Post datetime: 2017-11-10T23:34:05+00:00
- Post Title: South Park The Fractured But whole SDF archive

Does anyone know where music/sound files are located. I used the rouge_sdf extractor but i can't find any sound files only .bk2 video files
