## Post #1
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-02-08T16:14:52+00:00
- Post Title: Observation text files

Hi how are you? what's up?

I wanted to ask you if I want to extract Observation game subtitle files.
And as you know, the game files are in .dat format and I want to extract the game text from these files and translate it into my own language and add it to the game again. Can you tell me how I can extract the game text from these files? ? With what software?
[Annotation 2021-02-08 194104.png](https://xentaxbackup.github.io/file/19496_Annotation 2021-02-08 194104.png)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-08T20:28:13+00:00
- Post Title: Observation text files

Can you upload some samples?
## Post #3
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-02-09T07:54:09+00:00
- Post Title: Observation text files

> Reply from ikskoks ↑Tue Feb 09, 2021 4:28 am at Tue Feb 09, 2021 4:28 am
>
> 
Can you upload some samples?

yeah sure.
[Observation.rar](https://xentaxbackup.github.io/file/19499_Observation.rar)
## Post #4
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2022-02-02T16:53:02+00:00
- Post Title: Observation text files

Hello everyone, I wanted to say that I tried to extract the text of this game to translate it into my own language. But my problem is that the text files of this game are in a format that I have never worked with such files.
The format of these files is: .dat
If anyone can help me, tell me what I should do to extract them.
[EXe.png](https://xentaxbackup.github.io/file/21710_EXe.png)
## Post #5
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-07-03T13:35:39+00:00
- Post Title: Observation text files

These files are XML files that have been encrypted via a simple XOR cipher. This cipher is symmetric so the same process can be used to re-encrypt them once edited.

```
{
    for (int i = 0; i < bytes.Length; i++)
    {
        bytes[i] = ~(bytes[i] ^ 0x41);
    }
}

```
