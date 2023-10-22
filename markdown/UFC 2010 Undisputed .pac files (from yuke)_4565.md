## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-06T17:58:38+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

New game from Yuke. quick bms script for wrestling don't work.

[sample](http://www.sendspace.com/file/vrpp0o)
## Post #2
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-06-07T01:24:22+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

> Reply from Tosyk
>
> New game from Yuke. quick bms script for wrestling don't work.

sample
Open notepad and write this in it:

```
mkdir extracted\textures
quickbms -F "*.pac" UFC2010_PAC.bms . .\extracted
copy .\extracted\all.tex .\extracted\textures\all.tex
quickbms UFC2010_TEX.bms .\extracted\textures\all.tex .\extracted\textures
quickbms UFC2010_PAC.bms .\extracted\hud.tex .\extracted\textures
```

Save the file as extract.bat

Open notepad again for each of these code blocks, and save them as UFC2010_PAC.bms and UFC2010_TEX.bms.

UFC2010_PAC.bms:

```
get FILES long
GoTo 0x010
for i = 0 < FILES
getdstring NAME 16
getdstring FILEEXT 4
get SIZE long
get OFFSET long
get DUMMY long
string NAME + "."
string NAME + FILEEXT
log NAME OFFSET SIZE
next i
```


UFC2010_TEX.bms:

```
get FILES long
GoTo 0x010
for i = 0 < FILES
getdstring NAME 16 0
getdstring FILEEXT 4 0
get SIZE long 0
get OFFSET long 0
get DUMMY long 0
log NAME OFFSET SIZE
Open FDSE NAME 1
Endian little
IDString 1 "YZLI"
get ZSIZE ASIZE 1
GoTo 0x004 1
get SIZE long 1
Math ZSIZE -= 16 1
string NAME + ".dds" 1
ComType zlib 1
Clog NAME 16 ZSIZE SIZE 1
Endian big
next i

```


Then put quickbms.exe, the two BMS scripts, and the extract.bat file in the same directory as a model's PAC file, run the extract.bat file, and it will automatically extract all the textures from the Model PAC file.  BTW, these files will also work for UFC2009, and are what I used to easily and quickly extract stuff out of the model pac files in UFC2009.  The model files are in the folders in the "chara" folder, if you didn't know.

Optionally, you can just use the PAC BMS script I made for other PAC files.

When the Model PAC files are extracted, they may have .ymx files, use this script to extract those.

UFC2010_YMX.bms:

```
IDString "YZLI"
get NAME BASENAME
get ZSIZE ASIZE
GoTo 0x004
get SIZE long
Math ZSIZE -= 16
string NAME + ".yobj"
ComType zlib
Clog NAME 16 ZSIZE SIZE 0
```


The .ymx files contain the YOBJ files for the models.

Have Fun!
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-07T09:44:10+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

> Reply from brienj
>
> Have Fun!
Oh, your tools work just great  , but when i try to import models into 3ds max 2008 64x i get this error

```
msh FN error
```

can you tell me why?
## Post #4
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-06-07T19:16:01+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

> Reply from Tosyk
>
> brienj wrote:Have Fun!  
Oh, your tools work just great  , but when i try to import models into 3ds max 2008 64x i get this error
Code: Select allmsh FN error
can you tell me why?
Maybe because there is no plugin for UFC models.  

Just because they are made by Yukes and the SvR plugin will work with SvR, it doesn't mean that these models are the same.  That is something some a-hole from another forum, who spells his name backwards as if that is brilliant or something, is finding out when he has tried to put Wrestle Kingdom models into SvR, but as always, nobody wants to listen to what I say.  But anyway, every Yukes game has different models.  Only the SvR and LOWM models are the same, and even then, they aren't exactly the same.  

Edit: I removed my last comment that was directed at someone on another forum, as I understand kids could come upon these boards, and I shouldn't have posted it on here. I apologize to anyone that saw it, but not to the person it was directed at. I will let bygones be bygones, and it doesn't make me mad usually when someone calls me a name, but when I try to help them and they call me a name, that really sets me off. So once again, sorry to anyone offended by my comments.
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-08T06:51:33+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

> Reply from brienj
>
> Tosyk wrote:brienj wrote:Have Fun!  
Oh, your tools work just great  , but when i try to import models into 3ds max 2008 64x i get this error
Code: Select allmsh FN error
can you tell me why?
Maybe because there is no plugin for UFC models.  

Just because they are made by Yukes and the SvR plugin will work with SvR, it doesn't mean that these models are the same. Only the SvR and LOWM models are the same, and even then, they aren't exactly the same.
So we can't convert models from this game?  And if we can't when we can?  

From rumble roses xx models converting just great with this script.
## Post #6
- Username: ahon
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Dec 17, 2009 12:35 pm
- Post datetime: 2010-06-10T18:54:08+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

> Reply from brienj
>
> Tosyk wrote:brienj wrote:That is something some a-hole from another forum, who spells his name backwards as if that is brilliant or something, is finding out when he has tried to put Wrestle Kingdom models into SvR, but as always, nobody wants to listen to what I say.




PLease dont not talk about me!!!! I never disrepected you.  I have a PS2/PS3 you hack mean nothing to me.    I needed info not sarcasm.
## Post #7
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-06-10T20:10:58+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

> Reply from ahon
>
> brienj wrote:That is something some a-hole from another forum, who spells his name backwards as if that is brilliant or something, is finding out when he has tried to put Wrestle Kingdom models into SvR, but as always, nobody wants to listen to what I say. 


PLease dont not talk about me!!!! I never disrepected you so watch your F**kin mouth!!!  IF I Want to try to import a wrestler its MY business!   You was a cool guy until your hack came out, now your something like a B***H!  So again watch your mout FATMAN! and keep my Name or Names out of it!
Oh, so you never called me a DICK when I was trying to point out some things to help you?  Interesting.   

Keep on trying though, it is great entertainment and amusement.
## Post #8
- Username: ahon
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Dec 17, 2009 12:35 pm
- Post datetime: 2010-06-10T23:26:41+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

I though you were cool yeah I really did but evidentlly b :censored: es come in every form.


Sorry forum for the language ^^^^^^
## Post #9
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-06-11T17:00:38+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

I've edited my posts on here to remove the offensive comment, and I hope that ahon does the same.  It's the right thing to do.

I shouldn't be posting things on here about people that are two-faced to me, and will keep my offensive language for private conversations with those people.
## Post #10
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-06-11T17:16:33+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

> Reply from Tosyk
>
> brienj wrote:
Just because they are made by Yukes and the SvR plugin will work with SvR, it doesn't mean that these models are the same.  That is something some a-hole from another forum, who spells his name backwards as if that is brilliant or something, is finding out when he has tried to put Wrestle Kingdom models into SvR, but as always, nobody wants to listen to what I say.  But anyway, every Yukes game has different models.  Only the SvR and LOWM models are the same, and even then, they aren't exactly the same.  
So we can't convert models from this game?  And if we can't when we can?  

From rumble roses xx models converting just great with this script.
chrrox was working on an exporter script for the SvR models, he may be working on other Yukes models too.  I've also mentioned to Mr. Adults that it would be a cool thing to try and get Yukes model support in his tool, with conversions if possible.  

BTW, you may want to edit your post that quotes my post with the offensive comment.  I've stated why already.  Thanks.
## Post #11
- Username: omar93
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 07, 2010 10:35 pm
- Post datetime: 2010-11-08T19:51:35+00:00
- Post Title: UFC 2010 Undisputed .pac files (from yuke)

Thanks, your script is working great. But is there a way to rebuild the .pac archive with your (or another) script ?
