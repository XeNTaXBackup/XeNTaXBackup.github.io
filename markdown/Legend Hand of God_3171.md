## Post #1
- Username: Tiptoe
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 16, 2008 12:49 am
- Post datetime: 2008-09-30T09:19:47+00:00
- Post Title: Legend: Hand of God

Hello  

This is my first request, so I hope I do this right. I'd like to request support for a nice little action RPG game called Legend: Hand of God.

This is the official site: [http://www.legendhandofgod.com/](http://www.legendhandofgod.com/)

I'm very new to all this modding business, so I thought I'd start out small by trying to make a simple camera mod (if it's at all possible   ).

You see, the game's camera is at a fixed, almost top-down angle:



Which is fine for melee type characters, but not so great for ranged characters. So what I'd like to do, is slightly lower the camera's angle so it's possible to see further ahead.

Anyway, here are the two files which seem to define the camera: [http://rapidshare.de/files/40581517/Camera.rar.html](http://rapidshare.de/files/40581517/Camera.rar.html)

I hope I've gone about this the right way, if I've done something wrong or messed something up, please forgive me.

Thanks muchly.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-30T11:04:59+00:00
- Post Title: Legend: Hand of God

Seems to define camera moves (guess for ingame cinematics) rather than the normal ingame camera.
DAT is the directory.

```
struct Entry {
	string name; // why does that contain CR LF?
	byte zero; // double 0 terminated string?
	uint offset;
	uint uk; // checksum?
} entries[numEntries]<optimize=false>;
```
## Post #3
- Username: Tiptoe
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 16, 2008 12:49 am
- Post datetime: 2008-09-30T13:26:34+00:00
- Post Title: Legend: Hand of God

Thankyou for the quick response, I didn't think anybody would get around to looking at this so quickly .

So those files I uploaded are used to control the camera in the cutscenes, and not the camera ingame   . 

Ok, let's see if I can find them. I had another look through the game's Data directory and I found some script files (I've uploaded these to Rapidshare as well): [http://rapidshare.de/files/40582544/Script.rar.html](http://rapidshare.de/files/40582544/Script.rar.html)

Maybe the camera info I need is in those files *fingers crossed*. But even if they don't have the camera code, I'm still very curious to see what these script files contain (and what can be changed in them  ).

Just a quick question, how were you able to open those first files to view the data you posted? I tried to open them in MultiEx Commander but I didn't have any luck.

Thanks again for all your help.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-30T13:35:09+00:00
- Post Title: Legend: Hand of God

No clue what these scripts contain.
they got filenames like CITYGUARDHEIGHLANDQUEST.SCRIPT, CURSEDBOY.SCRIPT, FARMFRAU.SCRIPT, .. (hehe german developers )

You need a hex editor to figure out file formats. I personally use 010 Editor, that's why I always post 010 Editor binary templates (that code I posted).
## Post #5
- Username: Tiptoe
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 16, 2008 12:49 am
- Post datetime: 2008-10-01T06:44:15+00:00
- Post Title: Legend: Hand of God

Hmm I'm beginning to think my simple little mod isn't so simple after all  . I have a horrible suspicion that the camera might be hardcoded in the engine itself. Bummer!

Ah well, I suppose I can live with it. But the thing I really wanted to do is find some way to stop enemies respawning when you leave an area or reload the game, that's something I really, really hate.

I thought changing the camera would be an easy way to get my feet wet before I tried something harder  . But now I suspect that both the code for the camera and the respawning enemies is hardcoded.

There's no way to mod that is there?
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-10-01T12:27:19+00:00
- Post Title: Legend: Hand of God

Maybe there are other files that control it, but spawning is probably hardcoded or it is saved in the map files.
## Post #7
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-11-04T21:36:05+00:00
- Post Title: Legend: Hand of God

Here you can download an unpacker for the game DAT/PAK-files, if you want:
[viewtopic.php?p=27117#p27117](http://forum.xentax.com/viewtopic.php?p=27117#p27117)
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2008-11-10T16:03:36+00:00
- Post Title: Legend: Hand of God

If the game supports opengl rendering I can show you how to change the camera.
[http://glintercept.nutty.org/](http://glintercept.nutty.org/)
## Post #9
- Username: LemonBR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 19, 2023 3:22 am
- Post datetime: 2023-08-19T21:23:21+00:00
- Post Title: Legend: Hand of God

Hello, I know this post was made many years ago and I don't know if you or the users who were part of this discussion are still active here, but if you are still interested in the subject mentioned here, you could use some file extractor and edit the files named camera or any other file that is needed to edit camera settings. I'm currently thinking about translating this game into my language (Brazilian Portuguese) and after doing a lot of research on the internet I ended up coming to this post, it must have been nice to play this game years ago, I only found out about it a short time ago. If you know of any software that would be useful for extracting and editing text files etc, please comment here! 

I hope you are all well and thank you for your attention!!!
