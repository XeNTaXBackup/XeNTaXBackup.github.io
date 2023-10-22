## Post #1
- Username: root670
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 18, 2010 6:11 am
- Post datetime: 2012-11-16T03:09:13+00:00
- Post Title: Extract Samples and MIDI files from Square PS2 Games

I've only tested this method with Kingdom Hearts and Final Fantasy X, but other games should work fine. VGMTrans holds up pretty well (considering it's now over a decade old), but I belive it has issues with PSF files from non-Square Soft/Enix games. Anyway, here goes...

You'll need this stuff
PSF files from a game ([http://www.tzone.org/~llin/psf/](http://www.tzone.org/~llin/psf/) has tons)
VGMTrans ([http://filetrip.net/nds-downloads/utili ... 27960.html](http://filetrip.net/nds-downloads/utilities/download-vgmtrans-92909-f27960.html))
Awave Studio ([http://www.fmjsoft.com/awframe.html](http://www.fmjsoft.com/awframe.html)) You'll need the paid version, and I unfortunetly couldn't find any other software quite like it. 
Music tracking/producing software, such as FL Studio or LMMS. Must support SF2 samples.

1. Extract PSF files from archive using WinRAR or 7zip.
2. Open VGMTrans and drag'n'drop each PFS file you want to convert. You can do more than one at a time, but it's likely to crash the program.
3. Right click the item that says "BGM Seq" and choose "Save as MIDI". Save it to a location that you'll remember.
4. Right click the item that says "WD Set" and choose "Convert to DLS". Save it to the same location as the above file.
5. Open the DLS file in Awave studio. Here you can listen to samples from each instrument and rename them if you'd like.
6. Go to File -> Save Collection As, choose "SF2 - Emu SoundFont vX.XX bank" from the drop down box, then save it.

The SF2 file we just saved is compatible with more software. When used in combination with the MID file we saved earlier,
you can fully reconstruct songs from the game. Manual tweaking will probably necessarily as the reverb information is lost
in during this process.

With LMMS, you can quickly import the MIDI file alont with the correct samples from within the SF2 file. Here's how I did it...
1. Open LMMS, go to Edit -> Settings.
2. Click the second icon on the left (who's icon is a grey folder).
3. Click the icon next to the field under "Default Soundfont File" and point it to the SF2 file.
4. Click OK to confirm the changes. Restart LMMS...
5. Go to Project -> Import and find the MIDI file that you extracted with VGMTrans.

After this, each instrument should have been put on it's own track with a piano roll filled with notes   . The problem with this method is that for each new MIDI you want to import, you'll have to change the default sound font again. It's a little clumsy, but it just works.
## Post #2
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2012-12-15T22:13:23+00:00
- Post Title: Extract Samples and MIDI files from Square PS2 Games

This is extremely nice! I got one question. I'm have trouble trying to extract the wavs out of .bd files and converting .sd to .dls. When right click it to save it nothing apears in the folder and if try to extract it as raw it will 0 bytes of nothing.

BD = Sony PS2 Instrument Set
HD = VGM Sample Collection

I also have a few other files that im not sure what they are.(TD and SND)

THANKS! 
I hope some one can help me!
