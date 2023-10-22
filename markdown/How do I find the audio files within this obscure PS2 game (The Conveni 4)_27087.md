## Post #1
- Username: SimpleSymphony
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 14, 2022 4:35 am
- Post datetime: 2023-08-10T05:13:07+00:00
- Post Title: How do I find the audio files within this obscure PS2 game? (The Conveni 4)

Hello! Recently I (a total newbie at file extraction) have been trying to rip the music out of a couple of the unripped Conveni games (namely 3, 4, and Special); while 3 and SP went fine, 4 seems trickier, as my ripping software only found these files:

SYSTEM.CNF (56 bytes)
SLPM_627.24 (2,852,024 bytes)
IOPRP300.IMG (275,345 bytes)
DUMMY.DAT (461,373,440 bytes)
IMAGE.BIN (38,103,570 bytes)
STRM_PAC.BIN (36,962,304 bytes)
a folder named MOVIE, containing LOGO.PSS (14,401,540 bytes) and OPENING.PSS (72,286,212 bytes). I know these are movie files, and I have no interest in extracting them, as I already have methods at the ready for them.
EOF.DAT (10,485,760 bytes)

File ripping software used: jPSXdec

I don't know how to search through these files to find audio, or what I could do to solve this issue, so help would be VERY appreciated! If you want to find the game files for yourself, look around the web for a way to access them, or I can find a way to send the files myself. If you have any questions, feel free to ask them as well! Thanks in advance!
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-10T09:11:02+00:00
- Post Title: How do I find the audio files within this obscure PS2 game? (The Conveni 4)

jPSXdec is only for PS1 games and wasn't meant to be used for PS2 games (even the common PS2 file formats are already differs from that of PS1 anyway).

If you're looking for the game's BGM it's in STRM_PAC.BIN file, but it only contains the audio data without any header. The header info file itself are located inside the IMAGE.BIN file, which you can extract with this QuickBMS script

```

IDstring "PACK"
get FILES long
for i = 0 < FILES
	get DUMMY longlong
	get OFFSET long
	get SIZE long
	getDstring NAME 0x40
	log NAME OFFSET SIZE
next i

```


After you extracted all the files, locate the BGM00.STR inside the sound directory and put it on the same place as the STRM_PAC.BIN.

Then install [vgmstream](https://vgmstream.org/) plugin and a media player (like [foobar2000](https://www.foobar2000.org/download)). Don't forget to configure the plugin to accept the unknown extensions (ex: in foobar preferences, check the "Enable unknown exts" in the vgmstream section). Then save these text below as STRM_PAC.BIN.txth and put it on the same directory as the STRM_PAC.BIN and BGM00.STR. 

STRM_PAC.BIN.txth

```
body_file = STRM_PAC.BIN

subsong_count = @0x04
base_offset = 0x0c
subsong_spacing = 0x1c

codec = PSX
data_size = @0x08
start_offset = @0x10 * 0x800
sample_rate = @0x14
channels = @0x18
interleave = @0x04 / channels

sample_type = bytes
num_samples = @0x0c * channels

```


Lastly just open or drag and drop the STRM_PAC.BIN and all the music should be there. I haven't implemented the support for loop points in the TXTH script though so most of game's BGM will end abruptly. And it's due to me unable to find where the value for the loop points was located.

Or if you prefer not installing another media player, you can use the commandline tool. The steps from "extracting the IMAGE.BIN" until "put the TXTH scripts in the same place as STRM_PAC.BIN and BGM00.STR" still applies. To make the tool extracts all of the subsongs instead of just one, you have to add the "-S 0" switch, like this:

```

```
## Post #3
- Username: SimpleSymphony
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 14, 2022 4:35 am
- Post datetime: 2023-08-10T18:00:42+00:00
- Post Title: How do I find the audio files within this obscure PS2 game? (The Conveni 4)

Thanks so much for the detailed advice! I'm a bt embarassed with how I used a PS1 tool for PS2 games, but hey, at least it worked for the other one! I want to use that QuickBMS script you posted, but when I downloaded it from aluigi's website, it doesn't seem to work for some reason. Every time I click the exe, a window pops up for a split second, then it disappears! Do you know how I could fix this issue? I'd use administrator mode for it, but I'm a bit scared too since the website set off my antivirus.
## Post #4
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-10T22:20:03+00:00
- Post Title: How do I find the audio files within this obscure PS2 game? (The Conveni 4)

> Reply from SimpleSymphony ↑Fri Aug 11, 2023 2:00 am at Fri Aug 11, 2023 2:00 am
>
> 
Thanks so much for the detailed advice! I'm a bt embarassed with how I used a PS1 tool for PS2 games, but hey, at least it worked for the other one! I want to use that QuickBMS script you posted, but when I downloaded it from aluigi's website, it doesn't seem to work for some reason. Every time I click the exe, a window pops up for a split second, then it disappears! Do you know how I could fix this issue? I'd use administrator mode for it, but I'm a bit scared too since the website set off my antivirus.

Normally it should initiate the GUI mode by default but it seems it doesn't work on Windows 11 anymore (if that's what you're using)
That means you have to do it manually by using Command Prompt:

```

```


Or save yourself some trouble by forgetting the GUI mode and extracting it the commandline way while you're at it:

```

ex:

quickbms image_bin.bms IMAGE.BIN IMAGE

```


Of course in case you're forget, the Command Prompt's working directory must have the quickbms.exe, the bms script for IMAGE.BIN extraction, and the IMAGE.BIN itself.
## Post #5
- Username: SimpleSymphony
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 14, 2022 4:35 am
- Post datetime: 2023-08-11T00:31:07+00:00
- Post Title: How do I find the audio files within this obscure PS2 game? (The Conveni 4)

It took a bit of time, but everything worked out great! Once again, thank you for all the help, I couldn't have done this without ya! If you ever find the loop points, please let me know!
