## Post #1
- Username: ReclusiveEagle
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 25, 2021 4:15 pm
- Post datetime: 2021-09-30T13:17:27+00:00
- Post Title: Help with Persona 5 Royal USM key?

So I've extracted both Royal on PS4 and normal Persona 5 for PS3. PS3 I have no issues decoding the USM video files.
Persona 5 Royal however I can't extract. Apparently they encrypted the files.

Now that being said, apparently USM HCA keys are extremely easy to figure out using hex editors.
Unfortunately, I know nothing about Hex editing and wtf 0x20 even is. Can someone help figuring it out? 

According to this post [https://shrinefox.com/forum/viewtopic.p ... =870#p870/](https://shrinefox.com/forum/viewtopic.php?f=29&t=254&p=870#p870/), the key is 00000000001C87822 
(yes 17 characters. idk why) 

Unfortunately (again) this just leads to a horrific mess of noises on "decryption". Obviously its the wrong key. 

Here is a link to my Google Drive [https://drive.google.com/file/d/1sWlHkf ... sp=sharing](https://drive.google.com/file/d/1sWlHkfnhtDuNPzD5tidDcpVwMIneu79E/view?usp=sharing)
You will find Mov000.usm (opening cinematic). I know this USM has both video and audio so that will help with @SFA searches
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-03T14:42:54+00:00
- Post Title: Help with Persona 5 Royal USM key?

This key you mentioned is for the different version of the game
Try this instead:

```
crid_mod.exe -b 00000000 -a 035B6784 -v -x -i mov000.usm
```


You can read more about this on the wiki
[http://wiki.xentax.com/index.php/USM_Video](http://wiki.xentax.com/index.php/USM_Video)
