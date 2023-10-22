## Post #1
- Username: pepodmc
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 28, 2017 1:29 pm
- Post datetime: 2018-10-20T13:15:36+00:00
- Post Title: Super Street Fighter 2 3DO music files

Hello.

Im trying to mod the music of the game Super Street Fighter 2 for 3DO console. I extracted the music files and I can play the music files with Windows media player classic (with K-lite codec pack installed).


But when I want to open the music file with audacity, i open it with "brute import" because audacity doesnt recognize the format of the sound files.

Some files opens in "stereo signed 8bit pcm" and other in "mono signed 16 bit pcm", but when I play the files in Audacity, theres a lot of background noise that doesnt exist when i open the music with windows media player classic.

I need to know the exact format of the music files so, I can create New music files to insert in the iso of the game.

Can anybody help me with this?

These are samples of the music files of the game:


Google drive:  [https://drive.google.com/open?id=18c_qC ... KQrJdLoFQ4](https://drive.google.com/open?id=18c_qCQoDDyZIwp0Wai8lYMKQrJdLoFQ4)


Mega:  [https://mega.nz/#!L5BwkCZZ!AULEvCJJ_Fnv ... WldEiaHmu0](https://mega.nz/#!L5BwkCZZ!AULEvCJJ_Fnv-q-qiCfYkFYQMQnOrTjkUWldEiaHmu0)



Thanks!!!
## Post #2
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2018-10-20T15:26:55+00:00
- Post Title: Super Street Fighter 2 3DO music files

It's AIFC(Squareroot-delta-exact SDX2 8-bit DPCM), playble with vgmstream plugin.
To convert aiff/wav to aifc try ZStream Reader
[http://forum.3doplanet.ru/viewtopic.php?f=17&t=2481](http://forum.3doplanet.ru/viewtopic.php?f=17&t=2481)
