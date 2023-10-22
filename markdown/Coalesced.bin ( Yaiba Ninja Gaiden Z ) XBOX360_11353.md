## Post #1
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-03-23T20:35:28+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

Please help to decrypt the file.  
[https://mega.co.nz/#!0kZHECiI!jlHX2gefG ... 29hyAhe23I](https://mega.co.nz/#!0kZHECiI!jlHX2gefGExaH_dBGzAzPOshrePp2s39129hyAhe23I)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-23T20:50:36+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

PC version encrypted too?
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-24T00:43:44+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

> Reply from Ekey
>
> PC version encrypted too?PC version supported by umodel fine.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-24T01:21:39+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

> Reply from CriticalError
>
> Ekey wrote:PC version encrypted too?PC version supported by umodel fine.
I mean about Coalesced.bin file.
## Post #5
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-03-24T06:47:30+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

> Reply from Ekey
>
> PC version encrypted too?

in PC verison all files are in the clear, ie does not have a file coalecsed.bin, as in all games on Unreal Engin for PC.
AES encryption is likely in this case, but as a rule with him, I do not know. It seems to need the executable file to it to find a key for decryption. If you need it, then I give it too.
or here XOR encrypted.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-25T02:45:07+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

Job done. Here my tool for decrypt and encrypt - Tested only on PS3 version files.. Let me know if it not works on XBOX Coalesced files.

```
        YNGZCoalescedTool <pMode> <pInFile> <pOutFile>

[Modes]
        -d - Decrypt
        -e - Encrypt

[Examples]
        YNGZCoalescedTool -d COALESCED_INT.BIN COALESCED_INT.BIN.DEC
        YNGZCoalescedTool -e COALESCED_INT.BIN.DEC COALESCED_INT.BIN
```


Also in archive additional tool for unpack and pack BIN files - Seems author Gocha

Steps:
1) Decrypt BIN
2) Unpack decrypted BIN
3) Edit files
4) Pack BIN
5) Encrypt packed BIN
6) Profit

Enjoy 
[YNGZCoalescedTool_0.1.rar](https://xentaxbackup.github.io/file/7128_YNGZCoalescedTool_0.1.rar)
## Post #7
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-03-25T04:42:53+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

Thank you so much, everything works perfectly! You are a genius!
## Post #8
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2014-03-26T14:23:55+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

Nice! Ekey, there another game with the same problems: Spec Ops: The Line
If I get the coalesced, could u analyze it?
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-26T14:43:03+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

> Reply from xujozer
>
> Nice! Ekey, there another game with the same problems: Spec Ops: The Line
If I get the coalesced, could u analyze it?
[Here](http://forum.xentax.com/viewtopic.php?p=74964#p74964) tool by Rick
## Post #10
- Username: kosemen76
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 05, 2019 6:05 am
- Post datetime: 2022-07-30T14:05:53+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

[https://dosya.co/6x4wljtchitl/COALESCED_INT.rar.html](https://dosya.co/6x4wljtchitl/COALESCED_INT.rar.html)
PS3 NPUB31256 it doesn't work, same in other versions of ps3
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-08-01T17:22:08+00:00
- Post Title: Coalesced.bin ( Yaiba: Ninja Gaiden Z ) XBOX360

> Reply from kosemen76 ↑Sat Jul 30, 2022 10:05 pm at Sat Jul 30, 2022 10:05 pm
>
> 
https://dosya.co/6x4wljtchitl/COALESCED_INT.rar.html
PS3 NPUB31256 it doesn't work, same in other versions of ps3

I have tested the tools on your file and they work perfectly.
[COALESCED_INT_Unpacked.rar](https://xentaxbackup.github.io/file/22582_COALESCED_INT_Unpacked.rar)
