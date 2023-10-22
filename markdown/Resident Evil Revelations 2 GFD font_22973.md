## Post #1
- Username: gameside
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 07, 2020 6:21 am
- Post datetime: 2020-11-06T22:38:12+00:00
- Post Title: Resident Evil Revelations 2 GFD font

Hi i want to translate this game to my native language
there is no problem with text, but sadly i cant edit font, this game use some custom bitmap font (GFD and TEX file)
i upload some example, hope someone take a look at them and help me
thanks
[https://anonfiles.com/75Adv4nbp6/font_rar](https://anonfiles.com/75Adv4nbp6/font_rar)
## Post #2
- Username: Saeid0034
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-07T09:46:35+00:00
- Post Title: Resident Evil Revelations 2 GFD font

GFD is file storing character definitions and probably coordinates.
TEX is compressed texture file.

Check those links for reference
[https://residentevilmodding.boards.net/ ... -tutorials](https://residentevilmodding.boards.net/board/100/re-revelations-2-modding-tutorials)
[https://residentevilmodding.boards.net/ ... re-editing](https://residentevilmodding.boards.net/thread/7873/extract-revelations-mesh-texture-editing)
[https://residentevilmodding.boards.net/ ... ompression](https://residentevilmodding.boards.net/thread/9093/tutorial-framework-proper-texture-compression)

After converting TEX to DDS you can view them with IrfanView [https://imgur.com/a/eZuV8mI](https://imgur.com/a/eZuV8mI)
and edit with GIMP + DDS Plugin.

You can see some image in TEX file in texture cooker [https://imgur.com/a/9MAQM5f](https://imgur.com/a/9MAQM5f)
## Post #3
- Username: gameside
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 07, 2020 6:21 am
- Post datetime: 2020-11-07T12:55:43+00:00
- Post Title: Resident Evil Revelations 2 GFD font

> Reply from ikskoks ↑Sat Nov 07, 2020 5:46 pm at Sat Nov 07, 2020 5:46 pm
>
> 
GFD is file storing character definitions and probably coordinates.
TEX is compressed texture file.

Check those links for reference
https://residentevilmodding.boards.net/ ... -tutorials
https://residentevilmodding.boards.net/ ... re-editing
https://residentevilmodding.boards.net/ ... ompression

After converting TEX to DDS you can view them with IrfanView https://imgur.com/a/eZuV8mI
and edit with GIMP + DDS Plugin.

You can see some image in TEX file in texture cooker https://imgur.com/a/9MAQM5f
Thanks for reply
I Know how to edit and recreate Tex file
But my problem is I need to add like 100 new char to game font, so I can't just replace some existing char with new one, I need to create new font, i found some useful information about gfd file in this site [https://sigyn.tistory.com/6](https://sigyn.tistory.com/6) - [with google translate to english](https://translate.google.com/translate?hl=en&tab=wT0&sl=auto&tl=en&u=https%3A%2F%2Fsigyn.tistory.com%2F6). its explain gfd file format

Character  (red box)
Character position (green box)
Character size (blue box)
Offset-character size deviation (orange box)


 but becuse i dont have much experiment with these stuff, i cant create a tool by myself
i think its possible to create a new bitmap font with BMFont, then somehow convert BMfont char mapping (xml file) to GFD but i dont know how
can anyone help?
thanks
