## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2022-09-12T12:49:02+00:00
- Post Title: Unpack/Repack UnityWebData1.0 Files?

Hey Guys,
I wanted to know if it's possible to unpack and repack UnityWebData1.0 Files?
I was able to unpack the file using AssetStudio, resulting in having these files lying around:


I want to edit some of the contents (unity3d, sharedAssets) and I know how to do that, but I haven't found a way to actually repack the UnityWebData1.0 File after editing the files. 
Any Idea how to do that?

I've uploaded the file I want to unpack and Repack: [https://cellenser.es/Demo/PokemonPCTrai ... se.data.br](https://cellenser.es/Demo/PokemonPCTraining/Build/Release.data.br) (which actually isn't compressed with brotli)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-09-12T21:18:45+00:00
- Post Title: Unpack/Repack UnityWebData1.0 Files?

Your link doesn't work.

By the way, check this [http://wiki.xentax.com/index.php/List_of_Unity_Tools](http://wiki.xentax.com/index.php/List_of_Unity_Tools)
## Post #3
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2022-09-13T12:57:56+00:00
- Post Title: Unpack/Repack UnityWebData1.0 Files?

> Reply from ikskoks ↑Tue Sep 13, 2022 5:18 am at Tue Sep 13, 2022 5:18 am
>
> 
Your link doesn't work.

By the way, check this http://wiki.xentax.com/index.php/List_of_Unity_Tools
ahhhh yea, sorry. edited the file in the link multiple times.
unfortunately there are currently no tools that lets you decompress, edit and recompress UnityWebData (yet).

Just figured out that the UnityWebData-Files are just multiple files packed in one (without any compression whatsoever).


So I wrote a simple tool in c# that "rebuilds" the UnityWebData, using the modified files (extracted with AssetStudio or the tool I made).
For comparison of both files, here are the links:
Original, unmodified file: [https://cellenser.es/Demo/PokemonPCTrai ... se.data.br](https://cellenser.es/Demo/PokemonPCTraining/Build/Release.data.br)
Modified file (containing modified & uncompressed data.unity3d-file): [https://cellenser.es/Demo/PokemonPCTrai ... ed.data.br](https://cellenser.es/Demo/PokemonPCTraining/Build/Modded.data.br)

The UnityWebData File was easy to rebuild.
Here's the documentation I made to make a tool rebuilding the UnityWebData.


The modified files in the game actually work fine!
As PoC, I replaced the Game Logo with a translated one.
Original Game: [https://pc.pokemon-foundation.or.jp/](https://pc.pokemon-foundation.or.jp/)
PoC on my Server (currently trying to translate the game): [https://cellenser.es/Demo/PokemonPCTraining/](https://cellenser.es/Demo/PokemonPCTraining/)
## Post #4
- Username: khunawv
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 06, 2022 11:17 am
- Post datetime: 2022-10-22T14:09:56+00:00
- Post Title: Unpack/Repack UnityWebData1.0 Files?

Sorry bro! Can you share your tools to make rebuilding unitywebdata? I have a problem same, thank you very very much
## Post #5
- Username: khunawv
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 06, 2022 11:17 am
- Post datetime: 2022-10-22T14:12:35+00:00
- Post Title: Unpack/Repack UnityWebData1.0 Files?

and one question Which tools did you use to repack data.unity3d when you edit decompressed data.unity3d?
Thank you very much again!!!
