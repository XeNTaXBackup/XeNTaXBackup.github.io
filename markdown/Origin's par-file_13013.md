## Post #1
- Username: Christsnatcher
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2015-07-02T18:03:06+00:00
- Post Title: Origin's par-file

Hi.
This is a script for par-files from games in Origin.

```
if ID == 1007747626
	set POS 0
else
	set POS 4
endif

encryption XOR "q@pO3o#5jNA6$sjP3qwe1"
get SIZE asize
math SIZE -= POS
log "decrypted_par.txt" POS SIZE

```

Does anyone know assignment of first 4 bytes of par-file?
Most likely it is a checksum.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-07-06T23:59:23+00:00
- Post Title: Origin's par-file

here
[EAPARTool_0.1.rar](https://xentaxbackup.github.io/file/9398_EAPARTool_0.1.rar)
## Post #3
- Username: Christsnatcher
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2015-07-08T00:41:41+00:00
- Post Title: Origin's par-file

Origin PAR Tool by Ekey (h4x0r) & Haoose


```
http://sendfile.su/1529805
https://mega.nz/#!FXZkAAST!vKSD505ohUn_wIavonqzVLKa736Ot5ZwRKm73Riunx0
```

Open - decode par-file
Patch - patching par-file for use game in offline mode (removes the substring "RequiredToPlayV1,")
Save - encode par-file

Enjoy 
[OriginPARTool.rar](https://xentaxbackup.github.io/file/17097_OriginPARTool.rar)
## Post #4
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2015-09-07T14:01:30+00:00
- Post Title: Origin's par-file

You may want to check this. 
It only results in gibberish in your tool.
[MassEffect3Demo.zip](https://xentaxbackup.github.io/file/9692_MassEffect3Demo.zip)
## Post #5
- Username: HammerTank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 23, 2018 9:58 pm
- Post datetime: 2018-09-02T10:50:49+00:00
- Post Title: Origin's par-file

How are the first 4 bytes calculated actually? Can anyone tell?
## Post #6
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-09-07T04:17:31+00:00
- Post Title: Origin's par-file

No, but I’ll bet it’s distinctive...that is I feel there have been others that have tried before to extract the files from the game.
## Post #7
- Username: HammerTank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 23, 2018 9:58 pm
- Post datetime: 2018-11-07T17:19:06+00:00
- Post Title: Origin's par-file

Hmm, sadly none of the creators is reachable anymore.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-11-21T13:42:08+00:00
- Post Title: Origin's par-file

> Reply from HammerTank ↑Sun Sep 02, 2018 6:50 pm at Sun Sep 02, 2018 6:50 pm
>
> 
How are the first 4 bytes calculated actually? Can anyone tell?
This is CRC32 of encrypted data 

> Reply from HammerTank ↑Thu Nov 08, 2018 1:19 am at Thu Nov 08, 2018 1:19 am
>
> 
Hmm, sadly none of the creators is reachable anymore.
What you mean?
## Post #9
- Username: HammerTank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 23, 2018 9:58 pm
- Post datetime: 2019-12-05T20:18:16+00:00
- Post Title: Origin's par-file

> Reply from Ekey ↑Thu Nov 21, 2019 9:42 pm at Thu Nov 21, 2019 9:42 pm
>
> 
This is CRC32 of encrypted data
It doesn't seem to be CRC32. I already checked that. That's why I'm asking.
I took a par file, removed the first 4 bytes and the CRC32 doesn't match the hash I removed before.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-12-07T02:32:09+00:00
- Post Title: Origin's par-file

Make sure your CRC32 algorithm works with polynomial 0x04C11DB7
## Post #11
- Username: HammerTank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 23, 2018 9:58 pm
- Post datetime: 2019-12-09T20:28:21+00:00
- Post Title: Origin's par-file

> Reply from Ekey ↑Sat Dec 07, 2019 10:32 am at Sat Dec 07, 2019 10:32 am
>
> 
Make sure your CRC32 algorithm works with polynomial 0x04C11DB7

I used that. Look at the file I attached. The checksum in the file is 0x31E360B3, but when I calculate the CRC32, I get 0xBDC63D58 (polynomial 0x00000000) or 0xDCB13237 (polynomial 0x04C11DB7). So what's wrong? I don't get it. 


 RA95Launcher.zip
(296 Bytes) Downloaded 22 times
## Post #12
- Username: HammerTank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 23, 2018 9:58 pm
- Post datetime: 2020-06-30T20:21:03+00:00
- Post Title: Origin's par-file

Noone? 

In your tool, the following two different contents result in the same checksum. So this is obviously no CRC32 as it would also change with every byte that changed...

```
ContentId = 1001288
ProductTitle = "Command and Conquer Red Alert"
InstalledDistro = RequiredToPlayV1,AccessDigitalV3
SupportedDistros

```


```
ContentId = 1001288
ProductTitle = "Command and Conquer Red Alert"
InstalledDistro = RequiredToPlayV1,AccessDigitalV4
SupportedDistros

```


But both these contents result in the same checksum with your tool. Can you please explain?
## Post #13
- Username: HammerTank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 23, 2018 9:58 pm
- Post datetime: 2020-09-06T18:29:44+00:00
- Post Title: Origin's par-file

Sadly, noone is willing to help, right?
## Post #14
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2020-11-18T18:40:44+00:00
- Post Title: Origin's par-file

See these previous analysis
[https://forum.exetools.com/showthread.php?t=17472](https://forum.exetools.com/showthread.php?t=17472)
[https://yingtongli.me/blog/2018/11/16/drm1-1.html](https://yingtongli.me/blog/2018/11/16/drm1-1.html)
[https://github.com/ME3Explorer/ME3Explo ... /PAREditor](https://github.com/ME3Explorer/ME3Explorer/tree/v2.0.10/ME3Explorer/PAREditor)
## Post #15
- Username: HammerTank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 23, 2018 9:58 pm
- Post datetime: 2020-11-23T17:07:08+00:00
- Post Title: Origin's par-file

> Reply from mirh ↑Thu Nov 19, 2020 2:40 am at Thu Nov 19, 2020 2:40 am
>
> 
See these previous analysis
https://forum.exetools.com/showthread.php?t=17472
https://yingtongli.me/blog/2018/11/16/drm1-1.html
https://github.com/ME3Explorer/ME3Explo ... /PAREditor

Thank you very much. The second link did it with the hint that only every 4th byte is used.
