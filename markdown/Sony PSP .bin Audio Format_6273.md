## Post #1
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2011-03-23T20:17:07+00:00
- Post Title: Sony PSP .bin Audio Format

Hi, recently I created a topic on here about a different audio format, but I managed to figure it out. So, in a sense I'm sorry for posting again, but I need the help.

I have Yu-Gi-Oh! GX Tag Force on PSP, and I have extracted a file called psp_snddat.bin. Please note that that this is not an image file, and cannot be opened using an ISO extractor, etc. The file does contain audio tracks, but I am unsure how to get them out of the file. If I could open the file and see the tracks inside that would be a lot easier, or a converter to do it for me.

As it is a PSP file format, the file cannot be opened in programs such as MFaudio and cannot be scanned with Cube Media Player. The data cannot be imported into Audacity, as it reads the file incorrectly.

There is also a PS2 version of this game, with a file that the tracks can be scanned, imported, converted, etc. But the frequency is too high and the tracks are broken, as they will repeat themselves from the begginning at random intervals.

I can upload a sample of the .bin file if someone is willing to look. Other people such as users on YouTube have recorded audio from games like this simply by capturing what will be the output of the speakers, however I would like to rip the actually files from the game.

This is the first few lines of the .bin file:
0000 : 53  50  00  00  00  48  0B  00  20  00  00  00  00  00  00  00   SP...H.. .......
0010 : 00  00  00  00  40  00  00  00  00  00  00  00  00  00  00  00   ....@...........
0020 : 7F  40  00  00  00  00  00  00  00  00  00  00  00  00  00  00   .@..............
0030 : 00  00  00  00  00  00  00  00  77  63  01  00  00  00  00  00   ........wc......
0040 : 98  40  0B  00  52  49  46  46  90  40  0B  00  57  41  56  45   .@..RIFF.@..WAVE
0050 : 66  6D  74  20  34  00  00  00  FE  FF  02  00  44  AC  00  00   fmt 4.......D...
0060 : A0  1F  00  00  78  01  00  00  22  00  00  08  03  00  00  00   ....x...".......
0070 : BF  AA  23  E9  58  CB  71  44  A1  19  FF  FA  01  E4  CE  62   ..#.X.qD.......b
0080 : 01  00  28  2E  00  00  00  00  00  00  00  00  66  61  63  74   ..(.........fact
0090 : 08  00  00  00  00  3C  3D  00  00  08  00  00  64  61  74  61   .....<=.....data
00A0 : 38  40  0B  00  3A  62  05  01  41  80  01  01  01  01  01  01   8@..:b..A.......

I have no idea how to convert this, but I think it can be a native file format, as Riff and Wave is mentioned... But I'm not sure.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-03-24T02:43:28+00:00
- Post Title: Sony PSP .bin Audio Format

Hmm, try using Alpha's Wave Scanner script on the files first.

Most PSP games use ATRAC as their primary codec. So try Alpha's ATRAC scripts like AA_To_AA3 if the Wave Scanner doesn't succeed.
## Post #3
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2011-03-24T07:46:37+00:00
- Post Title: Sony PSP .bin Audio Format

This game uses Atrac3 or Atrac3 plus (can't remember which). Use nova extractor to scan for wave files then rename them to at3 and run them through alphas at3 to aa3 script then import them into Sony Vegas or Soundforge. Couldn't be simpler.
## Post #4
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2011-03-24T18:52:48+00:00
- Post Title: Sony PSP .bin Audio Format

I scanned using Extractor, and it found around 1,500 files inside... But changing to .at3, do I just change extension through renaming? Or do I need a converter?
## Post #5
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-03-24T22:52:42+00:00
- Post Title: Sony PSP .bin Audio Format

You can use a program called Bulk Rename Utility which can batch rename the extensions for you
## Post #6
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2011-03-24T22:57:57+00:00
- Post Title: Sony PSP .bin Audio Format

Thanks, I'll give it a go. 

Turns out I didn't look right, and there's 15,000 files... D: I'll have fun. Guess it's sound effects.
## Post #7
- Username: Skyknight
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 23, 2010 1:26 am
- Post datetime: 2011-03-25T18:41:45+00:00
- Post Title: Sony PSP .bin Audio Format

In the hex code you posted, I already see 1 at3 file screaming "extract me!"    

Anyway, you can do it yourself, it's just is a tedious job    I don't know if there's an automatic hex extractor or something since I do it myself.

If you upload the file I can point you out the correct headers for those AT3 files so you can do it.
## Post #8
- Username: JiburiruAries
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 6:06 am
- Post datetime: 2011-03-25T18:58:04+00:00
- Post Title: Sony PSP .bin Audio Format

I've managed to do it, I got the music! XD Hahah I'm so happy now lol... And I got programs to do it for me, so I didn't/won't have to mess around with hex numbers. C: Thanks for the help guys!
## Post #9
- Username: ghgh3022
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 19, 2021 10:40 pm
- Post datetime: 2021-02-19T14:46:03+00:00
- Post Title: Sony PSP .bin Audio Format

mind telling me what tools did u use
## Post #10
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-07-10T04:55:20+00:00
- Post Title: Sony PSP .bin Audio Format

Looks like he/she uses nova extractor, but it's a bit hard to find the download link now
