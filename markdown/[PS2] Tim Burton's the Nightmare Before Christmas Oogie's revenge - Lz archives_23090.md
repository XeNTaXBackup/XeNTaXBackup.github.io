## Post #1
- Username: atsushiDM
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 30, 2020 4:20 pm
- Post datetime: 2020-11-30T09:05:15+00:00
- Post Title: [PS2] Tim Burton's the Nightmare Before Christmas: Oogie's revenge - Lz archives

Faced troubles trying to translate this game.
After unpacking data.stm from USA-release (SLUS-20860) with bms-script, found a lot of .lz archives inside. They contain ingame models, scripts and dialogue text in files "talk_u.bms" and "event.bms" (require special chr-table).



screen 1.png (36.09 KiB) Viewed 55 times


They could easily be opened with QuickBMS, but the script doesn't support re-packing. I need a solution how to replace original messages and textures with edited inside that "xx.lz". Thanks in advance. The script and one of that achives are attached below.

[https://yadi.sk/d/Y259Vl3Nv3ee1Q](https://yadi.sk/d/Y259Vl3Nv3ee1Q)
[https://yadi.sk/d/iyuLskFIAmigyw](https://yadi.sk/d/iyuLskFIAmigyw)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-01T10:16:39+00:00
- Post Title: [PS2] Tim Burton's the Nightmare Before Christmas: Oogie's revenge - Lz archives

I'm afraid that the only thing that could be done is to write custom tool
for unpacking and packing in C++, Python etc.

This  quickbms script you provided is not that hard to rewrite
except this ALZ compression routine which may be problematic.

You could probably search through quickbms source to see how this alz function is implemented [https://aluigi.altervista.org/papers/qu ... 0.10.1.zip](https://aluigi.altervista.org/papers/quickbms-src-0.10.1.zip)
or just search for some language specific equivalent like this [https://pypi.org/project/pyunpack/0.1.2/](https://pypi.org/project/pyunpack/0.1.2/)
