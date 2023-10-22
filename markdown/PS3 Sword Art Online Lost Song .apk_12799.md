## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-04-26T05:32:19+00:00
- Post Title: PS3 Sword Art Online Lost Song *.apk

Hi, can someone help me to unpack *.apk files? There are 6 apk files in USRDIR\data folder.


It seems that pack.idx contains information of 6 apk files.


Most of *.apk files structure are not different from others, except data_rom.apk file.


data_rom.apk files PACKFSLS signature starts at 88A80h


All other *.apk file's PACKFSLS signature starts at 90h.

[sample 1.rar](https://xentaxbackup.github.io/file/9108_sample 1.rar)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-04-28T04:42:06+00:00
- Post Title: PS3 Sword Art Online Lost Song *.apk

[https://www.youtube.com/watch?v=GsfAn_S ... e=youtu.be](https://www.youtube.com/watch?v=GsfAn_SRXNc&feature=youtu.be)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-04-28T20:28:55+00:00
- Post Title: PS3 Sword Art Online Lost Song *.apk

Here's first crude script for MultiEx Commander or QuickBMS: 
It doesn't sort the filenames correct yet. 

```
IDString 0 "ENDILTLE" ;
Get D Long 0 ;
Get D Long 0 ;
GetDString PH 8 0 ;
# PACKHEDR
Get SSize Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get DataOffset Long 0 ;
SavePos P 0 ;
Math P += 20 ;
GoTo P 0 ;
GetDString PTOC 8 0 ;
# PACKTOC
Get SSize Long 0 ;
Get D Long 0 ;
SavePos P 0 ;
Math P += SSize ;
GoTo P 0 ;
GetDString FSLS 8 0 ;
# PACKFSLS
Get SSize Long 0 ;
Get D Long 0 ;
SavePos JuE 0 ;
Get FileNum Long 0 ;
Get EntrySize Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Set GENEST Long SSize ;
Math GENEST += JuE ;
SavePos P 0 ;
GoTo GENEST 0 ;
GetDString GENS 8 0 ;
# PACKFSLS
Get SSize Long 0 ;
Get D Long 0 ;
SavePos JuS 0 ;
Get SNum Long 0 ;
Math SNum *= 4 ;
Get D Long 0 ;
Get StOff Long 0 ;
Math JuS += StOff ;
Math GENEST += 32 ;
GoTo JuS 0 ;
Get PackName String 0 ;
String PackName += "/" ;
Math GENEST += 8 ;
GoTo P 0 ;
For T = 1 To FileNum ;
Get FID Long 0 ;
Get D Long 0 ;
Get Offset Long 0; 
Get D Long 0 ;
Get Size Long 0 ;
Get D Long 0 ;
SavePos P 0 ;
Math P += 16 ;
GoTo GENEST 0 ;
Math GENEST += 4 ;
Get SPOS Long 0 ;
Math SPOS += JuS ;
GoTo SPOS 0 ;
Get FileName String 0 ;
Set FN String "exc/" ;
String FN += FileName ;
Log FN Offset Size 0 0 ;
GoTo P 0 ;
Next T ;

```
## Post #4
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-04-29T01:52:50+00:00
- Post Title: PS3 Sword Art Online Lost Song *.apk

> Reply from Mr.Mouse
>
> Here's first crude script for MultiEx Commander or QuickBMS: 
It doesn't sort the filenames correct yet. 
Code: Select all#Sword Art Online .APK
IDString 0 "ENDILTLE" ;
Get D Long 0 ;
Get D Long 0 ;
GetDString PH 8 0 ;
# PACKHEDR
Get SSize Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get DataOffset Long 0 ;
SavePos P 0 ;
Math P += 20 ;
GoTo P 0 ;
GetDString PTOC 8 0 ;
# PACKTOC
Get SSize Long 0 ;
Get D Long 0 ;
SavePos P 0 ;
Math P += SSize ;
GoTo P 0 ;
GetDString FSLS 8 0 ;
# PACKFSLS
Get SSize Long 0 ;
Get D Long 0 ;
SavePos JuE 0 ;
Get FileNum Long 0 ;
Get EntrySize Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Set GENEST Long SSize ;
Math GENEST += JuE ;
SavePos P 0 ;
GoTo GENEST 0 ;
GetDString GENS 8 0 ;
# PACKFSLS
Get SSize Long 0 ;
Get D Long 0 ;
SavePos JuS 0 ;
Get SNum Long 0 ;
Math SNum *= 4 ;
Get D Long 0 ;
Get StOff Long 0 ;
Math JuS += StOff ;
Math GENEST += 32 ;
GoTo JuS 0 ;
Get PackName String 0 ;
String PackName += "/" ;
Math GENEST += 8 ;
GoTo P 0 ;
For T = 1 To FileNum ;
Get FID Long 0 ;
Get D Long 0 ;
Get Offset Long 0; 
Get D Long 0 ;
Get Size Long 0 ;
Get D Long 0 ;
SavePos P 0 ;
Math P += 16 ;
GoTo GENEST 0 ;
Math GENEST += 4 ;
Get SPOS Long 0 ;
Math SPOS += JuS ;
GoTo SPOS 0 ;
Get FileName String 0 ;
Set FN String "exc/" ;
String FN += FileName ;
Log FN Offset Size 0 0 ;
GoTo P 0 ;
Next T ;

Thanks for your effort! In my opinion, pack.idx contains important information. (Sample 1.rar contains character.apk, mission.apk, pack.idx)
There are ID Number and header information of each *.apk files.
ID = 00 00 00 00 means character.apk file.
ID = 01 00 00 00 means data.apk file.. and so on.

However, ID number value [0x24 or 24h] is null in each *.apk files.

character.apk


data.apk


data_rom.apk


Especially, pack.idx also contains PACKTOC information of data_rom.apk file.
 

It seems that pack.idx contains file names. And I think *.apk files contains dir names.


So, it is necessary to use FDDE option for unpacking *.apk files.

```
if EXTENSION != idx
    open FDDE idx 0
endif
open FDDE apk 1
```


p.s.1 Total size of data_rom.apk is too big [911MB] so, I attach Header section of data_rom.rar.
And, in the data_rom.apk file there are only one ENDILTLE, PACKHEDR, PACKTOC, PACKFSLS, GENESTRT, GENEEOF.
It is different from other *.apk files. However, other files, such as character.apk, mission.apk, data.apk, motion.apk, unit.apk has same structure.

p.s.2. There are also interesting different values. PACKTOC part of pack.idx and data_rom.apk file.


[Header section of data_rom.rar](https://xentaxbackup.github.io/file/9119_Header section of data_rom.rar)
## Post #5
- Username: bsod83
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 12, 2015 4:51 am
- Post datetime: 2015-08-11T21:56:38+00:00
- Post Title: PS3 Sword Art Online Lost Song *.apk

this is my first post here. cheers!
was wondering if anybody had got this translated into english? i have the japanese version and i see that it has all the english files already in it. ive been working on this for a while now.
thanks!
## Post #6
- Username: demmairo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 07, 2021 12:07 am
- Post datetime: 2021-12-06T16:23:48+00:00
- Post Title: PS3 Sword Art Online Lost Song *.apk

Good evening friends. Tell me how you can change the font and get the text of the missions and dialogues for translation into another language?
I would really like to at least translate the text
