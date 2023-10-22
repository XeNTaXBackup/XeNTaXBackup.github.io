## Post #1
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-06-11T14:07:57+00:00
- Post Title: bms script for game

Hi, i want to learn write basic bms script for reading a file to a txt file and after edited txt i want to  convert txt to old file format. I mean size can change after edition and they will have to change accordingly following size of String
File format is as following 
RED are size of following BLUE Strings    and  GREEN 00 are seperators  
0A0000004E494E493030314D490028000000596F7527726520696E2C204461726C696E672120596F7527726520696E20686572206D696E642100
0A0000004E494E493030324D49001A00000054656C6C206D652C207768617420646F20796F75207365653F00
thanks for help. I added sample as attachment
[NI_001en.rar](https://xentaxbackup.github.io/file/4319_NI_001en.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-11T18:16:22+00:00
- Post Title: bms script for game

quickbms is not for translations (for the moment?) so a bms script for it would be totally useless.
anyway that thing in bms is:

```
    get TEXTSZ long
    getdstring TEXT TEXTSZ
    print "%TEXT%"
next
```

remember that with a hex editor you can edit that file and the size doesn't matter if your new string is equal or shorter than the original.
for example if you replace "NINI001MI" with "hello" you must only place a 0x00 byte after the 'o' of "hello" for delimiting it and nothing else
## Post #3
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-06-11T19:20:30+00:00
- Post Title: bms script for game

but, there is problem for that 
596F7527726520696E2C204461726C696E672120596F7527726520696E20686572206D696E6421 if i changed this, 
I should change size of this: 28000000  I mean its hard to do it manually for it. 
So, first reading this file to a txt then  I edit it , then bms script will convert to orginal file. But, it should correct this 28000000  accordinly.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-11T21:48:51+00:00
- Post Title: bms script for game

I repeat, this is not a job for a bms script and if your string is equal/shorter than the original you don't need to change the size value
## Post #5
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-06-11T22:41:11+00:00
- Post Title: bms script for game

thanks for your concern. 
I wrote a code in java. and It works great.
But, I need help to edit font files. They are not dff files that are like GTAs files. 
I added tahoma_lin.dff file.
[Tahoma_lin.rar](https://xentaxbackup.github.io/file/4322_Tahoma_lin.rar)
