## Post #1
- Username: toadbirb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 04, 2022 1:14 pm
- Post datetime: 2022-03-14T23:02:33+00:00
- Post Title: HP:MA/Netease Spine file issues

I'm not sure if this is the correct thread to post this question, if it isn't please tell me!

I've been looking through Harry Potter: Magic Awakened's files for a few weeks now and recently I've been going through the process of viewing their 2d animations in Spine, but I've come across an issue with some of their animation files and I'm not sure how to go about fixing it..

I'm able to load all skeleton files (.JSON) into Spine easily and with no issues, but some of the skeletons will have animations attached and they wont be viewable in spine itself (nor will they upload to unity without having issues) even though in the actual .JSON it refers to animations like:

```
"born": "born",
"idle02": "idle02",
"idle01": "idle01"
},
```


when normally it will say something like "idle01": (and then have animation data), I've found other .DAT files (that I've turned into .JSON, but I'm not sure if that's the correct file type they should be) that contain the missing animation assets but I'm not sure how to connect them together to make them viewable.

I'll include image examples of my issues below, if anyone is able to help me that would mean a lot because this issue is quite annoying. 

Here is a onedrive with files that contain my issue (they're too big to upload directly to xentax) if this is something you'd need physical assets to see what the issue is:
[https://1drv.ms/u/s!Arf2THtyM80yiV7ZhWq ... q?e=KBKJao](https://1drv.ms/u/s!Arf2THtyM80yiV7ZhWq8C5fNmUaq?e=KBKJao)

*Note: The 2 screenshots I provided are showcasing separate skeleton files, every card in the game has a small animation and a big animation, the big animation is the one I'm having issues with.
