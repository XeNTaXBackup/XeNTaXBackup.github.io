## Post #1
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2017-05-01T21:31:13+00:00
- Post Title: Tekken 5 [2004] .BIN Files

Sup ALL, i noticed like most tekken games, they use the .bin format. and this game in particular has some great models innit; i've tried chrrox
quickbms script on them / PCSX2 save states but no success,

If anyone wants to take a look at one of the .BIN files; here's a relatively small one.

[https://www.mediafire.com/?15r7sl6iue1mgcr](https://www.mediafire.com/?15r7sl6iue1mgcr)
## Post #2
- Username: fast
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 07, 2016 1:58 am
- Post datetime: 2017-05-11T05:06:10+00:00
- Post Title: Tekken 5 [2004] .BIN Files

[url=[https://www.mediafire.com/view/?cuzh7uven28stg7](https://www.mediafire.com/view/?cuzh7uven28stg7)]
## Post #3
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2017-05-11T13:56:06+00:00
- Post Title: Tekken 5 [2004] .BIN Files

Why do not you try the Tekken5DR ps3?
Texture resolution is higher than ps2 version
## Post #4
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2017-05-12T11:30:57+00:00
- Post Title: Tekken 5 [2004] .BIN Files

i fixed the issue i was having, now i can get Tekken 5 models 

so this thread can be closed.. or removed, whichever!
## Post #5
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2017-05-13T11:04:16+00:00
- Post Title: Tekken 5 [2004] .BIN Files

And how - I wanna know it too... 
P.S: This method working with Tekken 4?
## Post #6
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2017-05-13T19:17:53+00:00
- Post Title: Tekken 5 [2004] .BIN Files

> Reply from Doronetty
>
> And how - I wanna know it too... 
P.S: This method working with Tekken 4?

Didn't try Tekken 4, but i use chrrox's BMS script to dump models n ' textures from the PCSX2 save states =p
## Post #7
- Username: fast
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 07, 2016 1:58 am
- Post datetime: 2017-05-14T16:21:07+00:00
- Post Title: Tekken 5 [2004] .BIN Files

Let's make a game
## Post #8
- Username: fast
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 07, 2016 1:58 am
- Post datetime: 2017-05-18T17:46:28+00:00
- Post Title: Tekken 5 [2004] .BIN Files

I unpacked 3d model from the game
## Post #9
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2017-05-18T18:16:45+00:00
- Post Title: Tekken 5 [2004] .BIN Files

> Reply from Reddance
>
> Doronetty wrote:And how - I wanna know it too... 
P.S: This method working with Tekken 4?

Didn't try Tekken 4, but i use chrrox's BMS script to dump models n ' textures from the PCSX2 save states =p
Can you please give me a link on this script?
## Post #10
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2017-05-27T02:05:12+00:00
- Post Title: Tekken 5 [2004] .BIN Files

> Reply from fast
>
> if you need 3d model use another script

goddamn! how'd you manage that!? explanation please
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-03T10:01:12+00:00
- Post Title: Tekken 5 [2004] .BIN Files

> Reply from Reddance ↑Tue May 02, 2017 5:31 am at Tue May 02, 2017 5:31 am
>
> If anyone wants to take a look at one of the .BIN files; here's a relatively small one.It looks like so:

> Reply from shakotay2 ↑Fri Jan 03, 2020 5:56 pm at Fri Jan 03, 2020 5:56 pm
>
> 

The script does an auto creation of faces, well, that's always not too nice  :
.



Tk5data2- sm 608,679.png (122.77 KiB) Viewed 313 times
## Post #12
- Username: Rmm4K
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 22, 2020 5:44 am
- Post datetime: 2020-01-21T23:16:07+00:00
- Post Title: Tekken 5 [2004] .BIN Files

Does anybody here have the Tekken 4 script to extract the 3d models with?
## Post #13
- Username: GEO
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 01, 2019 2:25 pm
- Post datetime: 2020-03-27T01:08:02+00:00
- Post Title: Tekken 5 [2004] .BIN Files

Could someone reupload the scripts? mediafire says it's been removed
## Post #14
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2021-02-15T21:27:44+00:00
- Post Title: Tekken 5 [2004] .BIN Files

copy and paste the below into notepad.....that is the script 

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
## Post #15
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2021-02-15T21:29:25+00:00
- Post Title: Tekken 5 [2004] .BIN Files

theres also another script but the results are not good for models but this one will give you the textures 
 Here 
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
## Post #16
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2021-02-15T21:34:06+00:00
- Post Title: Re: Tekken 5 [2004] .BIN Files

and for tekken 4 (a guy asked) i contacted the man behind it...its not good result but here it is  (somethings better than nothing) [viewtopic.php?t=14402](https://forum.xentax.com/viewtopic.php?t=14402)
