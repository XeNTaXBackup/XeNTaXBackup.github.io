## Post #1
- Username: TheMathDoc
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2013 11:57 pm
- Post datetime: 2015-06-09T20:01:01+00:00
- Post Title: Echo Of Soul .u file encryption

Echo Of Soul ([http://www.aeriagames.com/playnow/eosus ... e_overview](http://www.aeriagames.com/playnow/eosus/final_para_game_overview)) recently hit open beta, and I've been tweaking some existing software to extract the game's unreal packages (and sound/movie files, but that's not relevant for this). I've been doing well until I hit the game's .u files - unreal script files. They seem to be encrypted, and it looks almost like simple XOR encryption using a key close to 

0xCB, 0xAA, 0x07, 0xC4, 0x3C, 0xE4, 0xC5, 0x93

This key does transforms the unreal name table into something more comprehensible, however, it looks like the key itself changes as the bytes go by. For instance, the exact key above will decrypt the "None" name table entry, but then leaves the rest of the names as gibberish. I have been able to make out a few other names (things like "Core" and "Script") by tweaking the bytes in the key above for different chunks of the name table.

Anyways I was wondering if anyone wanted to try their hand at figuring out the algorithm used. Unfortunately, the game has a lot of security that prevents me from using a disassembler to see the decryption process. 

I've attached a two example file to look at and can of course provide more.

Thanks,
TheMathDoc
[.u samples.7z](https://xentaxbackup.github.io/file/9285_.u samples.7z)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-06-09T20:43:12+00:00
- Post Title: Echo Of Soul .u file encryption

Here my tool for decrypt U, INT, INI ect files.

Note: Before posting encrypted files you need also include main executable with all modules because encryption algorithm avaible only there.

```
        EOSDecryptor <pScrFile> <pDstFile>
[Examples]
        EOSDecryptor EOS.ini EOS.ini.dec
```


Download: See below.
## Post #3
- Username: TheMathDoc
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2013 11:57 pm
- Post datetime: 2015-06-10T14:15:17+00:00
- Post Title: Echo Of Soul .u file encryption

I figured that the game's exe was more or less useless because of its encryption, but will do for next time.

Thanks!
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-06-11T18:27:48+00:00
- Post Title: Echo Of Soul .u file encryption

> Reply from TheMathDoc
>
> I figured that the game's exe was more or less useless because of its encryption, but will do for next time.

Thanks!binaries are protected with Themida  I tested in Korean and no work tool for decrypt .u,etc files.

PS: how it work really, this is work? I try test with sample files of .u uploaded by TheMatDoc but anyway always convert the dec with 0 bytes, so what doing wrong?
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-06-12T09:34:36+00:00
- Post Title: Echo Of Soul .u file encryption

It's batch tool. Open EOSDecryptor.bat with notepad, set path for input file and output file. Example

```
EOSDecryptor "D:\Echo Of Soul\System\EOS.ini" "D:\Echo Of Soul\System\EOS.ini.dec"
```
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-06-12T14:40:26+00:00
- Post Title: Echo Of Soul .u file encryption

> Reply from Ekey
>
> It's batch tool. Open EOSDecryptor.bat with notepad, set path for input file and output file. Example
Code: Select allEOSDecryptor "D:\Echo Of Soul\System\EOS.ini" "D:\Echo Of Soul\System\EOS.ini.dec"yes Ekey thanks for the tip, i'm not noob buddy, no offend, but I know this process, just when I say how it works is because when convert file always got 0 byte file, here you have example of my system folder trying decode Fire.u.

PS: don't know if matter or no running Windows 7 x64.
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-06-12T20:32:05+00:00
- Post Title: Echo Of Soul .u file encryption

I have Win7 x64 and works fine. With other files you have this problem?
## Post #8
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-06-13T02:45:07+00:00
- Post Title: Echo Of Soul .u file encryption

> Reply from Ekey
>
> I have Win7 x64 and works fine. With other files you have this problem?

I'm on windows 8.1 x64 and having the same issue.
## Post #9
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-06-13T05:18:59+00:00
- Post Title: Echo Of Soul .u file encryption

> Reply from Ekey
>
> I have Win7 x64 and works fine. With other files you have this problem?any file like u,ini,etc got same issue.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-06-14T14:44:04+00:00
- Post Title: Echo Of Soul .u file encryption

Well i rebuild decryptor, try it. For me works perfect
[EOSDecryptor_0.1a.rar](https://xentaxbackup.github.io/file/9310_EOSDecryptor_0.1a.rar)
## Post #11
- Username: Keezie
- Rank: advanced
- Number of posts: 45
- Joined date: Tue Jun 04, 2013 8:12 am
- Post datetime: 2015-06-14T17:53:40+00:00
- Post Title: Echo Of Soul .u file encryption

> Reply from Ekey
>
> Well i rebuild decryptor, try it.

For me works perfect

Working fine for me now.
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-06-14T19:54:59+00:00
- Post Title: Echo Of Soul .u file encryption

[quote="Ekey"][/quote]ok now all be worked fine, now my question, any chance to help with unpack Themida v2.0.1.0 - v2.1.8.0? really I try all ways as I can in Windows Xp and no lucky, you are a experienced guy in reverse engineering and sure can do it, please if can take a look into binaries of this game, really grateful Ekey.

[https://cloud.mail.ru/public/8oAy/EvjnrTLQJ](https://cloud.mail.ru/public/8oAy/EvjnrTLQJ)
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-06-17T13:52:03+00:00
- Post Title: Echo Of Soul .u file encryption

[https://www.sendspace.com/file/qsokmk](https://www.sendspace.com/file/qsokmk)
## Post #14
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-06-17T14:59:29+00:00
- Post Title: Echo Of Soul .u file encryption

> Reply from Ekey
>
> https://www.sendspace.com/file/qsokmkmany thanks Ekey, anyway I unpacked myself, I think I do fine the process, but anyway thanks for support 

PS: maybe is good do a tutorial when you unpack it, I see you got others files I don't got in unpacking process.
PS2: here my guide.

[How Unpack Themida 2.x.x](http://forum.xentax.com/viewtopic.php?f=29&t=12953)
## Post #15
- Username: yolotrollo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 28, 2015 12:40 am
- Post datetime: 2015-06-27T17:17:20+00:00
- Post Title: Echo Of Soul .u file encryption

> Reply from Ekey
>
> Well i rebuild decryptor, try it. For me works perfect
Do you mind sharing some technical details such as what encryption algorithm and actual key was used? I want to encrypt back modifications to the .ini file(s). Thank you.
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-06-27T19:54:15+00:00
- Post Title: Re: Echo Of Soul .u file encryption

> Reply from yolotrollo
>
> Ekey wrote:Well i rebuild decryptor, try it. For me works perfect
Do you mind sharing some technical details such as what encryption algorithm and actual key was used? I want to encrypt back modifications to the .ini file(s). Thank you.
It's Wincrypt + Custom encryption parts code. Currently no way to encrypt it back.
## Post #17
- Username: reyzone
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 14, 2014 6:45 am
- Post datetime: 2015-07-26T23:12:35+00:00
- Post Title: Re: Echo Of Soul .u file encryption

anyone who can unpack ukx  echo of soul? i us umodel not work
## Post #18
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2015-12-06T00:47:15+00:00
- Post Title: Re: Echo Of Soul .u file encryption

Removed. (Find this info on my personal site or on Zenhax.)
