## Post #1
- Username: Mechnos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 18, 2007 7:08 am
- Post datetime: 2007-12-22T23:10:54+00:00
- Post Title: Unknown encryption file

Hello budies, I've extracted this two files from a GRA (I think by a programmer's mistake) it's the same image; with and without encryption.

Can you help me to understand witch kind of encryption is and how to decrypt them?

Mechnos
[CURSOR01.rar](https://xentaxbackup.github.io/file/1413_CURSOR01.rar)
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2007-12-23T22:52:53+00:00
- Post Title: Unknown encryption file

Are you sure that they're exactly the same file?

I haven't looked at it too much, but both files seem to have a unencrypted header, at least. The data doesn't look encrypted anyway. It seems an image.
## Post #3
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-04-01T11:50:44+00:00
- Post Title: Unknown encryption file

CURSOR01.XXX seems to be an RLE-encoded alpha-channel for CURSOR01.PCX
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2008-05-04T17:37:04+00:00
- Post Title: Unknown encryption file

The Sinking Island game use .lua files, but all encrypted. I need an decryptor, or I need to know, how can I decryt this.
Thx
[si_lua.zip](https://xentaxbackup.github.io/file/1503_si_lua.zip)
## Post #5
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-05-18T12:09:21+00:00
- Post Title: Unknown encryption file

> Reply from evin
>
> The Sinking Island game use .lua files, but all encrypted. I need an decryptor, or I need to know, how can I decryt this.
Thx

They are simply XORed by following pattern
{0x8a, 0x36, 0x5d, 0xc7, 0x99, 0x78, 0x90}
## Post #6
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2008-05-18T20:05:58+00:00
- Post Title: Unknown encryption file

> Reply from juskrey
>
> They are simply XORed by following pattern
{0x8a, 0x36, 0x5d, 0xc7, 0x99, 0x78, 0x90}

Thanks a lot.
## Post #7
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2013-05-09T01:19:41+00:00
- Post Title: Unknown encryption file

Ive translated the game using some tools long time ago, but it seems I've lost them now and cant pack it back. Any chance someone might help? I dont want my translation to go to waste. Thanks in advance.
