## Post #1
- Username: denzon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 03, 2023 3:02 pm
- Post datetime: 2023-04-05T05:54:39+00:00
- Post Title: About Priconne Grandmasters audio file extraction

I have a question I would like you to help me with.
I am attempting to extract audio files (.awb.acb) from Priconne Grandmasters.
I was able to find some of the audio files from the apk file, but I needed to find the download resource file.

I used the "MuMu Nebula emulator" and rooted.
I then found a file in /data/data/ that looked like a download resource.
I put it into AssetStudio and could not find any audio files (menus, in-game BGM).awb .acb files.

What other work should I have done?
When you usually extract sound files from Unity games, where do you extract from and what application do you use?
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2023-04-09T08:18:15+00:00
- Post Title: About Priconne Grandmasters audio file extraction

Asset Studio/Unity extractors will only find the audio if it is held in the unity archives, many games use other audio engine kinds that use separate own archives where things get more complicated.

You should extract the .obb and investigate the plain files instead of just feeding it to asset studio.
