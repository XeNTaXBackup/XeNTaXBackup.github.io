## Post #1
- Username: InKviZ
- Rank: advanced
- Number of posts: 51
- Joined date: Mon Sep 29, 2014 12:57 am
- Post datetime: 2017-04-09T07:45:05+00:00
- Post Title: RAGE (localization)

Hello. Who can help with the localization of the game RAGE. As I understand, the text is in the file gameresources_sp_01.patch. Hi. Who can help with export and import text.
[http://dropmefiles.com/pTvDb](http://dropmefiles.com/pTvDb)
## Post #2
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-04-29T11:41:13+00:00
- Post Title: RAGE (localization)

> Reply from InKviZ
>
> Hello. Who can help with the localization of the game RAGE. As I understand, the text is in the file gameresources_sp_01.patch. Hi. Who can help with export and import text.
http://dropmefiles.com/pTvDb
I can not download your file, please review the link
## Post #3
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2017-05-22T01:49:38+00:00
- Post Title: RAGE (localization)

Use a hex editor to dump the text like the attacked one or use quickbms for this, with the script below:

```
set offset 93436636            #this is the biggest files offset
set size 261355                #and size
log name offset size
```

Using the hex editor for insert, you need overwrite the original text file block with the translated text file. Or use the quickbms for that.
PS1: The translated text need to be the same size of the original or smaller. In hex editor process, you need fill the original file size with null, using the quickbms, this will be done automatically.
PS2: The offset and size values on bms script are an example, I don't know the values for that game files, you need discovery this by yourself, it's easy using the hex editor.

Edit: I downloaded the file from [this post](http://forum.xentax.com/viewtopic.php?f=35&t=16252) and the below bms script works fine:

```
set offset 19851475
set size 704311
log name offset size
```

[english.7z](https://xentaxbackup.github.io/file/12929_english.7z)
