## Post #1
- Username: John Connor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 21, 2008 6:16 am
- Post datetime: 2009-05-19T14:08:39+00:00
- Post Title: MF Audio & Interleave Settings

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-19T14:55:26+00:00
- Post Title: MF Audio & Interleave Settings

the interleave value is ever a boring field because in some games it can change for every file (like in "The Warriors") while in others it's ever the same.
in the case of the file you posted it's simply set to 0x1000 and the data starts at offset 0x800.

I recognized the offset because luckily the adpcm streams used on playstation and nintendo are easily recognizable simply following the pattern with the eyes and I guessed the interleave value watching the final part of the file (00 02 00 00 00...), practically 0x233ba0 - 0x232ba0 = 0x1000
hope this will help you also in future.

in the past I wrote a tool just for extracting the musics of The Warriors and it can be used also to build a SS2 file which can be played with winamp or any other player supporting the [vgmstream](http://hcs64.com/files/vgmstream/?C=M;O=D) plugin (so you don't need to reconvert it in wav/mp3 or using mfaudio).

my tool is called [vagguess](http://aluigi.org/papers/vagguess.zip) and the following is the example usage for the file you provided:
vagguess -o 0x800 -i 0x1000 -D BUTCHSHP.RWS

it will create the file 00000000.ss2 that you can play through vgmstream + winamp
## Post #3
- Username: John Connor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 21, 2008 6:16 am
- Post datetime: 2009-05-19T15:04:24+00:00
- Post Title: MF Audio & Interleave Settings

Great, thanks for the help, much appreciated.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-20T07:18:28+00:00
- Post Title: MF Audio & Interleave Settings

> Reply from John Connor
>
> Great, thanks for the help, much appreciated.

Indeed, so why not press bugtest's "thank post" button to show gratitude?
