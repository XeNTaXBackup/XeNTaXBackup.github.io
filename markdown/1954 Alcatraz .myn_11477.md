## Post #1
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2014-05-02T10:28:37+00:00
- Post Title: 1954: Alcatraz .myn

Hi, guys.

Do you know how to extract English.myn file? There is a text in it but I've never seen .myn file before.
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-05-14T12:45:35+00:00
- Post Title: 1954: Alcatraz .myn

Use this script on the myn file, then rename or delete it.

```
get SIZE asize
get NAME basename
string NAME += .csv
log NAME 0 SIZE
```
## Post #3
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2014-08-29T18:57:01+00:00
- Post Title: 1954: Alcatraz .myn

Thank you.
But could you describe me how can I use it on .myn file? By using quickbms? I'm not good in it.
## Post #4
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-08-29T23:45:20+00:00
- Post Title: 1954: Alcatraz .myn

> Reply from Saturno
>
> But could you describe me how can I use it on .myn file? By using quickbms? I'm not good in it.
[.myn files_Unpack_Pack_(script+bat).rar](https://xentaxbackup.github.io/file/7759_.myn files_Unpack_Pack_(script+bat).rar)
## Post #5
- Username: Saturno
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Apr 26, 2011 6:34 pm
- Post datetime: 2014-08-31T11:40:04+00:00
- Post Title: 1954: Alcatraz .myn

Thank you, guys. I solved my problem . You're both great.
Cheers.
## Post #6
- Username: leoxama
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 24, 2021 3:38 am
- Post datetime: 2021-06-24T09:06:59+00:00
- Post Title: 1954: Alcatraz .myn

Thank you for the script, it was really helpful. However, even if I can decrypt the .myn file and generate the .csv, when I perform any change on the .csv file, the corresponding save (.myn) would be invalid because of the key written at the end of the xml file which, apparently, is a half-byte repeated N times. I suppose the key is generated from the xml file but I do not know which encryption has been used, does anyone knows how to generate the key from the xml file and/or the encryption that has been used?
