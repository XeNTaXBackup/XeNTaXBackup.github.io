## Post #1
- Username: Redistrer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 12, 2019 10:16 pm
- Post datetime: 2020-04-14T18:51:07+00:00
- Post Title: How to convert GC .vid(Divx) movie file to .sfd?

I extracted GameCube games with dolphin and got MovieDivxPlayer.tgc MovieSfdPlayer.tgc.
So, I extracted these files again and found a .vid(MovieDivxPlayer.tgc) and .sfd(MovieSfdPlayer.tgc) files which seem to be movie files.
I was able to convert SFD files with vgmtoolbox, but I can't convert .vid files.
I think VID files are Divx movie.(MovieDivxPlayer)
Does anyone know how to convert these files?
## Post #2
- Username: cristyro
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 09, 2020 6:55 am
- Post datetime: 2020-05-13T13:16:33+00:00
- Post Title: How to convert GC .vid(Divx) movie file to .sfd?

I don't know if it works for your specific file, but whenever I had files that I was unable to convert to .sfd, I used ffmpeg to convert them to mpeg1 first and then I was able to use that file with sfdmux (it worked much better than Sega Dreamcast Movie Creator for me) to convert it to sfd.

Try using ffmpeg like this:
ffmpeg -i input.vid -b:v 3000K output.m1v 
Hopefully it'll do the job.
## Post #3
- Username: Redistrer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 12, 2019 10:16 pm
- Post datetime: 2020-06-01T14:54:06+00:00
- Post Title: How to convert GC .vid(Divx) movie file to .sfd?

Thank you for replying.
I tried your instruction, but ffmpeg said "input.vid: Invalid data found when processing input".
I'm no longer working on this issue as I can play it with Dolphin. 
If anyone knows something, please use this place.
Thank you.
