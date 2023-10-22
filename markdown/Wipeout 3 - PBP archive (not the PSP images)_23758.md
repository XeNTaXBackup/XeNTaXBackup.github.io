## Post #1
- Username: WalterNEST
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 16, 2018 3:41 am
- Post datetime: 2021-04-18T02:19:48+00:00
- Post Title: Wipeout 3 - PBP archive (not the PSP images)

Since the extractor linked on Wipeout zone seems to be gone...
[http://www.wipeoutzone.com/forum/showth ... ile-format](http://www.wipeoutzone.com/forum/showthread.php?9953-About-the-PBP-file-format)
I tried to figure out how to get the files myself - I managed to successfully split the archives to file chunks by making a fairly simple QuickBMS script.

```
# script for QuickBMS http://quickbms.aluigi.org

open FDDE "pbp"

set PATH string ""
callfunction EXTRACT

startfunction EXTRACT
	goto 0x80
    get FILES long
    for i = 0 < FILES
		set OFFSET 0x88
		set OFFSET_ADD 0xC
		math OFFSET_ADD * i
		math OFFSET + OFFSET_ADD
		goto OFFSET
        get OFFSET long
		get DUMMY long
		get SIZE long
        goto OFFSET
        log "" OFFSET SIZE
	next i
endfunction
```


Some of the files come out in same format as .cmp images in Wipeout/Wipeout 2097 and can be converted to .tim openable by a TIM viewer. I attached extracted texture of Qirex ship. However other files don't seem to have any common headers and are probably compressed in some way. Assuming the tracks are built in same or similar way as in previous games, the biggest file of a particular track should be the model containing the geometry to be placed around the track. Possibly again in .prm format.
[https://drive.google.com/file/d/12ZH82_ ... sp=sharing](https://drive.google.com/file/d/12ZH82_8v44sKT320WP7s7jE-ubdvWMyz/view?usp=sharing)
This is the biggest file by far, the 2nd and 3rd biggest files are textures of the track and textures of the environment (in .cmp format) at around 80kB each. All the other files are significantly smaller - most of them below 10kB.
If anyone could figure out how to turn the file into something usable it would be awesome 
[qirex_w3.jpg](https://xentaxbackup.github.io/file/19919_qirex_w3.jpg)
## Post #2
- Username: WalterNEST
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 16, 2018 3:41 am
- Post datetime: 2021-04-18T02:35:11+00:00
- Post Title: Wipeout 3 - PBP archive (not the PSP images)

Here is a zip with all the files from TRACKS01.PBP which is Porto Kora track. As far as I can tell, each track file has all the files necessary to play the track which includes all the ship models and possibly all assets including sounds. The ships textures definitely are copied into every track archive.
[https://drive.google.com/file/d/1TellOT ... sp=sharing](https://drive.google.com/file/d/1TellOTBzzdNlZbAuoV7Yh0aK9bl05f-8/view?usp=sharing)
PS: It seems 0000000a.dat and 0000000b.dat do have some sort of header with a lot padding and 2 groups of values.
