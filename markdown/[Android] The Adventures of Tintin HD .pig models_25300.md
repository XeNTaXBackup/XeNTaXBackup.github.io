## Post #1
- Username: farfocl3
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 29, 2022 12:12 pm
- Post datetime: 2022-04-29T04:46:19+00:00
- Post Title: [Android] The Adventures of Tintin HD .pig models

I'm trying to get the models from the somewhat obscure tintin game. The files sit in plain sight, arranged nicely into folders in the data file of the game (which can be grabbed for example from [here](https://androidblue.com/the-adventures-of-tintin-apk/)). 

After some digging I found that this is a pretty standard file format for gameloft games, and tried both the [PIG2FBX ](https://forum.xentax.com/viewtopic.php?f=16&t=11095) and all different flavors of the [A8Tool I found in its thread.](https://forum.xentax.com/viewtopic.php?f=16&t=17591).

In both instances I am getting nothing back. The window opens with blinking cursor, stays on for few seconds then closes. No fbx is created, no message thrown. I get the same effect regardless if I use drag&drop, command line (tool file.pig) or with PIG2FBX running it in folder with all the .pig files. While I expect that it might be issue on my end, I think it might be due to changes in the .pig format, as I have read about it in the topics linked above when it came to different games.

Any other tools, methods I can use to try to convert those files? 
Thanks in advance.
## Post #2
- Username: farfocl3
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 29, 2022 12:12 pm
- Post datetime: 2022-04-30T05:37:08+00:00
- Post Title: [Android] The Adventures of Tintin HD .pig models

Just a little update of what else I tried.

I tried following the same procedure found in [this thread](https://forum.xentax.com/viewtopic.php?f=16&t=22552&p=165859&hilit=.pig#p165859) that seems to be about the same game, but for ios instead of android. Couldn't get a preview to show any mesh with either AMR or AXE. I recreated it with the same .pig file from example shown in the topic, and still nothing.

So, I thought the files might be corrupted. Checked against a different source and they are the same, so it's either same bad dump all over the web, or some other esoteric issue that is way beyond me.

At this point I'm hoping someone smarter than me will be able to help. I'm attaching the exact .pig file used in the topic above if anyone wants to give it a go.
[gal_thompsons.zip](https://xentaxbackup.github.io/file/22171_gal_thompsons.zip)
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-01T14:53:14+00:00
- Post Title: [Android] The Adventures of Tintin HD .pig models

> Reply from farfocl3 ↑Sat Apr 30, 2022 1:37 pm at Sat Apr 30, 2022 1:37 pm
>
> 
if anyone wants to give it a go.
one submesh using MeshFinder(Android) or Hex2obj
[gal_thompsons.pig.png](https://xentaxbackup.github.io/file/22180_gal_thompsons.pig.png)
## Post #4
- Username: farfocl3
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 29, 2022 12:12 pm
- Post datetime: 2022-05-02T17:30:37+00:00
- Post Title: [Android] The Adventures of Tintin HD .pig models

That is awesome - thank you! Will dig into it tonight.

Is there some guide on how to effectively use those tools? I'm a newbie when it comes to ripping using hex values, and from quick glance it looks like you find the values for different fields by cross referencing it somehow with the hex editor/viewer.
