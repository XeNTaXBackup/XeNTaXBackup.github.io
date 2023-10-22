## Post #1
- Username: JDog
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 26, 2017 3:14 pm
- Post datetime: 2021-10-16T04:06:51+00:00
- Post Title: Crysis 2 Remastered lz4 compressed pak files.

The remaster of Crysis 2 has a mixture of standard zip-based CryEngine pak files and ones compressed with lz4. The files that are compressed have a ".lz4compression" file in the root directory. They still have PK headers, so they're zip files. But the contents aren't extractable.


Attempting to extract these using various tools, and even the C2 SDK Pak manager has been unsuccessful. At best you get garbage. I don't think these are encrypted, though because there's plaintext scattered throughout each archive.


Here is a sample pak file. [https://www93.zippyshare.com/v/V4t0mnao/file.html](https://www93.zippyshare.com/v/V4t0mnao/file.html)

Any help would be greatly appreciated.
## Post #2
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2021-10-16T06:39:17+00:00
- Post Title: Crysis 2 Remastered lz4 compressed pak files.

Normal zip file but using lz4.
[zip.zip](https://xentaxbackup.github.io/file/21032_zip.zip)
## Post #3
- Username: JDog
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 26, 2017 3:14 pm
- Post datetime: 2021-10-16T07:22:18+00:00
- Post Title: Crysis 2 Remastered lz4 compressed pak files.

> Reply from dzika ↑Sat Oct 16, 2021 2:39 pm at Sat Oct 16, 2021 2:39 pm
>
> 
Normal zip file but using lz4.
Thank you so much. This seems to work flawlessly.
## Post #4
- Username: ExcessiveGBH
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 22, 2021 8:43 am
- Post datetime: 2021-10-22T01:41:19+00:00
- Post Title: Crysis 2 Remastered lz4 compressed pak files.

I have a problem, I can decrypt scripts_ch0.pak and edit XML files (dsg1.xml) with note pad ++
and reimport and cmd window doesn't say any errors.
When I paste the recompiled script_ch0.pak back to Crysis 2 Remastered.
And start game I have window errors pop ups.

Not sure what I’m doing wrong.
[Crysis 2 Remastered error window.png](https://xentaxbackup.github.io/file/21061_Crysis 2 Remastered error window.png)
