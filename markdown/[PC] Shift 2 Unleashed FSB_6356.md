## Post #1
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-04-04T20:10:58+00:00
- Post Title: [PC] Shift 2 Unleashed FSB

Musics are in "FSB" files. Probably they are encrypted. I used fsbext , fsb_mpeg , guessfsb & decfsb. But none of them worked properly.
How can i extract & play this fsb files?
thanks for helping.

sample:
[http://dl.dropbox.com/u/24956470/Music/nfs_fe_music.fsb](http://dl.dropbox.com/u/24956470/Music/nfs_fe_music.fsb)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-04T23:13:07+00:00
- Post Title: [PC] Shift 2 Unleashed FSB

the password is the following:

```
p&oACY^c4LK5C2v^x5nIO6kg5vNH$tlj
```
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-04T23:19:11+00:00
- Post Title: [PC] Shift 2 Unleashed FSB

a trick for anyone interesting in finding the FSB passwords on the fly (it took me some seconds so the term is correct):
- launch fsbext
- select the FSB file
- type ? as asked by the tool
- you should see some text data at the beginning of the first or second block
- open the executable or nocd executable of the game with a hex editor
- search the first 3 or 4 characters of the string you saw in fsbext
- for example in this case I searched the string "p&o"
- the key was there completely in plain-text :)

hope it helps in the majority of the cases when are used complex passwords like here
## Post #4
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-04-05T06:48:50+00:00
- Post Title: [PC] Shift 2 Unleashed FSB

Thanks aluigi!
## Post #5
- Username: matt55
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Apr 19, 2010 8:13 pm
- Post datetime: 2011-04-08T20:50:35+00:00
- Post Title: [PC] Shift 2 Unleashed FSB

I don't get it, From what encryption type I need to write characters?
I try to unlock an engine sound, it export it as .wav files but it shows, that to open them I need to write and option -A to make them openable.
## Post #6
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2011-04-28T18:00:21+00:00
- Post Title: [PC] Shift 2 Unleashed FSB

> Reply from matt55
>
> I don't get it, From what encryption type I need to write characters?
I try to unlock an engine sound, it export it as .wav files but it shows, that to open them I need to write and option -A to make them openable.

matt can i ask where'f you found the engine sounds? i can't find them anywhere. thanks man
anyway an answer to your question, read this thread, it will help you > [http://aluigi.freeforums.org/extract-th ... t1127.html](http://aluigi.freeforums.org/extract-the-audio-files-from-songname-fsb-xen-files-t1127.html)
## Post #7
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2011-05-08T16:00:40+00:00
- Post Title: [PC] Shift 2 Unleashed FSB

Thanks for the tools, aluigi.  They worked great on the game's music files. I've been wondering, though, if the quality of the output files is somehow managed by the fsbext tool or if they are simply extracted "as is", because they are rather low quality (~ 160 kpbs MP3).
## Post #8
- Username: Caterpillar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 18, 2011 9:02 pm
- Post datetime: 2011-05-18T13:06:26+00:00
- Post Title: [PC] Shift 2 Unleashed FSB

> Reply from aluigi
>
> a trick for anyone interesting in finding the FSB passwords on the fly (it took me some seconds so the term is correct):
- launch fsbext
- select the FSB file
- type ? as asked by the tool
- you should see some text data at the beginning of the first or second block
- open the executable or nocd executable of the game with a hex editor
- search the first 3 or 4 characters of the string you saw in fsbext
- for example in this case I searched the string "p&o"
- the key was there completely in plain-text 

hope it helps in the majority of the cases when are used complex passwords like here

I've launch fsbext and select the fsb file (from shift2), but the tool don't ask me the password.
