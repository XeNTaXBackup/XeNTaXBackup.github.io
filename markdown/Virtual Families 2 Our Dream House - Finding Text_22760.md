## Post #1
- Username: Vivvian
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 30, 2020 10:08 am
- Post datetime: 2020-09-30T02:28:07+00:00
- Post Title: Virtual Families 2: Our Dream House - Finding Text

Hi, I'm Vivvian. It seems that this game was never translated it to spanish. I'm struggling to find text files. In previos games (Virtual Villagers) text was in a .xml file, so it was really easy to edit. But now I'm really lost, and the few .dat files I scanned trough a hex editor didn't give any sigh. I really want to translate it, so thank you so much if someone can help me
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-09-30T06:33:19+00:00
- Post Title: Virtual Families 2: Our Dream House - Finding Text

Did you try total commander method?
[https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
## Post #3
- Username: Vivvian
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 30, 2020 10:08 am
- Post datetime: 2020-09-30T06:55:33+00:00
- Post Title: Virtual Families 2: Our Dream House - Finding Text

Thank you so much! It seems that the game text is in a .rdata file. Now, is there a way to convert it to .xml? Or edit it?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-09-30T09:44:59+00:00
- Post Title: Virtual Families 2: Our Dream House - Finding Text

You can upload somewhere .rdata sample file, post here a link and I will check it later.
## Post #5
- Username: Vivvian
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 30, 2020 10:08 am
- Post datetime: 2020-09-30T13:53:15+00:00
- Post Title: Virtual Families 2: Our Dream House - Finding Text

Thank you!   Here's the link: [https://drive.google.com/file/d/1LU7-kN ... sp=sharing](https://drive.google.com/file/d/1LU7-kNZiRs_vHKn0bVaNvqBTYaGHNpuV/view?usp=sharing)
## Post #6
- Username: Vivvian
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-09-30T17:23:11+00:00
- Post Title: Virtual Families 2: Our Dream House - Finding Text

It seems that this file is some kind of .rdata section dump from EXE file:

> The .rdata section contains data that is to be only readable, such as literal strings, constants and debug directory information.
[https://keystrokes2016.wordpress.com/20 ... -sections/](https://keystrokes2016.wordpress.com/2016/06/03/pe-file-structure-sections/)

You can use hex workshop to directly edit strings [http://www.bpsoft.com/downloads/](http://www.bpsoft.com/downloads/)

or use sysinternal's strings tool to dump text to file [https://docs.microsoft.com/en-us/sysint ... ds/strings](https://docs.microsoft.com/en-us/sysinternals/downloads/strings)

```
strings64.exe -o rdata.rdata > out.txt
```
## Post #7
- Username: Vivvian
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 30, 2020 10:08 am
- Post datetime: 2020-09-30T23:22:22+00:00
- Post Title: Virtual Families 2: Our Dream House - Finding Text

Thanks! It was really helpful! Now I can finally translate the text
