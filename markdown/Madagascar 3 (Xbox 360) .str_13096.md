## Post #1
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-07-23T15:52:17+00:00
- Post Title: Madagascar 3 (Xbox 360) *.str

Hello! I need some help converting the .STR music files from Madagascar 3 (Xbox 360). The samples are included.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-24T03:32:07+00:00
- Post Title: Madagascar 3 (Xbox 360) *.str

95% of the time Xbox 360 titles use XMA audio so that should be your first choice.

Channel count is found at 0x07 (02 - Two channels - Stereo)
Sample rate is found at 0x0A (44AC - 44100Hz)
XMA flag "FC01C001" can be found at 0x17F6

For this and other files from this game, delete everything 6 bytes before the XMA flag "FC01C001" so for this file, it should start from 0x17F0.

Then use Alpha23's XMA Transform Script to add a proper XMA header and then decode using ToWAV.

Don't forget to set the proper sample rate in the script as well
## Post #3
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-07-24T09:24:47+00:00
- Post Title: Madagascar 3 (Xbox 360) *.str

Thanks! I have an error though.
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-24T09:33:39+00:00
- Post Title: Madagascar 3 (Xbox 360) *.str

It should look like this before you add the XMA header using the script. I've highlighted the XMA flag as well.



EDIT: Ahh I see what you did. You need to delete all of the data from the start of the file up to the six bytes before the XMA flag like my screenshot shows.
## Post #5
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-07-24T09:44:49+00:00
- Post Title: Madagascar 3 (Xbox 360) *.str

Works perfectly. Thanks very much Xentax members are very helpful.
