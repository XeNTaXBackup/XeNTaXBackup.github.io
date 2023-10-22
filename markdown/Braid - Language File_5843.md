## Post #1
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-18T15:56:48+00:00
- Post Title: Braid - Language File

Hello.
I want to translate the game "Braid"
I downloaded it from Steam today.
Text files are in, C:\Steam\SteamApps\common\braid\data\strings folder.

There are nine files;
english.mo
french.mo
german.mo
italian.mo
japanese.mo
korean.mo
portuguese.mo
spanish.mo
tchinese.mo

I can open the files easily with Game Translator.
The problem is in saving... When I save it and change it with the file, game doesn't start.
Can somebody take a look at attached file?
Thanks.
[english.rar](https://xentaxbackup.github.io/file/3815_english.rar)
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-01-19T10:59:28+00:00
- Post Title: Braid - Language File

Hi,
I tried it with POEdit (first convert .mo to .po, edit strings and then save to .mo) and game runs fine.
## Post #3
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-19T11:45:17+00:00
- Post Title: Braid - Language File

How to convert .mo to .po?
Just rename it?
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-01-19T12:23:50+00:00
- Post Title: Braid - Language File

No 
After installing POEdit go to the POEdit\bin directory.

Use command-line (or write a batch file):

```
msgunfmt english.mo > english.po
```
## Post #5
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-19T15:40:15+00:00
- Post Title: Braid - Language File

Thank you, works great.
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-01-19T16:39:30+00:00
- Post Title: Braid - Language File

Your welcome. Happy translating
## Post #7
- Username: harpseal
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:48 am
- Post datetime: 2011-01-22T12:29:19+00:00
- Post Title: Braid - Language File

Thank you for your answer.
## Post #8
- Username: sausage948
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 22, 2011 9:32 pm
- Post datetime: 2011-10-22T15:54:06+00:00
- Post Title: Braid - Language File

Hello, I am interested in translating Braid into Dutch. I have located the .mo files and was wondering how to convert them to .po files.

> Reply from merlinsvk
>
> No 
After installing POEdit go to the POEdit\bin directory.

Use command-line (or write a batch file):
Code: Select allmsgunfmt english.mo > english.po

I tried to follow merlinsvk’s directions here. The first time I directly copied that line into the “msgunfmt” file, and the english.mo file dissapeared from its folder… I couldn’t locate a .po file either. I still had a copy of the .mo file though so I just copied that back in. Afterwards I tried it again a couple of times and nothing happened. I also tried to put the complete file path names for the files, but that didn’t work either. I’m a bit of a newb with this kind of stuff, so could someone please help me with this? Thanks in advance.
