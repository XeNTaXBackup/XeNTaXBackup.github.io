## Post #1
- Username: IDKB
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 23, 2021 3:38 am
- Post datetime: 2021-07-03T22:44:11+00:00
- Post Title: Total War : Warhammer 2 OST

Hello there,

I would like to be able to edit/listen those files : [https://mega.nz/folder/KCA1WAAY#WN1Mlo8xXXDWUm2bfkqgIA](https://mega.nz/folder/KCA1WAAY#WN1Mlo8xXXDWUm2bfkqgIA)

They are in wem format and they are encrypted.

I already try to use a converter wem to ogg, but as i said they are encrypted and I get an error. I put a screenshot in the attachments.

Any help would be appreciated.
[ErrorConverter.PNG](https://xentaxbackup.github.io/file/20412_ErrorConverter.PNG)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-07-04T17:11:15+00:00
- Post Title: Total War : Warhammer 2 OST

Looks like simple Xor encryption, but not sure about the length of the decryption key.  It's easy enough to guess the first 16 bytes of the key from the header, which is "\x00\x00\x00\x00\x3e\xb2\xaf\xc0\x00\x00\x00\x00\x32\x96\xd9\xc1".  The full key might be in the executable file, but I can't really work it out just from the encrypted files ...
## Post #3
- Username: IDKB
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 23, 2021 3:38 am
- Post datetime: 2021-07-05T01:09:44+00:00
- Post Title: Total War : Warhammer 2 OST

Thank you for your answer.

I don't understand the way you get the first part, even the meaning of this. To my knowledge, one bit is equal to 0 or 1. I tried to open an wem file, and nothing looks like a key. Could you explain to me how do you find them ?

I also checked the exe file, and nothing again. 

Besides, if this is truly the first part of the key, there must be a way to generate the last part of it. I saw some code in python, but a barely understand how they work.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-07-05T11:33:39+00:00
- Post Title: Total War : Warhammer 2 OST

The only reason I know what that part of the key is is because I know what the .wem file header info should be, as it's a standard RIFF format.  Some of the info in the encrypted file is clearly visible like "RIFF" and "WAVE", so the key for those bytes is 0 as they don't change.  It seems like the key follows the pattern of 4 bytes of 0s, 4 encrypted bytes, etc.  The key could be 128 bytes, but because I don't know what most of the rest of the data is, it's not easy to work out.  The key isn't stored in the .wem file, so you won't "see" it,

The 4 bytes after "RIFF" is the length of the file minus 8 bytes, so for the file 650254, this value should be 0x91b3c - you can XOR those 4 bytes with 0x91b3c to get what the XOR key is for those.  Similarly, the 4 bytes after "WAVE" should be "fmt ", so you can worj that one out too.  Most of the rest of the data is unique to that file, so you can't easily guess it.
