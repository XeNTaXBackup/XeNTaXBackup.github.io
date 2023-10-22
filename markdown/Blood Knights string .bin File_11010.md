## Post #1
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-01T13:13:02+00:00
- Post Title: Blood Knights string .bin File

How To Edit Blood Knights string .bin File?
[english.zip](https://xentaxbackup.github.io/file/6814_english.zip)
## Post #2
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-03T14:47:18+00:00
- Post Title: Blood Knights string .bin File

> Reply from reznov
>
> How To Edit Blood Knights string .bin File?

Can anyone take a look at this files.
## Post #3
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-12-05T09:29:15+00:00
- Post Title: Blood Knights string .bin File

The game has some kind of file validation, so editing is not possible until someone find out what hash is it.
## Post #4
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-12-07T22:04:48+00:00
- Post Title: Blood Knights string .bin File

I search the game folder for keyword "hash", and found this in FledgeCore.dll: DJB2Hash, SDBMHash.
Does anyone know what are these things?
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-10T12:45:42+00:00
- Post Title: Blood Knights string .bin File

This 2 functions used for strings.

```
{
    unsigned long pHash = 5381;
    int pChar;

    while (pChar = *pString++)
        pHash = ((pHash << 5) + pHash) + pChar;
    return pHash;
}

unsigned long SDBMHash(unsigned char *pString)
{
    unsigned long pHash = 0;
    int pChar;

    while (pChar = *pString++)
        pHash = pChar + (pHash << 6) + (pHash << 16) - pHash;
    return pHash;
}
```


Well i disable hash validation. Here [results](http://oi44.tinypic.com/2nuirv4.jpg). In attach link for download. Enjoy.
[DL_Link.rar](https://xentaxbackup.github.io/file/6829_DL_Link.rar)
## Post #6
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-11T03:06:55+00:00
- Post Title: Blood Knights string .bin File

Perfect!
Thanks Ekey.
## Post #7
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-12-18T20:26:34+00:00
- Post Title: Blood Knights string .bin File

Here is a tool to edit bin file: [https://www.sendspace.com/file/xpdpvz](https://www.sendspace.com/file/xpdpvz)
And don't forget to use Ekey's patch.
## Post #8
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2013-12-19T17:00:13+00:00
- Post Title: Blood Knights string .bin File

Thanks!
It was a big help.
## Post #9
- Username: McGregor II
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jun 29, 2010 8:21 am
- Post datetime: 2014-01-22T21:34:19+00:00
- Post Title: Blood Knights string .bin File

Any way to edit font.bin file, or how can I add polish signs in font? Link below is to the font.bin and other font files (including textures) in case it will be helpful.

[http://www.sendspace.com/file/93p728](http://www.sendspace.com/file/93p728)

EDIT: Hey guys! I manage to edit font.bin file thanks to my fellow friend Brucie! He wrote a template for 010 Editor with which you can edit this file. Remember: do not insert new character (!), replace an already existing one. You can add new character on the texture but you can't add new one in file, replace some other unused character and use X and Y pixels address from the texture file.
[bloodknights_fonts.bin.rar](https://xentaxbackup.github.io/file/7000_bloodknights_fonts.bin.rar)
## Post #10
- Username: GamerEdu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 15, 2014 4:17 am
- Post datetime: 2014-08-14T20:37:32+00:00
- Post Title: Blood Knights string .bin File

Sorry my english. Could someone get me the tools to extract the file string.bin? The links are off! I would love to translate this game. Thank you very much!
## Post #11
- Username: PetkaBY
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 6:49 pm
- Post datetime: 2018-04-08T20:58:47+00:00
- Post Title: Blood Knights string .bin File

> Reply from Ekey
>
> This 2 functions used for strings.
Code: Select allunsigned long DJB2Hash(unsigned char *pString)
{
    unsigned long pHash = 5381;
    int pChar;

    while (pChar = *pString++)
        pHash = ((pHash << 5) + pHash) + pChar;
    return pHash;
}

unsigned long SDBMHash(unsigned char *pString)
{
    unsigned long pHash = 0;
    int pChar;

    while (pChar = *pString++)
        pHash = pChar + (pHash << 6) + (pHash << 16) - pHash;
    return pHash;
}

Well i disable hash validation. Here results. In attach link for download. Enjoy.

Any have this patch and tool ? Update pleas 
sorry for english if so.
## Post #12
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2018-04-09T07:15:24+00:00
- Post Title: Blood Knights string .bin File

@PetkaBY
Try this tool [https://www33.zippyshare.com/v/StU3r9ws/file.html](https://www33.zippyshare.com/v/StU3r9ws/file.html)
## Post #13
- Username: PetkaBY
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 6:49 pm
- Post datetime: 2018-04-09T08:52:59+00:00
- Post Title: Blood Knights string .bin File

> Reply from makcar
>
> @PetkaBY
Try this tool https://www33.zippyshare.com/v/StU3r9ws/file.html

Sanks. Anything by decision with Hash, Ekey remove it, but link dead.

Import text not working( create the same file with NEW_ prifix.
