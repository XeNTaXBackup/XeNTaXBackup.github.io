## Post #1
- Username: seonply
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jun 21, 2020 9:02 pm
- Post datetime: 2021-03-19T10:45:12+00:00
- Post Title: Batman: The Telltale Series (Android)

Hi xentax dudes. I want to translate Batman Telltale S. Android version. But I don't know how to repack it. I used ttarchext.exe for extract the files. And I tried -b -V 7 60 method for repack it. But it didn't work. (I think the files are compressed) Anyone help me please? Thank you for read.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-19T14:54:02+00:00
- Post Title: Batman: The Telltale Series (Android)

What do you mean by "it didn't work"? Did you get some error messages?
## Post #3
- Username: seonply
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jun 21, 2020 9:02 pm
- Post datetime: 2021-03-20T12:37:04+00:00
- Post Title: Batman: The Telltale Series (Android)

> Reply from ikskoks ↑Fri Mar 19, 2021 10:54 pm at Fri Mar 19, 2021 10:54 pm
>
> 
What do you mean by "it didn't work"? Did you get some error messages?

For example, I used -b -V 7 60 to rebuild episode 2. But the game stays on the black screen. And the episode doesn't start.

Then I noticed that the archive was compressed. I also tried TtgTools for rebuild. And agan just black screen.



Here is the ep 2 data file if you can help me.
[https://www.mediafire.com/file/y2aym3kw ... arch2/file](https://www.mediafire.com/file/y2aym3kwkigdtjz/BM_android_Batman102_data.ttarch2/file)
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-20T13:37:32+00:00
- Post Title: Batman: The Telltale Series (Android)

Which version of ttarchext and ttg tools are you using?

Also, you should choose proper version of the archive and select "Encrypt archive" if it is needed.
## Post #5
- Username: seonply
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jun 21, 2020 9:02 pm
- Post datetime: 2021-03-20T15:59:55+00:00
- Post Title: Batman: The Telltale Series (Android)

> Reply from ikskoks ↑Sat Mar 20, 2021 9:37 pm at Sat Mar 20, 2021 9:37 pm
>
> 
Which version of ttarchext and ttg tools are you using?

Also, you should choose proper version of the archive and select "Encrypt archive" if it is needed.

Ttg tools 1.0.6 and ttarchext is latest version. I've tried 'encrypt archive' and other methods. But again game stuck on black screen. 

I wonder, ttarchext can decompress 'compressed archives'. So is there a method to compress it back?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-20T21:35:01+00:00
- Post Title: Batman: The Telltale Series (Android)

> I've tried 'encrypt archive' and other methods. But again game stuck on black screen.
Then I would say that you have issue with your source files, not with archive itself.
Try to do only very small change first - like changing one letter only in some random word and try to check this change in game.


There is also a possibility that there is something wrong with the tool. 
When everything else fails, you can always raise an issue on github if you are 100% sure that it is some error.
## Post #7
- Username: seonply
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jun 21, 2020 9:02 pm
- Post datetime: 2021-03-20T22:43:10+00:00
- Post Title: Batman: The Telltale Series (Android)

> Reply from ikskoks ↑Sun Mar 21, 2021 5:35 am at Sun Mar 21, 2021 5:35 am
>
> 
I've tried 'encrypt archive' and other methods. But again game stuck on black screen. 
Then I would say that you have issue with your source files, not with archive itself.
Try to do only very small change first - like changing one letter only in some random word and try to check this change in game.


There is also a possibility that there is something wrong with the tool. 
When everything else fails, you can always raise an issue on github if you are 100% sure that it is some error.

Thank you for answering and helping. Actually, I tried rebuilding the archive without making any changes. And the game always stuck on the black screen. I think I need to send a message to the ttg tool maker. Again thank you for answer.  You are the best. ^^ If I find an answer I'll post it here.
