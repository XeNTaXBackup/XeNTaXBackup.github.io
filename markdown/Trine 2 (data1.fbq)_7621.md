## Post #1
- Username: Lygatt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 26, 2011 9:22 pm
- Post datetime: 2011-11-03T13:52:48+00:00
- Post Title: Trine 2 (data1.fbq)

Violation of rules.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-03T18:17:29+00:00
- Post Title: Trine 2 (data1.fbq)

[http://aluigi.org/papers/bms/trine2.bms](http://aluigi.org/papers/bms/trine2.bms)
## Post #3
- Username: Lygatt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 26, 2011 9:22 pm
- Post datetime: 2011-11-04T10:34:23+00:00
- Post Title: Trine 2 (data1.fbq)

Violation of rules.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-11-05T09:58:17+00:00
- Post Title: Trine 2 (data1.fbq)

The good news is these ogg files are supported by the latest version of ww2ogg ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)).  However, I believe the extraction script is flawed, the files all seem to be 0xc bytes too early.  I think this will fix it, but I haven't tested it.

[edit] script removed as aluigi has fixed his script linked above[/edit]

Another thing to be wary of is that ww2ogg 0.16 doesn't produce perfectly clean output in general (see the note about revorb), and it is even worse for this type of file (using shortened Vorbis packets which lack the previous and next window bits).  It is possible that the output files will not work properly in some hardware decoders, or programs that use the Tremor decoder.  I am thinking about how to fix this but I don't have a lot of time to do new work.

I was able to test a few files successfully with audacity, and it should be fine with the standard libvorbis reference decoder, so it will probably work once the extraction script is fixed.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-05T11:49:37+00:00
- Post Title: Trine 2 (data1.fbq)

thanx for the info hcs, I have corrected the script.
in short there is also ZSIZE - 0xc to be removed so I have simply used a BASE_OFF += 0xc at the beginning
## Post #6
- Username: Lygatt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 26, 2011 9:22 pm
- Post datetime: 2011-11-05T20:15:08+00:00
- Post Title: Trine 2 (data1.fbq)

Thank you HCS, really awesome, all worked perfectly!
I also used revorb to fix the output from ww2ogg as suggested and everything is fine.

Aluigi and HCS thanks a lot for your support.
## Post #7
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2011-12-07T16:52:06+00:00
- Post Title: Trine 2 (data1.fbq)

Hello.
Is there any way to pack files back to data1.fbq?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-08T11:42:10+00:00
- Post Title: Trine 2 (data1.fbq)

section 3 of quickbms.txt:
[http://aluigi.org/papers/quickbms.txt](http://aluigi.org/papers/quickbms.txt)
## Post #9
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2011-12-08T11:43:51+00:00
- Post Title: Trine 2 (data1.fbq)

> Reply from aluigi
>
> section 3 of quickbms.txt:
http://aluigi.org/papers/quickbms.txt
Thanx!
## Post #10
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2011-12-25T17:09:59+00:00
- Post Title: Trine 2 (data1.fbq)

thx aluigi but links no works [http://aluigi.altervista.org/papers/bms/trine2.bms](http://aluigi.altervista.org/papers/bms/trine2.bms) can you solve it plz.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-25T18:13:19+00:00
- Post Title: Trine 2 (data1.fbq)

Manually copy it into your browser.
## Post #12
- Username: speechless
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 30, 2011 1:00 pm
- Post datetime: 2011-12-30T05:15:54+00:00
- Post Title: Trine 2 (data1.fbq)

Read through this thread, followed the instructions. Gotten 4,036 perfect .ogg's
after i extracted the audio files out of the data.fbq file.

I wrote this .bat to do all the work for me.
I will leave this here

```

echo speechless .ogg conversion .bat file

::Paths for
::  1) input ogg folder
::  2) output ogg folder
::  3) ww2ogg folder
::  4) packed codebook for ww2ogg.exe
::  5) revorb folder
echo Setting Temp Paths
setlocal
:: NOTE TO ALL: make sure you have changed the SET paths below to the locations you want/where your files are at
SET inputOGGfolder=C:\Users\speechless\Desktop\Trine2OGG\data\audio\windows
SET outputOGGfolder=C:\Users\speechless\Desktop\outputOGG
SET ww2orgFolder=C:\Users\speechless\Ripping Music\ww2ogg
SET packedCodebook=C:\Users\speechless\Ripping Music\ww2ogg\packed_codebooks.bin
SET revorbFolder=C:\Users\speechless\Ripping Music\revorb

echo Converting .ogg files [please wait]
for %%a in ("%inputOGGfolder%\*.ogg") do "%ww2orgFolder%\ww2ogg" "%%a" --pcb "%packedCodebook%"
for %%a in ("%inputOGGfolder%\english_us_\*.ogg") do "%ww2orgFolder%\ww2ogg" "%%a" --pcb "%packedCodebook%"
for %%a in ("%inputOGGfolder%\french_france_\*.ogg") do "%ww2orgFolder%\ww2ogg" "%%a" --pcb "%packedCodebook%"
for %%a in ("%inputOGGfolder%\german\*.ogg") do "%ww2orgFolder%\ww2ogg" "%%a" --pcb "%packedCodebook%"
for %%a in ("%inputOGGfolder%\spanish_spain_\*.ogg") do "%ww2orgFolder%\ww2ogg" "%%a" --pcb "%packedCodebook%"

echo Moving converted .ogg files to Output Folder [please wait]
for %%a in ("%inputOGGfolder%\*.ogg_conv.ogg") do move "%%a" "%outputOGGfolder%"
for %%a in ("%inputOGGfolder%\english_us_\*.ogg_conv.ogg") do move "%%a" "%outputOGGfolder%\english_us_"
for %%a in ("%inputOGGfolder%\french_france_\*.ogg_conv.ogg") do move "%%a" "%outputOGGfolder%\french_france_"
for %%a in ("%inputOGGfolder%\german\*.ogg_conv.ogg") do move "%%a" "%outputOGGfolder%\german"
for %%a in ("%inputOGGfolder%\spanish_spain_\*.ogg_conv.ogg") do move "%%a" "%outputOGGfolder%\spanish_spain_"

echo Removing errors in converted .ogg files [please wait]
for %%a in ("%outputOGGfolder%\*.ogg_conv.ogg") do "%revorbFolder%\revorb" "%%a"
for %%a in ("%outputOGGfolder%\english_us_\*.ogg_conv.ogg") do "%revorbFolder%\revorb" "%%a"
for %%a in ("%outputOGGfolder%\french_france_\*.ogg_conv.ogg") do "%revorbFolder%\revorb" "%%a"
for %%a in ("%outputOGGfolder%\german\*.ogg_conv.ogg") do "%revorbFolder%\revorb" "%%a"
for %%a in ("%outputOGGfolder%\spanish_spain_\*.ogg_conv.ogg") do "%revorbFolder%\revorb" "%%a"
endlocal

echo .ogg conversion complete
pause

```


copy the code into a .bat file, edit/use it as you feel like.

p.s. it is not really that great, for that i apologize, this is the first .bat code i have ever written in my left
## Post #13
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-01-03T15:35:42+00:00
- Post Title: Trine 2 (data1.fbq)

I don't think QuickBMS will be able to patch the resources right, because the game uses a custom CRC, that is later checked.
I might be wrong, but however i make a unpakke module for these type of archives.

Check the forum topic here: [viewtopic.php?f=33&t=6168](http://forum.xentax.com/viewtopic.php?f=33&t=6168) or Unpakke's homepage here: [http://nullsecurity.org/unpakke/](http://nullsecurity.org/unpakke/)
## Post #14
- Username: revex
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 08, 2012 2:10 pm
- Post datetime: 2012-03-11T07:43:05+00:00
- Post Title: Trine 2 (data1.fbq)

when the going to reimport *.bin or *.fbi file shown error message (crash)
but reimport "trine 2" videos files with QuickBMS is ok
is there a solution to this problem?
## Post #15
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-03-14T11:41:23+00:00
- Post Title: Trine 2 (data1.fbq)

> Reply from revex
>
> when the going to reimport *.bin or *.fbi file shown error message (crash)
but reimport "trine 2" videos files with QuickBMS is ok
is there a solution to this problem?
I didn't get that one... is it about Unpakke or about QuickBMS?
## Post #16
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-11T14:40:47+00:00
- Post Title: Re: Trine 2 (data1.fbq)

Sorry for pulling an old thread, but i just want to mention that if you have sound problems after repacking "Trine 2", you can download the latest version of FBQ module for Unpakke.

Just don't forget to read the included readme file!
