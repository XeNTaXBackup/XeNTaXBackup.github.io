## Post #1
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-10T17:07:14+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

ok, i actually want to try to extract resource from a res.dat file from a psp iso but i heard theres very little tools that can help do this... so where can i start to give this a try?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-10T19:09:27+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

What is name of the game you are trying extract data from?

Also, please upload sample DAT file.
## Post #3
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-11T05:37:03+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

the game is boku ha tomodachi ga sukunai portable, i would like to put the sample file but the extension is .dat so i cant really put it as attachment, sorry...
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-11T09:54:37+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

> i cant really put it as attachment, sorry...

You can upload it to service like mega.nz, google drive etc. and then share a link here.
## Post #5
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-12T05:14:36+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

will this work?
[https://mega.nz/file/vVtEDbiR#OJ7Oe2gCJ ... 1H4q1LREuM](https://mega.nz/file/vVtEDbiR#OJ7Oe2gCJqAAnteblcyQ7OMvzEi_RqMSY1H4q1LREuM)
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-12T17:47:22+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

It seems that there is already a script which allows data extraction
[https://aluigi.altervista.org/bms/saena ... tekata.bms](https://aluigi.altervista.org/bms/saenai_heroine_no_sodatekata.bms)

Use it with quickbms [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)


Also, here is wiki article for this file format [http://wiki.xentax.com/index.php/Boku_w ... rtable_DAT](http://wiki.xentax.com/index.php/Boku_wa_Tomodachi_ga_Sukunai_Portable_DAT)
## Post #7
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-13T15:59:51+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

thanks, i didnt think it was that simple tbh, i found what i wanted but now i got a new problem, the textures are in gim extension... and i know gimconv can convert it back to png but how do i use it? didnt work using terminal
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-13T17:17:53+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

You can use it like this:

```
gimconv.exe in.gim -o out.png
```


Check also other GIM tools from the wiki [http://wiki.xentax.com/index.php/GIM_Image](http://wiki.xentax.com/index.php/GIM_Image)
## Post #9
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-14T05:13:10+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

yea... i gave it a try but now i just realized gimconv only works with ps3 type gims... the game i target was psp so it got the wrong format error... any ideas about which converter for gim works with the psp type?
## Post #10
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-14T20:16:23+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

> gimconv only works with ps3 type gims... the game i target was psp so it got the wrong format error...

No, you're wrong. Gimconv works fine with PSP GIM files. You can check it for example with those files:
RES\image_map\map00\bg.gim
RES\image_title\image_title\t_logo.gim

See result here [https://i.imgur.com/ONY4FOQ.png](https://i.imgur.com/ONY4FOQ.png)


You're getting "wrong format" error because most of those GIM files are also compressed with gzip.
Script for DAT file should handle it automatically, but it didn't, so I will post my script for decompression below.

You can see it for example for file RES\image_bg\BG01A.gim
Result here [https://i.imgur.com/obUGoN7.png](https://i.imgur.com/obUGoN7.png)

And here is the script:

```
# Creation Date: 14.07.2021

comtype gzip
get ZSIZE asize
set SIZE long 0

math SIZE = ZSIZE
math SIZE *= 20

get NAME basename
string NAME + "_new.gim"
clog NAME 0 ZSIZE SIZE
```
## Post #11
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-15T05:21:26+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

uh... okay then... is that supposed to be executed as a bat file? how do i exactly use it to decompress gzip compressed gim files? im not an expert at programming so i dont really have much of a clue on how to use the code you just sent me
## Post #12
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-15T07:04:56+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

It's just regular quickBMS script.
You can use it with quickBMS [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)

Here is the manual [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)
and some tutorials here [https://www.google.com/search?client=fi ... e+quickbms](https://www.google.com/search?client=firefox-b-d&q=how+to+use+quickbms)
## Post #13
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-15T14:19:55+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

thanks for the help, it works well also has some experience using quickbms with destiny child pck files so the rest is easy, but im curious about something... can quickbms process more than 1 file using the same script?
## Post #14
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-15T17:24:17+00:00
- Post Title: Boku wa Tomodachi ga Sukunai Portable (PSP) - DAT files

> can quickbms process more than 1 file using the same script?

Sure, but you need additional BAT script for that. 
So for example if you have some GIM files, quickbms script, quickbms executable and BAT script in the same directory,
then it would look like this [https://i.imgur.com/UEDscNr.png](https://i.imgur.com/UEDscNr.png)


And the script for automation could look like this:
[https://github.com/bartlomiejduda/Tools ... OR_ALL.BAT](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/RUN_FOR_ALL.BAT)
