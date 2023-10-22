## Post #1
- Username: dark mysterio
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 13, 2023 11:09 am
- Post datetime: 2023-09-13T04:32:41+00:00
- Post Title: [ps2] def jam vendetta + fifa street 1/2

Hello,

Im new to this kind of thing (game modding) but looking at this thread i did the same with the same game (def jam fight for ny) and looked at the characters voice line 

[viewtopic.php?t=21650](https://forum.xentax.com/viewtopic.php?t=21650)

however trying to do the same with the first def jam (vendetta) for the voice or the two fifa street for the music didn't really work that well.

for the def jam game only the dj commentator voice work and not the characters/fighter voice work.

as for the fifa street game the tool on the thread (nba live music extractor) could actually load the song (PRIME.MUS for both game) but they where all cut into multiple part. 

using an ea big file extractor tool (couldn't remember the name) or dragon unpacker i could access the loading screen instrumental of the 2 (located in LOADLOOP.BIG) but only one song is some what "listenable" bran van 3000 astounded (bram van load.bnk)  as an raw files on audacity others do work to but are not listenable and i don't know where the instrumental of the 1 are located.

so if somebody could help it's would be greatly appreciated thank you please for your response.

audio file link: 
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1ezRy1JRnhoO1znTsgqeI77_TbFW0wm9E?usp=sharing) (def jam vendetta) 
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1c_cOYQPwFanW0uwiUcnJjrkiyqhsZALj?usp=sharing) (fifa street 1)
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1e4xo8B8XCuhx3PHDqV5siXsAx95kn8uv?usp=sharing) (fifa street 2)
## Post #2
- Username: dark mysterio
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 13, 2023 11:09 am
- Post datetime: 2023-09-26T18:53:45+00:00
- Post Title: [ps2] def jam vendetta + fifa street 1/2

edit status/update   



Capture d’écran (56).png (161.06 KiB) Viewed 169 times


[https://www.nfscars.net/need-for-speed- ... view/5125/](https://www.nfscars.net/need-for-speed-high-stakes/2/files/view/5125/)
I used this viv editor (find on google) that actually found and read the def jam vendetta characters voice line but like the fifa street 2 instrumental the raw file are unlistenable.
## Post #3
- Username: dark mysterio
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 13, 2023 11:09 am
- Post datetime: 2023-10-17T21:28:31+00:00
- Post Title: [ps2] def jam vendetta + fifa street 1/2

greeting 
 an other update news   

finally i'm getting somewhere !      and part or partially of the job as been done !

i found out  that ea big file extractor (like this one from example [https://github.com/Experiment5X/BIG-File-Extractor](https://github.com/Experiment5X/BIG-File-Extractor) mentioned in first post) extracted where all in .bnk (may not have look at this part/forgotten to look at it).  

looking at this thread: [viewtopic.php?p=194966&hilit=bnk#p194966](https://forum.xentax.com/viewtopic.php?p=194966&hilit=bnk#p194966)
i used used this foobar2000 plugins video games file audio format opener ([https://www.foobar2000.org/components/v ... _vgmstream](https://www.foobar2000.org/components/view/foo_input_vgmstream)) managed to open the extracted file and read it clearly. 
[](https://zupimages.net/viewer.php?id=23/42/2c6r.png)


as for the def jam vendetta file using pssound ([https://www.romhacking.net/utilities/679/](https://www.romhacking.net/utilities/679/)) i managed to extract the sound and convert (forcing sample rate to 44100 hz) to .wav.
[](https://zupimages.net/viewer.php?id=23/42/1r02.png)

now are are just missing others things i couldn't basically do or i'm still in step one fifa street 2 songs  split in multiple part (even using others music extractor) fifa street 1 song/loading instrumental location unknown also regarding def jam vendetta will i did found all the characters voice lines i couldn't unfortunately find there blazing move yelling (when there about to do there special move/finisher) i tried both speech.viv and main.viv but found nothing of that (except in main.viv they where many weird sound file maybe they are here).
## Post #4
- Username: dark mysterio
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 13, 2023 11:09 am
- Post datetime: 2023-10-21T08:47:27+00:00
- Post Title: [ps2] def jam vendetta + fifa street 1/2

This isn't really a update or kind of progress

But in my post where i mentioned the fifa street 2 song i also find than similarly the song (only since can't find where the loading instrumental are) of the 1 are located also in PRIME.MUS. However just like the song of the second fifa street no tool i have can open these .mus file or the one that "open them  and export" and that are the only option to listen to them (they are readable on audacity) is nhl 06 asf player and game audio player. However as already mentioned they appear in a thousand pieces i tried to look a way to export them all but the nhl tool doesn't have a multiple export options and game audio player as an error message once the only "way" would be to export one file at a time which is nearly impossible hee... no way im doing that   .

[](https://zupimages.net/viewer.php?id=23/42/mwsf.png)
[](https://zupimages.net/viewer.php?id=23/42/r326.png)
translation of the french part (in error message):The file, directory, or volume name syntax is incorrect.

nhl 06 asf player (link in the thread): [viewtopic.php?t=21650](https://forum.xentax.com/viewtopic.php?t=21650)
game audio player: [https://github.com/ValeryAnisimovsky/Ga ... ree/master](https://github.com/ValeryAnisimovsky/GameAudioPlayer/tree/master)
