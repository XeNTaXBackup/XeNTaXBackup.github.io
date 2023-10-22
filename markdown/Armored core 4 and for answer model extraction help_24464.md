## Post #1
- Username: amogus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2021 10:50 am
- Post datetime: 2021-09-07T00:54:40+00:00
- Post Title: Armored core 4 and for answer model extraction help

I am trying to extract the models and textures from Armored Core 4 and Armored Core for answer (xbox 360 version, I believe they use the same engine so I can't imagine the process would differ between them). So far I have gotten down to .mdl files and I have tried with model researcher and hex2obj to convert them to something I can import into blender but I have no clue what i'm doing. 

I believe the header ends at 0x6860

Attached is the .mdl I have been working with
[hl0010_g.rar](https://xentaxbackup.github.io/file/20741_hl0010_g.rar)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-09-07T16:06:25+00:00
- Post Title: Armored core 4 and for answer model extraction help

> Reply from amogus ↑Tue Sep 07, 2021 8:54 am at Tue Sep 07, 2021 8:54 am
>
> ... but I have no clue what i'm doing.
Then you'd probably be more clueless with AXE: 



hl0010_g.png (130.16 KiB) Viewed 157 times



The polygon vertex index count is at address 0xA44 as an unsigned 16-bit integer. While at address 0xA80, there're respectively the size of the indices data followed by its relative start offset, then the size of the vertex block followed by its relative start offset, all as 32-bit integers. The base address of these relative start offsets is stored at address 8 (which is 0x1000).
## Post #3
- Username: amogus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2021 10:50 am
- Post datetime: 2021-09-08T03:53:09+00:00
- Post Title: Armored core 4 and for answer model extraction help

Awesome! I managed to have success with converting the model on my own. I was wondering how you were able to determine why those values were at those addresses? Or how you determined what was what. I went on to another model and the addresses did not line up. I would assume there has to be some kind of pattern that applies to all of the models within the game and that the binary for each model isn't completely different.

Attached is the next model I tried to use.
[am0010_g.rar](https://xentaxbackup.github.io/file/20745_am0010_g.rar)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-09-08T15:54:10+00:00
- Post Title: Armored core 4 and for answer model extraction help

> Reply from amogus ↑Wed Sep 08, 2021 11:53 am at Wed Sep 08, 2021 11:53 am
>
> 
I was wondering how you were able to determine why those values were at those addresses? Or how you determined what was what.
The boundaries between different data in this format is easy to recognize. The truth is that you analyze the data first, from which you get info like the counts and the addresses, etc., then you look for them in the file. That's why it's called "reverse" engineering. 

> Reply from amogus ↑Wed Sep 08, 2021 11:53 am at Wed Sep 08, 2021 11:53 am
>
> 
I would assume there has to be some kind of pattern that applies to all of the models within the game and that the binary for each model isn't completely different.
There're 3 entries before the first indices chunk at 0x2800, corresponding to the 3 submeshes in the file. Each entry takes exactly 0x50 bytes so if you set the number of columns to 80 in your hex editor you'll have them aligned like this:



ana.png (136.46 KiB) Viewed 117 times



But don't attempt to load the 3rd submesh in AXE yet coz it'll trigger a bug and crash the program.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-09-08T15:57:16+00:00
- Post Title: Armored core 4 and for answer model extraction help

1st submesh for your reference:



am0010_g.png (155.81 KiB) Viewed 117 times
## Post #6
- Username: amogus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2021 10:50 am
- Post datetime: 2021-09-15T14:39:33+00:00
- Post Title: Armored core 4 and for answer model extraction help

Awesome! Thank you very much for the detailed information, I'll give it all a try after my first set of exams.
