## Post #1
- Username: PTRACER
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 03, 2019 10:01 pm
- Post datetime: 2019-06-03T14:06:24+00:00
- Post Title: Psygnosis DAT / WAV files from Formula 1 (1995, PC)

Using Game Extractor, I managed to extract the WAVs from the DAT but the files still won't play properly.

The header is interesting, since it says RIFF WAVEcmp rather than WAVEfmt. Also the data following suggests it's a mono @ 22050. Problem is nothing seems to understand it.

I can just about hear the sound through the garbage if I import it at 11025. Any thoughts?

[https://www.4shared.com/postDownload/ez ... OER02.html](https://www.4shared.com/postDownload/ezs_j6fVee/BADOER02.html)
## Post #2
- Username: DrMcCoy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 20, 2016 12:17 pm
- Post datetime: 2019-10-19T19:54:40+00:00
- Post Title: Psygnosis DAT / WAV files from Formula 1 (1995, PC)

Mid 90s, so probably some ADPCM codec. Try opening it as raw IMA ADPCM in Audacity. Or extract the contents of the data (or cmp) chunk prior, and open that in Audacity.

It that sounds exactly right, bingo. It it sounds slightly like it should, you need to figure out which exact ADPCM scheme it is and what the parameters are. There the fun begins, because there are a million of different variations out there.
## Post #3
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-10-22T02:50:56+00:00
- Post Title: Psygnosis DAT / WAV files from Formula 1 (1995, PC)

> Reply from DrMcCoy ↑Sun Oct 20, 2019 3:54 am at Sun Oct 20, 2019 3:54 am
>
> 
Mid 90s, so probably some ADPCM codec. Try opening it as raw IMA ADPCM in Audacity. Or extract the contents of the data (or cmp) chunk prior, and open that in Audacity.

It that sounds exactly right, bingo. It it sounds slightly like it should, you need to figure out which exact ADPCM scheme it is and what the parameters are. There the fun begins, because there are a million of different variations out there.

If you look closely enough at the file in the hex editor, you can see the stream is compressed with ZLIB I believe, not IMA codec. So, the data of the stream will need to be decompressed before anything can be used.
