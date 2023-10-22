## Post #1
- Username: Raphael Splinterson
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 31, 2016 12:36 pm
- Post datetime: 2022-02-28T01:32:28+00:00
- Post Title: Marvel Duel (android) - Unity files

Hello. Since August, the Marvel Duel files have been packed into an archive unknown to me. Maybe someone knows how to unpack these archives and extract files from there?   

Attached is a link with an example file.

[https://disk.yandex.ru/d/LrB7zQ_BEru60A](https://disk.yandex.ru/d/LrB7zQ_BEru60A)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-28T17:02:58+00:00
- Post Title: Marvel Duel (android) - Unity files

This is standard UnityFS archive with 20-bytes extra header on the beginning
[http://wiki.xentax.com/index.php/Unity_Unity3d_UnityFS](http://wiki.xentax.com/index.php/Unity_Unity3d_UnityFS)

You can open it with AssetStudio.

Here is what you need to do:
1. Rename file to pkg69.unity3d 
2. Open file in hex editor.
3. Delete first 20 bytes and save the file.
4. Open pkg69.unity3d file in AssetStudio.
## Post #3
- Username: Raphael Splinterson
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 31, 2016 12:36 pm
- Post datetime: 2022-02-28T19:39:34+00:00
- Post Title: Marvel Duel (android) - Unity files

Thanks, I did it, but most of the archives are empty. Maybe some more bytes need to be deleted?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-28T20:22:33+00:00
- Post Title: Marvel Duel (android) - Unity files

You can upload some samples of these "empty" archives for others to check.
The one you have provided in the first post had exactly 2 assets inside.
## Post #5
- Username: Raphael Splinterson
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 31, 2016 12:36 pm
- Post datetime: 2022-02-28T20:33:46+00:00
- Post Title: Marvel Duel (android) - Unity files

These files weigh about 10 megabytes. The file cannot weigh so much without assets. Maybe something else needs to be done to fully open the archives?

[https://disk.yandex.ru/d/MDt4LYKgu6jSpA](https://disk.yandex.ru/d/MDt4LYKgu6jSpA)
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-28T22:25:33+00:00
- Post Title: Marvel Duel (android) - Unity files

You're right. In fact this is not one UnityFS file as I thought. There are MULTIPLE UnityFS files joined together in one big file.

You can use this script with quickbms to unpack them
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/UNITY_TOOLS/Multiple_UnityFS_files_in_one_archive_script.bms)
## Post #7
- Username: Raphael Splinterson
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 31, 2016 12:36 pm
- Post datetime: 2022-02-28T22:50:20+00:00
- Post Title: Marvel Duel (android) - Unity files

Thank you very much, friend! Now I can continue to publish models from this game. Now I will list you in the description.
