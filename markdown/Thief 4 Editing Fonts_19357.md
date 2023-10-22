## Post #1
- Username: OLogYMot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Feb 02, 2016 12:13 am
- Post datetime: 2019-01-20T00:42:46+00:00
- Post Title: Thief 4 Editing Fonts

Hey everyone!

Thief 4 has PROG_GUI_Fonts.upk file which contains all fonts per language. Extracted data is:



I guess .SwfMovie file is very similar to .swf. I can see what it contains with JPEXS Free Flash Decompiler:



There are two fonts game uses across languages: Adobe Jenson Pro and Frutiger LT Std 57 Cn. For english version, Adobe Jenson Pro font has limited characters beside other languages (such as fonts_FRA.SwfMovie):



So fonts_FRA.SwfMovie has all characters I need. But Frutiger LT Std 57 Cn font is same regardless to language. I need to add extra characters for it. Or maybe adding entire new font for this? 

In the end, I need to edit fonts_en.SwfMovie. Basically two steps: 
1 - Replace Adobe font with Adobe font inside fonts_FRA.
2 - Add extra characters for Frutiger.

Can you help me with this? Thanks 

PROG_GUI_Fonts.upk file:
[http://www.mediafire.com/file/hw99mbhzh ... s.rar/file](http://www.mediafire.com/file/hw99mbhzh5cyq22/PROG_GUI_Fonts.rar/file)
## Post #2
- Username: OLogYMot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Feb 02, 2016 12:13 am
- Post datetime: 2019-01-20T15:14:43+00:00
- Post Title: Thief 4 Editing Fonts

Actually I managed to get first step done. Can anyone help me with second?
## Post #3
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2019-01-22T07:46:36+00:00
- Post Title: Thief 4 Editing Fonts

Edited
## Post #4
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2019-01-22T07:51:23+00:00
- Post Title: Thief 4 Editing Fonts

give me a edited flash file and original upk
## Post #5
- Username: OLogYMot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Feb 02, 2016 12:13 am
- Post datetime: 2019-01-22T12:50:04+00:00
- Post Title: Thief 4 Editing Fonts

> Reply from GHOST DEAD
>
> give me a edited flash file and original upk

I simply renamed and packed fonts_FRA.SwfMovie to fonts_en.SwfMovie and it worked 

Anyway I included renamed flash file and one font which I want to change from Frutiger to:

[http://www.mediafire.com/file/3u17yzrsn ... n.rar/file](http://www.mediafire.com/file/3u17yzrsn282dpn/fonts_en.rar/file)

Original upk from first message:

[http://www.mediafire.com/file/hw99mbhzh ... s.rar/file](http://www.mediafire.com/file/hw99mbhzh5cyq22/PROG_GUI_Fonts.rar/file)

If its worked out, I will be very glad if you tell me how you did it. Thanks for interest.
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2019-01-23T23:07:29+00:00
- Post Title: Thief 4 Editing Fonts

Hello. I had similar issue with Deadpool translation.

I was able to edit font this way:
1. Open swfmovie using JPEXS Free Flash Decompiler
2. Edit your file and save it as SWF/GFX. (don't remember which one)
  Your file has to be smaller than original.
3. Copy header and footer from original swfmovie file and paste it to your saved SWF/GFX file. You can use Hex Workshop for that. You have to remember to also fill missing space with zeroes at this point (after SWF/GFX data and before footer).
4. Change filename to original filename and pack it to UPK using Gildor tools. 

You can also check my transaltion to see how edited files looks like [https://ikskoks.pl/deadpool-the-video-g ... lszczenie/](https://ikskoks.pl/deadpool-the-video-game-spolszczenie/)
## Post #7
- Username: OLogYMot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Feb 02, 2016 12:13 am
- Post datetime: 2019-01-24T21:46:02+00:00
- Post Title: Thief 4 Editing Fonts

> 3. Copy header and footer from original swfmovie file and paste it to your saved SWF/GFX file. You can use Hex Workshop for that. You have to remember to also fill missing space with zeroes at this point (after SWF/GFX data and before footer).

Could you please explain to me how to do it this step? How long header and footer are in .SwfMovie? Thanks for interest btw.
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2019-01-24T22:04:08+00:00
- Post Title: Thief 4 Editing Fonts

> Could you please explain to me how to do it this step?
Yes, of course. Here is package with screenshots, I hope it helps.


 screenshots_gfx_font.zip
(66.07 KiB) Downloaded 83 times



> How long header and footer are in .SwfMovie?

For header it's easy, you just take everything that is before "GFX" magic and copy it.
For footer, you have to compare saved GFX/SWF and swfmovie to get the length. You can use option Tools > Compare > Compare Files in Hex Workshop.
## Post #9
- Username: OLogYMot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Feb 02, 2016 12:13 am
- Post datetime: 2019-01-24T23:17:59+00:00
- Post Title: Thief 4 Editing Fonts

Thanks for screenshots. I did all steps you gave me. But game crashed. I can't get figure out
