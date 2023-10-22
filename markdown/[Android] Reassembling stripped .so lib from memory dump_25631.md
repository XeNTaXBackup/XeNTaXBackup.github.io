## Post #1
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2022-07-21T12:28:20+00:00
- Post Title: [Android] Reassembling stripped .so lib from memory dump

Hello,

I figured this was a good place to ask if anyone has any experience with reassembling a stripped ELF lib from memory. The game I'm working on uses advanced protection and reassembles its libraries at run time. Looking at the original APK packed .so file, the lib is mostly zeroed out. Having dumped the device's memory after the game loads, I was able to find the assembled ELF file in memory with its stripped symbols restored but there are some discrepancies between the memory and the APK pack file.

At pos 2387800 you can see where the non-stripped data looks different in memory.



I was wondering if anyone else has tried this technique with any success reading the lib in a program like IDA after reassembling it from memory. I did my best guesswork and merged the files. All 3 (original, pulled, and merged) can be found below:

[https://drive.google.com/file/d/1tSS6yt ... sp=sharing](https://drive.google.com/file/d/1tSS6ytMb28jc6oMbSZs4ZPBYxT765QBD/view?usp=sharing)

Any advice is greatly appreciated!
