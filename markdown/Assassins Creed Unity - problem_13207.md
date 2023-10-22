## Post #1
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2015-08-16T21:55:38+00:00
- Post Title: Assassins Creed Unity - problem

Hey guys, finally got around to playing Assassins Creed Unity.  Was trying to figure out how to extract the audio from the .pck files containing all the voice files and sound effects, but I ran into a problem.

So I am currently able to extract all the .wav files and convert them to .ogg, but the problem is that a lot of the sounds only play for like a split second then cut off.  The majority work fine, but there are probably hundreds that cut short when you try to play them.  Not sure why some sounds work and others do not.

Here is a quick rundown of the method I am using to extract and convert the sounds:

1.  Use QuickBMS in conjunction with wavescan.bms to extract all the wav files from the .pck file.
2.  Use a .bat file that automatically runs ww2ogg and revorb on the outputted .wav to convert them to playable .ogg files.

So after the above two steps, I am able to play all the .ogg files, but like I said, for some reason a lot of the sounds cut off prematurely.  This was never a problem with past AC games, so it must be something new regarding ACU.  Either that or I am screwing something up.

Anyway, here is a link to a .rar file that contains the following items:
1.  All the tools that I am currently using to try to make this work (quickbms, wavscan.bms, ww2ogg, revorb, etc).
2.  One of the smaller .pck files so you can try for yourself.  Most of the sounds work correctly in this .pck, but the first few sounds do not.  The problem is a lot more widespread in the larger .pck
3.  2 wav files and 2 ogg files that I already extracted.  One that works and one that doesn't so you can compare them.  sounds_eng_wrld_media_1~OasisID536924.ogg cuts off incorrectly, while sounds_eng_wrld_media_10~OasisID536945.ogg works properly.

Link:  [http://www.mediafire.com/download/r63b3 ... U_test.rar](http://www.mediafire.com/download/r63b3tge96jcbbz/ACU_test.rar)

Just wondering if there is a reason that some of the sounds don't work properly.  Not sure if it is the .bms script, or ww2ogg/revorb or even the .bat file itself.  Any help you guys can offer would be awesome.  Thanks.
## Post #2
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2015-08-18T18:40:27+00:00
- Post Title: Assassins Creed Unity - problem

Assassin's Creed Rogue Voice unpacker V1.00
https://yadi.sk/d/bAKjlU_UiXFCR
## Post #3
- Username: Seifer29
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 24, 2011 7:51 am
- Post datetime: 2015-08-19T22:53:17+00:00
- Post Title: Assassins Creed Unity - problem

Hey ponaromixxx, thanks for the link.  All the sounds extracted with that tool seem to work correctly.  Didn't even think about looking up AC Rogue, hah.  

Thanks again.
