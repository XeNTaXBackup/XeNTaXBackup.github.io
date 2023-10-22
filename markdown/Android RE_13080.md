## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-07-20T20:47:00+00:00
- Post Title: Android RE

So I got this game some people sent me the game data, APK and a bunch of SO files. The game data is encrypted and probably compressed. Unpacked the APKs to class files and looked at all the code and there was nothing about encryption or compression so I looked at the SO files. One was the unity SO, so nothing in there, but one SO was a CRI (you know, the cpk company). Found the file loading function, which calls a decryption function, and so on. Tried to find references to this function in the APK classes and the other SO files, but neither call any functions from the CRI SO file. So I figure I'm missing an SO file or something? Is there a way to track how data is loaded and used from the APK?
