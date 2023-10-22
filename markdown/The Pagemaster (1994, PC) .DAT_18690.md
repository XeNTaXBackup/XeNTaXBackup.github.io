## Post #1
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-08-16T19:39:21+00:00
- Post Title: The Pagemaster (1994, PC) .DAT

Anybody know how to open and extract the files from these?: [https://drive.google.com/open?id=1DmS8F ... YLUMSMuzLN](https://drive.google.com/open?id=1DmS8F_OJpPaskuBIvGze-JYLUMSMuzLN)
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-08-17T19:08:57+00:00
- Post Title: The Pagemaster (1994, PC) .DAT

This segment of QuickBMS code can dump your files:

```
	getdstring NAME 0x10
	get SIZE long
	get OFFSET long
	get ADVANCE byte
	goto -1 0 SEEK_CUR
	log NAME OFFSET SIZE
 while ADVANCE != 0

```


Copy and paste this into a text file and run it on the archive with QuickBMS.

Since there was no associated entry count, I just checked if the next supposed byte (Which would be the start of the name) was 0. That means it would be done. If you have issues with other archives just upload them here.
