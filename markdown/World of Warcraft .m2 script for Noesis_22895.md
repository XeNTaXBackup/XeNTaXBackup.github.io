## Post #1
- Username: kokoilie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 12, 2015 1:13 am
- Post datetime: 2020-10-24T16:50:35+00:00
- Post Title: World of Warcraft .m2 script for Noesis

I have written a script for Noesis that allows you to import .m2 models (player characters and mobs). It *should work with any version of the client, all you need to do is use an mpq editor to extract the .m2 model you want(and .skin file if it's WotLK or newer) from the game archive and open Noesis, then you can export it to your favourite format.


 fmt_blizz_m2.zip
(1.59 KiB) Downloaded 46 times


What is left to add is to read the bones.
*it should work but in case blizz decided to change something in a minor version please let me have a look at the model you can't open so i can adjust the code.
As i said in the Discord server - thank you to Chrrox, DKDave and Joshka for helping me understand python, the Noesis api and providing examples.

Edit: bone weights are stored in the vertexes, if anyone figures out how the bones are stored (position and indexes) please let me know.
Full info about the structure can be found here [https://wowdev.wiki/M2](https://wowdev.wiki/M2) but it didn't help me much.
