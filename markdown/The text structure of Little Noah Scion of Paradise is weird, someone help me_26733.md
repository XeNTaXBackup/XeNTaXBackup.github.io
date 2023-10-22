## Post #1
- Username: TaiyoshinRE
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 05, 2023 9:27 pm
- Post datetime: 2023-05-05T13:35:06+00:00
- Post Title: The text structure of "Little Noah: Scion of Paradise" is weird, someone help me

Hello, I want to translate "Little Noah: Scion of Paradise", but when I check its text structure it's weird
Here is the link to the text: [https://drive.google.com/file/d/1cAN7K_ ... sp=sharing](https://drive.google.com/file/d/1cAN7K_ETYj-hEjXi_nM_dP53uA_SFNL1/view?usp=sharing)
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-05-05T17:45:24+00:00
- Post Title: The text structure of "Little Noah: Scion of Paradise" is weird, someone help me

Nothing wierd.

actually is very simple.

use ths script with quickbms.

```

for rip = 1 to entries
   get unk long
   get unk long
   get textsz byte
   savepos backone
   get check byte

   if check != 1 && check != 2 && check != 3
      goto backone
   endif

   savepos offset
   slog "" offset textsz utf8
   xmath next_off "(textsz + offset)"
   goto next_off
next rip

```
## Post #3
- Username: TaiyoshinRE
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 05, 2023 9:27 pm
- Post datetime: 2023-05-06T05:18:49+00:00
- Post Title: The text structure of "Little Noah: Scion of Paradise" is weird, someone help me

Thank you very much, it worked
## Post #4
- Username: TaiyoshinRE
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 05, 2023 9:27 pm
- Post datetime: 2023-05-08T14:27:00+00:00
- Post Title: The text structure of "Little Noah: Scion of Paradise" is weird, someone help me

> Reply from Rabatini ↑Sat May 06, 2023 1:45 am at Sat May 06, 2023 1:45 am
>
> 
Nothing wierd.

actually is very simple.

use ths script with quickbms.
Code: Select allget entries long

for rip = 1 to entries
   get unk long
   get unk long
   get textsz byte
   savepos backone
   get check byte

   if check != 1 && check != 2 && check != 3
      goto backone
   endif

   savepos offset
   slog "" offset textsz utf8
   xmath next_off "(textsz + offset)"
   goto next_off
next rip
Hello, i tried the tool and it exported perfectly. But the game crashed when i edited some random texts and reimported it to the game. But when i try some other random text the game still works fine.
## Post #5
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-05-09T00:40:10+00:00
- Post Title: The text structure of "Little Noah: Scion of Paradise" is weird, someone help me

Are you using localizantion ath with 3 r? -r-r-r ?
## Post #6
- Username: TaiyoshinRE
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri May 05, 2023 9:27 pm
- Post datetime: 2023-05-09T09:25:17+00:00
- Post Title: The text structure of "Little Noah: Scion of Paradise" is weird, someone help me

[https://imgur.com/dOsjBuo](https://imgur.com/dOsjBuo)
You mean like this? I already did it but the game still crashes
