## Post #1
- Username: LividBunny
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 25, 2023 10:00 am
- Post datetime: 2023-07-25T02:54:04+00:00
- Post Title: Wish to extract Prince of Persia SoT PS2 Japanese Sound Files

If anyone wouldn't mind trying....

[https://www.mediafire.com/file/bl8qdqdw ... 2.zip/file](https://www.mediafire.com/file/bl8qdqdwi21un0i/SOUNDPS2.zip/file)
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-07-25T10:26:32+00:00
- Post Title: Wish to extract Prince of Persia SoT PS2 Japanese Sound Files

To extract SoT FAT/BIG files you can use the PoP_Sound_Repacker tool ([link](https://drive.google.com/file/d/1TmaExAMTBw574Q_ZdmDidpJ4L2pcWm7t/view?usp=sharing)) or my QuickBMS script below which more or less do the same thing minus the repacking.

```

open FDDE FAT
open FDDE BIG 1

get FAT_SZ asize
for i = 0
	savepos TMP
	if TMP >= FAT_SZ
		break
	endif
	get CURR_POS long
	get OFFSET long
	get SIZE long
	get ZERO long
	get NAME_LEN long
	getDstring NAME NAME_LEN
	log NAME OFFSET SIZE 1
next i

```


SB1 files are playable in vgmstream.
LS1/SS1 files however are not. But you can use DecUbiSnd to open and preview/export them to wav. Just set all the audio frequencies to 22050 Hz so they are sounded correct.
## Post #3
- Username: LividBunny
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 25, 2023 10:00 am
- Post datetime: 2023-07-25T13:23:11+00:00
- Post Title: Wish to extract Prince of Persia SoT PS2 Japanese Sound Files

I did find PoP_Sound_Repacker tool while looking for a way to extract for the PC version and tried on the PS2 files after but it didn't work at the time.
-Somehow it works now? WTF is this sorcery?-
Thank you, sorry for your time. v-v

Edit: Oh right, it can't extract that's what I was forgetting... <-<

Edit2: Script worked fine tho, Thanks.
