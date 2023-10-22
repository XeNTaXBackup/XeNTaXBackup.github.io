## Post #1
- Username: FantasyHeroBoy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Dec 11, 2012 4:15 am
- Post datetime: 2013-02-08T00:09:33+00:00
- Post Title: Rift: Storm Legion (Asset Files)

Greetings, one and all! I would like to know if there is a program that can extract music from Asset Files? Any help would be appreciated. Inon Zur music is just to good to miss out on.  While I was DL-Ing this game, I saw in the "New" folder a "Audio.PAK" file. After it was done installing the Game, all I see is Asset.001, Asset.002, Asset.003, etc, etc. So, I just assume that the Audio PAK file is packed in the Asset files.  Much would be appreciated if someone could give me an answer!!! xD
## Post #2
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-08T13:05:03+00:00
- Post Title: Rift: Storm Legion (Asset Files)

you can use this bms script after that's you must revorb them but only one by one so you must use one bat script 
so i will try and say more after 

```
#  
# Written by Ekey (h4x0r) 
# http://www.progamercity.net 
#  
# script for QuickBMS http://quickbms.aluigi.org 

comtype unzip_dynamic 

idstring "TWAD" 
get VERSION long
get DUMMY long
get DUMMY long
get FILES long

for i = 0 < FILES 
  get ID1 long # Pointer for Manifest ?
  get ID2 long # Pointer for Manifest ?
  get OFFSET long 
  get SIZE long 
  get SIZED long 
  get DUMMY long 
  getdstring SHA1 0x14 
  string NAME p= "%08X%08X" ID1 ID2 
  clog NAME OFFSET SIZE SIZE 
next iE OFFSET SIZE SIZE 
next i
```
## Post #3
- Username: FantasyHeroBoy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Dec 11, 2012 4:15 am
- Post datetime: 2013-02-08T23:23:43+00:00
- Post Title: Rift: Storm Legion (Asset Files)

Ok, Kilik, I've used the script and it worked just fine. I have over 1,000 files that have the extension "File". Can you please tell me how to get these files in WAV or OGG format? Also, what do you mean by "Revorb"?
## Post #4
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-08T23:39:42+00:00
- Post Title: Rift: Storm Legion (Asset Files)

same here i have use EkszBox-ABX for extract only wav 
and here [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html) you found
ww2ogg try drag and drop in this bat script

```
:getfile
if "%~1"=="" goto end
ww2ogg.exe "%~1"
shift
goto getfile
:end
```

pause

after use this one for read ogg 

```
for %%i In (*.ogg) do "%CD%/revorb.exe" %%i
```


note: you can only drag and drop by 100 or little more because path bat look to long 
and 50% can be convert only
## Post #5
- Username: FantasyHeroBoy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Dec 11, 2012 4:15 am
- Post datetime: 2013-02-10T22:28:16+00:00
- Post Title: Rift: Storm Legion (Asset Files)

Hmm? This is weird. When I try to convert the File, it just says "Invalid Command "CD" or arguments 1 at line 1 ". Am I doing something wrong, Kilik? If so, please inform me, Ok?
## Post #6
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-10T23:51:18+00:00
- Post Title: Rift: Storm Legion (Asset Files)

you have try manuely without the bat for see if this work's on one file already
## Post #7
- Username: FantasyHeroBoy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Dec 11, 2012 4:15 am
- Post datetime: 2013-02-22T17:09:23+00:00
- Post Title: Rift: Storm Legion (Asset Files)

Sorry about the loong wait.  I've tried it and no luck. :/

If you want to try yourself, here are some of the game's files.

Good Luck, Kilik! 

[http://speedy.sh/bdW9H/Rift-Storm-Legion-Files.rar](http://speedy.sh/bdW9H/Rift-Storm-Legion-Files.rar)
## Post #8
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-02-23T05:39:57+00:00
- Post Title: Rift: Storm Legion (Asset Files)

Like other thread upload...this is 13kb being rather seemingly improper upload given 2nd case...
## Post #9
- Username: plechito
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jul 06, 2012 2:51 pm
- Post datetime: 2017-10-03T13:16:44+00:00
- Post Title: Rift: Storm Legion (Asset Files)

Hi, i think it doesnt work for new versions anymore.. Is there any chance to make updated script?   
Thank you so much for answer!
