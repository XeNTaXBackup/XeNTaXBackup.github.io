## Post #1
- Username: Nanoka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 25, 2015 8:51 am
- Post datetime: 2020-01-13T01:25:06+00:00
- Post Title: Girls und Panzer - Encrypted unity3d files

Hello, I dumped files from a mobile game for extraction but apparently most are encrypted.
Files are unity3d. First of all I checked if it was consistent across all encrypted files but the only consistency I found was the first 3 bytes with text "EAB" followed by other encrypted bytes instead of the expected "UnityFS", though the version apparently isn't encrypted.
Searching the web all I found is that some guy on 2ch wrote a program for decrypting this but the link is dead and there is no information about the process or anything except what I already know.
I have no knowledge on encryption, so I come here looking for any help.

Here is a zip with a bunch of files, some encrypted and others not, from the same game:
[https://mega.nz/#!U8pECSyB!-jy03DT1fLGB ... A0NL_Z9Yk0](https://mega.nz/#!U8pECSyB!-jy03DT1fLGBPbjWrFFqTwfckn7iuLYKjA0NL_Z9Yk0)

Thanks in advance!

Edit:
After getting part of a decrypted file by dumping the game memory and comparing with the encrypted counterpart I have some findings.

First of all, the encryption stops at some point and this address is right here:

It is stored in little endian at 0x04 and is 2 bytes long.

Next, how (I think) this encryption works:

The first byte at 0x60 is XORed with the value from 0x06.

Then every next byte is XORed with the previous XORed byte and stops before the stored address at 0x04.

Dumped decrypted file:

Encrypted file:

XOR 0x61 with 0x60:

Then XOR 0x60 with 0x06:


Now I need help with writting a script for this or something.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2020-01-14T02:13:03+00:00
- Post Title: Girls und Panzer - Encrypted unity3d files

What game is it?
## Post #3
- Username: Nanoka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 25, 2015 8:51 am
- Post datetime: 2020-01-14T05:18:18+00:00
- Post Title: Girls und Panzer - Encrypted unity3d files

This is from girls und panzer mobile game.

I have actually wrote a windows batch file using some other utilities I found on the web and got myself a way for doing this by just running it.
While it worked for all files, it is a mess and needs so many external executables with their dependencies its inconvenient to hand it to somebody else.

If you want to take a look, I attach a zip with bat and some of the executables.


 gup_eab.zip
Hopefully this is well commented (103.11 KiB) Downloaded 53 times
## Post #4
- Username: tsumugi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 15, 2019 1:50 am
- Post datetime: 2021-04-19T16:43:56+00:00
- Post Title: Girls und Panzer - Encrypted unity3d files

> Reply from Nanoka ↑Tue Jan 14, 2020 1:18 pm at Tue Jan 14, 2020 1:18 pm
>
> 
This is from girls und panzer mobile game.

I have actually wrote a windows batch file using some other utilities I found on the web and got myself a way for doing this by just running it.
While it worked for all files, it is a mess and needs so many external executables with their dependencies its inconvenient to hand it to somebody else.

If you want to take a look, I attach a zip with bat and some of the executables.

gup_eab.zip

I can't really get this to work, I seem to get files like this for the few files that do open and everything else just makes Asset Studio crash and they are all between 3-18 KB in size. 



chr_akebi_bunkasai_1_4_ficon_l.png (39.54 KiB) Viewed 154 times



Not really sure what is wrong. 

Powershell just gives this error:
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-04-19T19:59:17+00:00
- Post Title: Girls und Panzer - Encrypted unity3d files

@tsumugi: I suppose you're trying to convert all files, while only some of them are encrypted. I've created quickbms script based on Nanoka's samples and info from the first post. You can run it against the whole folder, it will decrypt only encrypted files. Tested on current game version as well.
[girls_panzer_decrypt.zip](https://xentaxbackup.github.io/file/19928_girls_panzer_decrypt.zip)
