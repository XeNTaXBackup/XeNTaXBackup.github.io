## Post #1
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2017-09-11T18:14:32+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

Hi everyone. I need to convert in an audible format the soundtracks of this game. The audio tracks are in ".SFX" format and I do not know which settings to set in VGM ToolGUI for convert them correctly, both for Xbox and PS2 version. I leave here the link to download a sample of a track for both.


Link (Expired): [https://mega.nz/#F!MiJAWKrD!ufzTDwLS1GKvfN4jCBMT6g](https://mega.nz/#F!MiJAWKrD!ufzTDwLS1GKvfN4jCBMT6g)
## Post #2
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2018-03-08T16:36:21+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

It's MUSX, a multi-platform Eurocom 4-bit ADPCM solution that's playable by VGMstream plugin. The main question for me however is how you unpacked those huge FILELIST.000/.BIN and/or DATA.DAT archives. Do you mind sharing your extractor?
See you!
## Post #3
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2018-03-11T23:15:24+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

Hi man, I'm sorry for the delay, unfortunately I do not always see it. I'm sorry to have to give you the bad news, but unfortunately I did not extract anything, it was already as it was, I did nothing but take a sample from the folder that covered the audio tracks and post it directly here, waiting for someone to help me. But there is still a possibility, I don't known if this script can help you, but is dedicated to the extraction of files from games developed by Eurocom, and was made thanks to the programmer Luigi Auriemma. I hope this can help you:

[http://aluigi.altervista.org/bms/gforce.bms](http://aluigi.altervista.org/bms/gforce.bms)

P.S. : Thank you for the help, but unfortunately when I insert the PS2 file in VGMstream, I get written "Failed opening". What do you suggest me to do? Greetings.
## Post #4
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2018-03-12T08:46:28+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

Yep unfortunately all these SFX files can't be played ATM although similar (or exactly the same) type of PS2 MUSX has been implemented into VGMstream many years ago. We can either wait for an update for that plugin (I'm gonna notify its author about the issue) or use some workarounds.
Here's what you may use with XMPlay version of VGMStream: 2 TXTH docs which should work on all tracks with "_mus_mfx_" prefix as well as usa__streamdata.sfx (there're quite a few songs there starting at 1:51:07 & ending at 2:11:08). Simply copy both TXTHs to directory where *.sfx are located and add SFX files to playlist.
If you think that BGMs play too slow or too fast then you're free to edit my *.txth files (they're simple plain-text documents) and change values in lines #4 or #5. I hope this helps and you'll be able to find & play all the original ingame compositions you're looking for!
Best regards!
[txth.7z](https://xentaxbackup.github.io/file/14018_txth.7z)
## Post #5
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2018-03-16T02:16:16+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

Sorry again for the delay  
Thank you very much Ripper for the help, but unfortunately I inserted the two files that you have kindly shared, in the folder containing the audio tracks with the format in question, but when I try to add them either from the program or with the drag-in strangely nothing happens, load the file but do not show it (started the program with administrator rights). However, I downloaded the program from their official website, I do not know if the cause was that I had not downloaded a specific version  

[http://support.xmplay.com/files_view.php?file_id=676](http://support.xmplay.com/files_view.php?file_id=676)
## Post #6
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2018-03-16T12:10:20+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

[MUSX v5 [Predator: Concrete Jungle (Xbox/PS2)]](http://www.foobar2000.org/components/view/foo_input_vgmstream) has already been added to FB ver. of plugin so that install it instead and you'll be able to play those tracks with "_mus_mfx_" prefix. It'll only become possible after you change original *.sfx extension to *.musx though (Foobar variant relies heavily on file extensions in order to play back music properly, Winamp / XMPlay versions of VGMstream aren't so strict).
This solution worked perfectly fine for me and I hope you won't run into any more issues with these BGMs.

As for usa__streamdata.sfx: are you sure both usa__streamdata.sfx and usa__streamdata.sfx.txth are in the same folder? Can you find VGMStream in list of currently installed plugins in XMPlay or Winamp? Actually if you use the former there should be even 2 iterations of it in Plugins=>Input menu: vgmstream for XMPlay + Winamp[in_vgmstream.dll], at least one simply has to play usa__streamdata.sfx (or those sb_*.sfx banks if you even need them).
If the problem persists I will hardly be able to suggest anything else so you'll probably be on your own from there on. Sorry for that but this is just how I see it.

Best wishes and good luck!
## Post #7
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2018-03-17T19:45:20+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

Oh Ripper, I do not know where to start to thank you, finally now everything works!   
Both the audio tracks of the PS2 version and the Xbox are reproduced perfectly (thanks). The program I used for this was "Foobar" with the VGStream library (thanks for the alternative and the library). As for "XMPlay" the cause will certainly be me, because I have not installed the libraries of VGS, that's why it did not reproduce it (thanks for solving the problem, I was literally going crazy trying to make it work). I tried before downloading Foobar to install what I needed in XMPlay, following (after some research) as I had to do it, but unfortunately nothing changed. I tried taking all the .dll files of VGS and move them first in the "Plugins" folder (created according to instructions), then in the main folder, but in the "Plugins" section of the program settings did not detect anything unfortunately (although the instructions clearly said that it was not important where they were inserted, the folder "Plugins" was just to keep everything in clear order), but with the second alternative recommended by you I was able to easily make it.  
Before concluding I would like to ask you possibly one last thing. Is it possible to convert an audio track into this format, rename it and replace it with one of the available audio tracks and play it in-game?
## Post #8
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2018-03-18T07:55:02+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

It's nice to hear you've got it working and all probs gotten rid of!
As for audio modding of this game: I don't know since I've never really been into BGM replacement and so on. This MUSX codec looks to be relatively popular and not super-sophisticated but I'm still not sure you're going to find any WAVE-to-MUSX tool in the Web. You can always try I guess...
Best regards!
## Post #9
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2018-03-19T22:50:29+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

I understand. Thank you Ripper!
## Post #10
- Username: jmarti856
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 29, 2015 8:45 pm
- Post datetime: 2023-09-03T18:46:29+00:00
- Post Title: Predator: Concrete Jungle (PS2/Soundtrack/.SFX)

Hello!

Recently, with the publication of the Sphinx and the Cursed Mummy Authoring tools, we could know more about the SFX/MusX file format.

We created a GitHub with some audio modding tools, the EuroSound Explorer has support for Predator, you could take a look at this tool here: [https://github.com/eurotools/eurosound-explorer](https://github.com/eurotools/eurosound-explorer)

You also have the soundbanks editor published in this github organization:
[https://github.com/eurotools/eurosound-editor](https://github.com/eurotools/eurosound-editor)
