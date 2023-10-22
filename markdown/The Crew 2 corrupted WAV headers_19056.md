## Post #1
- Username: needsb
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2017 5:58 pm
- Post datetime: 2018-11-10T20:08:34+00:00
- Post Title: The Crew 2 corrupted WAV headers

I managed to dump all WAV files from sounds.dat using Winhex but the WAV file can't be opened. I open it in 010 editor and it automatically highlight the bytes, no errors. The file does seems to have artist info in it but Windows can't read it. I guess the header is invalid. The header modification is very known of DLL of Android unity games though...
I can't figured it out what to do with the WAV header as i'm not familar with audio format.
Anyone can help me recover the WAV header?
Sample: [https://usersdownload.com/bvj4cldqlw8r.html](https://usersdownload.com/bvj4cldqlw8r.html)
## Post #2
- Username: needsb
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2017 5:58 pm
- Post datetime: 2018-12-09T14:52:23+00:00
- Post Title: The Crew 2 corrupted WAV headers

Anyone are interested?
## Post #3
- Username: Delvau
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 21, 2018 7:50 pm
- Post datetime: 2018-12-10T12:05:43+00:00
- Post Title: The Crew 2 corrupted WAV headers

> Reply from needsb
>
> I managed to dump all WAV files from sounds.dat using Winhex but the WAV file can't be opened. I open it in 010 editor and it automatically highlight the bytes, no errors. The file does seems to have artist info in it but Windows can't read it. I guess the header is invalid. The header modification is very known of DLL of Android unity games though...
I can't figured it out what to do with the WAV header as i'm not familar with audio format.
Anyone can help me recover the WAV header?
Sample: https://usersdownload.com/bvj4cldqlw8r.html

I'm very interested, thanks for sharing!
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-12-11T17:09:53+00:00
- Post Title: The Crew 2 corrupted WAV headers

[vgmstream can playback/convert these files](https://github.com/bnnm/vgmstream-builds/blob/master/bin/vgmstream-latest-test-u.zip)

They are not PCM WAV files like you think they are.

They are Audiokinetic Wwise files because that is the audio middleware that was used on The Crew 2 for the game.

Audiokinetic Wwise audio files use a RIFF header similar to the one used in a standard PCM WAV file but are based on the WAVEFORMATEX style header.

Additionally, they're compressed/encoded with vorbis which also makes them different to a standard PCM WAV file.


tl;dr
Download vgmstream and rename the file extension from .wav to .wem and vgmstream will playback/convert them just fine
## Post #5
- Username: needsb
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2017 5:58 pm
- Post datetime: 2018-12-30T21:29:23+00:00
- Post Title: The Crew 2 corrupted WAV headers

Thanks very much. vgmstream did the job. Is there a way to convert multiple files instead just once?

EDIT: Found the batch script: [https://www.hcs64.com/mboard/forum.php?showthread=48467](https://www.hcs64.com/mboard/forum.php?showthread=48467)
