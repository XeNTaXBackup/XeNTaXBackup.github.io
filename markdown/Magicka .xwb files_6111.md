## Post #1
- Username: LoneTiger
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 16, 2010 3:51 am
- Post datetime: 2011-02-20T23:58:38+00:00
- Post Title: Magicka .xwb files

Hello people.

Recently the soundtrack fr Magicka got released for free at the game website but it got me curious about what they included and what the devs did not include.

The magicka sound files are in .xwb format, after a bit of googling used:
XWB/ZWB files unpacker 0.3.3a (unxwb) from Luigi Auriemma's site and it pulled the .wav files from the .xwb ones.

However the music files are weird and I believe you people have more experience with this as the music files do not play properly (winamp) or are just noise (audacity) but they did play great in VLC player. Searching a bit more apparently they use a different codec? not sure if that would be the right term but it got me curious to learn a bit more about it.

I include one of the extracted files as sample. all feedback is welcome to help me push ignorance away 
[00000026.rar](https://xentaxbackup.github.io/file/3957_00000026.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-21T23:30:48+00:00
- Post Title: Magicka .xwb files

it's normal with microsoft adpcm and ima adpcm because only some programs like mplayer and vlc handles them correctly
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-02-22T04:40:57+00:00
- Post Title: Magicka .xwb files

Here's a batch script that will convert Magicka's unlistenable .wav files into listenable .wav files.

```
for %%a in (*.WAV) do cmd /c "C:\Program Files\VideoLAN\VLC\vlc.exe" -I dummy -vvv %%a --sout=#transcode{acodec=s16l}:standard{access=file,dst=%%a.wav} vlc://quit
```
## Post #4
- Username: LoneTiger
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 16, 2010 3:51 am
- Post datetime: 2011-02-22T07:20:04+00:00
- Post Title: Magicka .xwb files

aluigi:
How did you identify the file? I know this is probably newbie question audio-files 101 course but heh, it is a start to learn new things 

brendan19:
The script is for a standard .bat file to execute at extracted magicka files directory?
## Post #5
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-02-22T07:27:21+00:00
- Post Title: Magicka .xwb files

Sort of...

I'd copy all of the .XWB files from the magicka installation folder to a new one. Extract the .xwb files using unxwb and then create a new folder for the extracted files e.g. Ambience, UI, Music etc.

Then put the .bat script inside each of those folders with the extracted .wav files and it will convert them for you. The converted files will have a .wav.wav extension. Once converted, you can delete the unlistenable .wav files.

Unfortunately VLC can't playback or listen to the .WMA files inside a couple of the .XWB archives. So that batch script won't work on those files.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-22T08:33:51+00:00
- Post Title: Magicka .xwb files

@LoneTiger
I have identified it by watching the RIFF header, the codec 0x02 is microsoft adpcm.
but even without the file I could have guessed it was msadpcm because I have already had problems with it when in use in xwb files :)
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-02-22T08:39:46+00:00
- Post Title: Magicka .xwb files

On the topic of the WMA files can you identify what codec these .WMA files are using and if there's a way to convert them to WAV at all aluigi?

[Unknown WMA File](http://www.flameupload.com/files/FJI4WWKQ/00000000.rar)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-22T08:51:50+00:00
- Post Title: Magicka .xwb files

this is a xma file, it's strange that it gets extracted as wma.
can you point me to the xwb file if it's not much big?
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-02-22T09:10:14+00:00
- Post Title: Magicka .xwb files

Sure. Here's the Wave Bank.xwb and the Loc.xwb that contain the .XMA/WMA files.

[Audio](http://www.flameupload.com/files/OKOZVIVD/Audio.rar)

The rest of the XWB files seem to be MSADPCM WAV as you said.
## Post #10
- Username: LoneTiger
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 16, 2010 3:51 am
- Post datetime: 2011-02-26T04:41:24+00:00
- Post Title: Magicka .xwb files

Yes also the Wave Bank.xwb file, using the tool to extract pulls the files as .wma files but they cannot be played. oddly enough audacity is the only one that gives any kind of message about it:

"yadayayada.wma" is a windows media audio file, Audacity cannot open this type of file due patent restrictions. You need to convert it to  a supported audio format.
