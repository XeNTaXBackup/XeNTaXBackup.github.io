## Post #1
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-07-02T16:08:58+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

We need a program or script to unpack. Our team wants to translate the game into Russian. As always, developers, our country was deprived us localization.

File - [https://cloud.mail.ru/public/05039ff2e379/resources.dat](https://cloud.mail.ru/public/05039ff2e379/resources.dat)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-02T19:13:10+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

Unknown encryption or compression.
## Post #3
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-07-03T04:52:27+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from Ekey
>
> Unknown encryption or compression.
Damn! And what to do?
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-03T05:28:24+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

I tried use comtype_scan but without results.
## Post #5
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-07-03T05:57:10+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from Ekey
>
> I tried use comtype_scan but without results.
Damn! It is bad. OK, let's wait, maybe in the future someone will be able to understand.
## Post #6
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2014-07-03T22:03:59+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from TimonS
>
> Ekey wrote:I tried use comtype_scan but without results.
Damn! It is bad. OK, let's wait, maybe in the future someone will be able to understand.
You would need to reverse engineer the game executable to find the encryption/compression method.
## Post #7
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-07-04T05:58:45+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from Caboose
>
> TimonS wrote:Ekey wrote:I tried use comtype_scan but without results.
Damn! It is bad. OK, let's wait, maybe in the future someone will be able to understand.
You would need to reverse engineer the game executable to find the encryption/compression method.

- [https://cloud.mail.ru/public/1ca5118be669/default.xex](https://cloud.mail.ru/public/1ca5118be669/default.xex)
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-04T15:33:08+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

Here small info

```

DWORD  dwID; //ARCV
SHORT wVersion; // ?? = 2
DWORD  dwTableZSize; //Compressed size
DWORD  dwCRC; // ??
DWORD  dwTableSize; // ?? - Uncompressed size > Endian little
```
## Post #9
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-07-04T18:46:39+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from Ekey
>
> Here small info
Code: Select allEndian BIG

DWORD  dwID; //ARCV
SHORT wVersion; // ?? = 2
DWORD  dwTableZSize; //Compressed size
DWORD  dwCRC; // ??
DWORD  dwTableSize; // ?? - Uncompressed size > Endian little

To be honest, for me this information, as for monkeys grenade. I'm not thinking straight. If you want, I can give decrypted executable file default.xex
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-04T19:15:56+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from TimonS
>
> To be honest, for me this information, as for monkeys grenade. I'm not thinking straight. If you want, I can give decrypted executable file default.xex
I do not needed it.

PS: one old script for unpack DAT files from games by Drinkbox Studios -> [here](http://aluigi.altervista.org/papers/bms/others/arcv.bms).
## Post #11
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-07-06T18:53:17+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from Ekey
>
> TimonS wrote:To be honest, for me this information, as for monkeys grenade. I'm not thinking straight. If you want, I can give decrypted executable file default.xex  
I do not needed it.

PS: one old script for unpack DAT files from games by Drinkbox Studios -> here.
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-06T21:18:24+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

Because it's old script and used decompression > zlib, compression for xbox is unknown.
## Post #13
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-07-07T20:00:34+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from Ekey
>
> Because it's old script and used decompression > zlib, compression for xbox is unknown.

compression - "deflate"
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-07T20:39:32+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from TimonS
>
> compression - "deflate"
Are you sure?
## Post #15
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-07-08T04:45:20+00:00
- Post Title: Guacamelee! Super Turbo Championship Edition (.dat) Xbox360

> Reply from Ekey
>
> TimonS wrote:compression - "deflate"
Are you sure?

I asked my acquaintance help determine which compression , and he told me that there "deflate"
We took this utility - [https://cloud.mail.ru/public/f1a3cf1337fd/offzip.rar](https://cloud.mail.ru/public/f1a3cf1337fd/offzip.rar), Put it in the root folder of the file from the game and launched Unpack2.bat.
The file begins to unpack, but... not all unpacked, wine, what a lot of data is skipped, and the fact that unfolds, 't open, because apparently there's block structure and each file is divided into chunks of 64 kilobytes.
## Post #16
- Username: gula
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 14, 2014 8:17 pm
- Post datetime: 2014-08-14T13:43:23+00:00
- Post Title: Re: Guacamelee! Super Turbo Championship Edition (.dat) Xbox

> Reply from Ekey
>
> TimonS wrote:compression - "deflate"
Are you sure?

Can you help Ekey?
## Post #17
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-08-14T14:55:20+00:00
- Post Title: Re: Guacamelee! Super Turbo Championship Edition (.dat) Xbox

Just an interesting note about the Windows Steam version: there's a skin importer included called DBImporter.exe that apparently can make .dat files, so even if the Xbox version isn't using DEFLATE, you can still figure out the proper archive structure.
## Post #18
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-08-14T20:16:31+00:00
- Post Title: Re: Guacamelee! Super Turbo Championship Edition (.dat) Xbox

Try this - [http://rghost.ru/57473539](http://rghost.ru/57473539)

```
GuacToolPS360 -r arc_name

```
## Post #19
- Username: gula
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 14, 2014 8:17 pm
- Post datetime: 2014-08-15T13:05:43+00:00
- Post Title: Re: Guacamelee! Super Turbo Championship Edition (.dat) Xbox

> Reply from Thief1987
>
> Try this - http://rghost.ru/57473539
Code: Select allGuacToolPS360 -u arc_name
GuacToolPS360 -r arc_name

Its work,thank you very much m8!
## Post #20
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-08-17T01:40:09+00:00
- Post Title: Re: Guacamelee! Super Turbo Championship Edition (.dat) Xbox

Found bug in program, updated.
[http://rghost.ru/57509519](http://rghost.ru/57509519)
## Post #21
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2014-08-19T21:48:07+00:00
- Post Title: Re: Guacamelee! Super Turbo Championship Edition (.dat) Xbox

> Reply from Thief1987
>
> Found bug in program, updated.
http://rghost.ru/57509519
Спасибо. Смотрю, ты на плойку сделал, а мы на бокс все никак не можем. Теперь уже сделаем точно  pipindor666
## Post #22
- Username: rballad
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 11, 2014 9:40 am
- Post datetime: 2014-11-07T13:59:41+00:00
- Post Title: Re: Guacamelee! Super Turbo Championship Edition (.dat) Xbox

> Reply from Thief1987
>
> Found bug in program, updated.
http://rghost.ru/57509519

Hello, can anyone reupload the file?
## Post #23
- Username: ToTheMadness
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 05, 2019 2:49 am
- Post datetime: 2019-09-10T17:37:55+00:00
- Post Title: Re: Guacamelee! Super Turbo Championship Edition (.dat) Xbox

> Reply from Thief1987 ↑Sun Aug 17, 2014 9:40 am at Sun Aug 17, 2014 9:40 am
>
> 
Found bug in program, updated.
http://rghost.ru/57509519
Does anybody have this file?
