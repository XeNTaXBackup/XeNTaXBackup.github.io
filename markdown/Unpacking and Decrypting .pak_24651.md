## Post #1
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2021-10-28T11:17:52+00:00
- Post Title: Unpacking and Decrypting .pak

Hey,

So i have been trying to unpack the TheIsle .pak file. The only problem is is that its encrypted. I can decrypt it cause i have the AES key, but i don't know how to extract them all. It's an Unreal Engine game and i have extracted a part of it. I extracted the uasset and uexp files but i can't seem to extract the remaining files. Like there are 2 folders filled with uasset and uexp files, the "Game" and "Engine" folders. However 2 folders, and "Plugins" are empty but should be filled with config files and more.
I tried UE Viewer which only gives me the uasset and uexp files.
I also tried QuickBMS which also gives me the same files. 



TheIsle and Plugins folders Screenshot_740.png (17.11 KiB) Viewed 256 times



If anyone knows how to extract all of the files in this .pak file, please tell me or show me cause i really want to know how to get them.

.pak file: [https://mega.nz/file/hbh1mKBZ#9D49Ocb3i ... aIltJ4ogZ4](https://mega.nz/file/hbh1mKBZ#9D49Ocb3iQ2Tw0-HH1ZWt7NMq_POgvGfsaIltJ4ogZ4)

AES Key:

And i found out that the Unreal Engine version should be 4.23, but i could be wrong.
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-10-28T15:06:28+00:00
- Post Title: Unpacking and Decrypting .pak

@StijnDark: umodel can recognize and extract only compatible assets from game packages, while quickbms script will extract everything from the package. I don't know what do you expect from extracted files, but if you've extracted them with quickbms, there is nothing else you can get from there.
## Post #3
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2021-10-28T17:28:00+00:00
- Post Title: Unpacking and Decrypting .pak

> Reply from Spiritovod ↑Thu Oct 28, 2021 11:06 pm at Thu Oct 28, 2021 11:06 pm
>
> 
@StijnDark: umodel can recognize and extract only compatible assets from game packages, while quickbms script will extract everything from the package. I don't know what do you expect from extracted files, but if you've extracted them with quickbms, there is nothing else you can get from there.

Does it matter which script you use? Like i can't make quickbms scripts at all, i'm just too stupid for that. And i can't find any scripts of the game or any kinds of that. Maybe i'm blind not sure   . I tried to look at how to make a script but it was too much for me already lol.
Thx for your reply by the way!
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-10-28T18:49:49+00:00
- Post Title: Unpacking and Decrypting .pak

@StijnDark: There are slightly different scripts for some UE4 games with changed package format, but they're all modifications of the same script - so if it worked for you without errors in the process, you've extracted everything.
## Post #5
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2021-10-29T15:57:42+00:00
- Post Title: Unpacking and Decrypting .pak

> Reply from Spiritovod ↑Fri Oct 29, 2021 2:49 am at Fri Oct 29, 2021 2:49 am
>
> 
@StijnDark: There are slightly different scripts for some UE4 games with changed package format, but they're all modifications of the same script - so if it worked for you without errors in the process, you've extracted everything.

Ahh alright i see, thanks for your help!
## Post #6
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2021-10-29T18:34:57+00:00
- Post Title: Unpacking and Decrypting .pak

And i see there is an reimport option thats within the quickbms folder that should repack my .pak file. When i use that it gives me this error:



What did i do wrong? I selected the script i used before, then i selected my zip file and then i chose where i want my .pak file to be. And then i got that error and i don't know why
## Post #7
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-10-29T23:00:04+00:00
- Post Title: Unpacking and Decrypting .pak

@StijnDark: UE4 quickbms scripts doesn't support reimport functionality due to their complexity. You need to use other tools for that - and also, you can't repack base package in almost all cases, so create mods instead. You can start with reading related linked posts at the bottom of my [base post](https://zenhax.com/viewtopic.php?f=9&t=1005&p=56251#p56251) at zenhax.
## Post #8
- Username: StijnDark
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Oct 28, 2021 7:00 pm
- Post datetime: 2021-10-30T09:46:55+00:00
- Post Title: Unpacking and Decrypting .pak

> Reply from Spiritovod ↑Sat Oct 30, 2021 7:00 am at Sat Oct 30, 2021 7:00 am
>
> 
@StijnDark: UE4 quickbms scripts doesn't support reimport functionality due to their complexity. You need to use other tools for that - and also, you can't repack base package in almost all cases, so create mods instead. You can start with reading related linked posts at the bottom of my base post at zenhax.

ahh i see thank you very much!
## Post #9
- Username: snagger
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 02, 2022 1:31 am
- Post datetime: 2022-05-01T17:33:55+00:00
- Post Title: Unpacking and Decrypting .pak

What is the AES key plz
