## Post #1
- Username: ISKYFALCONS
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Oct 13, 2020 6:40 pm
- Post datetime: 2021-06-10T18:25:32+00:00
- Post Title: Remember me - subtitle position

Hello
I added Arabic letters to the game files via hex, and an explanation on this [link](https://toloka.to/t69783) in the Ukrainian language will not be difficult for someone who knows how to use hex.
But I encountered a problem related to the translation's position, as it is at the very bottom. How can I change its position, or control it, or in which file is the format related to its location?
[https://1drv.ms/u/s!ApQFZmuVWUP9hJVdV0MvdAHpzVqQeQ](https://1drv.ms/u/s!ApQFZmuVWUP9hJVdV0MvdAHpzVqQeQ)
Game name: remember me 2012
development engine: Unreal Engine 3
## Post #2
- Username: ISKYFALCONS
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Oct 13, 2020 6:40 pm
- Post datetime: 2021-06-16T07:57:52+00:00
- Post Title: Remember me - subtitle position

I have a question
How to remove outline format for subtitle?
## Post #3
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2021-06-23T19:45:59+00:00
- Post Title: Remember me - subtitle position

Is it GFX or bitmap font ?
## Post #4
- Username: ISKYFALCONS
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Oct 13, 2020 6:40 pm
- Post datetime: 2021-06-23T23:14:29+00:00
- Post Title: Remember me - subtitle position

> Reply from dzika ↑Thu Jun 24, 2021 3:45 am at Thu Jun 24, 2021 3:45 am
>
> 
Is it GFX or bitmap font ?

bitmap font.
## Post #5
- Username: ISKYFALCONS
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Oct 13, 2020 6:40 pm
- Post datetime: 2021-06-23T23:15:53+00:00
- Post Title: Remember me - subtitle position

[](https://ibb.co/7pc4J8w)
[](https://ibb.co/M51wL7T)
## Post #6
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2021-06-24T11:30:09+00:00
- Post Title: Remember me - subtitle position

Upload your modified "DialogFont.Font"
## Post #7
- Username: ISKYFALCONS
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Oct 13, 2020 6:40 pm
- Post datetime: 2021-06-24T22:28:07+00:00
- Post Title: Remember me - subtitle position

> Reply from dzika ↑Thu Jun 24, 2021 7:30 pm at Thu Jun 24, 2021 7:30 pm
>
> 
Upload your modified "DialogFont.Font"

"DialogFontJPNDIRCOM.Font"
[https://1drv.ms/u/s!ApQFZmuVWUP9hL0XqX0 ... w?e=xG6fTD](https://1drv.ms/u/s!ApQFZmuVWUP9hL0XqX0gyhcDxrwVpw?e=xG6fTD)
## Post #8
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2021-06-25T18:50:41+00:00
- Post Title: Remember me - subtitle position

Use this file only for subtitles font (maybe helvetica or liberation).
[DialogFontJPNDIRCOM.rar](https://xentaxbackup.github.io/file/20360_DialogFontJPNDIRCOM.rar)
## Post #9
- Username: ISKYFALCONS
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Oct 13, 2020 6:40 pm
- Post datetime: 2021-06-26T16:46:37+00:00
- Post Title: Remember me - subtitle position

> Reply from dzika ↑Sat Jun 26, 2021 2:50 am at Sat Jun 26, 2021 2:50 am
>
> 
Use this file only for subtitles font (maybe helvetica or liberation).

It looks like you used this method:
make the metrics of the letters higher!
The important thing is that the translation no longer appears at the bottom of the screen.
My question is, is there a way to remove the Outline from the translation?
## Post #10
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2021-06-26T17:36:04+00:00
- Post Title: Remember me - subtitle position

> Reply from ISKYFALCONS ↑Sun Jun 27, 2021 12:46 am at Sun Jun 27, 2021 12:46 am
>
> 
It looks like you used this method:
make the metrics of the letters higher!
My method is to reduce the value of Y-offset.

> Reply from ISKYFALCONS ↑Sun Jun 27, 2021 12:46 am at Sun Jun 27, 2021 12:46 am
>
> 
My question is, is there a way to remove the Outline from the translation?
Sure, maybe something like changing the Outline's color to transparent/white.
But to find that value in which file will be very difficult.
And I can't help you with that.
