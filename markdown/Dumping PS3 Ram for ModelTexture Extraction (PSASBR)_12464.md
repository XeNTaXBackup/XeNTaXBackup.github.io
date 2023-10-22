## Post #1
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-01-03T19:05:04+00:00
- Post Title: Dumping PS3 Ram for Model/Texture Extraction? (PSAS:BR?)

I'm looking to get the decrypted archives from Playstation All Stars on PS3, and this requires (I think) a RAM dump of the ps3. How do I go about doing this, and what tools exactly does everyone else use? I've seen some threads on that game, but nobody has said exactly what they are using. Thanks in advance.
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-01-05T17:11:56+00:00
- Post Title: Dumping PS3 Ram for Model/Texture Extraction? (PSAS:BR?)

Even if you dump the ram you won't be able to retrieve the decrypted archive so easily.

1. It would be stored in the ram in pieces.
2. Each piece could be stored anywhere.
3. It might not load all the data at once in that archive anyway so you might only have a few files in the ram that are decrypted.

Your best bet is to dump the ram from a debug PS3. This might get you some files. But again, chunks of them could be stored in various places of the ram depending on how they load it into the memory itself. Another solution would be reverse-engineering the decryption algorithm.
## Post #3
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-01-05T17:49:14+00:00
- Post Title: Dumping PS3 Ram for Model/Texture Extraction? (PSAS:BR?)

Thing is, I do actually have a debug PS3. I just need to know the steps to take to dump it in the first place, because I'm inexperienced with all this stuff. The PS3 modding scene seems like it can be very suspicious and unreliable and I can't seem to find a clear tutorial showing how it's done correctly.
## Post #4
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2015-01-05T18:14:25+00:00
- Post Title: Dumping PS3 Ram for Model/Texture Extraction? (PSAS:BR?)

First things first, you need to get part of the sdk, specifically SN Systems' Target Manager and Debugger, once you have them you need to search about how to connect your ps3 via target manager it's done through the network, then you'll have to search to see how to make a debug eboot of the game you wish to debug. After that when your ps3 is connected to Target Manager you open the Debugger and attach the process of your debug eboot whilst the game is running. I haven't wrote this in any detail as its a lengthy process and I think if you search for what I've said individually you will find resources than can explain each step better than I can. But if you really are stuck at any point during this then I can try to go into a particular step in more detail.
## Post #5
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-01-05T18:43:12+00:00
- Post Title: Dumping PS3 Ram for Model/Texture Extraction? (PSAS:BR?)

I already have all that set up, I just need to know how dumping the ram specifically works. I already have a debug eboot of the game, I already have the target manager and all, it's completely set up, I just don't how how to actually dump it.
## Post #6
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2015-01-05T19:19:39+00:00
- Post Title: Dumping PS3 Ram for Model/Texture Extraction? (PSAS:BR?)

Well that's the easy part then, when you're in the part of the game you want to dump memory from, in the debugger just right click the memory and select save memory region/save memory, something like that and just select the range you'd like to save, if your range contains a part that the game isnt using it will fail, so make sure you get the right range, should be between  0x30000000 - 0x40000000
## Post #7
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2015-01-08T20:59:39+00:00
- Post Title: Dumping PS3 Ram for Model/Texture Extraction? (PSAS:BR?)

Now, about the dump itself, which I do have now (it's about 120 MB, which I assume is correct?) How would I go about extracting content from it? Does a tool exist to extract the files from it blindly? I dislike trying to pull apart the files myself and it often doesn't turn out correct.

I have found some model headers (EA05 in this case) and also using TextureFinder some textures are viewable, but they're all in a single .bin file.
## Post #8
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2015-01-08T22:34:06+00:00
- Post Title: Dumping PS3 Ram for Model/Texture Extraction? (PSAS:BR?)

No there's no way to do that, you'll have to continue doing it manually.
