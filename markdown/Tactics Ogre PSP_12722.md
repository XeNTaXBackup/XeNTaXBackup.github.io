## Post #1
- Username: Arolandis
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 28, 2015 11:13 am
- Post datetime: 2015-03-29T05:31:09+00:00
- Post Title: Tactics Ogre PSP

So I'm fairly new to this sort of thing and could use some help...

I've been spending the past few days trying to figure this game out. I can't tell if I just don't know how to "unpack" this game's contents or if it's encrypted/compressed, and requires a higher level of understanding.

I will say that as far as doing simple hex edits to change gameplay in the game has been very easy, text inside the game is displayed through a hex editor and easily edited, and I've even used TileMolester to view the sprites in the game. I just don't see any file names in what I've searched through, or at least I'm pretty sure there weren't any, so I can't tell if it's encrypted or what.

I'm working on the decrypted Data.bin from the INSDIR of the game, using pgdecrypt. ([You can get it here](http://filetrip.net/dl?uL2pbAz8dp))

The beginning of the file looks like this:



With "pakd" as the header. The black highlighted part is what I assume is the file size, since it leads to the end of the data portion of the first "pakd", then has 00's padded until the next "pakd" string appears.





Has anyone done any work on Tactics Ogre for PSP? Or could give me a little more direction for a newbie? I've had better success with easier formats like Phantom Brave for PSP, but this game's structure just has me dumbfounded. The only files I can find, if they are files, end in .src and seem to be used for event editing. Everything else is archaic... My ultimate goal is to be able to extract graphics files in the game but not much that I've seen makes sense. I also see a few strings saying "Photoshop ICC profile" occasionally.

Edit: If you want to have a look and maybe get a better grasp of it: [The file I'm working on](https://www.mediafire.com/?tl4bcfqqv6r3535)
## Post #2
- Username: offering7866
- Rank: advanced
- Number of posts: 59
- Joined date: Fri Feb 24, 2017 2:16 pm
- Post datetime: 2017-02-24T19:02:59+00:00
- Post Title: Tactics Ogre PSP

You could ask this topic creator from GameFAQs about it since they already made some tweaks in the game: [https://www.gamefaqs.com/boards/999440- ... r/74725095](https://www.gamefaqs.com/boards/999440-tactics-ogre-let-us-cling-together/74725095)
## Post #3
- Username: lojki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 17, 2017 9:17 pm
- Post datetime: 2017-03-17T13:20:52+00:00
- Post Title: Tactics Ogre PSP

So I'm fairly new to this sort of thing and could use some help...

I've been spending the past few days trying to figure this game out. I can't tell if I just don't know how to "unpack" this game's contents or if it's encrypted/compressed, and requires a higher level of understanding.

I will say that as far as doing simple hex edits to change gameplay in the game has been very easy, text inside the game is displayed through a hex editor and easily edited, and I've even used TileMolester to view the sprites in the game. I just don't see any file names in what I've searched through, or at least I'm pretty sure there weren't any, so I can't tell if it's encrypted or what.

I'm working on the decrypted Data.bin from the INSDIR of the game, using pgdecrypt. (You can get it here)

The beginning of the file looks like this:


With "pakd" as the header. The black highlighted part is what I assume is the file size, since it leads to the end of the data portion of the first "pakd", then has 00's padded until the next "pakd" string appears.


Has anyone done any work on Tactics Ogre for PSP? Or could give me a little more direction for a newbie? I've had better success with easier formats like Phantom Brave for PSP, but this game's structure just has me dumbfounded. The only files I can find, if they are files, end in .src and seem to be used for event editing. Everything else is archaic... My ultimate goal is to be able to extract graphics files in the game but not much that I've seen makes sense. I also see a few strings saying "Photoshop ICC profile" occasionally.

Edit: If you want to have a look and maybe get a better grasp of it:
