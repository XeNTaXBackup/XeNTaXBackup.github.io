## Post #1
- Username: zebrail231
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 19, 2022 12:11 am
- Post datetime: 2022-11-15T20:51:34+00:00
- Post Title: Hitman Blood Money - issues with translation

I want to translate Hitman Blood Money, but when i trying to open "M00_main.tex" with Notepad ++ or vGrim, see something like this: аЖа1Ж         1TXD1TXDЂ   @ @          Ђ?    BasicSurface/Simple/ColorWhite_01          Ђ?    Effects/Projector/Tree_shadow_06  Ђ                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          г  UUµ%Г  UЭшЦAqЊ   XЋsaU_^\  ‚ 	!  U]лE)  UU_x                                                                                                        з9  UUх
QЊ‚UUµMk  UяЁш!  U~xX                  A   @  ‚   &                  A                                                                                                                                   Г  х-5яMk  UяЇ-ЛZ  UU~\                                                                                                          A @    AP     ‚@@@ЂЖe)­Ґ%
уњA^^\\e)  UХЅўBa%µкЂBAp^Вз9  UХµ
  !                                         ЉR  UхЌ‰г  UU^`  ‚Ђ@@@E)AUЪшpГ  WWяcA UХ55ЖЗ9Ґ
ЇЖiJЂаxW¦1  ”ЧV\Г  \VWU!  Хµ5•Г  W\x~  ‚X(  A  PUUU  A 


Soo... What i can do with this? And, if its important, i use gog version 1.2
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-20T21:45:31+00:00
- Post Title: Hitman Blood Money - issues with translation

You're trying to open binary file with a text editor - you should never do that.
Instead, you should use hex editor, for example Hex Workshop.

But first, you should search for text strings.
This tutorial should be helpful [https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)

If the file is serialized in some way, you should reverse engineer it (figure out file format and create a tool to parse it)
Here is more info [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)


By the way, TEX files may contain anything - not only texts.
## Post #3
- Username: zebrail231
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 19, 2022 12:11 am
- Post datetime: 2022-11-21T20:29:26+00:00
- Post Title: Hitman Blood Money - issues with translation

Thank you, I am already know that this TEX file its file with texture, i dont need him. I have another question, how i can work with .Loc files? I can open it, but this such a mess.. Can i convert him into more simple format? I use notepad +++.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-21T21:41:53+00:00
- Post Title: Hitman Blood Money - issues with translation

You can convert only if there is some tool for it.
Luckily for you, there is one here [download/file.php?id=8981](https://forum.xentax.com/download/file.php?id=8981)
or here [https://download.elberethzone.net/hmc/loctool12beta.zip](https://download.elberethzone.net/hmc/loctool12beta.zip)

If no tool is provided, then your job is to reverse engineer file format and figure out unpacking/packing process yourself.
## Post #5
- Username: zebrail231
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 19, 2022 12:11 am
- Post datetime: 2022-11-24T17:30:30+00:00
- Post Title: Hitman Blood Money - issues with translation

> Reply from ikskoks ↑Tue Nov 22, 2022 5:41 am at Tue Nov 22, 2022 5:41 am
>
> 
You can convert only if there is some tool for it.
Luckily for you, there is one here download/file.php?id=8981
or here https://download.elberethzone.net/hmc/loctool12beta.zip

If no tool is provided, then your job is to reverse engineer file format and figure out unpacking/packing process yourself.

Sorry, i kinda stupid  . How to use them?
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-24T17:36:53+00:00
- Post Title: Hitman Blood Money - issues with translation

If you run the tool without arguments, you will see this:

```

Elbereth made this tool in a few hours, it may be (is) buggy.
Check https://download.elberethzone.net/hmc/ for latest version!
This is a completely UNNOFFICIAL tool. Use it at your own risk.

  Usage: loctool <action> <infile> [outfile]

 Action: x = Convert .LOC to .XML
         c = Convert .XML to .LOC

 Infile: Either .LOC file or .XML file
Outfile: If not indicated will be infile with new extension.
```


Also check out this link
[https://www.google.com/search?client=fi ... e+programs](https://www.google.com/search?client=firefox-b-d&q=how+to+run+command+line+programs)
