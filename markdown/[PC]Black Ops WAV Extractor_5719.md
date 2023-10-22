## Post #1
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-06T23:46:39+00:00
- Post Title: [PC]Black Ops WAV Extractor

In all the previous COD games the .wav files inside the .iwd archives were valid and could've simply been extracted, but Treyarch has changed that in their newest title, Call of Duty: Black ops by removing the standard wav header from the wavs and adding their own. As some have already requested a fix tool for that, I made this as soon as possible so you can get the music, voices and sfx from the game. The tool simply extracts the .wavs from the .iwd archives you drag in the .exe and it also fixes them along the way by parsing the data from Treyarch's own wav headers. Further instructions and info are included in the read_me.txt.

Name = Black Ops WAV Extractor

Author = Chronic

Category = Rippers (audio tools)

Game supported = Call of Duty Black Ops

File formats = .wav, .iwd

Platform = PC

Description = A tool that, along the usual extraction of .wav sound files, also fixes them due to their lack of a standard WAV header by parsing data from Treyarch’s own .wav headers. More info in enclosed read_me.txt

Version = 1.1

Filesize =  224 KB

Download = [http://gljivolog.com/data/releases/bo_rip_fix.rar](http://gljivolog.com/data/releases/bo_rip_fix.rar)

System = Windows

License = Public domain

Opensource = No
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-01-08T09:00:47+00:00
- Post Title: [PC]Black Ops WAV Extractor

COOL!
## Post #3
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-09T14:38:17+00:00
- Post Title: [PC]Black Ops WAV Extractor

An update has been released for Black Ops Sound Extractor, fixing the exploit of wrong length detection in certain audio/video programs. Now the lengths are correctly calculated.
Download link in the previous post updated.
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-01-26T20:40:08+00:00
- Post Title: [PC]Black Ops WAV Extractor

Hope im not bumping, but any thoughts about support for the wave data in .ff files? once you dezlib them, its the same debacle, but i can't seem to get any header working on them.
## Post #5
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-01-29T12:17:14+00:00
- Post Title: [PC]Black Ops WAV Extractor

Sure, thanks for noting that, didn't even think there would be any samples in .ff's. I'll take a look at it when I have the time and update the tool.
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-01-30T14:57:38+00:00
- Post Title: [PC]Black Ops WAV Extractor

Yeah, its the gunshots and misc sounds mainly, you can tell when you find one in a hex editor, because it has a file path for it, and then the data. I.e.: sound\wpn\flame\dyn_fire\dyn_fire_00_l.wav  (followed by data). they seem to mostly be at the end segments of .FF files, the last 20mb or so of the dezlib'd chunk.
## Post #7
- Username: Chronic
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Jan 06, 2011 7:36 pm
- Post datetime: 2011-07-07T17:03:33+00:00
- Post Title: [PC]Black Ops WAV Extractor

@Pepper: Sorry for such a late reply, but I'm afraid I can't do anything about the .ff .wav files as they are not in the same format as the .iwd ones. They usually have paths pointing to the same folders as in the .iwds, but there are no such .wavs in the .iwds, so those are unique to the .ff files.

Anyway, I've prepared a significant update for the WAV (samples, music) extractor for Call of Duty: Black Ops, which now includes a log file, an .ini config file and can generate a .m3u playlist of all extracted .wavs whose name you can choose (for every session). and is much, much faster. For instance, I managed to extract .wavs from all the 33 .iwd files in approx. 7 mins. The previous one was too slow, took about 3 mins for 1 .iwd; now it's a matter of seconds for most .iwds. Also, it produces slightly smaller fixed .wav files, but with no change in audio fidelity.

Please do read the read_me.txt included in the package as it includes some important new info.

Download BLOPS2WAV v2.0 from here [http://gljivolog.com/data/releases/bo_rip_fix.rar](http://gljivolog.com/data/releases/bo_rip_fix.rar) or here: [http://gljivolog.com/data/releases/blops2wav.rar](http://gljivolog.com/data/releases/blops2wav.rar)
## Post #8
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-07-13T01:01:17+00:00
- Post Title: [PC]Black Ops WAV Extractor

Yeah, they are a different format. and guess what. the blops mod tools beta on steam is released, they included all the wav files in a "RAW" folder, but the sounds still are this weird format, probably some kind of xwma or adpcm like WAW (which had a combo of a few xwma files here and there), but when you give something to modders and content devs to use and put it in a folder named "raw", i'd expect it to be, well, standard wav data. Damn you treyarch!
