## Post #1
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-10-30T02:29:18+00:00
- Post Title: Help extracting Heavenly Sword Textures

Working on extracting models from the game Heavenly Sword, but I have no idea how to get the textures from the game.
## Post #2
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-10-31T14:24:55+00:00
- Post Title: Help extracting Heavenly Sword Textures

I read in an older forum post that the textures are in the .dat files extracted by quickbms, but I haven't been able to find a tool that can read or convert the files.  Anyone have a suggestion?
## Post #3
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-11-04T17:21:31+00:00
- Post Title: Help extracting Heavenly Sword Textures

Still needing help with this, does anyone have any ideas?
## Post #4
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-11-05T09:29:57+00:00
- Post Title: Help extracting Heavenly Sword Textures

OK, This is what I've figured out so far:

```

get DUMMY long # First four bytes, not a string, no indication of file type, always the same

get SIZE long # The total size of the file from OFFSET

get FILENUM long # Number of files (?)

get ZERO long # Zero value

get OFFSET long # File Offset

get IMAGESIZE long # Actual image size, from OFFSET

get HASH long # Unknown value, possibly file name or hash

get ZERO long # Zero value

get HEIGHT short # Height of Image

get WIDTH short # Width of Image

get COLORS long # Color depth of image (?)

get ZERO long # Zero value

get ZERO long # Zero value
```


The next 80 bytes are all P (0x50), which I'm assuming is padding.  I'm attaching one of the dat files so people can take a look for themselves.
[00000db7.zip](https://xentaxbackup.github.io/file/13524_00000db7.zip)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-05T20:33:32+00:00
- Post Title: Help extracting Heavenly Sword Textures

128 byte big-endian header
at 0x18 - 1byte - format ID (this sample is dxt5 format)
at 0x19 - 1byte - num mips
at 0x20 - 2bytes - width 
at 0x22 - 2bytes - height

of course some of that is speculation until more than one sample is provided  



someweirdeyelookingthing.png (19.41 KiB) Viewed 63 times
## Post #6
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-11-06T06:16:48+00:00
- Post Title: Help extracting Heavenly Sword Textures

Acewell, what did you use to convert that?

edit - nevermind, TextureFinder seems to be working now.
## Post #7
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-11-06T07:16:23+00:00
- Post Title: Help extracting Heavenly Sword Textures

Big thank you to AceWell for giving me the clue to figuring this out!!  Not everything is working, unfortunately, but I've got the files I was looking for.
