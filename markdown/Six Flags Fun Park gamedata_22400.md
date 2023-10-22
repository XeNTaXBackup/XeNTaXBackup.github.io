## Post #1
- Username: Allentastic
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 14, 2020 9:20 pm
- Post datetime: 2020-07-14T13:35:52+00:00
- Post Title: Six Flags Fun Park gamedata

In the files of Six Flags Fun Park for the Wii, I found a folder called gamedata.pak, and I was able to extract it, but the contents are encrypted. Is there a way to decrypt it?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-14T14:30:02+00:00
- Post Title: Six Flags Fun Park gamedata

How did you extract it? What programs did you use?

And please attach samples.
## Post #3
- Username: Allentastic
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 14, 2020 9:20 pm
- Post datetime: 2020-07-14T17:15:24+00:00
- Post Title: Six Flags Fun Park gamedata

I turned it into a .zip folder and opened it with 7-zip. How do I attach an example?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-14T17:25:02+00:00
- Post Title: Six Flags Fun Park gamedata

You need to upload it to external hosting server and attach link to the post.
## Post #5
- Username: Allentastic
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 14, 2020 9:20 pm
- Post datetime: 2020-07-14T17:28:11+00:00
- Post Title: Six Flags Fun Park gamedata

What should I use for an external host?
## Post #6
- Username: Allentastic
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 14, 2020 9:20 pm
- Post datetime: 2020-07-14T17:32:06+00:00
- Post Title: Six Flags Fun Park gamedata

[https://drive.google.com/file/d/1bmbwX3 ... sp=sharing](https://drive.google.com/file/d/1bmbwX3Y_MepOPpZomQAnSUJwv9XtbjPF/view?usp=sharing) Here it is on Google Drive if that works.
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-14T18:04:07+00:00
- Post Title: Six Flags Fun Park gamedata

GD is fine, but you have to share public link, because right now it tells that permission request is required.
## Post #8
- Username: Allentastic
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 14, 2020 9:20 pm
- Post datetime: 2020-07-14T18:16:35+00:00
- Post Title: Six Flags Fun Park gamedata

[https://drive.google.com/file/d/1bmbwX3 ... sp=sharing](https://drive.google.com/file/d/1bmbwX3Y_MepOPpZomQAnSUJwv9XtbjPF/view?usp=sharing) I changed it to public.
## Post #9
- Username: Allentastic
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-14T21:31:14+00:00
- Post Title: Six Flags Fun Park gamedata

You can extract data with offzip [http://aluigi.altervista.org/mytoolz.htm#offzip](http://aluigi.altervista.org/mytoolz.htm#offzip)

```
 offzip -a gamedata.pak c:\output
```

[https://imgur.com/a/mjq5msC](https://imgur.com/a/mjq5msC)
## Post #10
- Username: Allentastic
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 14, 2020 9:20 pm
- Post datetime: 2020-07-14T21:55:10+00:00
- Post Title: Six Flags Fun Park gamedata

It says offzip isn't recognized. How do I use it?
## Post #11
- Username: Allentastic
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 14, 2020 9:20 pm
- Post datetime: 2020-07-14T22:37:37+00:00
- Post Title: Six Flags Fun Park gamedata

It now says offzip can't run on my PC.
## Post #12
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-15T06:34:27+00:00
- Post Title: Six Flags Fun Park gamedata

Please attach screenshot with full error message.
## Post #13
- Username: Allentastic
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 14, 2020 9:20 pm
- Post datetime: 2020-07-15T13:47:06+00:00
- Post Title: Six Flags Fun Park gamedata

I was able to use it on my old laptop, and I successfully extracted everything from the folder. Now, I just need to deal with what's in the folder.
## Post #14
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-15T19:22:25+00:00
- Post Title: Six Flags Fun Park gamedata

Half of them are common file formats like LUA scripts and XML files. Other half must be reversed manually in hex editor or ripped, depends on what you are trying to do.
## Post #15
- Username: Allentastic
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 14, 2020 9:20 pm
- Post datetime: 2020-07-15T21:01:25+00:00
- Post Title: Six Flags Fun Park gamedata

I'm trying to get the models, sprites, and sound effects from the game.
