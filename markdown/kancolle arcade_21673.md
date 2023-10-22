## Post #1
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2020-01-27T12:47:13+00:00
- Post Title: kancolle arcade

I wish ask if there is a project or a way to get files by Kancolle Arcade

I know its impossible because arcade kancolle is on arcade cabinet and models are available on cards only but  models are amazing
## Post #2
- Username: poudink
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 21, 2020 1:34 am
- Post datetime: 2020-01-27T18:22:01+00:00
- Post Title: kancolle arcade

it's possible to rip from arcade games as long as the rom contained in the cabinet gets ripped. I don't know if that's the case with this game though.
## Post #3
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2020-01-27T19:53:30+00:00
- Post Title: kancolle arcade

unluckily I have not found anything, it seems necessary to procure the cabinet physically and extract the ROM inside and the thing can be hard for data cards that contains the model data
## Post #4
- Username: Melvinnnn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Mar 14, 2019 5:06 am
- Post datetime: 2022-03-31T08:57:58+00:00
- Post Title: kancolle arcade

I just got a DVD rom of kancolle arcade nu 1.1. idk if you guys are still interested in this topic, but if you don't mind, could you please tell me how to extract a awesome 3d model?
## Post #5
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2022-03-31T21:26:50+00:00
- Post Title: kancolle arcade

> Reply from Melvinnnn ↑Thu Mar 31, 2022 4:57 pm at Thu Mar 31, 2022 4:57 pm
>
> 
I just got a DVD rom of kancolle arcade nu 1.1. idk if you guys are still interested in this topic, but if you don't mind, could you please tell me how to extract a awesome 3d model?

I'm interested in this too. I have some experience in reverse engineering.
## Post #6
- Username: Melvinnnn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Mar 14, 2019 5:06 am
- Post datetime: 2022-04-01T08:55:53+00:00
- Post Title: kancolle arcade

Well, the contents of rom are .pack and .app extensions. I tried to find out how to decrypt it, but didn't hit anything.

If anyone in this forum knows how to decrypt these please help....
## Post #7
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2022-04-04T02:59:24+00:00
- Post Title: kancolle arcade

I took a deeper look into how the encryption works.
Basically, the decryption involves two pieces of hardware, which is inside the Sega Nu machine itself and the key chip.Without those two things, you cannot decrypt the data.
The decryption combination of the Sega Nu machine and the key chip will allow decryption of the .pack file.The program inside the .pack file then decrypts the contents of the .app file.
So, in order to decrypt the game, you would need to dump the game while the Sega Nu machine is running the game. There is no way to do "offline" decryption of the game. All the dumps of Sega Nu games I've seen (running on Teknoparrot) have already been decrypted.
By the way, this is similar to how PS4 dumping works. The keys are embedded in the SAMU chip of the PS4 and are not dumped at this time, so the game needs to be dumped while the game is running.
So basically, what you need in order to decrypt is the game data, the key chip, and the Sega Nu machine. (You don't need the full cabinet)
## Post #8
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-04-05T03:47:02+00:00
- Post Title: kancolle arcade

> Reply from Melvinnnn ↑Thu Mar 31, 2022 4:57 pm at Thu Mar 31, 2022 4:57 pm
>
> 
I just got a DVD rom of kancolle arcade nu 1.1. idk if you guys are still interested in this topic, but if you don't mind, could you please tell me how to extract a awesome 3d model?

can you post samples?
## Post #9
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2022-04-05T11:23:40+00:00
- Post Title: kancolle arcade

> Reply from techtechi ↑Tue Apr 05, 2022 11:47 am at Tue Apr 05, 2022 11:47 am
>
> 
Melvinnnn wrote: ↑Thu Mar 31, 2022 4:57 pm
I just got a DVD rom of kancolle arcade nu 1.1. idk if you guys are still interested in this topic, but if you don't mind, could you please tell me how to extract a awesome 3d model?


can you post samples?

Can't really do that because the data is in giant (multiple GB) encrypted .app / .pack files, and only the Sega Nu / Key chip combination can really do the decryption.

If those files are sliced up to maybe 1MB it's still a useless encrypted blob without the key. No plaintext headers anywhere, and no plaintext executables to extract the decryption code from.
