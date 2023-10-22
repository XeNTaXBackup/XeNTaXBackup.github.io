## Post #1
- Username: ZezoConquer2023
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 13, 2023 5:08 am
- Post datetime: 2023-06-12T21:18:21+00:00
- Post Title: I am alive - help with translation

this game is very strange its unreal engine but is stuctured compleatly different compared to a normal UE3 game
Please I Need to How extract file umd Becouse i want to Translate Game
any Help?
## Post #2
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-12T23:32:03+00:00
- Post Title: I am alive - help with translation

Well, this game was made on Unreal Engine 2.5 (also referred as LEAD Engine).
It seems that UMD archive has EPCK signature and it's encrypted with some kind of XOR Cipher.

This format is shared with some other games e.g. Splinter Cell: Conviction
There are some topics already about this format:
[https://www.gildor.org/smf/index.php/to ... l#msg15196](https://www.gildor.org/smf/index.php/topic,458.msg15196.html#msg15196)
[viewtopic.php?t=11448](https://forum.xentax.com/viewtopic.php?t=11448)
[viewtopic.php?t=8497&start=45](https://forum.xentax.com/viewtopic.php?t=8497&start=45)
[https://web.archive.org/web/20230429105 ... t=249#p963](https://web.archive.org/web/20230429105349/https://zenhax.com/viewtopic.php?t=249#p963)

But if that's not enough, then someone needs to fully reverse engineer file format first.
## Post #3
- Username: ZezoConquer2023
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 13, 2023 5:08 am
- Post datetime: 2023-06-13T07:22:28+00:00
- Post Title: I am alive - help with translation

all links dead 
i Need To tools for this game if you can help pe for this
## Post #4
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2023-06-14T13:38:27+00:00
- Post Title: I am alive - help with translation

* I Am Alive original (English) localization files
* I Am Alive - Fonts Injector
## Post #5
- Username: ZezoConquer2023
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 13, 2023 5:08 am
- Post datetime: 2023-06-19T02:28:43+00:00
- Post Title: I am alive - help with translation

> Reply from terminator ↑Wed Jun 14, 2023 9:38 pm at Wed Jun 14, 2023 9:38 pm
>
> 
* I Am Alive original (English) localization files
* I Am Alive - Fonts Injector

What is the function of the 3 files, one_font.dds _ two_font.dds _ three_font.dds
How do I add the Arabic language and Arabic letters?
## Post #6
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2023-06-19T08:47:54+00:00
- Post Title: I am alive - help with translation

You have to edit those DDS files with GIMP or Photoshop - replace the fonts with your native language's alphabet, then inject or just place them back to the game (with proper folder structure), than test it ingame!
## Post #7
- Username: ZezoConquer2023
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 13, 2023 5:08 am
- Post datetime: 2023-06-19T23:45:07+00:00
- Post Title: I am alive - help with translation

Unfortunately, I can't do that because I'm a beginner and I don't know how to do it, but thank you really for responding and caring.
I will look for anyone who can help me modify fonts and add Arabic letters, Thx man
## Post #8
- Username: Ak1285
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 24, 2023 9:10 pm
- Post datetime: 2023-07-07T20:58:54+00:00
- Post Title: I am alive - help with translation

> Reply from terminator ↑Mon Jun 19, 2023 4:47 pm at Mon Jun 19, 2023 4:47 pm
>
> 
You have to edit those DDS files with GIMP or Photoshop - replace the fonts with your native language's alphabet, then inject or just place them back to the game (with proper folder structure), than test it ingame!
Where can I find the file containing the coordinates of the characters
## Post #9
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2023-07-08T15:49:35+00:00
- Post Title: I am alive - help with translation

When you open a font based character set (in any picture format) mostly you have nothing about "coordinates" - you have to work with what you have: standard character sizes in Photoshop (or any other picture manipulating software), what you help with it's grid or liners or else.
Sorry there is not any 'universal' solution for this.
