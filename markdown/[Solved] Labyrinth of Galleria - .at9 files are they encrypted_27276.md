## Post #1
- Username: falco
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 06, 2023 9:20 am
- Post datetime: 2023-10-06T01:32:54+00:00
- Post Title: [Solved] Labyrinth of Galleria - *.at9 files are they encrypted?

Hello I am trying to extract the sountracks of the game Labyrinth of Galleria.
I used quickbms to extract .dat assets and I got .at9 files in BGM folder.
Then tried to open .at9 files in foobar and other players it didn't work.
Then tried to convert .at9 files using "AT9&AT3 Converter v2.3" and also vgmstream it didn't work.

> E:\vgmstrream>vgmstream-cli -o gallery.wav 24_gallarey.at9
>
> failed opening 24_gallarey.at9

file example: [https://files.catbox.moe/m61kir.at9](https://files.catbox.moe/m61kir.at9)

What can I do to play the soundtracks? Are the files encrypted? How to decrypt them? Thank you.
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-10-06T09:33:06+00:00
- Post Title: [Solved] Labyrinth of Galleria - *.at9 files are they encrypted?

It's not even an actual at9 file, but was a resource pack for ogg files split by 3 sections (intro-middle-outro).
You can make it playable on vgmstream by using this txth script
Save these script below as ".at9.txth" and put it on the same directory as the at9 files

```
subfile_extension = ogg

```


By default, it will play those splitted sections as one full songs.
## Post #3
- Username: falco
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 06, 2023 9:20 am
- Post datetime: 2023-10-06T13:59:58+00:00
- Post Title: [Solved] Labyrinth of Galleria - *.at9 files are they encrypted?

Yes it finally plays in foobar thank you
