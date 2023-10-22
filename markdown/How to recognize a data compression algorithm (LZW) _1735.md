## Post #1
- Username: pythagoras
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 18, 2006 1:45 am
- Post datetime: 2006-02-17T17:58:29+00:00
- Post Title: How to recognize a data compression algorithm (LZW) ?

Greetings everyone,

This is my first post here and i'm glad i've found this forum. I've been messing for a few years now with various game file formats and i've written quite a few modding apps for games like Fallout and Darklands (yes, that old game).
Talking about Darklands i've been trying to figure out a graphic file format for some time now. It's supposedly an "animation" file, which means it must contain graphic frames which play an animation.
I suspect these files are compressed with the LZW compression. My suspicion is based on the fact that other graphic files (static, not animations) from Darklands use this compression algorithm. On top of the LZW compression, i highly suspect a RLE-encoding as is the case for the other graphic files.

My question to the experts here is how can i be sure what compression was used. I can't seem to find anything in the file that points me to a beginning of data-offset, for example as should be the case for LZW files (or maybe i'm mistaken).
I've enclosed a file with the format i'm talking about. This is from the game Darklands. If anyone could give me pointers to 'give-aways' in the file to identify the compression algorithm, it would be very helpful.

Thanks in advance, 

Pythagoras.
[A00CBDR.zip](https://xentaxbackup.github.io/file/619_A00CBDR.zip)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-02-18T00:20:58+00:00
- Post Title: How to recognize a data compression algorithm (LZW) ?

Welcome to the forum, Pythagoras. I can't help you, except to suggest that you try unencrypting/decompressing the file in question... I'm sorry, but I simply don't know enough.  

In the meantime though, please share your knowledge with us at the [wiki](http://wiki.xentax.com).
## Post #3
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-02-18T12:58:45+00:00
- Post Title: How to recognize a data compression algorithm (LZW) ?

you may try to look inside the main exe,what access or sometime strings of compression library copyright.

imho the main exe could say much more than analyzing in raw.
## Post #4
- Username: pythagoras
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 18, 2006 1:45 am
- Post datetime: 2006-02-18T19:01:59+00:00
- Post Title: How to recognize a data compression algorithm (LZW) ?

Thanks for your replies and your welcome. I will look inside the .exe file as suggested, that's a good idea. The LZW compression used by Darklands doesn't seem "canonical" though as the dictionnary used seems to be 2048 bytes long instead of the standard 4096.
Anyway, i'll gladly contribute my 2-cents to the Wiki, it is a great resource.
