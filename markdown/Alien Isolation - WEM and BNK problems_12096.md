## Post #1
- Username: Saimon367
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 12, 2014 8:10 pm
- Post datetime: 2014-10-12T12:19:42+00:00
- Post Title: Alien Isolation - WEM and BNK problems

Hi. I have a problem with extracting/converting audio from Alien Isolation. Tried a several methods, including the ones from this forum, but it doesn't work. All i managed to achieve is extract WAVs from BNK, but then i can't reformat/convert/open these WAVs with anything. Please help
## Post #2
- Username: dmsa2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 16, 2014 2:34 am
- Post datetime: 2014-10-15T21:12:11+00:00
- Post Title: Alien Isolation - WEM and BNK problems

I just want extract all audio files
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-11-06T09:19:24+00:00
- Post Title: Alien Isolation - WEM and BNK problems

Not all WEMs convertable: I've got 2117 oggs of 2289 WEMs if use ww2ogg.

Unfortunatly, I dont know how select unconvertable WEMs fast, so here a link to the list of ogg(s)|WEM(s) - [http://pastebin.com/XwcGb8Mv](http://pastebin.com/XwcGb8Mv)

Possible reasons - different chunks not supported by ww2ogg or something another.

-----------------
Convertable WEMs - [http://pastebin.com/e0vbks89](http://pastebin.com/e0vbks89)
Unconvertable WEMs - [http://pastebin.com/N1uJsyVr](http://pastebin.com/N1uJsyVr)

Few samples - [http://goo.gl/rDQfII](http://goo.gl/rDQfII)
## Post #4
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2014-11-13T13:40:43+00:00
- Post Title: Alien Isolation - WEM and BNK problems

Try this:

> Reply from marmelada
>
> I managed to write a small batch script to handle bnk files. Since sometimes you get over 20 of these when unpacking a file and I'm lazy I wrote this:
Code: Select allfor %%a in (*.bnk) do (
md "%%~na" 2>nul
move "%%a" "%%~na"
copy bnkextr.exe %%~na
copy ww2ogg.exe %%~na
copy revorb.exe %%~na
copy packed_codebooks_aoTuV_603.bin %%~na
cd %%~na
bnkextr.exe %%a
del %%a
ren *.wav *.wem

for %%f in (*.wem) do (
ww2ogg.exe %%f --pcb packed_codebooks_aoTuV_603.bin
if exist "%%~nf.ogg" del %%f
)
for %%f in (*.ogg) do revorb.exe %%f

del packed_codebooks_aoTuV_603.bin
del *.exe
cd ..
)
for /f "delims=" %%d in ('dir /s /b /ad ^| sort /r') do rd "%%d"
WARNING: This will delete original bnk files after unpacking them!

How to use:
Copy bnkextr.exe; ww2ogg.exe; revorb.exe and packed_codebooks_aoTuV_603.bin along with this bat file to directory with bnk files and run .bat script.

What's going to happen:
Each bnk file will get its own directory and get unpacked. Then .wem files will be converted to ogg and revorbed. Wem files will be deleted (only those that got converted! I don't know why sometimes ww2ogg doesn't want to convert files). And then it goes to another bnk. At the end all empty folders will be deleted.

Ta-da!

I hope it'll be helpful to someone
[bnkextr](http://ctpax-cheater.narod.ru/personal/bnkextr.zip)
[ww2ogg 0.22](http://www.hcs64.com/files/ww2ogg022.zip)
[revorb](http://yirkha.fud.cz/progs/foobar2000/revorb.exe)
## Post #5
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-11-22T04:32:13+00:00
- Post Title: Alien Isolation - WEM and BNK problems

I use it already and got the results up.
## Post #6
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-03-12T13:06:39+00:00
- Post Title: Alien Isolation - WEM and BNK problems

ww2ogg can convert unsupported WEMs without packed_codebooks.bin and packed_codebooks_aoTuV_603.bin, but result oggs unplayable and revorb.exe cant fix them.
## Post #7
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-03-22T12:41:07+00:00
- Post Title: Alien Isolation - WEM and BNK problems

Maybe that WEM's have different codec (wwise adpcm for example) and there is no way to convert another wwise codecs by now. Also it would be nice if someone upload some of that files.
## Post #8
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-03-30T18:09:33+00:00
- Post Title: Alien Isolation - WEM and BNK problems

[https://mega.co.nz/#!UBRQXIAA!qCRsVOXuF ... pFdBk1dvbs](https://mega.co.nz/#!UBRQXIAA!qCRsVOXuFWnQH3hAO6oWbwxjPgPTRhTO6pFdBk1dvbs)

Few examples.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-31T17:19:07+00:00
- Post Title: Alien Isolation - WEM and BNK problems

Tried all these. All converted OK with ww2ogg version 0.22 and new codebooks (packed_codebooks_aoTuV_603)
