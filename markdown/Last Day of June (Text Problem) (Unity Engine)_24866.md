## Post #1
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-12-20T13:23:05+00:00
- Post Title: Last Day of June (Text Problem) (Unity Engine)

Hello
I was able to extract the text of the game I wanted today, but as you can see in the picture, the text is completely strange and how should I solve this problem?
[1234.png](https://xentaxbackup.github.io/file/21427_1234.png)
## Post #2
- Username: aria1996
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-20T15:02:55+00:00
- Post Title: Last Day of June (Text Problem) (Unity Engine)

Text seems to be encrypted. Someone would need to reverse engineer encryption method and write a proper tool or script to solve this.
## Post #3
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-12-20T23:39:42+00:00
- Post Title: Last Day of June (Text Problem) (Unity Engine)

> Reply from ikskoks ↑Mon Dec 20, 2021 11:02 pm at Mon Dec 20, 2021 11:02 pm
>
> 
Text seems to be encrypted. Someone would need to reverse engineer encryption method and write a proper tool or script to solve this.

Thank You.
I had a question
Today I could hardly find the text of one of the games I wanted.
But there is a problem, the text files of this game are binary.
And when I want to translate them into my own language, when I translate and save them, it shows all my translations as a question mark.
What solution do you suggest for this problem?
My problem photo for example:
[666.png](https://xentaxbackup.github.io/file/21428_666.png)
## Post #4
- Username: aria1996
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-21T00:09:33+00:00
- Post Title: Last Day of June (Text Problem) (Unity Engine)

> What solution do you suggest for this problem?

First of all, you mustn't use text editor to edit binary files.
You should only use hex editor (like Hex Workshop).

There are two solutions basically:
1. Use program that was written to handle this type of file (for example UnityText [https://forum.zoneofgames.ru/topic/47582-unitytext/](https://forum.zoneofgames.ru/topic/47582-unitytext/))
2. Write your own program/script to parse binary files

First one is easier as it doesn't require any knowledge about programming or reverse engineering.
## Post #5
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-12-21T00:38:45+00:00
- Post Title: Last Day of June (Text Problem) (Unity Engine)

> Reply from ikskoks ↑Tue Dec 21, 2021 8:09 am at Tue Dec 21, 2021 8:09 am
>
> 
What solution do you suggest for this problem?

First of all, you mustn't use text editor to edit binary files.
You should only use hex editor (like Hex Workshop).

There are two solutions basically:
1. Use program that was written to handle this type of file (for example UnityText https://forum.zoneofgames.ru/topic/47582-unitytext/)
2. Write your own program/script to parse binary files

First one is easier as it doesn't require any knowledge about programming or reverse engineering.

Tanks a lot
## Post #6
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-12-21T10:35:11+00:00
- Post Title: Last Day of June (Text Problem) (Unity Engine)

> Reply from ikskoks ↑Tue Dec 21, 2021 8:09 am at Tue Dec 21, 2021 8:09 am
>
> 
What solution do you suggest for this problem?

First of all, you mustn't use text editor to edit binary files.
You should only use hex editor (like Hex Workshop).

There are two solutions basically:
1. Use program that was written to handle this type of file (for example UnityText https://forum.zoneofgames.ru/topic/47582-unitytext/)
2. Write your own program/script to parse binary files

First one is easier as it doesn't require any knowledge about programming or reverse engineering.

I used the first solution, but unfortunately this UnityText software does not support my language.
[999.png](https://xentaxbackup.github.io/file/21434_999.png)
## Post #7
- Username: aria1996
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-21T15:21:27+00:00
- Post Title: Last Day of June (Text Problem) (Unity Engine)

As for your original question about "Last day of June",
I was able to make some research.

(by the way, please keep your focus on one game per topic to avoid creating a mess on a forum)

So "Assembly-CSharp.dll" file in "\Last Day of June\LastDayOfJune_Data\Managed\" directory
can be decompiled with ILSpy [https://github.com/icsharpcode/ILSpy](https://github.com/icsharpcode/ILSpy)

After extracting the code, you can get this file "\uSky\uStars.cs" which reveals the true purpose of "StarsData" file
which is not a text file, but a binary file (*.bytes file) holding some position and color data.
Here is the file format:

```

// num_of_entries = 9110

num_of_entries *
{
   4 bytes (float) - position x
   4 bytes (float) - position z
   4 bytes (float) - position y
   4 bytes (float) - color r
   4 bytes (float) - color g
   4 bytes (float) - color b
}
```


So real text is kept somewhere else.
## Post #8
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-12-21T19:33:58+00:00
- Post Title: Last Day of June (Text Problem) (Unity Engine)

> Reply from ikskoks ↑Tue Dec 21, 2021 11:21 pm at Tue Dec 21, 2021 11:21 pm
>
> 
As for your original question about "Last day of June",
I was able to make some research.

(by the way, please keep your focus on one game per topic to avoid creating a mess on a forum)

So "Assembly-CSharp.dll" file in "\Last Day of June\LastDayOfJune_Data\Managed\" directory
can be decompiled with ILSpy https://github.com/icsharpcode/ILSpy

After extracting the code, you can get this file "\uSky\uStars.cs" which reveals the true purpose of "StarsData" file
which is not a text file, but a binary file (*.bytes file) holding some position and color data.
Here is the file format:
Code: Select all// StarsData.txt file format

// num_of_entries = 9110

num_of_entries *
{
   4 bytes (float) - position x
   4 bytes (float) - position z
   4 bytes (float) - position y
   4 bytes (float) - color r
   4 bytes (float) - color g
   4 bytes (float) - color b
}

So real text is kept somewhere else.

OK Thank you very much.
and Sorry for the mess in this forum
