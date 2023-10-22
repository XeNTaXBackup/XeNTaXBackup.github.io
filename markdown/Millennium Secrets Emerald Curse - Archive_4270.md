## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-03-27T11:53:21+00:00
- Post Title: Millennium Secrets: Emerald Curse - Archive

I'll appreciate any help or guidance to unpack the "resource.dat"-archive from "Millennium Secrets - Emerald Curse". 
The head.bin and tail.bin may be downloaded here: [http://www.motionpress.com/uploads/Mill ... _Curse.rar](http://www.motionpress.com/uploads/Millennium_Secrets_Emerald_Curse.rar)

Thanks in advance!
## Post #2
- Username: ubrax
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-28T19:40:52+00:00
- Post Title: Millennium Secrets: Emerald Curse - Archive

```
Get FN Long 0 ;
Get ASize Long 0 ;
SavePos S 0 ;
For T = 1 To FN ;
Get COMS Long 0 ;
Get UNCOMS Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get FNS Long 0 ;
GetDString Name FNS 0 ;
SavePos S2 0 ;
Get FNS2 Long 0 ;
If FNS2 > 0 ;
GetDString Path FNS2 0 ;
EndIf;
Next T ;
SavePos SOFF 0 ;
GoTo S 0 ;
For T = 1 To FN ;
Get COMS Long 0 ;
Get UNCOMS Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get FNS Long 0 ;
GetDString Name FNS 0 ;
SavePos S2 0 ;
Get FNS2 Long 0 ;
Set Path String "" ;
If FNS2 > 0 ;
Get B Byte 0 ;
Math FNS2 -= 1 ;
GetDString Path FNS2 0 ;
EndIf;
String Path += Name ;
Log Path SOFF COMS 0 0 ;
Math SOFF += COMS ;
Math SOFF += 4 ;
Next T ;

```


Use that script in MultiEx Commander to extract the stuff. 

Here's the BMS file:


 dat.7z
(343 Bytes) Downloaded 35 times

 (unpack with 7zip)

Here's an example of a file in the resource.dat:
[pers16_badguy1.jpg](https://xentaxbackup.github.io/file/2894_pers16_badguy1.jpg)
## Post #3
- Username: felixthekat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 15, 2011 11:20 pm
- Post datetime: 2011-02-06T17:18:12+00:00
- Post Title: Millennium Secrets: Emerald Curse - Archive

Good morning!
I wanted to use this script, with another game, is IDString  "wazzzzaup!" ; but I get the error you see in the screenshot.
Why is this happening?

[Resource.dat Megaupload](http://www.megaupload.com/?d=1V7FKTG8)


[1.jpg](https://xentaxbackup.github.io/file/3878_1.jpg)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-02-06T18:19:59+00:00
- Post Title: Millennium Secrets: Emerald Curse - Archive

Probably because one of the resources it wishes to extract is bigger than possible based on the location of the resource in the archive and the total size of the archive. That would suggest the script cannot be used as is, but must be adapted.
## Post #5
- Username: felixthekat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 15, 2011 11:20 pm
- Post datetime: 2011-02-06T19:08:37+00:00
- Post Title: Millennium Secrets: Emerald Curse - Archive

Ho hu. I am very noob as for adapted the script.
Yesterday, I recently made my first script, very basic, to extract the files, the game "Columbus - Ghost of the Mystery Stone" with some tutorials I found, here in the forum.

```
HEADERSZ get long
get long FILES
SKIP get long
for i = 0 <FILES
get short nSize
NAME getdstring nSize
         get long SIZE
OFFSET get long
log SIZE OFFSET NAME
next i
```


It is very complicated, tutorials in English and my English is very bad (google translate)
Thanks for responding
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-02-06T21:41:28+00:00
- Post Title: Millennium Secrets: Emerald Curse - Archive

```
ComType ZLib1 ;
Get FN Long 0 ;
Get ASize Long 0 ;
SavePos S 0 ;
For T = 1 To FN ;
Get UNCOMS Long 0 ;
Get COMS Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get FNS Long 0 ;
GetDString Name FNS 0 ;
SavePos S2 0 ;
Get FNS2 Long 0 ;
If FNS2 > 0 ;
GetDString Path FNS2 0 ;
EndIf;
Next T ;
SavePos SOFF 0 ;
GoTo S 0 ;
For T = 1 To FN ;
Get UNCOMS Long 0 ;
Get COMS Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get FNS Long 0 ;
GetDString Name FNS 0 ;
SavePos S2 0 ;
Get FNS2 Long 0 ;
Set Path String "" ;
If FNS2 > 0 ;
Get B Byte 0 ;
Math FNS2 -= 1 ;
GetDString Path FNS2 0 ;
EndIf;
String Path += Name ;
CLog Path SOFF COMS 0 0 UNCOMS 0;
Math SOFF += COMS ;
Math SOFF += 4 ;
Next T ;

```


There you go, that should extract each compressed file and decompress it. 
Save it as a .txt file and then use it as a MexScript.



menu00_menu_bk_02.jpg (799.13 KiB) Viewed 60 times
