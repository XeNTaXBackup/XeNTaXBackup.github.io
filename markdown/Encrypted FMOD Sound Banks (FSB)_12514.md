## Post #1
- Username: soneek
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Oct 20, 2011 5:43 am
- Post datetime: 2015-01-17T08:27:42+00:00
- Post Title: Encrypted FMOD Sound Banks (FSB)

I've come across encrypted FSB files with Mirror War: Reincarnation of Holiness (PC game). Has anyone dealt with encrypted FSB before, such as the encryption type, and also how to grab the en/decryption key from the actual game?

Edit: Since I've had no success with hcs's guessfsb tool, I'm assuming this may be FSB5.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-01-17T20:51:01+00:00
- Post Title: Encrypted FMOD Sound Banks (FSB)

I've come across a couple of instances (The Cave comes to mind) but there seems to be a standard password a lot of time.

Try "DFm3t4lFTW" with no quotes.

Batch script as well 

```
for %%i in (*.fsb) DO decfsb.exe %%i %%i.output.fsb "DFm3t4lFTW"
```
## Post #3
- Username: soneek
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Oct 20, 2011 5:43 am
- Post datetime: 2015-01-20T06:43:29+00:00
- Post Title: Encrypted FMOD Sound Banks (FSB)

Hmm, that didn't work out so well. I've been told FSB5 might use a new encryption method, so that might be one reason it didn't work.
