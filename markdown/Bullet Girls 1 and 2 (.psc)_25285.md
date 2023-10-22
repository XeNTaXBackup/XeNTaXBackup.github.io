## Post #1
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2022-04-22T22:08:37+00:00
- Post Title: Bullet Girls 1 and 2 (.psc)

The games use an unknown format (.psc) and they have a 'PSCA' header. I believe the format is the same between the two games. Model Researcher could find some vertices on the files. Hopefully someone with more knowledge or experience will take a look at this format. A script, like one for Noesis would be nice.

[https://cdn.discordapp.com/attachments/ ... titled.png](https://cdn.discordapp.com/attachments/493152982293282816/967012537210114058/Untitled.png)

Sample files: [https://cdn.discordapp.com/attachments/ ... -2_psc.rar](https://cdn.discordapp.com/attachments/493152982293282816/967012162541350932/bulletgirls1-2_psc.rar)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-04-25T22:55:59+00:00
- Post Title: Bullet Girls 1 and 2 (.psc)

> Reply from Natsuki Okusawa ↑Sat Apr 23, 2022 6:08 am at Sat Apr 23, 2022 6:08 am
>
> 
format (.psc) could find some vertices on the files
You have found the position of the bones.
to find vertices you need to look for "short_signed"
here is my plugin (draft).
mesh and bones (without parents):

(I'm too lazy continue to work on it.) 
[fmt_psc.zip](https://xentaxbackup.github.io/file/22157_fmt_psc.zip)
## Post #3
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2022-04-26T03:35:42+00:00
- Post Title: Bullet Girls 1 and 2 (.psc)

Thank you very much for taking the time to look at this. I highly appreciate it.
## Post #4
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2022-04-26T07:06:33+00:00
- Post Title: Bullet Girls 1 and 2 (.psc)

I went on and tried to find faces on a smaller file, and looks like I found them.
[https://imgur.com/kcSnMD8](https://imgur.com/kcSnMD8)

View in hex:
[https://imgur.com/itOndBw](https://imgur.com/itOndBw)

I'm not sure if I found the correct UVs
[https://imgur.com/jvoL5ZW](https://imgur.com/jvoL5ZW)

Hopefully these are gonna be helpful for improving the script. Sadly, I know nothing about scripting.   


 00000066.rar
00000066.psc (552 Bytes) Downloaded 20 times
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-04-26T17:27:43+00:00
- Post Title: Bullet Girls 1 and 2 (.psc)

i update 'plugin'.

> Reply from Natsuki Okusawa ↑Tue Apr 26, 2022 3:06 pm at Tue Apr 26, 2022 3:06 pm
>
> 
I went on and tried to find faces on a smaller file, and looks like I found them.
yes, it's a face, sort of like quads.
post yet small samples.
maybe I'll take a closer look.
## Post #6
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2022-04-26T17:47:57+00:00
- Post Title: Bullet Girls 1 and 2 (.psc)

Sure man, here you go:


 morepsc.rar
(29.42 KiB) Downloaded 18 times
## Post #7
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2022-04-26T17:57:57+00:00
- Post Title: Bullet Girls 1 and 2 (.psc)

I also have a feeling that the format may be similar to some danganronpa game
[viewtopic.php?t=16463](https://forum.xentax.com/viewtopic.php?t=16463)
even the header is similar
