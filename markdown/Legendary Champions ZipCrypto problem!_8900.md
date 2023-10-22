## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-05-07T06:12:08+00:00
- Post Title: Legendary Champions ZipCrypto problem!

With signsrch.exe, I find the offset to handle ZipCrypto @ 0045aa6f
so I lanch "signsrch -3 0045aa6f F:\OL-Games\LegendaryChampions\loader.exe"

Since the game had shut down for a year so I can't connect to the server and so it doesn't trigger the break point! Could anyone help me on this!?

If anyone want the client, you can still [download it form MMORPG](http://download.mmosite.com/default.php?controller=resource&action=freedown&id=4227&cid=1)

```
- 774144 bytes allocated
- load signatures
- open file C:\MySoftware\QuickBMS\signsrch016\signsrch.sig
- 1774060 bytes allocated for the signatures
- 2278 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  0045b875 31   Adler CRC32 (0x191b3141) [32.le.1024]
  0045bb3d 32   Adler CRC32 (0x191b3141) [32.be.1024]
  0045b87c 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  0045bb36 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  0045b897 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  0045bb4f 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  004ac31b 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]
  0047df02 357  Zlib dist_code [..512]
  0047dedc 358  Zlib length_code [..256]
  004807e2 360  Zlib base_length [32.le.116]
  0048092d 362  Zlib base_dist [32.le.120]
  0041c8f8 568  classical random incrementer 0x343FD 0x269EC3 [32.le.8&]
  00479bee 1090 Zip Crypto [32.le.16&]
  00456aa3 1523 zinflate_lengthStarts [32.le.116]
  00456a9e 1525 zinflate_lengthExtraBits [32.le.116]
  004953cd 1526 zinflate_lengthExtraBits [32.be.116]
  00456aef 1527 zinflate_distanceStarts [32.le.120]
  00456aea 1529 zinflate_distanceExtraBits [32.le.120]
  004a837c 1767 anti-debug: IsDebuggerPresent [..17]
  004bd5e4 2253 PADDINGXXPADDING [..16]
  00456c44 2259 unlzx table_three [32.le.64]
  0045aa6f 2273 function where is handled the ZipCrypto password [32.le.12&]

- 22 signatures found in the file
```


for more info. for the package! They are modified zip file with data on .pak and names, indices on .shake.

The format of .shake is

```
  dword         len
  char[len]     PackageName
  dword         numResource
}
Struct Resource {
  dword         len
  char[len]     ResourceName
  dword         numResource
  dword         FileFlag                 //0 = folder , 1 = data file
  dword         CRC
  word           ReferecneIndex     //the order in .pak file         
}
```


The .pak is just zip file with zip sign changed to "UZ", also removed then name and CRC!

Thanks!
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-10T12:44:38+00:00
- Post Title: Legendary Champions ZipCrypto problem!

Olly successfully break's on ZipCrypto func in main executable.
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-05-10T19:23:32+00:00
- Post Title: Legendary Champions ZipCrypto problem!

OK I try it with lgc.exe with breakpoint set @ 00a9df4d!
With break happened, it fall into ntdll not lgc.exe !?

Could anyone help me to find the password? I really want to include a full support on next update of FatImporter!

Thanks.
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-05-11T20:34:03+00:00
- Post Title: Legendary Champions ZipCrypto problem!

Is ASLR enabled for the executable? If it is, try disabling it?

(I don't know if your loader tool automatically compensates for it already)
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-05-18T10:32:16+00:00
- Post Title: Legendary Champions ZipCrypto problem!

I only have little knowledge on debuger so I can't find the password myself!
I think I will leave it open until someone help me on it and I will add support for the model format!
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-18T10:57:40+00:00
- Post Title: Legendary Champions ZipCrypto problem!

I don't see password.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-18T17:08:55+00:00
- Post Title: Legendary Champions ZipCrypto problem!

job done:
[http://aluigi.org/papers/bms/legendary_champions.bms](http://aluigi.org/papers/bms/legendary_champions.bms)
