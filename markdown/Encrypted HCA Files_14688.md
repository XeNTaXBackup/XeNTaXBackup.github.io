## Post #1
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2016-07-27T16:32:38+00:00
- Post Title: Encrypted HCA Files?

[https://www.dropbox.com/sh/g71is8d6rx1q ... LiEVa?dl=0](https://www.dropbox.com/sh/g71is8d6rx1qnrl/AAAcZ2dw1h-BaJO7R27mLiEVa?dl=0)

Looking at the headers of the files here they seem to be HCA but the Hex of the Strings are off by 80 in hex?

i don't know how to make them playable VGMStream just makes Squeaky Sounds.

and fixing the strings manually makes it play nothing.
## Post #2
- Username: tenyuhuang
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 16, 2016 2:01 am
- Post datetime: 2016-11-17T22:54:51+00:00
- Post Title: Encrypted HCA Files?

Try your luck searching for the decryption key in the binary file.
AFAIK, Criware-powered games ALWAYS like to store encryption keys in plain text.

The key should be in either decimal or hex, but should you run into a decimal one, you'll need to feed its hex form into the HCA decoder.
