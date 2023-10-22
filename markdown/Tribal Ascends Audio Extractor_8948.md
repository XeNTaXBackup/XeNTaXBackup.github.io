## Post #1
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2012-05-18T20:09:38+00:00
- Post Title: Tribal Ascends Audio Extractor?

I have Been looking around the internet to find something that can extract the files from the Free-To-Play Tribal Ascends    by Hi-Rez Studios.: [https://account.hirezstudios.com/tribesascend/](https://account.hirezstudios.com/tribesascend/)

The only thing I found was a Reddit Post: [http://www.reddit.com/r/udk/comments/q2 ... enextract/](http://www.reddit.com/r/udk/comments/q2acv/total_noob_here_is_there_a_way_to_openextract/) that said how to extract the voice commands. I have not gotten it to work, unfortunately, But I have the files from another source

 I was wondering if anyone could get a way to extract the sound Effect files, like the weapons.
 It would be greatly Appreciated
## Post #2
- Username: Adamj
- Rank: n00b
- Number of posts: 11
- Joined date: Thu May 17, 2012 5:20 am
- Post datetime: 2012-05-19T02:31:33+00:00
- Post Title: Tribal Ascends Audio Extractor?

Just drag the .U file onto the decompressor, and then onto the unpacker.

It unpacked all the files in the archive for me that way ^^

[http://puu.sh/vuZh](http://puu.sh/vuZh) for the Umodel_32 that I used
(The GUI explorer just states that it has errors)
## Post #3
- Username: Rafael09ed
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 21, 2011 8:52 am
- Post datetime: 2012-05-19T21:26:20+00:00
- Post Title: Tribal Ascends Audio Extractor?

Ok, Thank You for telling me how to extract the .u file.   
The problem now is that there are no normal sound files. The ones I found in the TribesGameContent.u where .SoundNodeWave files

* Edit. upon more research, I found out that the umodel has a feature to extract these. 
Using Command Prompt: umodel -Export -Sounds  Then the File path (of the .u file), It will extract (unconfirmed amount) of the audio files into OGG format and it will extract some other types of files into other folders.
The only audio files there are Weapon Foley and Reloads
I will try extracting other files to see if I can get some of the other SFX
