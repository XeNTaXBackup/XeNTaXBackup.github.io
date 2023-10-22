## Post #1
- Username: BlueberryAi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 29, 2023 12:15 am
- Post datetime: 2023-05-28T17:59:54+00:00
- Post Title: HIT2 TW - UE4 Game AES Encryption Key

Hi! I'm pretty new to this forum and game data extraction in general. HIT2 is a Korean MMO made in UE 4.25.4 and it's the sequel to HIT - Heroes of Incredible Tales. The Taiwanese version released last week on may 23rd, and I saw ripped content being sold a week early on may 15th by a Chinese guy, so I'm not sure which version it was extracted from, but I really want to port a model from it, without paying $60.
I am only able to play the TW version and I've tried extracting the game's .pak files, but they use AES encryption. I've tried following this guide ([https://blog.jamie.holdings/2019/03/23/ ... -projects/](https://blog.jamie.holdings/2019/03/23/reverse-engineering-aes-keys-from-unreal-engine-4-projects/)), but I could not find a relevant string (e.g. "Corrupted index offset in pak file") when debugging the game's Shipping exe with x64dbg. Not sure if quickbms scripts can handle AES, but I could not find a relevant script anyway.
So, I'm asking here if anyone can help me with decrypting the game files, or can access some Korean/Chinese forums for info about extracting the game or models that have been ported from it. Thanks!
## Post #2
- Username: BlueberryAi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 29, 2023 12:15 am
- Post datetime: 2023-05-30T09:49:41+00:00
- Post Title: HIT2 TW - UE4 Game AES Encryption Key

Welp, it's the same key as the KR one. Found it on a Russian website, if anyone is interested: [https://cs.rin.ru/forum/viewtopic.php?f=10&t=100672](https://cs.rin.ru/forum/viewtopic.php?f=10&t=100672)
