## Post #1
- Username: TKFRvision
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 28, 2021 6:07 am
- Post datetime: 2021-10-27T22:26:20+00:00
- Post Title: Repack Cars 2: The Video Game Zip

Hey,
I want to repack the cars 2 zips but the game rejects them behaving like they don't exist.
They are not standard.
This is how the chunks are listed:
1. EndLocator (points to second DirEntry)
2. DirEntry
3. FileRecords
4. DirEntry (Copy of first one)
5. EndLocator (Copy of first one)

In addition every DirEntry has a md5 of the file in its ExtraField.
This is a [script](https://github.com/TKFRvisionOfficial/CARS2/blob/main/why.py) I wrote and the Zips are to my eye the exact same except for the compression size and order of files. But it still dosen't work.
Thanks for your help.
## Post #2
- Username: TKFRvision
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 28, 2021 6:07 am
- Post datetime: 2021-10-28T15:25:56+00:00
- Post Title: Repack Cars 2: The Video Game Zip

I'VE DONE IT
I successfully modded cars 2. You can pack your zips using above mentioned script. It is working now.
