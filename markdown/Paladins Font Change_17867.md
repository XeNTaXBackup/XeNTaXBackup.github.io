## Post #1
- Username: DaveRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 11, 2017 10:58 am
- Post datetime: 2018-03-24T07:07:19+00:00
- Post Title: Paladins Font Change

Hello! Recently I'm trying to change Paladins' Korean font. Its engine is Unreal 3.

Paladins is already contains Korean font, but it looks slightly weird, so that's why I'm trying to change font.

I've discorvered that Paladins' fonts are in Steam\steamapps\common\Paladins\ChaosGame\CookedPCConsole\GFxFonts.upk.
So I extracted that file, then I got several files. There was 'fonts_kr.SwfMovie' - this is Korean font! Then I converted it to .swf, and I'm able to see its content with SWF Decompiler.

And... I don't know what to do now. I don't know how to change font and repack files to apply changes to game.

Please help me... X(

GFxFonts file is here: [http://www.mediafire.com/file/3o7rzazay ... xFonts.upk](http://www.mediafire.com/file/3o7rzazaybh3xz0/GFxFonts.upk)
## Post #2
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2018-03-24T15:51:45+00:00
- Post Title: Paladins Font Change

.gfx  [http://dropmefiles.com/chvoA](http://dropmefiles.com/chvoA)

Use UPKunpack.exe and UPKrepack.exe to edit .upk or UDK. 
Use JPEXS Free Flash Decompiler to convert .SwfMovie in .gfx 

Use Hex editor (add new 4 bytes magic and footer)
Exaample:
Add new 4 bytes magic new .gfx in .SwfMovie
.gfx


.SwfMovie



Add footer .SwfMovie in new .gfx


Cut .SwfMovie and paste new .gfx in .SwfMovie
Exaample:
Cut .SwfMovie 




paste new .gfx + footer in .SwfMovie

[.upk Unpack_Pack.rar](https://xentaxbackup.github.io/file/14082_.upk Unpack_Pack.rar)
## Post #3
- Username: DaveRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 11, 2017 10:58 am
- Post datetime: 2018-03-25T04:13:57+00:00
- Post Title: Paladins Font Change

I don't know I'm doing right, but when I use UPKrepack, I got this error.

!!!!! ERROR !!!!!:Can't open PKGInfoFile:res\.UPKpkgInfo

How can I do?

-------

Oh... I did wrong XD. sorry!
## Post #4
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-25T05:43:00+00:00
- Post Title: Paladins Font Change

Give Me your ttf Font and characters in your language
and GFxUI.int and DefaultEngine.ini from main Data

I will creat a Font for you...
## Post #5
- Username: DaveRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 11, 2017 10:58 am
- Post datetime: 2018-03-25T09:05:26+00:00
- Post Title: Paladins Font Change

Here it is! [http://www.mediafire.com/file/a7h624uwz ... sDatas.zip](http://www.mediafire.com/file/a7h624uwzq6z8ia/PaladinsDatas.zip)

You said give you GFxUI.int, but I'm trying to apply my own Korean font, and there was GFxUI.kor, so I included it, too!

I'm sorry if it's unnecessary. Thanks!
## Post #6
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-26T04:37:59+00:00
- Post Title: Paladins Font Change

Here... Test it and tell me how its work, if you have any problem whit that, call me

link: [http://www.mediafire.com/file/7ijevhtf2 ... xFonts.rar](http://www.mediafire.com/file/7ijevhtf2mm96cu/GFxFonts.rar)

Good Luck
## Post #7
- Username: DaveRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 11, 2017 10:58 am
- Post datetime: 2018-03-26T07:48:15+00:00
- Post Title: Paladins Font Change

It works verrrrrrry well!!!! Thank you very much!!!

But I'd like to change it for a thicker one and test other fonts. I think it's bothering you if I keep request you font, so could you please teach me how to do this?

Thanks!
## Post #8
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-26T11:16:14+00:00
- Post Title: Paladins Font Change

> Reply from DaveRipper
>
> It works verrrrrrry well!!!! Thank you very much!!!

But I'd like to change it for a thicker one and test other fonts. I think it's bothering you if I keep request you font, so could you please teach me how to do this?

Thanks!

teaching you? no dude... i used unreal engine 3 to do that, i dont know any tool
if you have any question about unreal engine 3, call me.
good luck body...
## Post #9
- Username: DaveRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 11, 2017 10:58 am
- Post datetime: 2018-03-27T11:17:38+00:00
- Post Title: Paladins Font Change

Oh... But could you please give me a hint about this? 

I've googled sooo many times but I couldn't get any information... Please help me... Thanks!
## Post #10
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-03-27T12:01:10+00:00
- Post Title: Paladins Font Change

> Reply from DaveRipper
>
> Oh... But could you please give me a hint about this? 

I've googled sooo many times but I couldn't get any information... Please help me... Thanks!

help about what, my frind? i just opened your UPK file in unreal engine 3 and extract font (.gfx) and replace characters and import on your upk file... just like that, udk or other tool cant open any package file, i am a game enginer and i can use engine... but you can try with a hex editor... as you can see,  i dont know any tool
## Post #11
- Username: Csucskos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 11, 2019 6:16 am
- Post datetime: 2019-02-10T22:33:35+00:00
- Post Title: Paladins Font Change

OMG!
I have a similar problem, and I would be more than happy if it could be solved. My case is: I'M trying to translate Borderlands 2 to Hungarian. (The game has been out for quite a while, but noone really got into this, or haven't shared the results.) Now this is where my problem lies: In the ingame font 4 national characters are missing. (Namely ű,ő and their capital pairs.)

So I hopped on the internet, and with it's help figured out, what the ingame font was. It's Compacta Bd BT, so I searched for it, and was able to find it online. After that I added the missing characters, and than faced the bigger problem. How can I insert this into the game?

I've been running around on forums, for the answer, but without any luck. I was wondering if you could help. (This case looked vaguely familiar.)
I'm only concerned, because maybe the game stores the fonts differently. (I was able to find upk extractor tools, and was able to find out, that in the Startup_LOC_INT folder there are .font and .texture2d files. I don't know though if they are what I'm looking for. In the GFxUI there are only "FontLib=UI_FontsEn.FontsEn" and "BodyFont=Compacta Bd BT,normal" lines.)
## Post #12
- Username: tehrantoday
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 07, 2023 12:38 am
- Post datetime: 2023-08-26T09:10:33+00:00
- Post Title: Paladins Font Change

> Reply from GHOST DEAD ↑Mon Mar 26, 2018 12:37 pm at Mon Mar 26, 2018 12:37 pm
>
> 
Here... Test it and tell me how its work, if you have any problem whit that, call me

link: http://www.mediafire.com/file/7ijevhtf2 ... xFonts.rar

Good Luck

Please prepare this file for me...

[https://dropmefiles.com/Z5dy4](https://dropmefiles.com/Z5dy4)

[https://archive.org/download/font_20230824/font.zip](https://archive.org/download/font_20230824/font.zip)

I added these files : ttf , DefaultEngine.ini , GFxUI.int , GFxFonts.int , fonts_en.upk in font.zip

change font please...
