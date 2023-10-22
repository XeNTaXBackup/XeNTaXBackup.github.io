## Post #1
- Username: anakinator
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2023 7:41 pm
- Post datetime: 2023-08-06T07:12:14+00:00
- Post Title: Sound format *.sdt

Hello, friends!
Again I have to turn to you for help.
I was analyzing the game files of the game "Harry Potter and the Goblet of Fire".
After unpacking the files, I came across the audio format *.sdt
After Googling a little, I found out that you can convert this format using "ffmpeg", as well as the program "sx.exe ". 
However, these programs do not open on my computer. When opened, the console window appears for 1 second and disappears. 
Vgmstream writes "failed opening" when converting.
Can you tell me how you can pull character dialogues from a *.sdt file? I will be insanely grateful.
I'm attaching one of the files, maybe someone can open it?   
[https://drive.google.com/file/d/1l3lYYl ... W0JhA/view](https://drive.google.com/file/d/1l3lYYl5F0MqAxqY0eMbVpEmxZ1PW0JhA/view)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-08-06T20:21:23+00:00
- Post Title: Sound format *.sdt

The file you linked is a container for EA audio files 
[http://wiki.xentax.com/index.php/EA_SDT](http://wiki.xentax.com/index.php/EA_SDT)
[http://wiki.xentax.com/index.php/EA_SCHl_Audio](http://wiki.xentax.com/index.php/EA_SCHl_Audio)

You can use this script with quickbms to unpack ASF files from the archive
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Harry%20Potter%20and%20the%20Goblet%20of%20Fire/harry_potter_and_the_goblet_of_fire_SDT_script.bms)

Then you can just open them with foobar2000 with vgmstream plugin or with Media Player Classic.
## Post #3
- Username: anakinator
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2023 7:41 pm
- Post datetime: 2023-08-07T05:03:48+00:00
- Post Title: Sound format *.sdt

Unfortunately, it didn't help. An error comes out

Error: invalid command "xmath" or arguments 2 at line 17

Press RETURN to quit
## Post #4
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-07T06:01:25+00:00
- Post Title: Sound format *.sdt

> Reply from anakinator ↑Mon Aug 07, 2023 1:03 pm at Mon Aug 07, 2023 1:03 pm
>
> 
Unfortunately, it didn't help. An error comes out

Error: invalid command "xmath" or arguments 2 at line 17

Press RETURN to quit

The script works for me

[](https://ibb.co/GWPxRqs)

Update your QuickBMS
## Post #5
- Username: anakinator
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2023 7:41 pm
- Post datetime: 2023-08-07T08:15:35+00:00
- Post Title: Sound format *.sdt

Thanks, it helped, but I noticed that not all files open like that. For example, here is one of these, for some reason does not lend itself. Do you know why this is so?
[https://drive.google.com/file/d/1rSXbGj ... z9vr4/view](https://drive.google.com/file/d/1rSXbGjjx7V8AA8znIAjGBqOXaaMz9vr4/view)
## Post #6
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-07T09:01:25+00:00
- Post Title: Sound format *.sdt

> Reply from anakinator ↑Mon Aug 07, 2023 4:15 pm at Mon Aug 07, 2023 4:15 pm
>
> 
Thanks, it helped, but I noticed that not all files open like that. For example, here is one of these, for some reason does not lend itself. Do you know why this is so?
https://drive.google.com/file/d/1rSXbGj ... z9vr4/view

This one doesn't have TOC (Stuff like offset and size fields) like your previous sample but continuously packed SCHl audio files. You have to find a tool to separate it. VGMToolbox's "Advanced Cutter/Offset Finder" can do that (or anything that able to cut the files in).

For VGMToolbox put these parameters to cut your files:

[](https://ibb.co/PNfsKhZ)

Then just drag and drop the continously packed SDT file there.
## Post #7
- Username: anakinator
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2023 7:41 pm
- Post datetime: 2023-08-07T09:20:28+00:00
- Post Title: Sound format *.sdt

I did everything according to your instructions, however, in the end it turned out from this .srt file - 802 format files .asf from 1kb to 200kb, which are not reproducible. 
I'm sorry if I'm being very stupid somewhere.


[C:\Users\Nik\Desktop\Новая папка (4)\cs-cz_s.sdt]
  Extracted [cs-cz_s_00000000.asf] begining at 0x00000000, for string found at: 0x00000000, with size 0x0003C140
  Extracted [cs-cz_s_00000001.asf] begining at 0x0003C140, for string found at: 0x0003C140, with size 0x00000AC0
  Extracted [cs-cz_s_00000002.asf] begining at 0x0003CC00, for string found at: 0x0003CC00, with size 0x00000EC0
  Extracted [cs-cz_s_00000003.asf] begining at 0x0003DAC0, for string found at: 0x0003DAC0, with size 0x00000CC0
  Extracted [cs-cz_s_00000004.asf] begining at 0x0003E780, for string found .........................................
................................................
  Extracted [cs-cz_s_00000321.asf] begining at 0x00678140, for string found at: 0x00678140, with size 0x00000400
  Warning: For string found at: 0x00678540, cut size is less than 1 (FFFFFFFFFF987ABF)...Skipping


[https://ibb.co/jy4hHYw](https://ibb.co/jy4hHYw)
[https://ibb.co/KKt79qM](https://ibb.co/KKt79qM)
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-08-07T15:23:25+00:00
- Post Title: Sound format *.sdt

Try this script for the second sample:
[https://github.com/bartlomiejduda/Tools ... ript_2.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Harry%20Potter%20and%20the%20Goblet%20of%20Fire/harry_potter_and_the_goblet_of_fire_SDT_script_2.bms)

After extraction every ASF file can be played in foobar2000 with vgmstream plugin.
## Post #9
- Username: anakinator
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2023 7:41 pm
- Post datetime: 2023-08-08T08:08:19+00:00
- Post Title: Sound format *.sdt

I coped with the 5th and 6th parts of the Harry Potter game on my own. But in part 7, when unpacking game resources, sounds are already output in the format.wav, not played.
With this   [https://github.com/Vextil/Wwise-Unpacker](https://github.com/Vextil/Wwise-Unpacker)     extracted files in mp3 and ogg, however, it sounds like a cartoon with a spy. As if the level of discretion is not the same. Can you tell me how to change, decipher?
I attach the files one of the original wav and the extracted mp3
[https://drive.google.com/file/d/1evh86F ... F8dw6/view](https://drive.google.com/file/d/1evh86FCEwlD5aXyIqC3c--Yq-UzF8dw6/view)
