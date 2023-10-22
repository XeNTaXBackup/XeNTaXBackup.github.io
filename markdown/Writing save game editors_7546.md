## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-10-22T18:51:24+00:00
- Post Title: Writing save game editors

I'm thinking of writing a save game editor, but not sure about a few things (since I've never actually looked at save files lol)

IN GENERAL:

1: I imagine the process for editing save game is simply figuring out which values correspond to what. Ok, so it's just simple hex-editing that can be done by hand, but writing a tool to do it for you would make it more convenient. So if it's a matter of looking for the appropriate addresses...

2: Do games usually store all of the data that can possibly change throughout the game, in the save file, all the time?

So say you have a game where you recruit new members in your party further down the storyline, and so at the beginning of the game we'd just have a bunch of null values for those characters. Or do those entries get written when you actually recruit the character? (or both, and really depends on the game)

3: A simple example that people usually want is lots of money, more than you'll ever need. Is the address for the value that stores the money usually fixed at a single location, so once you find it you're done, or is it more common for these values to change addresses overtime as the game progresses?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-10-22T19:28:10+00:00
- Post Title: Writing save game editors

The short answer is "it depends on the game".

Depending on the type and age of the game in question, its save game files may be fixed-size or variable-size (and even split up between multiple files!), and while stuff like amount of currency isn't likely to change in location in the format spec, it may change in location in variable-sized files, depending what other stuff is stored before it.

In addition, some games - especially more modern ones - may use hashes, checksums, or even encryption to discourage tampering with the save files.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-10-22T21:38:32+00:00
- Post Title: Writing save game editors

So generally you'd have to figure out the entire spec before trying to write a fool-proof tool for it, and that would probably involve asking around for save files at different levels of completion. Or...actually playing the game and seeing the changes first-hand.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-10-22T21:47:27+00:00
- Post Title: Writing save game editors

Right, but most of the time, you should be fine even with an incomplete spec - it's easy enough to find out for any given game (just change the value you suspect to be money/experience/whatever and load the edited save in-game; if the game doesn't crash or throw an error, and the attribute has changed, you know you're right on). Usually the only times you'd need even most of the spec would be if the format is variable-size.
## Post #5
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-01T16:07:06+00:00
- Post Title: Writing save game editors

> Reply from finale00
>
> 
1: I imagine the process for editing save game is simply figuring out which values correspond to what. Ok, so it's just simple hex-editing that can be done by hand, but writing a tool to do it for you would make it more convenient. So if it's a matter of looking for the appropriate addresses...

In some cases - yes. The saves CAN contain variables at fixed addresses, or not. For example, if you have 0 money, and the max money is 4294967295, Then:

Case1:
Save at example address 0x5f contains "00 00 00 00". The game reads bytes from offset 0x5f to 0x62 (4bytes). If you'll get e.g. 2516 money, then 0x5f-0x62 offset would be: 00 00 09 D4. (Big endian)

Case2:
There is specific header, with byte length information. Then you search for header, and read length byte, to specify how much bytes next you'll need to read. Useful, when you'll operate on giant data, like encoding player's emblem in save file. 

Case2a: The software itself saves addresses at start of the file in most cases, so the game know where to search for variables.

> Reply from finale00
>
> 
2: Do games usually store all of the data that can possibly change throughout the game, in the save file, all the time?

So say you have a game where you recruit new members in your party further down the storyline, and so at the beginning of the game we'd just have a bunch of null values for those characters. Or do those entries get written when you actually recruit the character? (or both, and really depends on the game)

It's mainly called story flags. Yep, in many cases, the 00's are present. But, looking for Case 2a above, you can see, that first save could be 1KB, and at the of game, it can increase up to 200 KB. So in this case, you'll have to look how file is changing, and look for address pointer at the header. It's something like an archive. 

> Reply from finale00
>
> 
3: A simple example that people usually want is lots of money, more than you'll ever need. Is the address for the value that stores the money usually fixed at a single location, so once you find it you're done, or is it more common for these values to change addresses overtime as the game progresses?

See reply to 1. 


And remember, saves can be compressed. I'll give you a practical example:
I worked on KnightShift 2 saves. I found, that they're compressed with RFC1950 (Zlib).
I wrote a program, to decompress and compress files. Then I made three saves, where I tried to only change amount of my EXP. Then seen what're the differences between those two files. If I had 51032 EXP, then I searched for C758. This was Big-endian, so I had to search for 58 C7. Before that 58 C7 was a byte "02". When I earned additional 22000 EXP, I had 11D48. So big-endian would be: 48 1D 01. And guess what, that number before my EXP changed it's number from 02 to 03. Game read the file from beginning. See's the header, and knows what's the value is. For example the structure of this save was like:

1.Name of character
2.Role (mage, warrior)
3.EXP
etc...

The game had unique header for Name, role and exp. So when read from beginning it read like this:
AB - Hey! That's my unique header for name!
0B - Oh! Looks like the name has 11 chars, okay, I'll read next 11 bytes as name, and after that I'll await next header
64 - 'd'
69 - 'i'
6e - 'n'
6f - 'o'
67 - 'g'
75 - 'u'
79 - 'y'
31 - '1'
30 - '0'
30 - '0'
30 - '0'
AD - Hey! Another header.. AD was... Oh, yea, a role!
and etc...
Also, the save could not have a header, as the game can read the first byte as length, and just work like this:
Section one is 15 bytes of data. 
Section two is 2 bytes of data.
Section three is 24 bytes of data.
Now the game itself reads it's own files, to indetify these sections. 
I mean, the header can be in save itself, or just checked with a game data, not written to save. 

Phew.
