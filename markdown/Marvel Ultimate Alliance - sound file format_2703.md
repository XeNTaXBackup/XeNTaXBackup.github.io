## Post #1
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-12T12:31:58+00:00
- Post Title: Marvel Ultimate Alliance - sound file format

I found the specs on the WIKI for the ZSM/ZSS file format and wrote an extractor. While the filenames are ".WAV" files, the content is just data. The files seem to be too small for WAV, probably some compressed format.  These are possibly headerless also.  Anyone care to take a whack at one?

Smallest file attached.

    8 -rw-r--r--  1 Users       Users      4864 Jul 12 08:17 ISEEYOU5_A.wav

/s: filedmp ISEEYOU5_A.wav
0000  ad090539  93321311  2139931d  0ac20abb  *...9.2..!9......*
0010  bbc90aa1  2b1330b1  10191a93  50912109  *....+.0.....P.!.*
0020  33a9931b  a9b9992b  b1210da1  239ab931  *3......+.!..#..1*
0030  1a923109  11a9912a  90bc14a0  311232b2  *..1....*....1.2.*
0040  50b910b3  af140aa3  2c995388  a022bd33  *P.......,.S..".3*
0050  ba219b97  38ba2219  9649a011  20aba039  *.!..8."..I.. ..9*
0060  cab06281  199340b3  1d9208db  19d00ab8  *..b...@.........*
0070  18b9aa09  31a1333b  94329cb0  b90fa008  *....1.3;.2......*
0080  11522917  00121ca2  119da24a  b09b91eb  *.R)........J....*
0090  083a9529  b0528902  0c00b33b  0b031359  *.:.).R.....;...Y*
00a0  b102dbbb  a8bbbd99  31241115  38b33990  *........1$..8.9.*
00b0  1509b020  bb11b159  0b923114  01bb3111  *... ...Y..1...1.*
...

Again, TIA!
[ISEEYOU5_A.zip](https://xentaxbackup.github.io/file/1259_ISEEYOU5_A.zip)
## Post #2
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-12T14:24:09+00:00
- Post Title: Marvel Ultimate Alliance - sound file format

Working on it. Found some info over in another forum. I extracted all the files and am using Vox Studio 3 to re-encode them.  The input paramters are:

Type: BiCom, adpcm, 22050 sampling rate.  The sounds play fine. Trying for conversion to standard WAV now... will report back and post extractor source.
## Post #3
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-12T15:15:47+00:00
- Post Title: Marvel Ultimate Alliance - sound file format

> Reply from Dandapani
>
> Working on it. Found some info over in another forum. I extracted all the files and am using Vox Studio 3 to re-encode them.  The input paramters are:

Type: BiCom, adpcm, 22050 sampling rate.  The sounds play fine. Trying for conversion to standard WAV now... will report back and post extractor source.

Vox Studio 3.0 seems to have trouble converting more than 5 files in a batch.  I did some more searching and found this towav.exe tool on a russian site.  Here's googles translation of the page. This tool takes the entire ZSM/ZSS file and pulls out the sounds and puts them into a subdir in WAV format.

[http://translate.google.com/translate?u ... uage_tools](http://translate.google.com/translate?u=http%3A%2F%2Fwww.ctpax-x.ru%2F&langpair=ru%7Cen&hl=en&ie=UTF-8&oe=UTF-8&prev=%2Flanguage_tools)
## Post #4
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-12T20:32:10+00:00
- Post Title: Marvel Ultimate Alliance - sound file format

I was able to decode the ".SFD" movies, at least to pull the audio out. I found an old tool on a Japanese Dreamcast site call sfd2mpg.  It relies on an external audio decoder (toolame32) to convert the audio from wav to mp2.  I wrote a dummy tool named toolame32 that just prints its arguments and does nothing else and sfd2mpg stops when it finds that the external audio tool failed to create a "tmp.mp2" from the "tmp.wav" it had extracted from the SFD file.  Bingo.  Wrote a script that pulls all of this together and just renames the "tmp.wav" into a more meaningful name and ran the script against all the SFD files. Audio!
## Post #5
- Username: Supermann
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 09, 2006 2:04 pm
- Post datetime: 2007-10-13T19:51:42+00:00
- Post Title: Marvel Ultimate Alliance - sound file format

Hi there, could you upload the game music to somewhere? The Russian site is down.
## Post #6
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2007-11-29T17:46:59+00:00
- Post Title: Marvel Ultimate Alliance - sound file format

Sorry to bump, but I'm from over at marvelmods.com.  One of our users, Winstrol, has built a ZSS/ZSM builder that works for both PC and Xbox.  We have one issue however:  The PC format isn't actually Bicom VOX.  They extract fine, but using Vox Studio 3 to encode back to the same settings (Bicom, ADPCM, 22050) results in a rather scratchy sound in game.  If anyone can help us out that'd be great.  All the information (along with sample files and the tool we use) can be found in the topic below, pages 15-18

[http://marvelmods.com/forum/index.php?topic=4.0](http://marvelmods.com/forum/index.php?topic=4.0)
