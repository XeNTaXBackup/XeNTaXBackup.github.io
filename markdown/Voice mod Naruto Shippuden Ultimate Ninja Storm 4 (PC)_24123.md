## Post #1
- Username: gabrielsanches19
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 28, 2021 2:53 pm
- Post datetime: 2021-06-28T06:57:57+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

I want to replace the game's battle audios.
well already I was able to extract the .xfbin through bms with script, and now I have the .bnsf files and already converted them to .wav but how do I do the reverse process? put it in .bnsf again and then in a single .xfbin file
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-06-28T21:16:38+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

Hi, which quickbms script did you use? And how did you convert bnsf to wav?

And what is the full name of your game? Is it "Naruto Shippuden: Ultimate Ninja Storm 4"? On which platform do you have it?
## Post #3
- Username: gabrielsanches19
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 28, 2021 2:53 pm
- Post datetime: 2021-07-14T13:11:36+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

the name of the game is Naruto Shippuden: Ultimate Ninja Storm 4 steam, and the bms script I used to extract the bnsf files, that's the one I'll send down

# ================================================================================
# JoJo's Bizarre Adventure: Eyes Of Heaven
# XFBIN extract
# QuickBMS script by Dave, 2021
# ================================================================================

IDString "NUCC"

FindLoc OFFSET String "TONE" 0 ""

If OFFSET = ""
	Break
Endif

Goto OFFSET
Get JUNK Long

FindLoc TONE_TABLE String "TONE" 0 ""				# 2nd occurence is the actual file table

If TONE_TABLE = ""
	Print "File table not found"
	Break
Endif

Goto TONE_TABLE
Get JUNK Long

FindLoc PACK_DATA String "PACK" 0 ""				# audio data

If PACK_DATA = ""
	Print "Data block not found"
	Break
Endif


Goto TONE_TABLE
Get JUNK Long
Get JUNK Long
Get ENTRIES Long
SavePos TONE_ENTRY

For A = 1 To ENTRIES
	Goto TONE_ENTRY
	Get INFO_OFFSET Long
	Get INFO_SIZE Long
	XMath INFO_OFFSET "INFO_OFFSET + TONE_TABLE + 12"
	Goto INFO_OFFSET
	Get FILE_TYPE Short
	Get JUNK Short
	Get JUNK Long
	Get TEXT_LEN Byte
	GetDString FILENAME TEXT_LEN

	Padding 4

	Get JUNK1 Long
	Get JUNK2 Long

	If FILE_TYPE = 0xFFFF
		Get OFFSET Long
		XMath OFFSET "OFFSET + PACK_DATA + 8"
		Get SIZE Long

		If SIZE > 0
			Goto OFFSET
			GetDString FILE_ID 4

			If FILE_ID = "BNSF"
				String FILENAME + ".bnsf"
			Elif FILE_ID = "RIFF"
				String FILENAME + ".at3"
			Endif

			Log FILENAME OFFSET SIZE

		Endif

	Endif

	Math TONE_ENTRY + 8
Next A
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-14T16:12:53+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

First you need to convert your WAV file to BNSF. 
That may be tricky, but I have found some tutorial here
[https://exvsfbce.home.blog/2020/02/04/g ... bnsf-is14/](https://exvsfbce.home.blog/2020/02/04/guide-to-encoding-bnsf-is14-audio-files-converting-wav-back-to-bnsf-is14/)
I'm not sure if it will work for your game, I haven't tested it.

Then you just need to import new BNSF file to XFBIN archive.
Reimport mode from quickbms should be able to handlle this.
Read more about it here [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)
## Post #5
- Username: gabrielsanches19
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 28, 2021 2:53 pm
- Post datetime: 2021-07-14T22:17:59+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

I don't understand about reimporting .bnsf files, isn't there a bms script for that?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-14T22:31:07+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

As far as I know, there is no script for that.
## Post #7
- Username: gabrielsanches19
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 28, 2021 2:53 pm
- Post datetime: 2021-07-15T01:10:50+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

I gave it a read in re-import mode and tried to use but this error ):

QuickBMS generic files extractor and reimporter 0.11.0
by Luigi Auriemma
e-mail: [me@aluigi.org](mailto:me@aluigi.org)
web:    aluigi.org
        (Apr  5 2021 - 13:56:34)

                          quickbms.com  Homepage
                            zenhax.com  ZenHAX Forum
                     @zenhax @quickbms  Twitter & Scripts

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select BMS script. type ? for using the content of clipboard like a script
- select input archives/files, type * for the whole folder and subfolders
- select output folder where extracting files

- REIMPORT mode enabled!
  - remember to select the SAME script, file and folder you selected during
    the previous extraction
  - it's highly suggested to leave only the edited files in the folder, it's
    faster and less prone to errors with compressed files

- open input file C:\Users\Gabriel Sanches\Desktop\Nova pasta (5)\Nova pasta\S_PL_ATK_ckrAtk_a_v1.bnsf
- open script C:\Users\Gabriel Sanches\Downloads\quickbms\script.bms
- set output folder C:\Users\Gabriel Sanches\Desktop\Nova pasta (5)\Nova pasta (2)

  offset   filesize   filename
--------------------------------------

- signature of 4 bytes at offset 0x00000000 doesn't match the one
  expected by the script:

  this one: "BNSF"
  42 4e 53 46                                       BNSF

  expected: "NUCC"
  4e 55 43 43                                       NUCC

- 0 files reimported in 0 seconds
  coverage file 0     0%   4          10968      . offset 00000004

Press ENTER or close the window to quit
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-15T07:29:01+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

You should use this script only with XFBIN file.
You're getting this error, because you tried to use it with BNSF file.
## Post #9
- Username: gabrielsanches19
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 28, 2021 2:53 pm
- Post datetime: 2021-07-27T13:15:49+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

I was able to reimport the xfbin files, thank you very much, but I still couldn't pass the wav to bnsf, I even found a converter ([http://www.solidfiles.com/v/NGx3665eamxN2](http://www.solidfiles.com/v/NGx3665eamxN2)) but when I reimport it says the file is bigger than the original
## Post #10
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-27T14:44:09+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

Maybe just use Audacity to cut or compress your WAV file first.


By the way, your "converter" is just a vgmstream with BAT scripts for bnsf conversion.

```
for %%f in (*.wav) do vgmstream -o %%~nf.bnsf %%~nf.wav
```

You can get the newest version from github [https://github.com/vgmstream/vgmstream](https://github.com/vgmstream/vgmstream)
## Post #11
- Username: gabrielsanches19
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 28, 2021 2:53 pm
- Post datetime: 2021-07-27T23:07:18+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

even compressing the audio is like this
[Screenshot_2.png](https://xentaxbackup.github.io/file/20524_Screenshot_2.png)
## Post #12
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-28T17:28:31+00:00
- Post Title: Voice mod Naruto Shippuden: Ultimate Ninja Storm 4 (PC)

I would try to cut the audio just for testing. Try to cut only 3 seconds from the audio and reinsert that.
