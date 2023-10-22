## Post #1
- Username: Shademp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 30, 2015 12:27 am
- Post datetime: 2016-11-18T18:42:10+00:00
- Post Title: Question: How to play Dirge of Cerberus audio files?

Addressing either of the two approaches I have made might be the key to succeeding in properly extracting and playing the audio files.

#1: Ripping .pss files and using that. The only tutorial I found online (at [animemusicvideos](http://www.animemusicvideos.org/forum/viewtopic.php?t=29514)) on how to actually get the .pss files is no longer applicable, because the Nova Software Extractor is not available online. Does anybody have that software, or know of an equivalent, or will I not find the audio files by trying to rip .pss files?


#2: Playing .at2 and .at3 files. After following instructions on how to unpack Dirge of Cerberus using Noesis, the files that appear to deal with sound have the .at2 and .at3 extensions.
- [Link to filelist example](http://i.imgur.com/U7hmHHc.png)
In this [topic from two years ago](http://forum.xentax.com/viewtopic.php?f=17&t=12160&hilit=at3), the recommendation was to use Foobar2000. I installed Foobar2000 but it would not recognize the Dirge of Cerberus files. Is some customization of Foobar2000 necessary? My impression so far has been that you can only play .at3 files with PSP and PS3 titles.


My main goal is to find and play back the voice acted lines of the game. I own all four versions of Dirge of Cerberus, so version differences are not an issue here.
## Post #2
- Username: Shademp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 30, 2015 12:27 am
- Post datetime: 2016-11-21T11:37:26+00:00
- Post Title: Question: How to play Dirge of Cerberus audio files?

Posting the fruits of my research for others who are interested in the Dirge of Cerberus audio.

By using the [PSound](http://www.zophar.net/utilities/psxutil/psound-soundreaver2.html) utility you can listen to the four .wd files that exists in the data > sound2 folder.

These four files contain a variety of stock sound effects (including a dolphin squeek!) and grunts and exclamations from various characters in the game. All voiced clips are in Japanese in all versions where these files are found.

wave0001.wd contains voice clips from the player character of the Dirge of Cerberus Multiplayer. Look to wave0001.wd in the original Japanese release to get the greatest number of these short voice clips.


In the US and PAL versions, the sound2 folder contains the "jsnddb.txt" file. It is a guide to the sound directory of the game. (japanese sound directory band, perhaps?). The guide is listed as one long string, but I created a version with proper line breaks so that the document might be analysed.

Google Sheet Docs:
- [Guide to jsnddb.txt](https://docs.google.com/spreadsheets/d/1oKRRLf4H9qSuHeL3wDsiZPvkiZlJ1KWnY5HrO7ayTt4/edit)
- [Comparing jsnddb.txt](https://docs.google.com/spreadsheets/d/1y7Ay0R2b9AY_nA2I5kdI7lS_Dg18_jDHp3JchckQgvY/edit)

The PAL file contains more references to online mode material. Whether or not this means that more files are actually available to unlock and listen to is at this time unknown to me.


In particular I am interested in listening to these files:
csj_471	リーブとの会話２-２-１	Conversation with Reeve 2 - 2 - 1
csj_472	リーブとの会話２-２-２	Conversation with Reeve 2 - 2 - 2
csj_473	リーブとの会話２-２-３	Conversation with Reeve 2 - 2 - 3
csj_474	リーブとの会話２-２-４	Conversation with Reeve 2 - 2 - 4
csj_475	リーブとの会話２-２-５	Conversation with Reeve 2 - 2 - 5
csj_476	リーブとの会話２-２-６	Conversation with Reeve 2 - 2 - 6
csj_477	リーブとの会話２-３	Conversation with Reeve 2 - 3

These listed sounds seem to concern the conversations with Reeve on the Shera. A primary reason for me wanting to rip the audio from the game is so that I can listen to these sound clips and confirm all scene variations, as Cait Sith has one line that changes depending on if certain conditions have- or have not been met.


EDIT: Further research via Cheat Engine indicates that the line 
   csj_470 Conversation with Reeve 2 - 1 - 2
is what contains all the variations of Cait Sith's line on the Shera, but I am yet to find a way to play it in full.
## Post #3
- Username: Shademp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 30, 2015 12:27 am
- Post datetime: 2016-11-24T14:08:50+00:00
- Post Title: Question: How to play Dirge of Cerberus audio files?

The two questions from my first post were finally answered.

"#1: Ripping .pss files"
After a friend found the Nova Software Extractor 2.5 online, I confirmed that this old method of extracting videos and sound from PS2 titles does not work for Dirge of Cerberus. At the most I could extract some images, but nothing more. [See this thread post](http://thelifestream.net/forums/showpost.php?p=726548&postcount=575) for a more extensive report.


"#2: Playing .at2 and .at3 files"
I was directed to a [proper tutorial](http://forums.ppsspp.org/showthread.php?tid=7506&pid=60309#pid60309) on how to use foobar2000 to play .at3 files, but even with the proper component installed it could not read or convert the .at3 file from Dirge of Cerberus.


In conclusion, new tools must be developed in order to play the audio files from Dirge of Cerberus.

Unless you are only looking to play the few sound samples that exist in the four waveX00X.wd files, which I already explained that you can play using PSound.
