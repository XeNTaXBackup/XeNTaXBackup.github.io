## Post #1
- Username: spartanmark6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 28, 2016 9:11 am
- Post datetime: 2016-05-28T01:33:05+00:00
- Post Title: Tekken 4 PS2 Models

Hello, I am a little new here, and I have a question. I was wondering how I can rip the models from Tekken 4 on the Playstation 2. Since I recently saw someone rip the the models from Tekken Tag HD, I was curious if somebody has been successful in ripping all of the models. Now, I have tried a couple methods on extracting these and have not accomplished anything significant. I used Ninja ripper and that didn't work, and I tried this QuickBMS script, and the models came out screwed up. I would like to know if someone has already ripped these or if they can show me how to. 
Thanks,
spartanmark6

Sources:
Tekken 4 Quick BMS script: [http://ps23dformat.wikispaces.com/Tekken+4](http://ps23dformat.wikispaces.com/Tekken+4)
## Post #2
- Username: fast
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 07, 2016 1:58 am
- Post datetime: 2016-05-29T20:26:54+00:00
- Post Title: Tekken 4 PS2 Models

‎
## Post #3
- Username: spartanmark6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 28, 2016 9:11 am
- Post datetime: 2016-05-30T00:11:52+00:00
- Post Title: Tekken 4 PS2 Models

How did you get the texture files? I didn't get those when attempting to rip Yoshimitsu. When I ripped him, he didn't turn out too well.

Also, this is what it looks like to me when I ripped it: 



Am I doing something wrong?

Here is what I got when I tried to rip Christie:
## Post #4
- Username: fast
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 07, 2016 1:58 am
- Post datetime: 2016-05-30T08:01:44+00:00
- Post Title: Tekken 4 PS2 Models

‎‎‎‎
## Post #5
- Username: spartanmark6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 28, 2016 9:11 am
- Post datetime: 2016-05-30T15:29:06+00:00
- Post Title: Tekken 4 PS2 Models

Oh okay. I would really like to figure this out eventually.
## Post #6
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2019-12-28T20:44:53+00:00
- Post Title: Tekken 4 PS2 Models

USE TYHE SCRIPT ON THE SAVEDATA CAUSE THE QUICK SAVE WILL HAVE THE mODEL SAVED IN THERE AS WELL
## Post #7
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2019-12-29T12:04:04+00:00
- Post Title: Tekken 4 PS2 Models

Still hope to see released Tekken 4/5 models...
## Post #8
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2019-12-29T16:18:47+00:00
- Post Title: Tekken 4 PS2 Models

i have the script for tekken 5 here.
open note pad and paste this code in it and save it with whatever name
#Tekken5 

get FSIZE asize
set COUNT_G long 1
set COUNT_T long 1
set NAME string ""
SavePos POS 0
Do
   get DATA long 0
   If DATA == 0x00745865
      goto 0x0C 0 SEEK_CUR
      get DATA long 0
      If DATA == 0x58444947
         goto -0x44 0 SEEK_CUR
         SavePos OFFSET 0
         get SIZE long
         goto OFFSET 0 SEEK_SET
         goto SIZE 0 SEEK_CUR
         string NAME p= "%08d" COUNT_T
         string NAME += ".tm2"
         math COUNT_T += 1
         set MEMORY_FILE binary "\x54\x49\x4D\x32\x04\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00"
         append
            log MEMORY_FILE OFFSET SIZE 0
         append
         get SIZE asize MEMORY_FILE
         log NAME 0 SIZE MEMORY_FILE
      endif
   elif DATA == 0x5044554E
      goto 0x04 0 SEEK_CUR
      get DATA byte 0
      if DATA == 0x03
         goto 0x05 0 SEEK_CUR
         get DATA short 0
         if DATA == 0x00
            goto -0x0C 0 SEEK_CUR
            get SIZE long 0
            goto -0x08 0 SEEK_CUR
            SavePos OFFSET 0
            goto SIZE 0 SEEK_CUR
            string NAME p= "%08d" COUNT_G
            string NAME += ".nud"
            math COUNT_G += 1
            log NAME OFFSET SIZE 0
         else
            goto -0x02 0 SEEK_CUR
         endif
      else
         goto -0x05 0 SEEK_CUR
      endif
   Endif
   SavePos POS 0
While POS < FSIZE

IMPORTANT: first go to customization and choose your character.......Then use F1 to save your current status........go to your pcsx folder which has the memcard folder..........NOW this pcsx folder will also have sstates folder......go to it.....now whichever slot you saved your game status with your character in customization......copy it...............download quick bms.........paste it there and also this script from notepad.......Now download 7-zip..... use it to extract the savew state..........The rest is easy......click the quick bms launcher and choose the script,....then choose this eememory (its one of the files after you have extracted the sstate),..then tell quickbms which folder to put in.Download noesis to view your models.but all your customiztion elements will be in one model.thats the ONLY problem....remove them with an editor

NOW for textures use this script...........use noesis to view them 

log MEMORY_FILE 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE4 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;
log MEMORY_FILE7 0 0 ;
log MEMORY_FILE8 0 0 ;
log MEMORY_FILE9 0 0 ;
log MEMORY_FILE10 0 0 ;
Get Q ASIZE 0 ;
Math number = 0 ;
For T = 0 < Q ;
Math number += 1 ;
findloc OFFSET string "\x4E\x55\x44\x50" 0 0 ;
If OFFSET = 0 ;
Math test = 0 ;
Math T = Q ;
Math T += 1 ;
Math ttest = 0 ;
ELSE ;
GoTo OFFSET 0 ;
SavePos Start 0 ;
GoTo 0x08 0 SEEK_CUR ;
Get test Byte 0 ;
SavePos null 0 ;
EndIF ;
If OFFSET != 0 ;
If test = 3 ;
Put Start Long MEMORY_FILE4 ;
EndIF ;
EndIF ;
Next T ;
Put Q Long MEMORY_FILE4 ;


Get listf ASIZE MEMORY_FILE4 ;
Math spyrodragon = listf ;
Math spyrodragon /= 4 ;
Math spyrodragon -= 1 ;
Math rubyfox = 0 ;
Math diafox = 0 ;
Math rfv = 0 ;
For Y = 1 To spyrodragon ;
log MEMORY_FILE7 0 0 ;
log MEMORY_FILE8 0 0 ;
log MEMORY_FILE1 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
GoTo rubyfox MEMORY_FILE4 ;
Get start Long MEMORY_FILE4 ;
SavePos rubyfox MEMORY_FILE4 ;
Get size Long MEMORY_FILE4 ;
Math size -= start ;
Log MEMORY_FILE7 start size 0 ;
GoTo 0 MEMORY_FILE7 ;
Math count = 0 ;
Math gt = 0 ;
Math Qprime = 0 ;
Math red = 0 ;
SavePos found MEMORY_FILE7 ;
For T = 0 < size ;
GoTo found MEMORY_FILE7 ;
findloc OFFSETT string "\x00\x00\x00\x20\x80\x00\x00\x00\x01\x80" MEMORY_FILE7 0 ;
If OFFSETT = 0 ;
Math T = size ;
Math twotest = 1 ;
EndIF ;
If OFFSETT != 0 ;
GoTo OFFSETT MEMORY_FILE7 ;
GoTo 10 MEMORY_FILE7 SEEK_CUR ;
Get onetest Byte MEMORY_FILE7 ;
Get twotest Byte MEMORY_FILE7 ;
SavePos found MEMORY_FILE7 ;
EndIF ;
If twotest = 120 ;
Put count Long MEMORY_FILE1 ;
Math count += onetest ;
Math foxcount = count ;
Math foxcount -= 1 ;
Put foxcount Long MEMORY_FILE1 ;
Put onetest Long MEMORY_FILE1 ;
Put found Long MEMORY_FILE1 ;
EndIF ;
Next T ;

Get mqa ASIZE MEMORY_FILE1 ;
Math mqa /= 16 ;
For jjj = 1 To mqa ;
GoTo gt MEMORY_FILE1 ;
Get min long MEMORY_FILE1 ;
Get max long MEMORY_FILE1 ;
Get nuv long MEMORY_FILE1 ;
Get loc long MEMORY_FILE1 ;
SavePos gt MEMORY_FILE1 ;
Math hhhggg = max ;
Math hhhggg -= 2 ;
GoTo loc MEMORY_FILE7 ;
SavePos werefox MEMORY_FILE7 ;
For cvb = 1 To nuv ;
GoTo werefox MEMORY_FILE7 ;
Get Type1 Long MEMORY_FILE7 ;
Get Type2 Long MEMORY_FILE7 ;
Get Type3 Long MEMORY_FILE7 ;
SavePos werefox MEMORY_FILE7 ;
GoTo Qprime MEMORY_FILE2 ;
Put Type1 Long MEMORY_FILE2 ;
Put Type2 Long MEMORY_FILE2 ;
Put Type3 Long MEMORY_FILE2 ;
SavePos Qprime MEMORY_FILE2 ;
Next cvb ;
Math max -= 2 ;

For fff = min To max ;

Math fafter = fff ;
Math fafter += 1 ;
Math fafterafter = fff ;
Math fafterafter += 2 ;
Math fafterafterafter = fff ;
Math fafterafterafter += 3 ;
GoTo red MEMORY_FILE3 ;
Put fff Short MEMORY_FILE3 ;
Put fafter Short MEMORY_FILE3 ;
Put fafterafter Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
Put fff Short MEMORY_FILE3 ;
Put fafterafter Short MEMORY_FILE3 ;
Put fafter Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos red MEMORY_FILE3 ;
Next fff ;





Next jjj ;






Get Zw3 ASIZE MEMORY_FILE3 ;
Math Zf3 = Zw3 ;
Math Zf3 /= 8 ;
Get Zw2 ASIZE MEMORY_FILE2 ;
Math Zf2 = Zw2 ;
Math Zf2 /= 12 ;
Math FaceNumber = Zf3 ;
Math VertexNumber = Zf2 ;
Math Snake = VertexNumber ;
Math Snake *= 12 ;
Math Dragon = FaceNumber ;
Math Dragon *= 8 ;
Math Sum = Dragon ;
Math Sum += Snake ;
Math QQQ = 60 ;
Math QQQ += Snake ;
Math QQ = 52 ;
Math qaz = 0 ;
Math wsx = 0 ;
Math hqw = Sum ;
Math hqw += 60 ;
Log MEMORY_FILE8 0 hqw ;
For Vertex = 0 < Zw2 ;
GoTo qaz MEMORY_FILE2 ;
Get D byte MEMORY_FILE2 ;
SavePos qaz MEMORY_FILE2 ;
GoTo QQ MEMORY_FILE8 ;
Put D Byte MEMORY_FILE8 ;
SavePos QQ MEMORY_FILE8 ;
Next Vertex ;
For Face = 0 < Zw3 ;
GoTo wsx MEMORY_FILE3 ;
Get D byte MEMORY_FILE3 ;
SavePos wsx MEMORY_FILE3 ;
GoTo QQQ MEMORY_FILE8 ;
Put D Byte MEMORY_FILE8 ;
SavePos QQQ MEMORY_FILE8 ;
Next Face ;
GoTo 0 MEMORY_FILE8 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum ;
Math M += 60 ;
Put M Long MEMORY_FILE8 ;
set M Byte 0x02 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x0A ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x03 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum 
Math M += 44 ;
Put M Long MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum 
Math M += 38 ;
Put M Long MEMORY_FILE8 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x72 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x67 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6F ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6A ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum 
Math M += 22 ;
Put M Long MEMORY_FILE8 ;
Set M Byte 0x10 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE8 ;
Math M = Snake ;
Math M += 8 ;
Put M Long MEMORY_FILE8 ;
Math M = VertexNumber ;
Put M Short MEMORY_FILE8 ;
Math JumpJump = Snake ;
Math JumpJump += 52 ;
GoTo JumpJump MEMORY_FILE8 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE8 ;
Math M = FaceNumber ;
Math M *= 8 ;
Math M += 8 ;
Put M Long MEMORY_FILE8 ;
Math M = FaceNumber ;
Put M Short MEMORY_FILE8 ;
Get purpledragon ASIZE MEMORY_FILE8 ;
Math name = Y ;
string name += .3ds ;
Log name 0 purpledragon MEMORY_FILE8 ;
Next Y ;

hope this helps
## Post #9
- Username: spartanmark6
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 28, 2016 9:11 am
- Post datetime: 2019-12-29T16:44:38+00:00
- Post Title: Tekken 4 PS2 Models

Thanks, I will see if I can do something with the information that you provided. I kinda gave up on it since I couldn't figure out a way to rip anything without it screwing up all of the mesh, but I will try to see if I can figure something out.
## Post #10
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2019-12-29T17:13:37+00:00
- Post Title: Tekken 4 PS2 Models

mariokart64n wrote one of these scripts Here [viewtopic.php?f=16&t=11866&start=15](https://forum.xentax.com/viewtopic.php?f=16&t=11866&start=15) i just shred them
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-30T17:19:25+00:00
- Post Title: Tekken 4 PS2 Models

I used that script on the Tekken 5 BIN file here: 
> Reply from Reddance ↑Tue May 02, 2017 5:31 am at Tue May 02, 2017 5:31 am
>
> 
which resulted in about 100 nud and tm2 files plus "some" purged 16 byte sized tm2 files (over 20 millions to be exact   )

Got this from a nud file:
.



nud22_point_cloud.png (96.6 KiB) Viewed 334 times

(auto creation of faces ugly, as always  )
## Post #12
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2020-01-01T19:14:38+00:00
- Post Title: Tekken 4 PS2 Models

Bro ........... you have to get your character to the customization menu  and THEN save the state in the customization Menu
you MUST use this ONLY on a SAVESTATE.savestates are quick saves they will be alongside the memcard folder
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-01T23:04:20+00:00
- Post Title: Tekken 4 PS2 Models

Bro..... I don't have  a PS2/PCSX2. I use what I find in this forum, nothing else.
## Post #14
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2020-01-02T02:06:46+00:00
- Post Title: Tekken 4 PS2 Models

neither did i.....until i downloaded tekken 5 from torrent and pcsx2 from their website
## Post #15
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2020-01-02T16:34:08+00:00
- Post Title: Tekken 4 PS2 Models

Hey Guys GREAT NEWS.... the guy behind wikispace has given me permission to share his Old Tekken 4 eememorybin to 3ds script......i think he was behind the tekken 5 script as well that i shared few days back  his name is  Michael Peter [albinoleopard@yahoo.com](mailto:albinoleopard@yahoo.com) . So here it is Now the models may not come out as perfect but hopefully he can modify the script  
HERE
log MEMORY_FILE 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE4 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;
log MEMORY_FILE7 0 0 ;
log MEMORY_FILE8 0 0 ;
log MEMORY_FILE9 0 0 ;
log MEMORY_FILE10 0 0 ;
Get Q ASIZE 0 ;
Math number = 0 ;
For T = 0 < Q ;
Math number += 1 ;
findloc OFFSET string "\x43\x48\x52\x54\x4B\x34" 0 0 ;
If OFFSET = 0 ;
Math T = Q ;
Math T += 1 ;
Math ttest = 0 ;
ELSE ;
GoTo OFFSET 0 ;
SavePos Start 0 ;
Put Start Long MEMORY_FILE4 ;
GoTo OFFSET 0 ;
GoTo 0x08 0 SEEK_CUR ;
Get size Long 0 ;
SavePos null 0 ;
EndIF ;
Next T ;
Put Q Long MEMORY_FILE4 ;


Get listf ASIZE MEMORY_FILE4 ;
Math spyrodragon = listf ;
Math spyrodragon /= 4 ;
Math spyrodragon -= 1 ;
Math rubyfox = 0 ;
Math diafox = 0 ;
Math rfv = 0 ;
For Y = 1 To spyrodragon ;
log MEMORY_FILE7 0 0 ;
log MEMORY_FILE8 0 0 ;
log MEMORY_FILE1 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
GoTo rubyfox MEMORY_FILE4 ;
Get start Long MEMORY_FILE4 ;
SavePos rubyfox MEMORY_FILE4 ;
Get size Long MEMORY_FILE4 ;
Math size -= start ;
Log MEMORY_FILE7 start size 0 ;
GoTo 0 MEMORY_FILE7 ;
Math count = 0 ;
Math gt = 0 ;
Math Qprime = 0 ;
Math red = 0 ;
SavePos found MEMORY_FILE7 ;
For T = 0 < size ;
GoTo found MEMORY_FILE7 ;
findloc OFFSETT string "\x04\x01\x00\x01\x00\x00\x00\x10\x5E\x40" MEMORY_FILE7 0 ;
If OFFSETT = 0 ;
Math T = size ;
Math twotest = 1 ;
EndIF ;
If OFFSETT != 0 ;
GoTo OFFSETT MEMORY_FILE7 ;
GoTo 10 MEMORY_FILE7 SEEK_CUR ;
Get onetest Byte MEMORY_FILE7 ;
Get twotest Byte MEMORY_FILE7 ;
SavePos found MEMORY_FILE7 ;
EndIF ;
If twotest = 104 ;
Put count Long MEMORY_FILE1 ;
Math count += onetest ;
Math foxcount = count ;
Math foxcount -= 1 ;
Put foxcount Long MEMORY_FILE1 ;
Put onetest Long MEMORY_FILE1 ;
Put found Long MEMORY_FILE1 ;
EndIF ;
Next T ;

Get mqa ASIZE MEMORY_FILE1 ;
Math mqa /= 16 ;
For jjj = 1 To mqa ;
GoTo gt MEMORY_FILE1 ;
Get min long MEMORY_FILE1 ;
Get max long MEMORY_FILE1 ;
Get nuv long MEMORY_FILE1 ;
Get loc long MEMORY_FILE1 ;
SavePos gt MEMORY_FILE1 ;
Math hhhggg = max ;
Math hhhggg -= 2 ;
GoTo loc MEMORY_FILE7 ;
SavePos werefox MEMORY_FILE7 ;
For cvb = 1 To nuv ;
GoTo werefox MEMORY_FILE7 ;
Get Type1 Long MEMORY_FILE7 ;
Get Type2 Long MEMORY_FILE7 ;
Get Type3 Long MEMORY_FILE7 ;
SavePos werefox MEMORY_FILE7 ;
GoTo Qprime MEMORY_FILE2 ;
Put Type1 Long MEMORY_FILE2 ;
Put Type2 Long MEMORY_FILE2 ;
Put Type3 Long MEMORY_FILE2 ;
SavePos Qprime MEMORY_FILE2 ;
Next cvb ;
Math max -= 2 ;

For fff = min To max ;

Math fafter = fff ;
Math fafter += 1 ;
Math fafterafter = fff ;
Math fafterafter += 2 ;
Math fafterafterafter = fff ;
Math fafterafterafter += 3 ;
GoTo red MEMORY_FILE3 ;
Put fff Short MEMORY_FILE3 ;
Put fafter Short MEMORY_FILE3 ;
Put fafterafter Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
Put fff Short MEMORY_FILE3 ;
Put fafterafter Short MEMORY_FILE3 ;
Put fafter Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos red MEMORY_FILE3 ;
Next fff ;





Next jjj ;






Get Zw3 ASIZE MEMORY_FILE3 ;
Math Zf3 = Zw3 ;
Math Zf3 /= 8 ;
Get Zw2 ASIZE MEMORY_FILE2 ;
Math Zf2 = Zw2 ;
Math Zf2 /= 12 ;
Math FaceNumber = Zf3 ;
Math VertexNumber = Zf2 ;
Math Snake = VertexNumber ;
Math Snake *= 12 ;
Math Dragon = FaceNumber ;
Math Dragon *= 8 ;
Math Sum = Dragon ;
Math Sum += Snake ;
Math QQQ = 60 ;
Math QQQ += Snake ;
Math QQ = 52 ;
Math qaz = 0 ;
Math wsx = 0 ;
Math hqw = Sum ;
Math hqw += 60 ;
Log MEMORY_FILE8 0 hqw ;
For Vertex = 0 < Zw2 ;
GoTo qaz MEMORY_FILE2 ;
Get D byte MEMORY_FILE2 ;
SavePos qaz MEMORY_FILE2 ;
GoTo QQ MEMORY_FILE8 ;
Put D Byte MEMORY_FILE8 ;
SavePos QQ MEMORY_FILE8 ;
Next Vertex ;
For Face = 0 < Zw3 ;
GoTo wsx MEMORY_FILE3 ;
Get D byte MEMORY_FILE3 ;
SavePos wsx MEMORY_FILE3 ;
GoTo QQQ MEMORY_FILE8 ;
Put D Byte MEMORY_FILE8 ;
SavePos QQQ MEMORY_FILE8 ;
Next Face ;
GoTo 0 MEMORY_FILE8 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum ;
Math M += 60 ;
Put M Long MEMORY_FILE8 ;
set M Byte 0x02 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x0A ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x03 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum 
Math M += 44 ;
Put M Long MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum 
Math M += 38 ;
Put M Long MEMORY_FILE8 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x72 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x67 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6F ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6A ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum 
Math M += 22 ;
Put M Long MEMORY_FILE8 ;
Set M Byte 0x10 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE8 ;
Math M = Snake ;
Math M += 8 ;
Put M Long MEMORY_FILE8 ;
Math M = VertexNumber ;
Put M Short MEMORY_FILE8 ;
Math JumpJump = Snake ;
Math JumpJump += 52 ;
GoTo JumpJump MEMORY_FILE8 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE8 ;
Math M = FaceNumber ;
Math M *= 8 ;
Math M += 8 ;
Put M Long MEMORY_FILE8 ;
Math M = FaceNumber ;
Put M Short MEMORY_FILE8 ;
Get purpledragon ASIZE MEMORY_FILE8 ;
Math name = Y ;
string name += .3ds ;
Log name 0 purpledragon MEMORY_FILE8 ;
Next Y ;
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-03T09:56:52+00:00
- Post Title: Re: Tekken 4 PS2 Models

I used that script (which didn't provide uvs, iirc) in 2014.
From the Tekken 5 BIN file here: 
> Reply from Reddance ↑Tue May 02, 2017 5:31 am at Tue May 02, 2017 5:31 am
>
>  you get this (submeshes 662 to 1285 not shown):
.



TK5DATA2-bin.png (128.25 KiB) Viewed 208 times

(Had to handle the uvs separately)

btw: this is the Tekken 4 thread.

For Tekken 5 maybe continue here:
[viewtopic.php?p=130250#p130250](https://forum.xentax.com/viewtopic.php?p=130250#p130250)
## Post #17
- Username: Rmm4K
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 22, 2020 5:44 am
- Post datetime: 2020-01-21T21:49:01+00:00
- Post Title: Re: Tekken 4 PS2 Models

Hi

I'm new in this thread, I've tried the Tekken 5 script and it works perfectly, but the script for Tekken 4 makes the models messy and distorted, the models have holes and are missing parts. I was wondering if there were other scripts to use for the game, if any new one has been made or discovered
## Post #18
- Username: Caladbolg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 27, 2021 6:46 am
- Post datetime: 2021-05-26T22:49:59+00:00
- Post Title: Re: Tekken 4 PS2 Models

A bit late, but I'm wondering if the code used to rip Tekken 4 Models applies to the stages as well? I want to rip just the stages in Tekken 4, (textures included) nothing else. If this code only works for character models, could someone please direct me to a guide or something on how to rip just the stage elements?
## Post #19
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2022-10-09T22:38:18+00:00
- Post Title: Re: Tekken 4 PS2 Models

search " Tutorial_ ripping textures and 3D models from Playstation 2 games (part 2_ models) " you can use blender as well, just would need to adjust the pivot.just scale the model down after loading.once you see the model, go to edit mode and move the mesh in the center of the pivot.use xray vision to select all.hope that helps
