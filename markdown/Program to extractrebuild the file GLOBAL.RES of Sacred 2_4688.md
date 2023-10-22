## Post #1
- Username: elias2999
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 01, 2010 5:53 am
- Post datetime: 2010-06-30T22:09:52+00:00
- Post Title: Program to extract/rebuild the file GLOBAL.RES of Sacred 2?

Hello everyone here on the forum XeNTaX I'm from Brazil and I am doing translation of texts from Sacred game and a sequel as I give the translation, I began to move in the archives of Sacred 2, and as usual the producer of the game where is the Ascaron puts all these texts in a file called "GLOBAL.RES," I managed to open it with a program, my friend, Jenner did, but when I try to open the same file ie "GLOBAL.RES "Sacred 2 of the program Jenner gives an error message.

Well then get my internet search, I found the site: "DarkMatters" posted there for help in extracting the text file "GLOBAL.RES" of Sacred 2, and a user from there told me that a user here called , Mr.Mouse once managed to make a program to move the "GLOBAL.RES" of the Sacred one, I wonder if anyone here managed to open forum file "GLOBAL.RES" of Sacred 2, or even Mr.Mouse .

I thank those who help me, because I am in search of that program to two days now and can not find anything, if anyone can help me I appreciate.

Thanks, and I'm waiting for a response.
## Post #2
- Username: Schot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 12, 2007 7:08 am
- Post datetime: 2010-07-01T02:21:29+00:00
- Post Title: Program to extract/rebuild the file GLOBAL.RES of Sacred 2?

Nice!  Glad you could find it elias.  Here's a link to the demo to help with the request.    

[http://www.bigdownload.com/games/sacred ... ngel-demo/](http://www.bigdownload.com/games/sacred-2-fallen-angel/pc/sacred-2-fallen-angel-demo/)


Btw, big thanx for plugins made in the past for Sacred Underworld.  They were awesome!  I hope you still have a soft spot in your heart for Sacred Mr.Mouse and that you can find the time to help us out.  Since the demise of Ascaron our DarkMatters community has been hungrily exploring the world of modding.

Many thanx!


Schot

[DarkMatters.org](http://darkmatters.org)
[SacredWiki.org](http://sacredwiki.org)
## Post #3
- Username: elias2999
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 01, 2010 5:53 am
- Post datetime: 2010-07-01T22:14:07+00:00
- Post Title: Program to extract/rebuild the file GLOBAL.RES of Sacred 2?

Well the full game I have here, just wondered whether anyone can help me or has a program or a plugin for a program to open the GLOBAL.RES of Sacred 2: Fallen Angel, I have a program here that opens the GLOBAL.RES the Sacred one, only that this program can not read the GLOBAL.RES of Sacred 2: Fallen Angel   , if someone can look at this program I thank you.   

Thanks and I'm waiting for someone who can help me.
## Post #4
- Username: Thorium
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 02, 2010 6:46 pm
- Post datetime: 2010-07-03T07:27:32+00:00
- Post Title: Program to extract/rebuild the file GLOBAL.RES of Sacred 2?

In case someone wants to break the format:

I tried it but it's very complex and i do not have enough time for it, here is what i know about it:
It has nothing to do with the global.res format from sacred 1. No need to compare the both, they are complete different.

The first 4 byte seam to indicate the format of the file, 2 possible values: L10C or L10N.
The next 4 byte also can be of 2 values but i have no clue what they mean: 0x10100000 or 0x20100000.
Next 12 byte are complete unknown but i think one of the double words have to be the count of data sets.
Then there comes a big block of double words that count up. I think that could be hashes so the actual data could be structured in a hash table.
Then there follows the block of data set headers with 3 members per data set.
Then finaly there are the strings, encrypted or compressed. It's not the encryption used in Sacred Underworld.

The global.res gets strait loaded to memory, no processing is done on loading time. So the decryption or decompression of the strings is done right when they are needed by the string manager.
Loading of global.res is in s2logic.dll and the string manager also is in s2logic.dll and is called LokaMgr.

Good luck, for me its a hard nut to break. ^^
## Post #5
- Username: elias2999
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 01, 2010 5:53 am
- Post datetime: 2010-07-12T00:56:19+00:00
- Post Title: Program to extract/rebuild the file GLOBAL.RES of Sacred 2?

Somebody help me? Told me that here I would find the guys who did the EXTRACTOR texts from file ". RES of Sacred ONE (1), and I also find the guy who's got the Sacred 2?

I'm waiting for answers, I would like to translate the texts of Sacred 2, since I administer the Translation Project for the Portuguese Brazil's first game and that is almost 100% translated.
