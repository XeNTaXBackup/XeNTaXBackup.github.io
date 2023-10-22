## Post #1
- Username: cabera2
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 24, 2016 4:13 am
- Post datetime: 2021-09-28T18:18:25+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

At first, I'm not english speaker so I apologize about my bad english.

I'm trying to extract resources from PC version of "NEO: The World Ends With You(a.k.a NTWEWY or NeoTWEWY)".
few resources was in "resources.assets" and I could extract it. but It looks like most of assets are in "*.unity3d" files.

I tryind lot of tools that can unpack *.unity3d file,(Asset Studio, QuickBMS, UABEA, etc) but nothing worked.

here I uploaded some of those files.(there are almost 6 thousands of *.unity3d files in folder)
[https://drive.google.com/file/d/10BFzv1 ... sp=sharing](https://drive.google.com/file/d/10BFzv1W6EG31EHykzRJPC3Lo6iGzp2N7/view?usp=sharing)

Someone help me please.
## Post #2
- Username: cabera2
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 24, 2016 4:13 am
- Post datetime: 2021-09-29T02:52:40+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

GameAssembly.dll was abled to unpack with Il2CppDumper
i got a lot of dll files and it was able to see the contents use ILSpy

Still no Clue for unpacking resources
## Post #3
- Username: akintos
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 06, 2018 5:24 pm
- Post datetime: 2021-09-29T09:00:26+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

AES-128-CBC encryption

KEY 6d6b3a39747a785752467d4a707a7732
IV 4e46586a6571286e3a33672738263d3b

you can get the encryption info using

HnLib.AssetBundleManager.Instance.mCrypt.mRijndael.Key
HnLib.AssetBundleManager.Instance.mCrypt.mRijndael.IV
## Post #4
- Username: Sneakyerz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 01, 2018 4:57 pm
- Post datetime: 2021-09-30T11:13:10+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

How can we use the key? Asset Studio and QuickBMS are the programs i mainly use, and I'm have no clue on how to make a script to decrypt files. Unless you know how to make one?
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-09-30T17:50:53+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

Here is simple quickbms script for decrypting unity3d assets. Credits to akintos for the key.


 neo_twewy_decrypt.zip
(368 Bytes) Downloaded 117 times
## Post #6
- Username: L33THAK0R
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 13, 2021 2:48 pm
- Post datetime: 2021-10-01T02:25:40+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

> Reply from akintos ↑Wed Sep 29, 2021 5:00 pm at Wed Sep 29, 2021 5:00 pm
>
> 
AES-128-CBC encryption

KEY 6d6b3a39747a785752467d4a707a7732
IV 4e46586a6571286e3a33672738263d3b

you can get the encryption info using

HnLib.AssetBundleManager.Instance.mCrypt.mRijndael.Key
HnLib.AssetBundleManager.Instance.mCrypt.mRijndael.IV

@@akintos have you had any luck with decrypting the .USMs for the title in question? I've had little luck decrypting them unfortunately.
## Post #7
- Username: akintos
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 06, 2018 5:24 pm
- Post datetime: 2021-10-01T03:45:43+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

I have no idea and I am not interested in those files. Though I don't think they will encrypt any video data.
## Post #8
- Username: L33THAK0R
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 13, 2021 2:48 pm
- Post datetime: 2021-10-01T05:45:36+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

> Reply from akintos ↑Fri Oct 01, 2021 11:45 am at Fri Oct 01, 2021 11:45 am
>
> 
I have no idea and I am not interested in those files. Though I don't think they will encrypt any video data.

Thats a shame, fingers crossed someone'll figure out how to decrypt em one day.
## Post #9
- Username: Skyth
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 06, 2016 2:28 am
- Post datetime: 2021-10-10T17:42:45+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

Found the key for HCA and USM files: 53346933792338754

I was able to play the movies in the official CRI SDK tools by providing this decryption key. I'm not sure if there is any community made tools for it, though.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-11T21:44:12+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

Well, there is also crid_mod, but it doesn't work with your key.
Other keys work fine, so it's either wrong key or newer USM file format.
More info here [http://wiki.xentax.com/index.php/USM_Video](http://wiki.xentax.com/index.php/USM_Video)

Btw, is this CRI SDK available only for registered developers?
## Post #11
- Username: Skyth
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 06, 2016 2:28 am
- Post datetime: 2021-10-13T08:40:37+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

Yeah, it is only available for registered developers. However, they send it to basically anyone if you fill their form.

The key I sent was in decimal, it appears it was put as hexadecimal in that wiki page. Perhaps that's the problem.

I tried the tool you mentioned with the hexadecimal version of the key and it seems to extract the video properly:

upper 32b: 00BD86C0
lower 32b: EE8C7342

Not sure about the audio, it seems it's a bunch of encrypted HCA files combined to one file when extracted with this tool? (probably still uses the same key)
## Post #12
- Username: cabera2
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 24, 2016 4:13 am
- Post datetime: 2021-10-13T17:03:15+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

> Reply from ikskoks ↑Tue Oct 12, 2021 5:44 am at Tue Oct 12, 2021 5:44 am
>
> 
Well, there is also crid_mod, but it doesn't work with your key.
Other keys work fine, so it's either wrong key or newer USM file format.
More info here http://wiki.xentax.com/index.php/USM_Video

Btw, is this CRI SDK available only for registered developers?

> Reply from Skyth ↑Wed Oct 13, 2021 4:40 pm at Wed Oct 13, 2021 4:40 pm
>
> 
Yeah, it is only available for registered developers. However, they send it to basically anyone if you fill their form.

The key I sent was in decimal, it appears it was put as hexadecimal in that wiki page. Perhaps that's the problem.

I tried the tool you mentioned with the hexadecimal version of the key and it seems to extract the video properly:

upper 32b: 00BD86C0
lower 32b: EE8C7342

Not sure about the audio, it seems it's a bunch of encrypted HCA files combined to one file when extracted with this tool? (probably still uses the same key)
Thank you! I have successfully decrypted with ikskoks's tool and Skyth's key.
Now I'm searching for the way to encrypt after editing the video
## Post #13
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-13T20:17:45+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

> The key I sent was in decimal, it appears it was put as hexadecimal in that wiki page. Perhaps that's the problem.

Sorry, my mistake. xD 
I have never seen USM key in decimal before. I've updated the wiki article with the key that works.  Thank you.
## Post #14
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2021-10-19T17:46:48+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

someone found about audio 
look acb hca look sample here
[TOCi.zip](https://xentaxbackup.github.io/file/21045_TOCi.zip)
## Post #15
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2021-10-19T18:09:02+00:00
- Post Title: NEO: The World Ends With You (Unity 3D)

[https://github.com/vgmstream/vgmstream/issues/123](https://github.com/vgmstream/vgmstream/issues/123)

found  [http://hcs64.com/files/utf_tab07b6_special.zip](http://hcs64.com/files/utf_tab07b6_special.zip)

acb is readable with last foobar plugin

need now know how extract awb file ? 

any idea is welcome thank's
