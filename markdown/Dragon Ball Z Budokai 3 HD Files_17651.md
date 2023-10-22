## Post #1
- Username: LeanMB56
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 03, 2018 7:03 am
- Post datetime: 2018-02-02T23:07:31+00:00
- Post Title: Dragon Ball Z Budokai 3 HD Files

The PS3 version of Budokai 3 (The Budokai HD Collection release) has the files compressed but I don't know what format of compression is. 
Can you help me?
The compress files are from Budokai 3 HD (PS3) and the uncompress files are from Budokai 3 (PS2)

[http://www.mediafire.com/file/893cu4g1jc3ecbg/Files.rar](http://www.mediafire.com/file/893cu4g1jc3ecbg/Files.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-03T00:34:17+00:00
- Post Title: Dragon Ball Z Budokai 3 HD Files

this bms script will decompress those bin samples  

```

comtype gzip
endian big
get ZSIZE long
get NAME basename
string NAME + _decomp.bin
clog NAME 0x4 ZSIZE ZSIZE

```
## Post #3
- Username: LeanMB56
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 03, 2018 7:03 am
- Post datetime: 2018-02-09T18:33:34+00:00
- Post Title: Dragon Ball Z Budokai 3 HD Files

> Reply from AceWell
>
> this bms script will decompress those bin samples  
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

comtype gzip
endian big
get ZSIZE long
get NAME basename
string NAME + _decomp.bin
clog NAME 0x4 ZSIZE ZSIZE

Thanks, man, it works!
## Post #4
- Username: GamingZVault
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 24, 2021 10:00 am
- Post datetime: 2021-04-24T02:03:04+00:00
- Post Title: Dragon Ball Z Budokai 3 HD Files

Hey can you guys explain to me the process of unpacking a bin file? I'm new to this and don't know how to do it amd the possible software I need to do so. Thanks!

(I know I'm replying to this thread over 3 years late so really hope someone can help)
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-24T13:13:10+00:00
- Post Title: Dragon Ball Z Budokai 3 HD Files

The only software you need is QuickBMS.
You can download it here [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Instruction how to use it is explained with details here
[http://aluigi.altervista.org/papers/quickbms.txt](http://aluigi.altervista.org/papers/quickbms.txt)
## Post #6
- Username: GamingZVault
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 24, 2021 10:00 am
- Post datetime: 2021-04-29T14:22:20+00:00
- Post Title: Dragon Ball Z Budokai 3 HD Files

Thanks for the tips! But the instruction you sent (while very helpful) are a bit too vast haha. I'm trying to unpack the Budokai 3 files OP uploaded in order to get the audio files from them so can you direct me to how to unpack those files specifically without being a bit overwhelmed? It would mean a lot!
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-29T18:01:47+00:00
- Post Title: Dragon Ball Z Budokai 3 HD Files

Here is the simplified version [https://aluigi.altervista.org/quickbms/howto.htm](https://aluigi.altervista.org/quickbms/howto.htm)
You can also google something like "how to use quickbms" for youtube tutorials.
