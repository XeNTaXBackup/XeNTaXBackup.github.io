## Post #1
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2011-12-21T02:30:28+00:00
- Post Title: Star Wars: The Clone Wars extracted wav

The following file was extracted from common.xwb from the Xbox version of Star Wars: The Clone Wars, however I'm not sure whether the extraction went properly. It extracted the files as XMA wav files, however xmaencode can't decrypt them and I can't import them as any type of raw file in Audacity. Perhaps someone else can shed some light on this.
[SW_CW.zip](https://xentaxbackup.github.io/file/4923_SW_CW.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2011-12-21T05:25:45+00:00
- Post Title: Star Wars: The Clone Wars extracted wav

MFAudio says it is compressed. 
GSpot info says it is 11025Hz  22 kb/s (1 chnl)

```
    groupID[4]	         RIFF	
    size	               2888	  	
    riffType[4]	        WAVE	

format	                		
    chunkID[4]	         fmt 
    chunkSize	          52	
    wFormatTag	         358	
    wChannels	          1     	
    dwSamplesPerSec	    11025	
    dwAvgBytesPerSec      2808		
    wBlockAlign	        4	               	
    wBitsPerSample	     16		
    unknown[36]		        	

unknown		               	
    chunkID[4]            seek    
    chunkSize             0

data		                       	
    chunkID[4]	         data		
    chunkSize	          2808		
    samples[1404]
```


EDIT
extract the wav files from common.xwb with [unxwb](http://aluigi.altervista.org/papers/unxwb.zip)
convert the xma wav files to wav with [xbadpdec](http://aluigi.altervista.org/papers/xbadpdec.zip)

batch file to convert the whole folder

```
for %%G in ("%~dp0"\*.wav) do xbadpdec "%%G" "new_%%~nxG"
```
## Post #3
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2020-05-22T02:18:42+00:00
- Post Title: Star Wars: The Clone Wars extracted wav

Pardon me, but I think the file bits are much higher than that. Somebody else managed to extract the sound files from the game, but they are at their proper speed and pitch at 22050 Hz. Here is where the sounds are: 
[https://www.sounds-resource.com/xbox/st ... ound/9074/](https://www.sounds-resource.com/xbox/starwarstheclonewars/sound/9074/)
[https://www.sounds-resource.com/xbox/st ... ound/9078/](https://www.sounds-resource.com/xbox/starwarstheclonewars/sound/9078/)

I found the sounds you posted elsewhere, but they don’t possess the quality these sounds on VG-Resources has. I hope you’re able to get the sounds at a better quality with their names to identify them.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-05-23T11:00:44+00:00
- Post Title: Star Wars: The Clone Wars extracted wav

While the other .wav files in the game are higher quality PCM audio, the sounds in common.xwb are only 11025/mono/XBOX ADPCM.

Not sure what you used to extract them, but my attached script will extract them correctly in a playable format, with the right filenames.
[swcw_xwb_xbox.zip](https://xentaxbackup.github.io/file/18199_swcw_xwb_xbox.zip)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-05-24T00:55:56+00:00
- Post Title: Star Wars: The Clone Wars extracted wav

> Reply from ARAJediMaster ↑Fri May 22, 2020 10:18 am at Fri May 22, 2020 10:18 am
>
> Somebody else managed to extract the sound files from the game, but they are at their proper speed and pitch...
great! i'm glad progress was made in the 9 years since the last post.   

> Reply from ARAJediMaster ↑Fri May 22, 2020 10:18 am at Fri May 22, 2020 10:18 am
>
> I found the sounds you posted elsewhere, but they don’t possess the quality these sounds on VG-Resources has. I hope you’re able to get the sounds at a better quality with their names to identify them.
you must have me confused, i have posted no sounds anywhere, audio is not my field.
## Post #6
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2020-05-24T14:55:20+00:00
- Post Title: Star Wars: The Clone Wars extracted wav

Actually, I had found that somebody on GameToast had released the assets to “Star Wars: The Clone Wars” here: [http://www.gametoast.com/viewtopic.php?f=64&t=25926](http://www.gametoast.com/viewtopic.php?f=64&t=25926), and I presumed that “AceMastermind” was you, Acewell. Please pardon me for my mistake. I was hoping to get the sounds from the game at a high quality with the name files attached to them.
