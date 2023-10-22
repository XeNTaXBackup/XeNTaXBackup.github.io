## Post #1
- Username: viper0419
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 26, 2018 10:29 pm
- Post datetime: 2019-01-12T16:03:34+00:00
- Post Title: Rainbow Six: Siege audio exporting with proper file names?

As the title suggests, I am wondering if its possible to extract Siege sounds with their proper names? rather than being sound_sfx_000001.wav (just an example of what a filename would be named).

Any help would be appreciated.
## Post #2
- Username: Ryo Hazaki
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 02, 2019 10:03 am
- Post datetime: 2019-02-02T05:16:07+00:00
- Post Title: Rainbow Six: Siege audio exporting with proper file names?

If you're extracting them with Wwise Unpacker, which is what I used to extract sounds from Ghost Recon Wildlands, it will not give the exact file name. It will, however, give the same file number. For example in Wildlands' sounds_sfx_music_.pck, I extract the files to mp3 format. They are numbered as sounds_sfx_music__1.mp3 and so on. Inside the .pck file, it corresponds to File0001.wwise_v. The same numbering rule applies to sounds_sfx_music__2.mp3 and inside the .pck file as File0002.wwise_v. Hope this helps. If it doesn't, please feel free to contact me.
