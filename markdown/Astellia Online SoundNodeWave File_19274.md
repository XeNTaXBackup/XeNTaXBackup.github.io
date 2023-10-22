## Post #1
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2019-01-06T06:41:17+00:00
- Post Title: Astellia Online SoundNodeWave File

I'm trying to get my hands on the music files of the Korean Unreal Engine 3 MMORPG Astellia Online. Format is SoundNodeWave. Just renaming them into .OGG does not work and the tool from swuforce doesnt work either.

Sample Download
[https://www.file-upload.net/download-13 ... w.zip.html](https://www.file-upload.net/download-13459478/New.zip.html)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2019-01-07T13:48:12+00:00
- Post Title: Astellia Online SoundNodeWave File

Strip away all the data before offset 0x136. The file should start with the first "OggS".

After that, rename the file extension to .ogg will allow it to playback just fine

If you want to do multiple files at once, use this [OGG Extract tool](https://drive.google.com/file/d/1kIHVILdmiymE8H63Ij-OXYfeNHwV732E/view?usp=sharing)

Put all of your SoundNodeWave files into the same folder as the tool and run the oggextract.bat file
## Post #3
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2019-01-07T16:34:03+00:00
- Post Title: Astellia Online SoundNodeWave File

> Reply from brendan19
>
> Strip away all the data before offset 0x136. The file should start with the first "OggS".

After that, rename the file extension to .ogg will allow it to playback just fine

If you want to do multiple files at once, use this OGG Extract tool

Put all of your SoundNodeWave files into the same folder as the tool and run the oggextract.bat file

I'm a noob and don't know how to do the first part.

/edit nvm it works fine with the tool thx
