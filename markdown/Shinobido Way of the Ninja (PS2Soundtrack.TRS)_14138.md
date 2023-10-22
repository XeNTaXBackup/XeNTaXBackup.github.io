## Post #1
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-24T21:15:19+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Hi everyone, I'd like to extract the soundtrack of this game. The audio is stored inside a four archive in .TRS format: 

BGM.TRS
CUTIN.TRS
STPACK.TRS
VLETTER.TRS

Sadly I don't know how to open them.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-03-25T03:20:35+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Upload a sample of the files for people to take a look at
## Post #3
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-25T09:08:01+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Hi Brendan. Is it okay MEGA?
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-03-26T01:09:40+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

MEGA will be fine
## Post #5
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-26T11:58:17+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

I have uploaded the four audio archives:

Link 1 (Expired): [https://mega.nz/#!00YinbZC!pCNESbwUoHpL ... 5JCpba5HVU](https://mega.nz/#!00YinbZC!pCNESbwUoHpLfkOMqnFcE4rJojGYEbpvT5JCpba5HVU)
Link 2 (Expired): [https://mega.nz/#!x1pgUQzK!5grSfPp9qcgb ... ik6-iYS3tI](https://mega.nz/#!x1pgUQzK!5grSfPp9qcgbBMI5pzd80y-hLuSxWX7erik6-iYS3tI)
Link 3 (Expired): [https://mega.nz/#!8p42kAIR!jVdGVrH9wBGr ... PQcTzW8IzE](https://mega.nz/#!8p42kAIR!jVdGVrH9wBGrMROX5548-fP1yFlVY8r84PQcTzW8IzE)
Link 4 (Expired): [https://mega.nz/#!p1YRgTgQ!J1eNSjjm_Gt_ ... 22ZyNqkdUo](https://mega.nz/#!p1YRgTgQ!J1eNSjjm_Gt_AuU8Re5dGUP1dViK-Gr6522ZyNqkdUo)
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-27T11:31:09+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

The first file (BGM.TRS) has 156 music files.
## Post #7
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-27T20:07:39+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

And the others? Which of the four files contain the soundtracks ?
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-27T20:32:28+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

I only checked files 1 & 3.

1 - 156 music files
3 - more than 1000 of screams & shouts

I don't know what you mean under "soundtracks", I never seen this game.
## Post #9
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-28T11:03:02+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

The music of this game. 
At this link:

[https://downloads.khinsider.com/game-so ... -the-ninja](https://downloads.khinsider.com/game-soundtracks/album/shinobido-way-of-the-ninja)

it contain almost all the soundtracks of the game, published in a CD.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-28T15:35:40+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

That soundtrack was made from official release on iTunes. It's only 33 tracks (about 60 minutes), and the files contain at least 156.

Ok, I will try and help you extract it. Wait.

Get VGMToolbox, create genh with these values:

PlayStation 4-bit ADPCM
header 0x1fb8
interleave 0x20
channels 2
frequency 44100
no loops

This will give you 166 minutes long file with all music in one peace.  
Actually 95 minutes of music + 70 minutes of cut-scenes.
Some of it is 44100, some 48000. I think all music is 44100, and cut-scenes are 48000.
Listen to it. If it's ok for you, then we're done. If not, I can write a tool to cut all tracks with proper samplerate.
## Post #11
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-29T15:35:06+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Ok, but, now I have created the genh file with the your value, but the program has created only one compressed file in this format, and now? I tried to extract this genh achive with the program, but at the end, the program give me one more time the file .TRS.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-29T15:42:03+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

You can play GENH file or convert it to WAV with VGMStream.

I though you knew it.
## Post #13
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-29T15:46:32+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Sorry Daemon, but I don't understand. Can you help me telling me how to do? Thank you.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-29T15:50:25+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

download vgmstream.

there will be TEST.EXE

drag GENH file on TEST.EXE
## Post #15
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-29T16:04:41+00:00
- Post Title: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

I did what you told me, but sadly nothing happenned. I also attached a screenshot.
[1.JPG](https://xentaxbackup.github.io/file/10651_1.JPG)
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-29T16:38:57+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

I see its decoding the file. It's OK. Let it finish.
## Post #17
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-29T17:06:42+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

Hi, the program has extract the files, infact, i have loss about 640Mb of space, but I can't find the file, in the root of the folder which is present the program, there is no file extracted. What is the output file location?
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-29T17:15:41+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

its where you had GENH file
## Post #19
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-29T17:19:10+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

Desktop/New Folder/VGM/VGMStream (r1040-test)/Extracted/VGMStream (r1040-test)/ and in this folder I have insert the file BGM.genh which I have drag and release on test.exe, which it has extracted. But I can't find the extracted files.
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-30T16:36:37+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

file must be there. If not, just use search, or use command line to run test.exe
## Post #21
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-31T20:25:52+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

Ok, I'll try to do that.
## Post #22
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-03-31T22:20:05+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

Hi tried but nothing, the program consume only space, but the file not appear. I have "cmd.exe" in the vgmstream folder, I open the program, then I have inserted "test.exe" opening the "panel of control" of vgmstream, but when I'm write "test -o BGM.genh BGM.genh.wav" appear an error message: 

"Failed opening BGM.genh.wav" 

the same thing happened when I entered "test -o BGM.genh BGM.wav". What I must do?
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-01T04:22:53+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

> Reply from Carro2000
>
> Hi tried but nothing, the program consume only space, but the file not appear

Impossible. Can you make a screenshot of a folder with test.exe and your file?
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-01T04:43:16+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

> Reply from Carro2000
>
> but when I'm write "test -o BGM.genh BGM.genh.wav" appear an error

it must be "test -o BGM.genh.wav BGM.genh"
## Post #25
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-01T20:03:46+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

Hi, I have fix the problem using an version modified of vgmstream which permit me to select (manually) the input and the output of the selected file. So I have extracted for test prupose one song which is in ADPCM, then I have used VGMToolbox to convert the file with your parameter in .genh, but when I insert the file in test.exe and the program convert it, the music was only noisy.
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-01T20:36:52+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

if you are really sure you extracted the song right, use the same parameters, but header = 0.
## Post #27
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-01T21:34:57+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

Hi, I rerun the procedures with the header skip = 0, but the audio file now (unlike before which was in mono) is heavily obscured by interference noises.
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-02T06:18:30+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

> Reply from Carro2000
>
> Hi, I remade as you told me , however, with the header skip = 0 , but the file now , unlike before you can feel the music in mono , heavily obscured by interference noises .

that mean you extracted the song wrong. You must cut it exactly where it starts, or it will be noisy. I really suggest you to do as I said, extract the whole thing in one file and then cut it in audio form.
## Post #29
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-02T15:11:23+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

I understand. Just for curiosity, in the program how can I select the right preset for other games? 
What are the correct procedures to follow to understand it?
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-02T16:02:25+00:00
- Post Title: Re: Shinobido - Way of the Ninja (Rip PS2 Soundtrack) Please

You can be lucky if the game has the same format as some other game. The only way to be sure is to study the file carefully in hex editor.
## Post #31
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-04T20:39:33+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Daemon I try how you told me, the file works perfectly, however, there is a way to cut the music in their original length?
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-04T20:47:28+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

yes there is. But this will require coding
## Post #33
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-04T20:49:42+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Daemon, in what sense require coding? And you answered yes, precisely in what sense?

P.S. - Is there a program that allows me to cut the track by setting the beginning and end of the offset?
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-05T15:55:12+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Yes, meaning, there was a way to cut the music in their original length.

Yes, there is a program that allows to cut the track by setting the beginning and end of the offset.

But to do that, you need to find these offsets and cut all files manually, that will take a lot of time.
## Post #35
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-06T13:26:11+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Ok, Daemon what is the name of this program (Please the name of the most powerful and reliable program that there is)? For the offset I have all the information but for the BGM.TRS file, so I don't knows if the offset information of all song which I have are yet compatible with the archive converted in wav, but I would try.
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-06T17:02:52+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

> Reply from Carro2000
>
> Ok, Daemon what is the name of this program (Please the name of the most powerful and reliable program that there is)?

There's no difference which program you use. This is very simple action. Maybe you can try the same vgmtoolbox, "simple cutter", next to "advanced cutter" you already used. Just enter start/end offsets or length.

> Reply from Carro2000
>
> For the offset I have all the information but for the BGM.TRS file

You already tried some offset, and it was wrong. Why do you think now its right?
## Post #37
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-06T17:16:01+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

No Daemon, I never tried to extract audio tracks with offset, but I have used a program that help me to detect all the soundtrack positions from the compressed files, which it unfortunately extrapolated badly. Perhaps the first song have the offset that start at 8072 and end at 3902680, how I can cut? Can you help me, indicating the steps I need to perform?
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-06T18:09:33+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

no, first song start at   8120 and end at 3902776

1. put these numbers as start address & end address
2. click batch mode
3. type something in "output file extension"
4. drag the BGM into "source files"

with wrong offsets you'll get very noisy sound

after that you can really do it, using these 00 07 77 77 77 77 ...... 77 lines as a marker
## Post #39
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-06T19:02:05+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Hi Daemon, I have used "Cube Media Player 2" to locate the offset of the track, if so then it is not. How did you locate it? Please, tell me. However I did like you said, I have uploaded the file, selected "Batch Mode" and entered the numbers of start and end address. This procedure helped me to extract the song successfully, but sadly I have another problem, the tracks did not have a length (I refer to the duration), it indicates to me that it is only in .wav format, but when I try to boot it does not feel anything, why?


P.S. - Then what did you mean with "00 07 77 77 77 77 ...... 77 lines as a marker".
P.S.S. - Please hast another little patience with me
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-06T19:08:44+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

> Reply from Carro2000
>
> the tracks did not have a length (I refer to the duration), it indicates to me that it is only in .wav format, but when I try to boot it does not feel anything, why?

Please explain again, I don't understand.
## Post #41
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-08T15:42:45+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

ok I'm deleting your file again. If you feel you're ready to talk about this again, then let me know.
## Post #42
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-08T16:55:30+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Yes, sorry Daemon, I took a screenshot. The file which I have cutted is large 3.71 MB, but when I open the file I can't ear nothing, the track is silent and the system can't detect the lenght of the track.
[BGM.waw (Cut track).JPG](https://xentaxbackup.github.io/file/10749_BGM.waw (Cut track).JPG)
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-08T17:52:41+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

ah, ok. You're using google translator?

This file you got is not WAV file, its PS2 ADPCM, you need to decode it after you cut it.

PlayStation 4-bit ADPCM
header 0
interleave 0x20
channels 2
frequency 44100
no loops
## Post #44
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-08T20:08:16+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

(Yes, I use it partly to help me   )

Perfect, simply perfect, the track now is fixed, but Daemon now how can I find the exactly offset for the other tracks?
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-09T14:30:23+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Have you ever used hex editor?
## Post #46
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-09T15:22:26+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Yes Daemon, for hack some games to permit me to play them in widescreen. What should I do?
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-09T18:16:29+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

here i made a picture for you:


you can see for each file:

size (green), offset (yellow) ....... channels=2 (blue), interleave=0x20 (grey), sampling rate (red)

the first file offset you know already, so you must add this number for EVERY other file
you can use hex calculator for that
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-09T19:01:56+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

I mean you can see the first yellow field here = 00000000, because all offsets are relative to the beginning of audio part.
## Post #49
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-10T06:36:19+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Daemon can you tell me the program which you use for that?
## Post #50
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-10T07:26:27+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

any hex editor, they are all the same
## Post #51
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-10T11:07:53+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

I'm sorry, but I can't understand (the information that you wrote I understood it, but I can not get the information offset in decimal from the esadecimal). For example, the initial offset of the first track is 8120 and end 3902776, you make me understand how you managed to get these values?
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-10T11:18:11+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

You don't need decimal. In vgmtoolbox offset & size fields (just like all other fields) you can enter hex values. Like this:

0x1fb8
or
0x1FB8  (it doesn't matter)

There is a hex calculator in about every hex editor and also in Windows standard calculator. It also has a feature to translate to decimal, but why waste time? Use Hex.
## Post #53
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-10T11:54:32+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

But how do I extract the other tracks, I do not understand, if you talk to me that way, I will never understand, unfortunately I was not born an expert like you. You can do at least a screenshot of the steps I need to do to extract these tracks? And for the hex editor I'm using "HxD" that does not make me perform conversions, but just find and replace values, that's why I asked you what program you were using.
[1.JPG](https://xentaxbackup.github.io/file/10752_1.JPG)
## Post #54
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-10T13:14:21+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Ehm... so?
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-10T13:30:21+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

i can't answer right now, it can't be explained in 5 minutes.

so just relax, and do something else
## Post #56
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-10T14:16:29+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Excuse me, but for the desire to finally be able to extract them after so many years thanks to you, I did not realize that these things take longer than one imagined.
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-10T17:59:24+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

I was NOT born an expert either. I learned everything, and you can't learn everything in 1 hour. So be patient, read my previous messages again, if you need it, there was all information you needed.

And if you really want to know, I'm using Windows calculator to add hex values.

All your words about yellow numbers on the screenshot are right. With one exception. It would be true if audio data started from the beginning of the file, 0 offset.

But as I said, offsets are relative. So next let me give you an example of how to extract track 2.
## Post #58
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-10T18:04:20+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

track 2:

offset 3B6D80, size 2E2F80 (yellow and green numbers)

now add 1FB8 to the offset:

3B6D80 + 1FB8 = 3B8D38

Use "programmer mode" in calculator, also click on "hex", and you can copy/paste values

Now you enter 0x3B8D38 and 0x2E2F80 as "start address" and "length" in simple cutter, as you did before.

After you cut the track, don't forget to decode it as usual
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-10T18:07:07+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

also note, that nobody usually cuts 52 tracks manually. You usually write a tool or script for that.
## Post #60
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-10T22:15:35+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Thank you Daemon, but please do not get me wrong, what I said was not an accuse to justify my difficulty in understanding you, but it was just a compliment (but in fact reading, more than a compliment it seems an offense). Unfortunately I know it all too well that one hour is not enough (indeed nothing) to understand all of this, and for that I wrote you so, just to let you know that what you told me I had trouble understanding it, apart from a few details. When I have time I will do as you tell me. 
Thanks again for all, especially for the great patience you are having.
## Post #61
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-13T16:12:22+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

Daemon I've done all the steps and it works, I applied the same method to other tracks and it works! Anyway I noticed that the archive contains 82 audio tracks, but it is obvious that many of them are for the cutscene. Only one thing I would like to ask you. Why do I need to apply this value "1FB8" to the offset? It applies to all tracks encoded in ADPCM? How can I understand the value that I have to give to another track encoded in a different way? 
Thank you very much
## Post #62
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-13T16:36:47+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)

This is the size of the header. And offsets in this file are relative.

In some other game offsets may be absolute, and you don't have to add anything.
## Post #63
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2016-04-13T16:42:39+00:00
- Post Title: Re: Shinobido: Way of the Ninja (PS2/Soundtrack/.TRS)


