## Post #1
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-30T21:23:48+00:00
- Post Title: Modern Warfare 2 .PAK

.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T21:50:14+00:00
- Post Title: Modern Warfare 2 .PAK

mah, this file is too strange.
practically it's only a sequence of zlib compressed blocks (2293) of various size and with no other info within them or at the end.
the only header is composed by the first 12 bytes which is a signature and an unrelated number.

I have tried to watch in the blocks and in a file generated with all these blocks ("offzip -a -1 imagefile3.pak . 0") but there are no info, no headers, nothing of nothing.
## Post #3
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-30T22:02:20+00:00
- Post Title: Modern Warfare 2 .PAK

Yeah, I tried that too. No file table anywhere, I've got no clue what this stuff is...
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-30T23:57:08+00:00
- Post Title: Modern Warfare 2 .PAK

there must be another file that comes with the game an external file table somewhere ma bee even in the exe (I don't have the game to look)
## Post #5
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-31T00:09:26+00:00
- Post Title: Modern Warfare 2 .PAK

I've found the music. Different Pak that I'd overlooked -> not compressed.
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2009-11-01T19:55:30+00:00
- Post Title: Modern Warfare 2 .PAK

It may not be compressed, but its a weird format for sure. starts with riff wave, and then has "IWXI" and "seek" in the header.  Infinity ward xma interleaved or something? (wild guess) did you get them to play/decode somehow?
## Post #7
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-11-02T16:00:37+00:00
- Post Title: Modern Warfare 2 .PAK

Yeah they work fine with ToWav. The structure is rather odd, I believe the seek is found in older xma headers, but far down the header rather than in the beginning.
## Post #8
- Username: CoDEmanX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 12, 2009 1:39 pm
- Post datetime: 2009-11-12T23:32:39+00:00
- Post Title: Modern Warfare 2 .PAK

> Reply from pietastesgood
>
> I've found the music. Different Pak that I'd overlooked -> not compressed.
unfortunately, the IWDs do not contain all of the sound fx and music 

there's only one weapon wave file in the archives for instance: iw_21.iwd\sound\weapons\grenade\weap_flashbang_tone.wav
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-13T19:36:59+00:00
- Post Title: Modern Warfare 2 .PAK

> Reply from pietastesgood
>
> Modern Warfare 2 was leaked today, and I've downloaded it

Read the rules. :

> * no warez
>
> * no talking about warez
>
> 
>
> Like I said in another thread: It is assumed everyone here owns a legal copy of any game they discuss. Discussing warez is against the rules and can be bannable on this forum.
>
> 
>
> Downloadable demos and other stuff you can legally get on your harddisk are fair game though.
## Post #10
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-11-14T06:47:28+00:00
- Post Title: Modern Warfare 2 .PAK

Sorry, I'll remember that in the future.
