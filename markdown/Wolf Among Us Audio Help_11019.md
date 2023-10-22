## Post #1
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-12-04T06:32:17+00:00
- Post Title: Wolf Among Us Audio Help

I was hoping I can get some help extracting the dialogue from The Wolf Among Us. I believe it's possible with ttarchext:
[http://aluigi.altervista.org/papers.htm#ttarchext](http://aluigi.altervista.org/papers.htm#ttarchext)

Problem is I have no idea how to use it. I'm a noob so if it's not too much can someone give me a step-by-step? I would really appreciate it thank you.
## Post #2
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-12-06T00:51:42+00:00
- Post Title: Wolf Among Us Audio Help

Anyone?
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-12-06T03:16:38+00:00
- Post Title: Wolf Among Us Audio Help

Copy and paste this into notepad.

Then save it as Convert.bat

```
mkdir "Output"
for %%i in (*.ttarch2) DO ttarchext.exe -m 54 "%%i" "Output"
```


This will convert the audio from the archives
## Post #4
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-12-07T05:06:51+00:00
- Post Title: Wolf Among Us Audio Help

> Reply from brendan19
>
> Copy and paste this into notepad.

Then save it as Convert.bat
Code: Select all@echo off
mkdir "Output"
for %%i in (*.ttarch2) DO ttarchext.exe -m 54 "%%i" "Output"

This will convert the audio from the archives

Thanks I'll give it a show
## Post #5
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2013-12-07T08:32:43+00:00
- Post Title: Wolf Among Us Audio Help

> Reply from brendan19
>
> Copy and paste this into notepad.

Then save it as Convert.bat
Code: Select all@echo off
mkdir "Output"
for %%i in (*.ttarch2) DO ttarchext.exe -m 54 "%%i" "Output"

This will convert the audio from the archives
 Thanks works great!!

Much appreciated!
