## Post #1
- Username: Kerem123
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Dec 02, 2017 1:56 am
- Post datetime: 2022-03-25T01:32:46+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

[https://file.io/J4q4Y0hVF3XW](https://file.io/J4q4Y0hVF3XW)
Hello. I'm translating The Walking Dead: Survival Instinct to my language and I need to know how can I extract and import this .subb file. Looking for help, thank you. You can download the file via link.
## Post #2
- Username: Kerem123
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Dec 02, 2017 1:56 am
- Post datetime: 2022-03-27T09:17:15+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

Please help  
[tm_01.rar](https://xentaxbackup.github.io/file/22027_tm_01.rar)
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-27T19:27:52+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

I had to clean this topic, because there were a lot of SPAM messages here...

As for subb file, I've checked it, but I didn't see any useful information in the header for extracting data.
Did you try to edit in hex editor?
## Post #4
- Username: Kerem123
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Dec 02, 2017 1:56 am
- Post datetime: 2022-03-28T04:02:39+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

> Reply from ikskoks ↑Mon Mar 28, 2022 3:27 am at Mon Mar 28, 2022 3:27 am
>
> 
I had to clean this topic, because there were a lot of SPAM messages here...

As for subb file, I've checked it, but I didn't see any useful information in the header for extracting data.
Did you try to edit in hex editor?

I tried and it looked like this.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-28T08:00:48+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

I can't see your image. Can you upload it to IMGUR or here as an attachment?
## Post #6
- Username: Kerem123
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Dec 02, 2017 1:56 am
- Post datetime: 2022-03-28T11:45:02+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

> Reply from ikskoks ↑Mon Mar 28, 2022 4:00 pm at Mon Mar 28, 2022 4:00 pm
>
> 
I can't see your image. Can you upload it to IMGUR or here as an attachment?

Here.
[Screenshot_3.png](https://xentaxbackup.github.io/file/22035_Screenshot_3.png)
## Post #7
- Username: Kerem123
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Dec 02, 2017 1:56 am
- Post datetime: 2022-03-31T07:50:50+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

> Reply from ikskoks ↑Mon Mar 28, 2022 4:00 pm at Mon Mar 28, 2022 4:00 pm
>
> 
I can't see your image. Can you upload it to IMGUR or here as an attachment?

Anyone helps?
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-31T17:30:00+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

I have checked your sample, but I haven't seen any values that may represents string lengths or offsets.
More research needs to be done on this kind of file.
## Post #9
- Username: Kerem123
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Dec 02, 2017 1:56 am
- Post datetime: 2022-03-31T18:36:49+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

> Reply from ikskoks ↑Fri Apr 01, 2022 1:30 am at Fri Apr 01, 2022 1:30 am
>
> 
I have checked your sample, but I haven't seen any values that may represents string lengths or offsets.
More research needs to be done on this kind of file.

What should I do?
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-31T20:43:24+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

You can try to debug game's code and see how the SUBB file is parsed.
Here you can find some explanation how to do that [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #11
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-07-03T20:04:03+00:00
- Post Title: The Walking Dead: Survival Instinct Subb File

Below is the full format but for the purpose of localisation you just need to make sure your replacement text is both null (0 byte) terminated and 4 byte aligned.

```
{
  uint Version;       // must be 3
  byte Unknown04[16]; // checksum? skipped by game
  uint Unknown14;     // always 0
  uint EntryCount;
  Entry Entries[EntryCount];
}

struct Entry
{
  char Text[20][];    // strings are null terminated and 4 byte aligned
                      // 20 slots but not all locales are supported
  float startTime;    // in seconds
  float endTime;
}

enum Locale
{
  English_US,
  French_France,
  Italian,
  Spanish_Spain,
  German,
  Japanese,
  Dutch,
  Korean,
  Polish,
  Russian,
  Spanish_Mexico,
  Chinese_PRC,
  Swedish,
  Norwegian,
  Finnish,
  Danish,
  Spanish_US,
  Czech,
  Portugese,
  Hungarian,
}

```
