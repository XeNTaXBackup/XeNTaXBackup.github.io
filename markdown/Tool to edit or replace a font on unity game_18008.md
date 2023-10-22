## Post #1
- Username: bazickoff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 17, 2018 6:43 am
- Post datetime: 2018-04-20T21:29:27+00:00
- Post Title: Tool to edit or replace a font on unity game

Hello , this my first post  here 

I'm looking for tool to edit or replace fonts  ( TTF and Bitmap )  on unity games , the font that I want to edit inside " sharedassets0.assets " , after I edit the fonts I need to Import again to " sharedassets0.assets "

any help would be appreciated
## Post #2
- Username: bazickoff
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-04-21T10:00:51+00:00
- Post Title: Tool to edit or replace a font on unity game

What type of font is it? If it is TTF, you can use High-Logic FontCreator. If it is Bitmap, you can export DDS file with UnityEx or UAE and then use GIMP with DDS plugin.
## Post #3
- Username: bazickoff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 17, 2018 6:43 am
- Post datetime: 2018-04-25T21:18:18+00:00
- Post Title: Tool to edit or replace a font on unity game

> Reply from ikskoks
>
> What type of font is it? If it is TTF, you can use High-Logic FontCreator. If it is Bitmap, you can export DDS file with UnityEx or UAE and then use GIMP with DDS plugin.

my  friend ikskoks I Don't Know How To Thank You Enough, you saved my Life 
all tools are very helpful ( High-Logic FontCreator, UnityEx, UAE ) now I'm able to edit fonts like a Pro
## Post #4
- Username: BoomBookTR
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Jun 03, 2019 6:36 am
- Post datetime: 2020-12-31T10:21:45+00:00
- Post Title: Tool to edit or replace a font on unity game

> Reply from bazickoff ↑Thu Apr 26, 2018 5:18 am at Thu Apr 26, 2018 5:18 am
>
> 
ikskoks wrote:What type of font is it? If it is TTF, you can use High-Logic FontCreator. If it is Bitmap, you can export DDS file with UnityEx or UAE and then use GIMP with DDS plugin.

my  friend ikskoks I Don't Know How To Thank You Enough, you saved my Life 
all tools are very helpful ( High-Logic FontCreator, UnityEx, UAE ) now I'm able to edit fonts like a Pro

hi
i'm working on spranded deep localization.
there is font problem for me.
There is unsupported language characters.
How can i fix it?

i extracted with UnityEX
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-31T12:04:31+00:00
- Post Title: Tool to edit or replace a font on unity game

@JesWhite, You have to tell us more details. What type of font is this? What files did you extract? What methods of font editing did you try already? What is exact issue with font editing?

Plase also upload font files and some screenshots if necessary.
## Post #6
- Username: BoomBookTR
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Jun 03, 2019 6:36 am
- Post datetime: 2020-12-31T12:16:44+00:00
- Post Title: Tool to edit or replace a font on unity game

> Reply from ikskoks ↑Thu Dec 31, 2020 8:04 pm at Thu Dec 31, 2020 8:04 pm
>
> 
@JesWhite, You have to tell us more details. What type of font is this? What files did you extract? What methods of font editing did you try already? What is exact issue with font editing?

Plase also upload font files and some screenshots if necessary.

firstly thanks for your reply
here is my details...
i used UnityEX for extract with that code.

```
color a
for %%a in (*.assets;*.unity3d;*.bundle) do UnityEX.exe export "%%a" -t ttf,txt
for /l %%i in (0,1,30) do if exist level%%i UnityEX.exe export "level%%i" -t ttf,txt
UnityEX.exe export "resources.assets" -mb_new -t LanguageSourceAsset,LanguageSource
pause
```

[https://prnt.sc/wdmi9u](https://prnt.sc/wdmi9u)

Resources folder
[https://prnt.sc/wdmj2s](https://prnt.sc/wdmj2s)
Font folder
[https://prnt.sc/wdmjd5](https://prnt.sc/wdmjd5)

There is texts there and i import them with TR lang.
it worked but no support İ ı ş Ş ğ Ğ characters.

after that.
[https://prnt.sc/wdmkyx](https://prnt.sc/wdmkyx)


another folders
[https://prnt.sc/wdml6f](https://prnt.sc/wdml6f)

[https://prnt.sc/wdmlex](https://prnt.sc/wdmlex)
[https://prnt.sc/wdmll2](https://prnt.sc/wdmll2)
[https://prnt.sc/wdmlqj](https://prnt.sc/wdmlqj)

i activated tr characters with fontlab 7
and replaced them. after that imported game.
but nothing changed.
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-31T13:10:23+00:00
- Post Title: Tool to edit or replace a font on unity game

Maybe double check each font file with High-Logic FontCreator
if TR glyphs are present in fonts.

Also maybe check if there are any DDS fonts in textures folder.
## Post #8
- Username: BoomBookTR
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Jun 03, 2019 6:36 am
- Post datetime: 2020-12-31T14:13:44+00:00
- Post Title: Tool to edit or replace a font on unity game

> Reply from ikskoks ↑Thu Dec 31, 2020 9:10 pm at Thu Dec 31, 2020 9:10 pm
>
> 
Maybe double check each font file with High-Logic FontCreator
if TR glyphs are present in fonts.

Also maybe check if there are any DDS fonts in textures folder.
i found that dds for fonts.
[https://prnt.sc/wdoe05](https://prnt.sc/wdoe05)

but i dont understand anything
## Post #9
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-31T14:21:46+00:00
- Post Title: Tool to edit or replace a font on unity game

Those are PNG images and you can easily edit them with GIMP.
## Post #10
- Username: BoomBookTR
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Jun 03, 2019 6:36 am
- Post datetime: 2020-12-31T17:12:57+00:00
- Post Title: Tool to edit or replace a font on unity game

> Reply from ikskoks ↑Thu Dec 31, 2020 10:21 pm at Thu Dec 31, 2020 10:21 pm
>
> 
Those are PNG images and you can easily edit them with GIMP.

No way for me 
I didnt find how can i change font and characters in game...
i need tutorial or a video for replace them.
## Post #11
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2021-06-17T18:48:02+00:00
- Post Title: Tool to edit or replace a font on unity game

I can create this font, but it's very difficult to do that!
with all the letters you need!
## Post #12
- Username: nonamebatbai
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Sep 22, 2019 10:32 am
- Post datetime: 2021-08-11T07:59:57+00:00
- Post Title: Tool to edit or replace a font on unity game

> Reply from jonasjtg ↑Fri Jun 18, 2021 2:48 am at Fri Jun 18, 2021 2:48 am
>
> 
I can create this font, but it's very difficult to do that!
with all the letters you need!

Can you create a new font for unity game, without editing the old game font???
any game of unity engine???
## Post #13
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2021-08-15T04:30:05+00:00
- Post Title: Tool to edit or replace a font on unity game

I change that exists, or I can change the font style exists!
## Post #14
- Username: nonamebatbai
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Sep 22, 2019 10:32 am
- Post datetime: 2021-08-23T03:22:25+00:00
- Post Title: Tool to edit or replace a font on unity game

> Reply from jonasjtg ↑Sun Aug 15, 2021 12:30 pm at Sun Aug 15, 2021 12:30 pm
>
> 
I change that exists, or I can change the font style exists!
Can you help me create a font with Vietnamese characters?? I'm so grateful to you for that 
fullcharviet : !"#$%&'()*+,-./0123456789:;<=>?@abcdefghijklmnopqrstuvwxyz[]^_`abcdefghijklmnopqrstuvwxyz{|}~©®ÀÁÂÃÈÉÊÌÍÒÓÔÕÙÚÝàáâãèéêìíòóôõùúýĂăĐđĨĩŨũƠơƯưẠạẢảẤấẦầẨẩẪẫẬậẮắẰằẲẳẴẵẶặẸẹẺẻẼẽẾếỀềỂểỄễỆệỈỉỊịỌọỎỏỐốỒồỔổỖỗỘộỚớỜờỞởỠỡỢợỤụỦủỨứỪừỬửỮữỰựỲỳỴỵỶỷỸỹ
for game Pathfinder Kingmaker Definitive Edition
## Post #15
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2021-08-23T20:30:53+00:00
- Post Title: Tool to edit or replace a font on unity game

Yes, I can help, but I need the game!
Without the game I can't do anything!
If you donate the game version steam to me I can do it!
