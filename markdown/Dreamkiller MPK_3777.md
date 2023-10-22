## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-10-13T01:06:47+00:00
- Post Title: Dreamkiller MPK

Here i have a file from the new mindware game, dreamkiller, but it seems way different than Painkiller overdoses pack files, this string: 
```
MENGxV4.PACK
```
 couild indicate the format but im not farmiliar with it.

[http://www.megaupload.com/?d=PRD2KA5L](http://www.megaupload.com/?d=PRD2KA5L)

Thanks in advance
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-13T11:02:08+00:00
- Post Title: Dreamkiller MPK

it looks like a data only archive, there are no filenames and not a structure which allows to extract the files so I bet there is also an index file somewhere
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-10-13T11:12:18+00:00
- Post Title: Dreamkiller MPK

The only index file i find is th eone that lists the packs not whats inside of them.

Each level has three packs, A stream pack, a regular pack and a byte code pack, the bye code one looks like it could have some clues.

[http://www.megaupload.com/?d=9COEWN4E](http://www.megaupload.com/?d=9COEWN4E)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-13T12:06:55+00:00
- Post Title: Dreamkiller MPK

the problem remains the compression used for the files so it's not possible to extract them in their original format.
the following example script extracts only the non-compressed files:

*edit* updated script in the next post
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-10-13T13:18:18+00:00
- Post Title: Dreamkiller MPK

Thanks aluigi.

Was looking for the audio and it seems its ogg vorbis, i can scan the uncompressed headers, I hope there are not other ogg compressed headers though.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-17T16:38:46+00:00
- Post Title: Dreamkiller MPK

I have figured the decompression algorithm and I have included it in the new version of quickbms (0.3.4):
[http://aluigi.org/papers/bms/dreamkiller.bms](http://aluigi.org/papers/bms/dreamkiller.bms)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-18T13:56:59+00:00
- Post Title: Dreamkiller MPK

> Reply from OrangeC
>
> Was looking for the audio and it seems its ogg vorbis
in the script I have just updated in this moment (version 0.1.1) the files are saved in folders with the names of their types like CODE, TEXT, MESH and so on.

the ogg files are located in the WDAT folder and each file is a sequence of Oggs so you should just use oggextract to dump them all.

anyway they should be indexed in the files located in the WBNK folder but I have noticed something strange: if you extract shared.mpk and open the file WBNK\457.dat you will notice that the names of the files are a bit corrupted (like "l.@ayer/" instead of "player/"), the problem is that this archive is extracted as is from the mpk archive because it's not compressed so it is in that strange "corrupted state" originally.
## Post #8
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-10-29T19:35:52+00:00
- Post Title: Dreamkiller MPK

I've extracted [this file](http://www.sendspace.com/file/ytufi0) with above located 'bms' script.

So question is: what's next?

It 100% contains some text/subtitles for the game, but how to edit file correctly to translate?
Also where could be texture for the game to redraw font or does it uses a simple system font?
