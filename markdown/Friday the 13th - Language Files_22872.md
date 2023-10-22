## Post #1
- Username: Wenter
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 21, 2020 9:18 am
- Post datetime: 2020-10-21T01:19:33+00:00
- Post Title: Friday the 13th - Language Files

First of all, I just want to translate Friday the 13th: The Game but i didn't know anything about tools or codes. Can anyone help me about what tool i need to use?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-21T07:13:42+00:00
- Post Title: Friday the 13th - Language Files

This game is on Unreal Engine 4 so you need to use quickbms script probably
[https://zenhax.com/viewtopic.php?f=9&t= ... 251#p56251](https://zenhax.com/viewtopic.php?f=9&t=1005&p=56251#p56251)
to unpack content and then some locres tools to modify language files
[https://zenhax.com/viewtopic.php?t=1022](https://zenhax.com/viewtopic.php?t=1022)
## Post #3
- Username: Wenter
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 21, 2020 9:18 am
- Post datetime: 2020-10-21T21:22:05+00:00
- Post Title: Friday the 13th - Language Files

When i try to unpack the .pak file, it's asking me for a variable KEY. What should I do?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-21T21:28:02+00:00
- Post Title: Friday the 13th - Language Files

In this situation you should type a valid key for the game to unpack content.
There are sites on the internet where you can find collections of such keys.

I have grabbed one for you:

```
Friday the 13th: The Game   0x3545393442413134363631443542433534333633323446424642444142363343
```
## Post #5
- Username: Wenter
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 21, 2020 9:18 am
- Post datetime: 2020-10-21T22:02:45+00:00
- Post Title: Friday the 13th - Language Files

Thanks to you, I'm in localization file. But there is one problem too, in localization file there is a Game.locmeta file. I was expecting .locres file, what should I do again?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-21T22:11:15+00:00
- Post Title: Friday the 13th - Language Files

I don't know, upload some samples to analyze and we'll see 

Edit: I have searched the web and found this

> LocMeta (Localization MetaData Resource) and LocRes (Localization Resource)
Are you sure you looking for text properly?
Maybe try total commander method first [https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
## Post #7
- Username: Wenter
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 21, 2020 9:18 am
- Post datetime: 2020-10-21T22:15:05+00:00
- Post Title: Friday the 13th - Language Files

[https://resmim.net/i/smJR](https://resmim.net/i/smJR)

as you can see, there is just a .locmeta files.
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-22T07:20:52+00:00
- Post Title: Friday the 13th - Language Files

No, it's definitely wrong file. It has 1KB of total size. Language files are often much larger.
Use my total commander method to search for text or just look for files in other folders.
