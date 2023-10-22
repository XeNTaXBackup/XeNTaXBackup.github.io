## Post #1
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-02-28T16:38:38+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

Hi,

I was trying to get the multitracks and loops out of Amplitude, so I started to work with the .str files. Unfortunately it was only possible to extract a .wav file out of it and that was not the multitrack folder. The multi-channel songs are in the "main.ark" data but of course I can't extract anything. That arktool programm doesn't work and I managed to find a line in that file 
```
Decrypt_28L....Decrypt_28R [...] R:\FREQ2\FreQ2_Metagame\Song Encrypt Audio\Decrypt_28L.wav:...R:\FREQ2\FreQ2_Metagame\Song Encrypt Audio\Decrypt_28R.wav
```


Many of the Files are in .wav format (ps2 console! wtf?!) 
```

R:\FREQ2\FreQ2_Game Levels\supersprode\Wav Slices\Bass\qy_chor_blipbass\qy_chor_blipbass 22K\qy_chor_blipbass_44 030_22.wav
```


Any suggestions how to open, encrypt or extract that file? This game is from Harmonix and people managed to hack GH1/RB1 - 2009, so a game from 2003 should be easier? Plus it contains extremely rare loops. Any RB or GH hacking vets here?

Thx for your help
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T11:31:10+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

no file no party :)

that 28L and 28R sounds like left and right, maybe it's a simple rotate_left/right?
would be too simple, anyway I can give it a 30 seconds look
## Post #3
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-03-01T11:56:32+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

should I upload parts of the file or sth? I don't have a clue what to do and the encrypted files would be incredible great...
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T11:59:27+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

as far as I have understood only the wav files are encrypted right?
so start uploading one of them (the smallest)
## Post #5
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-03-01T12:56:46+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

> Reply from aluigi
>
> as far as I have understood only the wav files are encrypted right?
so start uploading one of them (the smallest)

No the thing is, I only have the .ark file and the .wavs, .bnk and loops are in it. I have no idea how to extract them and even if I could do that, they would be encrypted (as good as it was possible for harmonix in 2003). I can upload the "main.ark" file (over 1GB) if you think that you are capable of doing sth with it.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T13:19:22+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

maybe upload only the first 10 megabytes.
but as it sounds it doesn't seem something on which I can do something
## Post #7
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-03-01T13:45:33+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

fist 10mb: [http://www.mediafire.com/?mi49lixao4qr221](http://www.mediafire.com/?mi49lixao4qr221)
last 6mb: [http://www.mediafire.com/?fsl17tg1llfdeh7](http://www.mediafire.com/?fsl17tg1llfdeh7)

If you can't do this: do you know any user who is experienced in such things?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T14:42:34+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

try this one with quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get DUMMY long
get FILES long
math OFFSET = FILES
math OFFSET *= 20
math OFFSET += 8
goto OFFSET
get SIZE long
math OFFSET += 4
log MEMORY_FILE OFFSET SIZE
math OFFSET += SIZE
goto OFFSET
get ENTRIES long
savepos OFFSET
math SIZE = ENTRIES
math SIZE *= 4
log MEMORY_FILE2 OFFSET SIZE
goto 8
for i = 0 < FILES
    get OFFSET long
    get NAME_OFF long
    get FOLDER_OFF long
    get SIZE long
    get DUMMY long

    math NAME_OFF *= 4
    goto NAME_OFF MEMORY_FILE2
    get NAME_OFF long MEMORY_FILE2
    goto NAME_OFF MEMORY_FILE
    get NAME1 string MEMORY_FILE

    math FOLDER_OFF *= 4
    goto FOLDER_OFF MEMORY_FILE2
    get FOLDER_OFF long MEMORY_FILE2
    goto FOLDER_OFF MEMORY_FILE
    get NAME string MEMORY_FILE

    string NAME += /
    string NAME += NAME1

    log NAME OFFSET SIZE
next i
```
## Post #9
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-03-01T15:22:10+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

Thank you so much, you are incredible!!! It worked perfectly. Now I have to find the song files... I spotted the "sound" folder with .bnk files in it. I don't know if they contain the loops but there are also .mid files of the songs, so it has to be the right one.

what do you say?: [http://www.mediafire.com/?igi6h4zaifk4o1s](http://www.mediafire.com/?igi6h4zaifk4o1s)
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T15:48:10+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

the str files seem to contain raw audio at 32khz, 16bit stereo.
it sounds a bit noisy so it's not to be excluded a light codec used on it (adpcm?)

the rest seems almost like a midi and sound instruments, for sure an "original" solution.
anyway there is for sure someone with more experience than me that can say something useful
## Post #11
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-03-01T16:03:54+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

The .str is a preview. Thanks to Jaeder Naub, which can convert .str files into .wavs. Well I hope that someone can help...
## Post #12
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-05-15T21:59:38+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

Push. And 25$ or more payment for the first one who can decrypt the files. I need the loops and stems, then I'll pay   

Hopefully this is an incitement for you
## Post #13
- Username: marlborox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 09, 2011 10:03 am
- Post datetime: 2011-05-17T18:43:48+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

does the script work on the whole ark file as it only extracted around 5mb worth before it gave an error extracting from an offset?
## Post #14
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-05-18T22:09:44+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

> Reply from marlborox
>
> does the script work on the whole ark file as it only extracted around 5mb worth before it gave an error extracting from an offset?

The script should work, it extracted everything from the main.ark file (arenas, attract, audio, cnf, ...). Are you using the full game (.iso file)?
## Post #15
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-05-20T01:50:35+00:00
- Post Title: Amplitude .ark (multitracks, stems) decryption

> Reply from marlborox
>
> does the script work on the whole ark file as it only extracted around 5mb worth before it gave an error extracting from an offset?

I have same error, I try with PAL full version
## Post #16
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-05-20T17:27:36+00:00
- Post Title: Re: Amplitude .ark (multitracks, stems) decryption

> Reply from grotesque
>
> marlborox wrote:does the script work on the whole ark file as it only extracted around 5mb worth before it gave an error extracting from an offset?

I have same error, I try with PAL full version

I have the EU version, so maybe get the Amplitude_Eu.iso version. By the way, thanks for your help. I'm maybe going up to 50$.
## Post #17
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-05-20T19:01:54+00:00
- Post Title: Re: Amplitude .ark (multitracks, stems) decryption

> Reply from kain34
>
> grotesque wrote:marlborox wrote:does the script work on the whole ark file as it only extracted around 5mb worth before it gave an error extracting from an offset?

I have same error, I try with PAL full version

I have the EU version, so maybe get the Amplitude_Eu.iso version. By the way, thanks for your help. I'm maybe going up to 50$.

You talk about pirate version?
Because I extract the file from my original dvd...
## Post #18
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-05-21T10:41:22+00:00
- Post Title: Re: Amplitude .ark (multitracks, stems) decryption

> Reply from grotesque
>
> You talk about pirate version?
Because I extract the file from my original dvd...

No? But you can rip the game from your original dvd into an .iso file. No pirated versions in this thread
## Post #19
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-05-21T11:08:22+00:00
- Post Title: Re: Amplitude .ark (multitracks, stems) decryption

I extract main.ark direct from dvd (copy/paste) and from iso, but same result:
## Post #20
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-05-21T23:07:08+00:00
- Post Title: Re: Amplitude .ark (multitracks, stems) decryption

> Reply from grotesque
>
> I extract main.ark direct from dvd (copy/paste) and from iso, but same result

That's just strange   
Something seems to be wrong... maybe the script must be changed.

And what if I give you the sound folders, so you can experiment with them?!
[http://www.mediafire.com/?igi6h4zaifk4o1s](http://www.mediafire.com/?igi6h4zaifk4o1s)
