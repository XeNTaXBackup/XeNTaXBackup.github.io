## Post #1
- Username: Teapot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 01, 2020 2:15 am
- Post datetime: 2020-03-31T18:34:42+00:00
- Post Title: [HELP] Genshin Impact Unity Assets Decryption

Hey, Genshin Impact's closed beta began some time ago.
It runs on Unity, but everything except for audio, video and few other files are saved in .blk files.
They're unity assets files (StreamingAssets) but they're encrypted. Apparently they use a key group for XOR encryption. I have a sample for you guys since I can't figure it out. Also, the first closed beta used different files, being .asb instead of .blk and the encyrption was different.
I got this as a key for the asb but I'm still not able to get in it even with that. I will also attach the .asb

```
\x0f\xfb\xf5\xbb\xf6\x81\x48\x15\xfa\xd7\x77\x35\x82\x17\xd9\x9d
\x56\x28\x2e\xa9\x51\xba\x66\x2f\x22\xdd\xbb\x8a\x3b\xad\x90\x63
\xc6\x64\xfb\xd6\xcf\xa8\xbc\x48\x02\xc3\xbe\x36\xb2\x93\xbc\xd9
```

Skip "mark" at the beginning of asb
asb has 4 data blocks 612 and a 112 byte data block
4 bytes separated by each block need to be ignored

Any help would be appreciated. I can send more files from the game if that can help.

Link to sample files: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1ZNIVARG2x8fGc0dXaeo4ZBsOO9IPSkyt?usp=sharing)
## Post #2
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2020-09-16T03:11:09+00:00
- Post Title: [HELP] Genshin Impact Unity Assets Decryption

Can you upload the CBT 2 client? I will be grateful to you.
