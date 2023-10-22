## Post #1
- Username: John Connor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 21, 2008 6:16 am
- Post datetime: 2009-05-11T09:05:17+00:00
- Post Title: Gamecube .snd files

Anyone have any experience with this type of file? I can't seem to extract anything   

It comes from a folder named bgm so I assume there's music in there somewhere

Sample

```
http://rapidshare.com/files/231632302/01.snd
```


I'd be very greatful for any help
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-11T22:36:41+00:00
- Post Title: Gamecube .snd files

that file contains a gamecube adpcm stream.
you can identify it enough easily with a hex editor using the same method for the VAG adpcm of PS1/PS2, indeed if you scroll the file you will notice something like a "common layout" each 8 bytes.

the only problem is that I don't understand where is located the correct coefficient bytes of that file (I tried all the values betwen 0x26c and 0x 2b8) because otherwise it sounds a bit "noisy".
