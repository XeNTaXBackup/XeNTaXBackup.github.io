## Post #1
- Username: Moon
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 06, 2004 12:08 am
- Post datetime: 2004-05-05T16:32:56+00:00
- Post Title: Question about one new game and two not that new.

I was looking for support for these games in a number of utilities, but nothing seems to have it... so I thought I'd ask...

The new game is "Conan"; the game itself is very bad, but it's supposed to have some new themes by Basil Poledouris who scored the "Conan" film, and that's why I was interested in extracting the music. Unfortunately, the .wav files with the music seem to be encrypted in some way... I tried a number of extractors/identifiers and converters on them, and nothing recognized them. If you're interested in a look, the demo can be found e.g. here: [http://www.3dgamers.com/games/conan/](http://www.3dgamers.com/games/conan/)

The first older game is "Project IGI". I was trying to extract "stuff" from it a while ago, but couldn't; I ended up taking screenshots and recording music and sounds through Wave output. 

The older game is "Indiana Jones and the Infernal Machine". I found utilities capable of extracting the smaller files from the game's big resource libraries (.GOB) but the most interesting extracted files, such as graphics and sound, seem encrypted or compressed. (Once again, I was mostly interested in the music from the game.) It seems to be stored in large .CND files that may also be partially encrypted or packed. (Partially, since there is some readable text inside, but much contents of the files seem packed)

A demo of "Indy" is e.g. here:

[http://www.lucasarts.com/products/indy/indydemo.exe](http://www.lucasarts.com/products/indy/indydemo.exe)

And here are three tools that I used to extract stuff from the .GOBs:


Oh, and this is not that related, but nobody on the "Soldier of Fortune" forums new and the developers wouldn't tell, so perhaps someone here would know - what is the format of the .ADP files that the first "SoF" stored its music in? They looked like a packed sound format - I even thought they would be simply MP3s - but no sound utility would recognize them.
[Gobs.rar](https://xentaxbackup.github.io/file/17_Gobs.rar)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-11T22:47:00+00:00
- Post Title: Question about one new game and two not that new.

Okay, that are a lot of games to support!   

Anyway, yeah, I'm a bit busy with my job and the Painkiller business (as you may have noticed) but I did not forget to read your post. 

I will help whenever I can! I just can't give an estimate when it will be done. I hope you understand.
## Post #3
- Username: Moon
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 06, 2004 12:08 am
- Post datetime: 2004-05-27T23:54:26+00:00
- Post Title: Question about one new game and two not that new.

I've found something to deal with IGI 

[http://www.extractor.ru/download_your.phtml#is_wav](http://www.extractor.ru/download_your.phtml#is_wav)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-11T19:13:50+00:00
- Post Title: Question about one new game and two not that new.

> Reply from Moon
>
> 
The new game is "Conan"; the game itself is very bad, but it's supposed to have some new themes by Basil Poledouris who scored the "Conan" film, and that's why I was interested in extracting the music. Unfortunately, the .wav files with the music seem to be encrypted in some way...

Unfortunately I don't have a solution (except the usual recording way) but have some information which could be useful in a possible future.
The wave files are not encrypted but use just an audio codec (type 69), ADPCM as written in the game executable.

Then also a note about the .GCM files which are files compressed with an enough simple algorithm but aren't package files and don't contain readable text, I think they are compressed textures or something similar since my video driver then used this data.
## Post #5
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-12T11:31:18+00:00
- Post Title: Question about one new game and two not that new.

"Conan" wave files just standard Xbox ADPCM.You need install XboxADPCM codec and all play whithout problem.
[xb_adpcm_codec.rar](https://xentaxbackup.github.io/file/490_xb_adpcm_codec.rar)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-17T13:39:59+00:00
- Post Title: Question about one new game and two not that new.

I didn't resist and wrote a xbox adpcm to wave converter 8-)

[http://aluigi.altervista.org/papers.htm#others-file](http://aluigi.altervista.org/papers.htm#others-file)

So also the users of any other operating system can hear this files.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-17T15:41:38+00:00
- Post Title: Question about one new game and two not that new.

> Reply from Bugtest
>
> I didn't resist and wrote a xbox adpcm to wave converter 

http://aluigi.altervista.org/papers.htm#others-file

So also the users of any other operating system can hear this files.

Would you add these new tools you write to the [http://wiki.xentax.com/index.php/Game_Tools](http://wiki.xentax.com/index.php/Game_Tools) section of the WIKI? Would be great!!
## Post #8
- Username: WaltDizzy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 08, 2006 2:08 am
- Post datetime: 2006-01-07T18:36:36+00:00
- Post Title: Question about one new game and two not that new.

I'd love to see that Indy CND music converted to WAV or MP3, too
## Post #9
- Username: Vess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 08, 2006 2:14 am
- Post datetime: 2006-01-27T18:26:05+00:00
- Post Title: Question about one new game and two not that new.

Fun fact about Infernal Machine and Windows XP: it will probably not work on XP and Lucasarts "engineers" will shake their heads and say "It's impossible to fix".

Yes. Except... to have it running perfectly under XP, simply start up MS's MediaPlayer and then run the game. Keep MP running in the background - don't open anything in it, just have it active before the game is run and while it's running. It will work without crashing now.
## Post #10
- Username: Vess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 08, 2006 2:14 am
- Post datetime: 2006-02-19T05:01:16+00:00
- Post Title: Question about one new game and two not that new.

Some more information (and that's about as much as I can find on my own, the rest would have to be looked into and explored by a programmer or maybe the game's developer ). The GOB files contain the big CND ones. The CNDs seem to hold 90% of the game - multiple textures and sounds. If you view them, you can see file names inside...

There appear to be Jedi Knight .MAT ([http://www.massassi.net/programs/](http://www.massassi.net/programs/) , [http://www.lactarius.com/sylvicolus/jk/mats.shtml](http://www.lactarius.com/sylvicolus/jk/mats.shtml)) files in there, but with removed or encrypted headers. If you copy some of that data to headers of "normal" MAT files, you can actually see some garbled graphics from the game.

A section of each CND files seems to contain sounds: there is a sound name followed by binary data. Each segment of the binary data seems to begin with "WVSM" - is that the start of the header of this unknown sound format, like RIFF in WAVs?

There is a reference to "16-bit VBR ADPCM audio" in the game, but is that really the format? Nothing can recognize those fragments as any audio format.

There is a lot of other interesting information about the game inside the GOBs. For example, there are remaining parts of a whole unused level.

And finally, here is something that someone experienced in such matters might check: a section of the CND file that seems to contain the sound "mus_flourish.wav" (the file with the extension .xyz) - AND a file straight from Lucasarts (from an "Infernal Machine" Windows theme), which MAY be the unpacked version of the same sound (Flourish.wav)... For a possible comparison.

indy.rar
[indy.rar](https://xentaxbackup.github.io/file/622_indy.rar)
## Post #11
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-08-28T13:23:45+00:00
- Post Title: Question about one new game and two not that new.

Hello,

sorry to poke this old thread, but this might help you with the CND files: [http://oezmen.eu/gameresources/](http://oezmen.eu/gameresources/). I haven't built in support for all compression schemes that are actually possible in CND archives, but all resources in my copy of the game were based on one format anyway. However, as I have the german language version, your mileage may vary and I'd be glad to get some feedback.

For the record: The executable indeed references an ADPCM method, but this is probably related to a different part of the code. The files containing the WVSM header structure use a quite simple (but probably non-standard) compression method. Source code is included, so anybody who wants to convert this into a MultiEx module is welcome.

I'll see to add the format description to the Wiki some time ...


Have fun,

Deniz
## Post #12
- Username: Vess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 08, 2006 2:14 am
- Post datetime: 2009-02-19T22:03:20+00:00
- Post Title: Question about one new game and two not that new.

Most excellent, thanks!
