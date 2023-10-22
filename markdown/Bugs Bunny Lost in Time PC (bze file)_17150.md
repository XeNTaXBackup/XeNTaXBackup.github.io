## Post #1
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2017-10-17T18:50:10+00:00
- Post Title: Bugs Bunny Lost in Time PC (bze file)

There is this .bze file that is, if I'm correct, all the information about the level, it may contain models, textures and the sound files, when I extract it with Dragon Unpacker I receive an .669 file.
 Then I try to import as a raw file into audacity and I can hear some sound pretty baddly and in the background you can hear some static noise because of the codification but the sounds maybe are contained inside an archive on the .bze or in the .669 file but stills unknow.
I'll leave here the .bze file and the .669 file so you guys can check it out.


Thanks.
[bze.zip](https://xentaxbackup.github.io/file/13455_bze.zip)
## Post #2
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2017-10-17T18:51:04+00:00
- Post Title: Bugs Bunny Lost in Time PC (bze file)

Here's the .669 file
[669.zip](https://xentaxbackup.github.io/file/13456_669.zip)
## Post #3
- Username: SlavaVlasov
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:00 am
- Post datetime: 2019-06-23T17:26:52+00:00
- Post Title: Bugs Bunny Lost in Time PC (bze file)

I also studied the PC version. As I understand it, in the PC version the files are decompressed. This I often observe (for example, compressed graphics in Toy Story 2 and Magical Racing Tour on PS1 and uncompressed on PC). However, in the PC version of this game I see the mixed byte "FF", which is displayed on my Russian OS as "я" char in a hex editor. For example "Steяreo".

I decided to experiment roughly, and simply deleted it by replacing the FF byte in the entire file in the hex editor. Then I tried to open such a file in Tile Molester. And if earlier it opened incorrectly, now part of the image has been displayed as it should. The only point is that it seems that not all FFs should be deleted, since It seems that some of them are responsible for the image pixels, and due to the absence of such a byte, another part of the image is shifted.

Like this:

Test file: L_Mwitch_1.bze, 582 KB from the BZE folder
I opened it in Tile Molester with the following settings: 15bpp BGR (555) and Canvas Size: 72 columns x 63 rows.

After removing the FF byte, it had to be opened with other parameters: 15bpp BGR (555) and Canvas Size: 64 columns x 66 rows.

And now...

I used russian version of game. What is interesting, firstly, the picture partially began to look close to the original (especially in color). Secondly, the first half of the image (Title) and the first half of the bottom part of the image (Loading) quite began to look normal (compared to what it was). It is also interesting that the last time there were 72 columns, and after manipulating the file it took 64. It turns out that the difference of "8" is that FF byte.

As for the sound (I also heard this noise - I listened in MFAudio) - it looks like the same story with this byte. I think it causes this background noise. Also, I tried to open the sound of the game (like speech00.xa) in Audacity (well, that this program can open untyped sound files), and I want to say that if you play around with the settings, you can open the file so that there is less noise. While in theory I can conclude that if you clean the sound of the FF byte, then there is a chance to open it correctly at least partially. I have not checked it myself yet ...

I hope I helped a little.
## Post #4
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2020-04-05T20:34:58+00:00
- Post Title: Bugs Bunny Lost in Time PC (bze file)

So what I did discovered with this is that BZE files are basically containers that hold VAG files and TIM files that are formats used in the PS1 games, basically the developers just ported the ps1 files to the PC and made it work. I have a tool that can edit the tim files but when I import back it doesn't work properly. The tools I have is only for the PS1 files but still, they are pretty similar in how they work. I didn't made this tool, it was a friend of mine that now doesn't have time to look back on it but yeah. 

Your discovery is amazing but will try to get more work done into the PS1 version before passing to the PC version and study it more.
