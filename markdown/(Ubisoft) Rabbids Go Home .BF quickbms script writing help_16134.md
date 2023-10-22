## Post #1
- Username: SecretAgent2001
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 18, 2016 11:18 am
- Post datetime: 2017-04-13T00:43:35+00:00
- Post Title: (Ubisoft) Rabbids Go Home .BF quickbms script writing help?

The game Rabbids Go Home consists of three .BF archives that make up the game, two of which have the game's sounds: RGH.BF (0.98 GB) and RGH.wii.sns.BF (734 MB). The sounds from the latter file have been extracted and played successfully; however, there was little luck of getting the sound files from the other file. Upon extraction, RGH.wii.sns.BF yielded 13,383 .sns files, all of which could be converted to .wav via vgmstream. They all had a RIFF/WAVE header, too: [http://i.imgur.com/aKn4r4P.png](http://i.imgur.com/aKn4r4P.png). When extracting RGH.BF, it gave off heaps of random files with either unknown or no file extensions. This is probably because this file consists of the game's programming, models, etc., as well as the sounds. There were some .sns files, but they didn't have RIFF headers and were simply pointers to the sounds in RGH.wii.sns.BF ([http://i.imgur.com/XWpt2RK.png](http://i.imgur.com/XWpt2RK.png)). I know that sounds exist in this file, because, upon further examination and opening the unextracted file in a hex editor, there were some RIFF/WAVE headers buried within the code. The extracting script crammed these headers and some of their content in some of the unknown files I had mentioned earlier, but the RIFF/WAVE headers weren't actually headers in this case and were simply sitting in the middle of the file: [http://i.imgur.com/uuHTmqE.png](http://i.imgur.com/uuHTmqE.png). Not all files had these headers shoved randomly into them.

Since there is no way the sounds can be gotten via these methods, I need someone to modify and rewrite the script I used to extract the files (as this script was used for the same engine, but a different game) or create a new script altogether to extract these sounds and to solve this mystery once and for all. Help is very much appreciated.

Here's the bms script I used: [http://aluigi.altervista.org/bms/tintin.bms](http://aluigi.altervista.org/bms/tintin.bms)
And here's the file I need the sounds to be extracted from: [https://mega.nz/#!OoQlkKbD!3JsIHbaqOKXM ... QB1sEEriCw](https://mega.nz/#!OoQlkKbD!3JsIHbaqOKXMwhYJLNPWtut0-pm7av-2EQB1sEEriCw) (0.98 GB, I know, but I deeply appreciate the effort people will give me to help me out)
## Post #2
- Username: SecretAgent2001
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 18, 2016 11:18 am
- Post datetime: 2017-04-14T11:41:24+00:00
- Post Title: (Ubisoft) Rabbids Go Home .BF quickbms script writing help?

Anyone?
## Post #3
- Username: SecretAgent2001
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 18, 2016 11:18 am
- Post datetime: 2017-04-20T00:01:27+00:00
- Post Title: (Ubisoft) Rabbids Go Home .BF quickbms script writing help?

Bumping in a hope that this question gets answered.
## Post #4
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-20T00:18:21+00:00
- Post Title: (Ubisoft) Rabbids Go Home .BF quickbms script writing help?

My unfinished script deals with these kind of archives, yet I have yet to support the new .bf format you`ve shown because the tintin.bms script doesn`t get the directory tree right yet.

Not to mention that I`ve tried to make the directory tree just right, but then it proved to be the most difficult part of the researching process.

Oh wait, we`re talking about sounds here. Well, in any case the "random file" you`re talking about is just that. You can use the latest version of vgmtoolbox and then "Misc. Tools" -> "Extraction Tools" -> "Generic" -> "Advanced Cutter/Offset Finder". Once there, find an second white bar with "Presets" written below it. Click on that arrow of that white bar and click on "RIFF Style Header". Finally, click on "Load" and on the left side of that second white bar, you can drag-and-drop the file you`re having trouble with. Depending on how many RIFF files there are, the "tool" will try to extract many .wav files in the same directory as the file you drag-and-dropped on.

If this is not the solution to the problem, then I don`t know how to help you.
## Post #5
- Username: SecretAgent2001
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 18, 2016 11:18 am
- Post datetime: 2017-04-20T02:49:44+00:00
- Post Title: (Ubisoft) Rabbids Go Home .BF quickbms script writing help?

Thanks for your reply. Unfortunately, running the file through vgmtoolbox just gives off an unplayable .wav. I even tried running the .sns files that vgmstream successfully converted before, and they didn't even work. So, I guess the only solution to this is rewriting that bms script, so that the sound files are arranged correctly and can be run through vgmstream without any problems (like the .sns ones). 
Does anyone know any good script writing tutorials so I can try to tackle this script-writing problem myself? And what are the minimum requirements of a script to extracting a file? In other words, how many arguments do you need to write in a script to successfully extract files from the archive?
## Post #6
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-20T15:05:48+00:00
- Post Title: (Ubisoft) Rabbids Go Home .BF quickbms script writing help?

Not as I know of.
## Post #7
- Username: louisboss99
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 28, 2017 9:21 am
- Post datetime: 2017-10-13T00:46:07+00:00
- Post Title: (Ubisoft) Rabbids Go Home .BF quickbms script writing help?

Rabbid's go home uses Ubisoft's engine name Lyn not jade (just so you know)
## Post #8
- Username: oshul
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 18, 2018 2:06 am
- Post datetime: 2018-03-18T10:06:05+00:00
- Post Title: (Ubisoft) Rabbids Go Home .BF quickbms script writing help?

how did you extract the files?
