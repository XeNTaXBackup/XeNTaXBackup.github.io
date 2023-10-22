## Post #1
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-11-09T06:30:36+00:00
- Post Title: Metal Gear Rising: Revengeance .Wem Audio files

I need help with the sound format of this game the game uses Wwise's .wem audio format it's usually not very difficult to do modding for this type of format the problem is that when I convert the audio inside the program and put it inside the game it happens 2 strange things nothing or sounds like corrupted audio

i have the original files and i noticed that they have a considerable difference within the hex tool i wanted to know what i'm doing wrong i'm about to go insane i compiled from 5 versions of wwise including the one from when the game is in development comparing the formats of these versions I believe the wwise version is not the problem they have slight differences in the format of the
2012.2 and identical to 2013.2
I believe there is not much difference I know that the first version is 2012.2
the pc version of the game released and 2014 in January so a version between 2012.2 to 2014.1

if anyone can help me i would appreciate it

Samples:

ALL GAME SOUND COTENT
[https://drive.google.com/file/d/1NBBt_B ... share_link](https://drive.google.com/file/d/1NBBt_BizUcP0ASzLBGCWjP_CGue1jbSf/view?usp=share_link)

Small sample
[https://drive.google.com/file/d/1FKPYYL ... share_link](https://drive.google.com/file/d/1FKPYYLsV63C-xTL1EypCgzuVGmnIv5AN/view?usp=share_link)

Platinum Document About Metal Gear Rising (Frequency and Compression Information)
[https://www.audiokinetic.com/download/d ... BGM_en.pdf](https://www.audiokinetic.com/download/documents/customer_profiles/MGR_Wwise_BGM_en.pdf)
[https://www.audiokinetic.com/download/d ... _SE_en.pdf](https://www.audiokinetic.com/download/documents/customer_profiles/MGR_Wwise_SE_en.pdf)
## Post #2
- Username: LeoFeroz
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jan 07, 2021 1:08 am
- Post datetime: 2022-11-10T05:12:23+00:00
- Post Title: Metal Gear Rising: Revengeance .Wem Audio files

Some things I discovered using hex tool (Before asking me something I don't know much about binary formats but I know how to handle a hex tool, everything that is here is merely by trial and error tests)


For some reason the original format has big data until it finds the @DDs in 7CAB
[/img][https://cdn.discordapp.com/attachments/ ... 6/7CAB.png](https://cdn.discordapp.com/attachments/741478296331485184/1040129497720160316/7CAB.png)[/img]

On recompilation with the same version of the program it has @DDs very on top


When I downloaded a newer version of the program and enabled an option that only exists in newer versions of the program called "Allow Channel upmix"

it generated a file more similar to the original not totally clear but because of the fact that @DDs is very low in 8CB


The audio used in the tests is the same as the original, only extracted and placed in the program again
