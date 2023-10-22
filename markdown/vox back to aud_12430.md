## Post #1
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2014-12-26T16:10:28+00:00
- Post Title: vox back to aud

Hi. I wonder if anyone knows how to convert a vox file to aud.

The vox files are from german version of Sam & Max 301, and I would like to use them for the english version of the game, so that english speech turns to german speech.

Problem is, that english version is using aud instead of vox audio files. So I need to convert vox to aud.

Any help is appreciated.
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-26T17:36:03+00:00
- Post Title: vox back to aud

Can you send some sample files?
## Post #3
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2014-12-26T19:44:40+00:00
- Post Title: vox back to aud

Sure. Just tell me if you need more sample files..
Thanks in advice for your help.

[http://www.megafileupload.com/en/file/5 ... s-rar.html](http://www.megafileupload.com/en/file/591967/sample-files-rar.html)
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-26T19:57:28+00:00
- Post Title: vox back to aud

Hmm... Both files start with

```
45 52 54 4D 01 00 00 00        ERTM....
```


Have you tried simply changing the extension from vox to aud?
## Post #5
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2014-12-26T20:18:34+00:00
- Post Title: vox back to aud

yeah. that's the first thing i tried..

Edit: ok, seems that I solved the problem. I just need to try on the other vox files, to see if everything is ok..
## Post #6
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2014-12-28T14:35:20+00:00
- Post Title: vox back to aud

It appears that .aud file is nothing different than an .ogg stream with a header.

This is what I did: 
I converted .vox to .ogg with telltale speech extractor.
After that, I get a headerless .ogg file. Now I copied the header from original .aud file to the converted .ogg file and I renamed the file to .aud. 
This works so far and you hear german speech in game, if you put the modified .aud file in game folder.
But the problem now is, that I can't hear the last word of the spoken sentence, because the wrong duration of the audio file is played. 
Instead 12,980 seconds of the edited .aud stream, you hear always that duration of 11,187 seconds from the original .aud stream...

This is the header of the original .aud stream file:



EDIT: The duration is stored in the granulpos field of the last page in the vorbis stream. 
The duration is stored in samples and not in milliseconds/seconds. But if you divide the samples by the samplerate, you get the duration in seconds.
The original english ogg file consists of 493348 samples. The value is stored at offset 15743. The samplerate of the ogg file is 44100Hz.
493348 divided by 44100 equals 11,187 seconds.



Same with german .aud file. Duration consists of 572418 samples. The value is stored at offset 15afc and samplerate is also 44100Hz.
572418 divided by 44100 equals 12,980 seconds.



So as I said, if I now add the header from original aud file to german ogg file and I rename it to aud and put it in game pack folder, the game plays the edited audio file always with a duration of 493348 samples / 11,187 seconds, though in edited aud file the duration contains 572418 samples / 12.980 seconds.
I don't know if any other file is missing that tells the game to play the right duration of this audio file or if I have to edit/modify the header in a way, that the right duration of 12,980 seconds is beeing recognized by the game correctly...
[sample.rar](https://xentaxbackup.github.io/file/8390_sample.rar)
