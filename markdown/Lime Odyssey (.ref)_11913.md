## Post #1
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-09-06T16:17:37+00:00
- Post Title: Lime Odyssey (.ref)

Someone can help me extract files encrypted in .ref?

*.ref: [https://mega.co.nz/#!K4ZFmDCS!COjVDeD_d ... 2kLnQb7iSc](https://mega.co.nz/#!K4ZFmDCS!COjVDeD_dC-7n8ndOM7JcUseMrhYgEmhG2kLnQb7iSc)

I will be very grateful for the help.
Thanks.
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-09-07T07:56:58+00:00
- Post Title: Lime Odyssey (.ref)

Use offzip:

```
offzip -a -z -15 [input_file].ref [output_folder] 0
```
## Post #3
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-09-07T10:54:37+00:00
- Post Title: Lime Odyssey (.ref)

But with offzip, i extract files with wrongs names.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-07T13:20:08+00:00
- Post Title: Lime Odyssey (.ref)

Wrong names? REF don't contain names or obfuscated. Offzip dumped files named as offset.
## Post #5
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-09-07T13:44:56+00:00
- Post Title: Lime Odyssey (.ref)

There is no way to fix?



It is impossible that I can find for example the correct texture of this *.nif.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-08T09:34:12+00:00
- Post Title: Lime Odyssey (.ref)

Need client for reversing.
## Post #7
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2014-09-08T18:20:52+00:00
- Post Title: Lime Odyssey (.ref)

> Reply from Ekey
>
> Need client for reversing.
Client(*.exe and *.pdb): [https://mega.co.nz/#!f0Rz3DiR!twDla_udk ... yydFHvT680](https://mega.co.nz/#!f0Rz3DiR!twDla_udkPeJeInejv6Lwq4eQMVvyy_IGyydFHvT680)
Complete Client: [https://mega.co.nz/#!HhZWSQ7S!tWu-jMLOF ... HcouodXiB4](https://mega.co.nz/#!HhZWSQ7S!tWu-jMLOF7JUpTiqKre_yBuHTkr4tnv-cHcouodXiB4)

I will be forever grateful for your help.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-12T15:27:24+00:00
- Post Title: Lime Odyssey (.ref)

Well REF's it's normal ZIP but with encrypted table. Here my simple snippet code for decrypt.

```
{
    DWORD dwSeed1 = 0x16B14;
    DWORD dwSeed2 = 0;
    do
    {
       dwSeed2 = 0xB1C8 * (dwSeed1 + (BYTE)*pBuffer);
       *pBuffer ^= BYTE((dwSeed1 >> 8) & 0xFF);
       ++pBuffer;
       --dwSize;
       dwSeed1 = dwSeed2 + 0x11894;
    }
    while ( dwSize );
}
```


Maybe Luigi can make script i'm too lazy for implementing  > [http://zenhax.com/viewtopic.php?f=9&t=147](http://zenhax.com/viewtopic.php?f=9&t=147)
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-12T19:03:25+00:00
- Post Title: Lime Odyssey (.ref)

Well > credits to aluigi > script for unpack [http://aluigi.org/papers/bms/others/lime_odissey.bms](http://aluigi.org/papers/bms/others/lime_odissey.bms)
