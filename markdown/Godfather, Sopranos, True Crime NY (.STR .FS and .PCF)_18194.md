## Post #1
- Username: il capo di tutti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jun 07, 2018 12:38 pm
- Post datetime: 2018-06-07T04:45:28+00:00
- Post Title: Godfather, Sopranos, True Crime NY (.STR .FS and .PCF)

Hey, I've been trying to rip models and textures from those two games and I need some help. I need to find out the way, I have no knowledge at all about scripting or anything, I usually rip models with NinjaRipper and import them into 3d max.
I ripped some models succesfuly from Godfather, and that's OK, but I was wondering if there's a way to export the models directly from the original files.
Ped models are .STR format. How can I get into that?

And now talking about Sopranos, I tryed ripping it through PCSX2 using some programs, but it exports the whole scene with tons of bugs. I'd like to get the models with T-Pose 
Is there a way to get into the data files, that are .FS format? 

Thanks, and rembember i'm not a pro.
## Post #2
- Username: il capo di tutti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jun 07, 2018 12:38 pm
- Post datetime: 2018-06-14T06:25:23+00:00
- Post Title: Godfather, Sopranos, True Crime NY (.STR .FS and .PCF)

I tryed using the tools that I saw for Dead Space about .STR files (Gibbed Visceral) but still doesn't work. I even used some BMS scripts.

Edit: Beside these two games now I'm trying to rip True Crime New York and the models are .PCF
Again I cant figure it out. Anyone knows how to make that format able to edit? Idk why but NinjaRipper doesn't work on that game
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-14T07:59:55+00:00
- Post Title: Godfather, Sopranos, True Crime NY (.STR .FS and .PCF)

> Reply from il capo di tutti
>
> rembember i'm not a pro.
It has nothing to do with you not uploading any sample files, which is ususlly what makes people ignore your posts.
## Post #4
- Username: il capo di tutti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jun 07, 2018 12:38 pm
- Post datetime: 2018-06-14T20:06:05+00:00
- Post Title: Godfather, Sopranos, True Crime NY (.STR .FS and .PCF)

> Reply from Bigchillghost
>
> il capo di tutti wrote:rembember i'm not a pro.
It has nothing to do with you not uploading any sample files, which is ususlly what makes people ignore your posts.

I'm sorry I didn't know you guys work that way. Really, the last thing I want is to offend and look like i'm forcing you guys to help me out. Again, sorry if I was misunderstood.
Before creating this post I made a research and I tryed a lot of things but it didn't work out.

Here you go guys. I attached some files for example. (.FS file from sopranos is super big so I didn't put it on the .rar, but i attached a .CED (I guess this is the model) and .WIM (texture) from MadeMan for y'all if want to help me to open them.

[https://www.upload.ee/files/8561209/fil ... x.RAR.html](https://www.upload.ee/files/8561209/filesXentax.RAR.html)
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-14T23:00:14+00:00
- Post Title: Godfather, Sopranos, True Crime NY (.STR .FS and .PCF)

I am getting some stuff from "thug_model.str", but not quite there.



Not sure why it comes out like that. It is fine until like 260 indices, after that some faces get weird. Also there are some integer values around 0x4E61 that might be related to the indices. Maybe an alternate triangle list?

"JOEYA_BODYSKIN.CED" is easier. No problems with that.



This is the best I can do. I hope these examples will help you understand how the model data should look like inside the file. Good luck!

Edit:

Since you said that you are mostly using NinjaRipper, I though you might not be familiar with the program I used above (hex2obj). So here is the guide of the tool : [viewtopic.php?f=29&t=10894](http://forum.xentax.com/viewtopic.php?f=29&t=10894)
## Post #6
- Username: il capo di tutti
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jun 07, 2018 12:38 pm
- Post datetime: 2018-06-15T02:40:53+00:00
- Post Title: Godfather, Sopranos, True Crime NY (.STR .FS and .PCF)

> Reply from akderebur
>
> I am getting some stuff from "thug_model.str", but not quite there.



Not sure why it comes out like that. It is fine until like 260 indices, after that some faces get weird. Also there are some integer values around 0x4E61 that might be related to the indices. Maybe an alternate triangle list?

"JOEYA_BODYSKIN.CED" is easier. No problems with that.



This is the best I can do. I hope these examples will help you understand how the model data should look like inside the file. Good luck!

Edit:

Since you said that you are mostly using NinjaRipper, I though you might not be familiar with the program I used above (hex2obj). So here is the guide of the tool : viewtopic.php?f=29&t=10894

Thanks for your reply, buddy! I'll check that out
