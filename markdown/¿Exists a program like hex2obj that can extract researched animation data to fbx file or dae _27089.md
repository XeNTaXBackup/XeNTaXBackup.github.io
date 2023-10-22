## Post #1
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-08-10T10:23:39+00:00
- Post Title: ¿Exists a program like hex2obj that can extract researched animation data to fbx file or dae ?

Hello i researched CarrotRunnerMaster! and y geted mesh data by


on HXD editor opened file search patron coded with int 16 bytes in this case for carrot runner faces start at offset 0x064E4
i select all bytes to end of patron of coded int 16 bytes 
the leinght size is 48C i divide this by 2 on calculator and i get 582 on decimal that is the count of faces 
now i open hex2obj opening file and put data.
I geted count of vertices but need to add +6 on 696A is = 6970 
i put data on float 32
now get next offset 0x7028 on this offset i start search patron that contains 8 null bytes or 4
i finded and next is 7400 that is for uvs on float 16 bytes and result is carrot runner on t-pose with texture on blender

now i need to find program can extract animation data 

any help is very full 
thanks.
[CarrotRunner!.zip](https://xentaxbackup.github.io/file/24211_CarrotRunner!.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-07T08:07:04+00:00
- Post Title: ¿Exists a program like hex2obj that can extract researched animation data to fbx file or dae ?

Ha, you and your CarrotRunner. How many years do we talk about fmlb files? 7 Years?

Ok, now for your request. Watch out for ARC:

> Reply from Bigchillghost ↑Thu Sep 14, 2023 11:05 pm at Thu Sep 14, 2023 11:05 pm
>
> 
.

> Reply from Bigchillghost
>
> 4) Main Features
1. Support for parsing animation related data of all sorts of data types;

You will need: 1) some basic understanding of animations, that is keyframe, translation, rotation, quaternion, and so on.
2) much time to learn, a month at least, if not more

Remember that the forum will shut down at year's end. So start now or never. 

btw, you know English uses irregular verbs, do you? Your text is partially a tornment to read.
There is no such verb as "finded", it's "found". And it's "got", not "getted".

[https://www.englishclub.com/vocabulary/ ... s-list.php](https://www.englishclub.com/vocabulary/irregular-verbs-list.php)
## Post #3
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-10-08T13:04:29+00:00
- Post Title: ¿Exists a program like hex2obj that can extract researched animation data to fbx file or dae ?

Bacouse i am from spain
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-08T14:03:49+00:00
- Post Title: ¿Exists a program like hex2obj that can extract researched animation data to fbx file or dae ?

> Reply from Dani ↑Sun Oct 08, 2023 9:04 pm at Sun Oct 08, 2023 9:04 pm
>
> 
Bacouse i am from spainUsers from spain can also use the irregular verbs list.  
I'm not a native speaker, too and my english is modest, I guess.
But using the list is basic, imho.

But you're not alone: did a search for "readed" and there were 17 matches solely in the models forum.

What about ARC? Will you try to use it?
