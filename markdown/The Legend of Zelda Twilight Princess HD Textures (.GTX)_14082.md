## Post #1
- Username: theJulman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 13, 2016 6:15 am
- Post datetime: 2016-03-12T22:18:47+00:00
- Post Title: The Legend of Zelda: Twilight Princess HD Textures (.GTX)

Hello Guys,
I really want to extract the Textures of the Wii U edition.
For now I extracted the Content of the .pack.gz package with a quickbms script.
then there were a geo and a tex folder.
But when i looked into the tex folder there was only one file.
And when i converted the .GTX texture to .DDS with texconv2 and opened it with Noesis
there was only the eye or the marks but no body or face texture at all.
Am I missing something?
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-03-14T21:49:37+00:00
- Post Title: The Legend of Zelda: Twilight Princess HD Textures (.GTX)

That's because the *.GTX files are using a slightly newer format compared to the ones in other Wii U games. Most of the *.GTX files in TPHD store more than one texture, and the texture converter only picks up the first one because of which. I'll be working on a GTX splitter sometime later this month, hopefully it won't be too hard to figure out.
## Post #3
- Username: theJulman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 13, 2016 6:15 am
- Post datetime: 2016-03-17T17:11:12+00:00
- Post Title: The Legend of Zelda: Twilight Princess HD Textures (.GTX)

thx for the reply
I thought the same cause the output was much smaller compared to the input.
I'm not very experienced in reverse engineering therefore i haven't figured out how to
split them on my own
but I would really appreciate it if you release a splitter for this  .
## Post #4
- Username: wadeMaster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 21, 2017 9:03 am
- Post datetime: 2017-07-12T21:43:40+00:00
- Post Title: The Legend of Zelda: Twilight Princess HD Textures (.GTX)

Sorry to resurrect an old threat, but is there any chance you might be able to tell me how you were able to open the .pack file? I have yet to find any script for quickBms that is capable of it.
