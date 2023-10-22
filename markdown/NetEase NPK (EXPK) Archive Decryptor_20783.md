## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-07-07T15:05:57+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

- Feature: 
Decrypt encrypted NPK archives with "EXPK" signature and write the data back into the source archive.

- Usage:
The tool requires an encryption key in order to perform the decryption. You can get the up-to-date key from [here](https://mega.nz/#!mJd03Ihb!dofuXylr1zlHFVkcRB6t8lW-Ukju0Vca2mCIH-830lc). Copy all the files (including the key) into your working directory and run the batch file.

- Supported Games:
Marvel Super War
Onmyoji Arena

- Note:
The key provided above is compatible for both Onmyoji Arena (OA) and Marvel Super War (MSW) below v2.6.0. MSW above v2.6.0 has switched to a different key which can be downloaded [here](https://mega.nz/#!nVcAHQiD!DN7xYWFMDb-wECsIaCvA5MZhSKm9ZAPUP0f5MaA67OA).

- About Encryption Key:
The two games above use simple xor for encryption, but with an infinite fixed sequence as key. Now thanks to BlueEffie the method to compute the key is made public. But for the sake of the continuity of this tool and its performance, I decided to not change the old routine but simply update the xorkey for both games. 

Below is the historic info of the xor key just for record:
1. The original key (871 KB) mostly was taken from this [page](https://github.com/zhouhang95/neox_tools) (credit to zhouhang95). 
2. The previous key described in this [post](viewtopic.php?p=159269#p159269) has been extended by 980% in length (9414 KB) compared with the original one, making it possible to decrypt larger data. It's sufficient to handle the largest asset of OA and MSW (up to v2.6.0). 
3. Current xor keys for both games are extended to 16 mega bytes using the [method](viewtopic.php?p=160174#p160174) posted by BlueEffie.



 EXPKDec.zip
v0.4.2 (5.45 KiB) Downloaded 724 times
## Post #2
- Username: TakeAaron
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 08, 2019 4:23 pm
- Post datetime: 2019-07-07T15:42:17+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

thank you
## Post #3
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-07-08T08:32:18+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

Thank you! Gonna test this out for Marvel Super War.
## Post #4
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2019-07-08T10:03:59+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

epic   
will u keep adding more key in the future?
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-07-09T09:01:08+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

Update: 
Fixed a stupid bug that cause the decryption failed with Onmyoji Arena. Added support for Win XP.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-07-16T11:24:08+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

Update: 
Fixed another bug that introduced by previous fix.  Sorry about that.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-10T03:42:57+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

Update:
1. Changed the detecting method to adjust with different version games;
2. Fixed an issue for decrypting MARVEL Super War.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-15T09:43:15+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

Update:
Added a longer xor key. Check the first post for details.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-17T04:23:33+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

Update:
1. Another update to the long key: now approximately 1155 KB;
2. Updated decryptor to v0.4.1 for better perfomance;
3. Added encryption key for Marvel Super War above v2.6.0.

Check the main post for details.
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-21T17:47:04+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

Update:
1. Ultimate update to the long key for Onmyoji Arena and Marvel Super War (below v2.6.0): now approximately 9414 KB;
2. Updated decryptor to v0.4.2: added real-time status message during decryption.

The key for MSW above v2.6.0 hasn't been updated yet.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-23T13:36:35+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

Update:
Added longer key for MSW above v2.6.0: 1915 KB approximately. Sufficient for every high res character package.
## Post #12
- Username: BlueEffie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 19, 2015 3:07 pm
- Post datetime: 2020-02-20T14:02:26+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

I found the decryption method and key of [Forever 7 Day's Capital] [Onmyoji Arena] [Marvel Super War] in IDA Pro 

This is the decryption code fragment written by C#. Just decryption without extraction


 NPKDecrypt.rar
(14.39 KiB) Downloaded 335 times
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-21T06:59:55+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

> Reply from BlueEffie ↑Thu Feb 20, 2020 10:02 pm at Thu Feb 20, 2020 10:02 pm
>
> 
I found the decryption method and key of [Forever 7 Day's Capital] [Onmyoji Arena] [Marvel Super War] in IDA Pro
Congratulations!

I've updated the xorkeys generated with the method you posted.
## Post #14
- Username: Untily
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 11, 2020 4:48 pm
- Post datetime: 2020-06-11T09:08:56+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

Thank you
## Post #15
- Username: m545891031
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Jul 21, 2016 4:04 am
- Post datetime: 2020-06-13T09:37:07+00:00
- Post Title: NetEase NPK (EXPK) Archive Decryptor

> Reply from Bigchillghost ↑Fri Feb 21, 2020 2:59 pm at Fri Feb 21, 2020 2:59 pm
>
> 
BlueEffie wrote: ↑Thu Feb 20, 2020 10:02 pm
I found the decryption method and key of [Forever 7 Day's Capital] [Onmyoji Arena] [Marvel Super War] in IDA Pro 

Congratulations!

I've updated the xorkeys generated with the method you posted.

Unable to get the file name when decompressing using QuickBMS script, does it mean that using this tool can get the correct name when decompressing NPK?
## Post #16
- Username: iruzer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 10, 2009 7:28 pm
- Post datetime: 2020-07-29T00:09:19+00:00
- Post Title: Re: NetEase NPK (EXPK) Archive Decryptor

> Reply from m545891031 ↑Sat Jun 13, 2020 5:37 pm at Sat Jun 13, 2020 5:37 pm
>
> 
Bigchillghost wrote: ↑Fri Feb 21, 2020 2:59 pm
BlueEffie wrote: ↑Thu Feb 20, 2020 10:02 pm
I found the decryption method and key of [Forever 7 Day's Capital] [Onmyoji Arena] [Marvel Super War] in IDA Pro 

Congratulations!

I've updated the xorkeys generated with the method you posted. 


Unable to get the file name when decompressing using QuickBMS script, does it mean that using this tool can get the correct name when decompressing NPK?

use this extract ([https://github.com/zhouhang95/neox_tools](https://github.com/zhouhang95/neox_tools))
## Post #17
- Username: thewitchboy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 29, 2019 7:04 am
- Post datetime: 2021-06-27T12:14:39+00:00
- Post Title: Re: NetEase NPK (EXPK) Archive Decryptor

I am having troubles, I am following the steps but it is coming up with in the batch command "wrong archive format" All I want to do is extract the sound effects and fx/ textures from MARVEL Super War.

can you please help
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-28T15:28:31+00:00
- Post Title: Re: NetEase NPK (EXPK) Archive Decryptor

> Reply from thewitchboy ↑Sun Jun 27, 2021 8:14 pm at Sun Jun 27, 2021 8:14 pm
>
> I am following the steps but it is coming up with in the batch command "wrong archive format"
Had you decrypted the file already? You can't decrypt a file twice otherwise you'll get that error message.
## Post #19
- Username: thewitchboy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 29, 2019 7:04 am
- Post datetime: 2021-07-04T12:21:34+00:00
- Post Title: Re: NetEase NPK (EXPK) Archive Decryptor

> Reply from Bigchillghost ↑Mon Jun 28, 2021 11:28 pm at Mon Jun 28, 2021 11:28 pm
>
> 
thewitchboy wrote: ↑Sun Jun 27, 2021 8:14 pmI am following the steps but it is coming up with in the batch command "wrong archive format"

Had you decrypted the file already? You can't decrypt a file twice otherwise you'll get that error message.

Would you be able to extract them for me at all?
## Post #20
- Username: gabematz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 26, 2020 10:01 pm
- Post datetime: 2023-04-04T00:29:24+00:00
- Post Title: Re: NetEase NPK (EXPK) Archive Decryptor

Hi!

Would it be possible for this tool to work with Harry Potter Magic Awakened?
## Post #21
- Username: xyyi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 22, 2022 4:02 pm
- Post datetime: 2023-08-31T13:37:32+00:00
- Post Title: Re: NetEase NPK (EXPK) Archive Decryptor

Wrong archive format! What is the reason for this
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-01T11:10:23+00:00
- Post Title: Re: NetEase NPK (EXPK) Archive Decryptor

> Reply from xyyi ↑Thu Aug 31, 2023 9:37 pm at Thu Aug 31, 2023 9:37 pm
>
> 
Wrong archive format! What is the reason for this
It means you're not supposed to use the tool on that file.
