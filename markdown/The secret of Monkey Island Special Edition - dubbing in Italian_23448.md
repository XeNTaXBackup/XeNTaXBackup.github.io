## Post #1
- Username: giannisilv
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 15, 2021 9:29 pm
- Post datetime: 2021-02-15T13:40:05+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

I would like to know how to insert an audio file into the file speech.xwb
I unpacked the file with towav.exe, and after I repack it with XACT.
I tried with Xact, to repack in the same order, but the game crash. So I changed first 3 lines (with an hex tool) of the hex file speech.xwb (created), and so the game works perfectly.
If I change one wav, with another sound with same name, and repack xwb, the game crash.
What is my error???
Is there other tools??? There is a connection with the file speechcue.xsb??
## Post #2
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2021-02-17T21:22:35+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

Hi giannisilv

In [this thread](https://forum.xentax.com/viewtopic.php?f=17&t=21633) is some information on repacking .xwb/.xsb files. Most important factor is to use the same version of XACT  as the game was created with. I think there was an option in XACT to create the .xwb as either 'in memory' or 'streaming'. I repacked a .xwb file for a different game long ago and remember having issues with that.

Hope this helps for a start!
## Post #3
- Username: steve88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 01, 2022 6:27 pm
- Post datetime: 2022-05-06T07:46:17+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

Hi everyone, I'm trying to continue the work started by @giannisilv, dubbing The Secret of Monkey Island SE in Italian. I've tried everything but I desperately need help. I've extracted the original wave files from Speech.xwb with towav.exe, I've installed the correct version of Microsoft DirectX SDK, and through XACT I've created an XWB file inserting all the wave files in the same order and setting "Steaming" and "Friendly Names", but the game starts with mute audio. I tried to replace a wave file with one dubbed in my language, but the game does not start (white screen). 

I tried to use xactextract.exe, but it simply extracted the WAV files from the XWB file, with "non-speaking" names (e.g. "000003.wav", while towav.exe extracted files like "GUY_dock_32_1.wav"), which would make it very difficult to organize the work to make the new WAV files dubbed in Italian.
In any case, as I explained, with the new XWB the game starts mute. Should I also create an XSB file and overwrite it with the original? If yes, how?

Could someone explain me how to insert new WAV in the XWB so that The Secret of Monkey Island SE starts correctly?

Thank you very much!
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-07T11:04:45+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

I've recently explained here [viewtopic.php?p=183974#p183974](https://forum.xentax.com/viewtopic.php?p=183974#p183974)
how to proceed with creating new XWB files. I've helped there a guy with making dubbing for Bully and he confirmed that this method works fine.
This instruction is specific for Bully, but most of the steps should be similar in your case.


Check also this article [http://wiki.xentax.com/index.php/XACT_XWB_XSB_XGS_Audio](http://wiki.xentax.com/index.php/XACT_XWB_XSB_XGS_Audio)
as it has very useful info on those audio formats.


If you need more assistance, please upload few samples and tell me exactly on what platform (PC, XBOX etc.) and version your game is.
## Post #5
- Username: steve88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 01, 2022 6:27 pm
- Post datetime: 2022-05-07T11:55:14+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

Thank you so much for the reply!

I had followed your guide, the clearest one on the internet, but with no success.
I also read that link about the structure of XWB files, but I could not understand much.

with the XACT tool contained in Microsoft DirectX SDK (March 2009) I was able to recreate a speech.XWB file with the same English dialogues. The speech.XWB file did not work, so I opened it with a hexadecimal editor. Noticing that the first few bytes of the original file were different from those in my file, I then copied the first few bytes of the original XWB, pasted them into mine, and finally got a working speech.XWB file.
I would like to understand what's the easiest method to create an immediately-working speech.XWB without using hexadecimal editor for every test, but I have not found any guide about it. If someone could enlighten me I would be very grateful!

>>> Then I've tried editing just one WAV file and build the XWB, but the game doesn’t start (white screen). <<<

To add to the confusion, the towav.exe application produces files with a number in front of them, for example "31 TRL_57_bridge_24_1.wav". Exporting the speech.xwb file with Monkey Island Explorer instead, you get files without the number in front, e.g. "BOB_38_lookout_1_4.wav". @giannisilv says:
"I imported all the files into an XACT project, however in my opinion files must be without the little number in the order ahead; so I created a little tool in visual basic that would rename all the files for me correctly within the XACT project file."
How is it possible that I was able to get the speech.xwb file to work despite using wavs have the number in front (extracted with towav.exe)?

I'm working on Windows.
4 bytes (uint32) - tool version (dwVersion / XACT_CONTENT_VERSION) = 45
4 bytes (uint32) - file format version (dwHeaderVersion) = 43
Corresponding DirectX SDK version: 2009, March

Original Speech.xwb:
[](https://ibb.co/fpfRxrQ)

Original Speech.xwb recreated by me (original English dialogues), without hex editing:
[](https://ibb.co/FJSxMS1)

below are the wav files exported from speech.xwb with different tools (different filenames obtained, I don't know what's better to choose) and the audio files in the game folder of the game. the game version is 1.0 of the secret of monkey island SE.
[](https://ibb.co/t2T6dcs)

@giannisilv was in my situation and wrote: "I tried editing 1 audio file only, and repackaged everything, but the game crashes.
I think the problem is in the fact that it changes all the offsets (hex addresses of the file). Surely there's a correlation with the SpeechCue.xsb file, because I've seen that XACT can create one, but since it's not identical it doesn't start the game."

how can I create a working XWB file with my audio files?

Thanks a lot for the help!
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-08T11:30:49+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

Your case is much more complicated than it was in "Bully", because in the file "Speech.xwb" there are multiple audio files
and in "Bully" there was only one audio file per XWB.

Currently I don't have any working solution for this. Maybe some custom tools needs to be created to work this out.
## Post #7
- Username: steve88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 01, 2022 6:27 pm
- Post datetime: 2022-05-08T14:22:52+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

This is very bad news!   
On the Italian topic @giannisilv, after writing that he was going to try to edit in hexadecimal, he wrote that he had succeeded. 
Which file do you think he was talking about, the XWB or the XSB? In your opinion how did he make the modifications? I have absolutely no idea where to start. Thanks!
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-08T19:55:20+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

> Which file do you think he was talking about, the XWB or the XSB?

I think it was XWB, because it is main container for audio data. If you import data that is smaller or equal than original, then modding could be possible even with quickbms script. The real issue is when you want to import larger files, because that would require recreating XSB files as well.

> I have absolutely no idea where to start.

45/43 format is not fully documented, but it should be similar to 46/44 format 
which is described on the wiki on the article's beginning. 
You can try to analyze format and try to find some differences (if there are any)
and then try to replace some values and see how the game will handle it (will it crash or not).
Then you can start learning quickbms scripting (or programming) and try to write a script that will replace
only audio data. If it works for one audio file, then it may work for all files (with size smaller or equal original size).
## Post #9
- Username: steve88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 01, 2022 6:27 pm
- Post datetime: 2022-05-08T21:26:56+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

thank you very much, my modified wav file was bigger than the original wav; with a wav file smaller than the original size, the xwb file works!
I will write soon a guide of everything I did.

do you think i could use the following tool to speed up the creation of the XWB files instead of XACT? i don't understand which version of the directx SDK it uses. thanks!
[https://github.com/microsoft/DirectXTK/wiki/XWBTool](https://github.com/microsoft/DirectXTK/wiki/XWBTool)

based on the XACT settings you suggested in your guide, the command should be:

```
.\XWBTool.exe -o Speech.xwb "<myWavePath>\*.wav" -s -f
```


parameters explanation:

```
   -o   sets output filename for .xwb file. Otherwise, it defaults to the same base name as the first input .wav file
   -s   creates a streaming wave bank
   -f   include entry friendly names
```


Low priority question: why the header of the file produced by XACT is different from the original? i use the correct version of XACT! am I doing something wrong? this makes the file not working and I have to edit the header by hand with the hex editor. is there a method to build a directly working XWB file? i refer to the hex screenshots in my post of Sat May 07, 2022 1:55 pm

thank you very much!
## Post #10
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2022-05-09T19:13:18+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

> Low priority question: why the header of the file produced by XACT is different from the original?

Sorry for not having time to take a closer look. Do you mean the difference at offset 0x8c? That's the time stamp (8Byte), so it has to be different from the original.

As for the screenshots with the extracted file names: there are cue names in the .xsb (these are not necessarily the correct file names). If the 'friendly names' flag is set, then there are file names in the .xwb. Because of this, different tools export the files with different names.

> do you think i could use the following tool to speed up the creation of the XWB files instead of XACT? i don't understand which version of the directx SDK it uses. thanks!

After a quick look in the code on github, XWBTool seems to produce 44/46
## Post #11
- Username: steve88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 01, 2022 6:27 pm
- Post datetime: 2023-04-28T14:45:55+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

thank you very much for your reply! my team and i have been working non-stop over the last few months, and there are some new features that i will announce in the near future regarding the automation of this process. with regard to what you wrote above, could you please detail as much as possible the procedure regarding the XSB file that would allow me to upload wav files larger than the originals to the xwb file? i was convinced that it was not possible to upload wav files larger than the originals. did i misunderstand? thank you very much!
## Post #12
- Username: steve88
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 01, 2022 6:27 pm
- Post datetime: 2023-05-13T14:39:47+00:00
- Post Title: The secret of Monkey Island Special Edition - dubbing in Italian

could anyone help me please? thanks!
