## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-05-31T17:52:43+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

[Ai Sp@ce](http://aisp.jp/) is a Japanese virtual 3D massively multiplayer online social game, you can write your own script for people to join and play your script!

I need help on this game achrive whick I believe they use zlib and blowfish to encrypt resources!?

```
- 6823936 bytes allocated
- load signatures
- open file C:\MySoftware\QuickBMS\signsrch016\signsrch.sig
- 1774060 bytes allocated for the signatures
- 2278 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  008ebb45 31   Adler CRC32 (0x191b3141) [32.le.1024]
  009e4000 32   Adler CRC32 (0x191b3141) [32.be.1024]
  008ebb4c 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  009e4400 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  008ebb67 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  009e4800 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  008e0327 167  Rijndael Te0 (0xc66363a5U) [32.le.1024]
  008e0b89 169  Rijndael Te1 (0xa5c66363U) [32.le.1024]
  008e0b82 171  Rijndael Te2 (0x63a5c663U) [32.le.1024]
  008e0bc0 173  Rijndael Te3 (0x6363a5c6U) [32.le.1024]
  008e04b5 175  Rijndael Te4 (0x63636363U) [32.le.1024]
  008e0964 176  Rijndael Td0 (0x51f4a750U) [32.le.1024]
  008e0989 178  Rijndael Td1 (0x5051f4a7U) [32.le.1024]
  008e0971 180  Rijndael Td2 (0xa75051f4U) [32.le.1024]
  008e09a7 182  Rijndael Td3 (0xf4a75051U) [32.le.1024]
  008e1440 184  Rijndael Td4 (0x52525252U) [32.le.1024]
  009d9248 185  Rijndael rcon [32.le.40]
  008e0336 190  Blowfish bfp table [32.le.72]
  008e030b 192  Blowfish ks0 table [32.le.1024]
  009d5e48 194  Blowfish ks1 table [32.le.1024]
  009d6248 196  Blowfish ks2 table [32.le.1024]
  009d6648 198  Blowfish ks3 table [32.le.1024]
  008dfc0b 208  camellia [32.le.48&]
  008dfa11 210  camellia_sp1110 [32.le.1024]
  008dfa18 212  camellia_sp0222 [32.le.1024]
  008dfa22 214  camellia_sp3033 [32.le.1024]
  008dfa2f 216  camellia_sp4404 [32.le.1024]
  009d5a20 325  Haval hash pass2 [32.le.128&]
  008e7ad2 357  Zlib dist_code [..512]
  008e7aac 358  Zlib length_code [..256]
  008ead90 360  Zlib base_length [32.le.116]
  008eaeda 362  Zlib base_dist [32.le.120]
  008f14e7 568  classical random incrementer 0x343FD 0x269EC3 [32.le.8&]
  009d5a00 1299 Haval init [32.le.32&]
  009d5aa0 1301 Haval mc3 [32.le.128]
  009d5b20 1303 Haval mc4 [32.le.128]
  009d5ba0 1305 Haval mc5 [32.le.128]
  009d5b80 1451 HAVAL1_DS [32.le.32]
  009d5b00 1453 HAVAL2_DS [32.le.32]
  008ead81 1525 zinflate_lengthExtraBits [32.le.116]
  009e21c5 1526 zinflate_lengthExtraBits [32.be.116]
  008eaec5 1529 zinflate_distanceExtraBits [32.le.120]
  009d5a48 1561 Blowfish_s_init [32.le.4096]
  00a650d8 1767 anti-debug: IsDebuggerPresent [..17]
  00b135fc 2253 PADDINGXXPADDING [..16]

- 45 signatures found in the file

```


I think *.hed are indices file and *.dat are the actual data resource.
Other than that I can't do anything and hoping people here can help me out of this!

[The Upload](http://www.sendspace.com/file/cgma4f) contains the *.exe, *.dll, *.hed and *.dat files.

Thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-31T21:14:52+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

please upload .\data\chara\3\0000.dat that I want to make a final check and the script is ready
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-05-31T22:06:18+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-31T22:08:55+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

ops my big fault, I meant .\data\chara\1.hed
sorry :)
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-05-31T22:13:44+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

here is the 1.hed, [dat + hed is here](http://www.sendspace.com/file/9xoqqn) ~42M
[1_hed.rar](https://xentaxbackup.github.io/file/3095_1_hed.rar)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-31T22:18:44+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

ok confirmed, the script works perfectly :)
the only problem is that it's necessary a new version of quickbms that I will release tomorrow :(
come on it's not much to wait, only some hours
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-01T20:05:07+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

as promised:
[http://aluigi.org/papers/bms/aispace.bms](http://aluigi.org/papers/bms/aispace.bms)
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms) (version 0.4.5)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-04-09T00:29:07+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

I tried the script but it said 0 files found.

So then I took a look at it and figured maybe I should try specifying that quickbms is version 0.4.10b and it seems to have done something, but then it tells me it didn't have enough space while trying to allocate 1 GB of space.

So I decided to run it through command line using option -l, figuring that I might not need to allocate any space that way, and then it said 

> Error: incomplete input file number -1, can't read 1623406405 bytes.
>
>        anyway don't worry, it's possible that the BMS script has been written
>
>        to exit in this way if it's reached the end of the archive so check it
>
>        or contact its author or verify that all the files have been extracted

Is it because the data structure has changed over the past 9 months and so the script no longer works?

I've attached the current 1.hed file. 

and [0000.dat](http://www.mediafire.com/?8ld13oh5ty4lugz)
[1.7z](https://xentaxbackup.github.io/file/4189_1.7z)
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-09T09:37:24+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

it's for sure the key that has been changed
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-04-09T12:34:43+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

lol oh well.
Is it much different from what it was before? (based on the existing script)

Maybe someone can modify the script to reflect the current state? =)
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-09T15:26:44+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

I have a crazy idea, upload the following files:
script.hed
settings.hed
shader.hed
tools.hed
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-04-09T16:20:06+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

Attached the hed files in the data folder (not any subfolders).
I've included other hed files in case they might be useful.

Will you need the dat files as well?
I'm mainly interested in the models, items, and environment objects.

Thanks
[data.7z](https://xentaxbackup.github.io/file/4192_data.7z)
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-10T09:00:57+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

I have updated the script:
[http://aluigi.org/papers/bms/aispace.bms](http://aluigi.org/papers/bms/aispace.bms)

I'm still not 100% sure if the key I have retrieved is correct because there are some things not clear (some files start from offset 0 for unknown reasons), anyway let me know if works and all the output files are perfect
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-04-10T17:36:52+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

lol wow I sent the request 2 days ago and you put up a new script just like that.

Anyways a whole lot of files came out. The total filesize for each output folder match the total filesize for the corresponding dat files, so I'm guessing that might mean it extracted everything.

It uses dds textures and dxg models, but the dxg models have gotten me stumped and it appears I'll have to go googling around some more. Can't verify that they are correct until then =/

Maybe you can take a look while I'm running around the internet? I've attached one of the folders from the "chara" folder and contains textures, models, animations, and some "attr" (attributes maybe)

But it appears to work.
Thanks a lot!
[00100.7z](https://xentaxbackup.github.io/file/4200_00100.7z)
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-04-10T20:55:23+00:00
- Post Title: Need help on unpack "Ai Sp@ce" archive

Oh, someone mentioned that "tpskillshot" dds files can't be opened for some reason.
Here are the hed files for a couple of them.

They were all extracted but could not be opened with neosis or imagemagick or some other attempts.
I've included one of the dds files in the archive as well as some hed files in case they fell under one of the "weird" indices you mentioned.

Otherwise if it's impossible then I'll just have to tell him "too bad lol"
[tpskillshot.7z](https://xentaxbackup.github.io/file/4202_tpskillshot.7z)
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-04-12T15:31:27+00:00
- Post Title: Re: Need help on unpack "Ai Sp@ce" archive

lol they keep updating the hed files when new stuff comes in.
I should figure out how to extract the data so I can deal with new updates myself.

Where should I start (with respect to aispace hed files, not data extraction in general))
Then again, it probably doesn't mean anything if I can't seem to do anything with the dxg files.

Someone uploaded the patch files: [here](http://hotfile.com/dl/114196153/8701a66/aispace_110412_Update_%28Kurisu_Patch%29.rar.html)
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-08T14:00:03+00:00
- Post Title: Re: Need help on unpack "Ai Sp@ce" archive

ai sp@ce is shutting down on the 30th =(
Oh well.

I'm looking at the hed files and trying to figure out the key, but am not sure how to go about doing it.

The previous scripts say rot encryption is used, but I'm not sure where to start even with that lol
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-26T22:27:31+00:00
- Post Title: Re: Need help on unpack "Ai Sp@ce" archive

I don't know why I found this so difficult.
Since aluigi already found the key once and the hed files are the same, I could've just taken the difference between a decrypted file and an unknown file and just produce the key there.

So rather than figuring out how to guess the key I took the easy way out.

Though, that still leaves me stuck with pandora saga key.

Updated for the final patch.
[aispace.7z](https://xentaxbackup.github.io/file/4544_aispace.7z)
