## Post #1
- Username: xclusn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 27, 2011 12:45 pm
- Post datetime: 2011-03-27T05:19:03+00:00
- Post Title: Yet Another PAMF (PAM, PMF) Sound (AA3, OMA) Extractor

After trying hard to find working tool for extracting Atrac3 (AA3, OMA) from all the PAM files that I have (most troublesome was 512 Kbps, 5.1 channels format), I decided to write my own QuickBMS script.
Usage is simple:
1. Get quickbms
2. Run quickbms.exe -o extractAA3fromPMF.bms <your pam file> <your working dir>
(for large files use quickbms_4gb_files.exe)
3. Open resulting aa3 in Sony Sound Forge
4. Save it as Wav (You probably will want to convert it to stereo)
5. Now you can convert the video using ffmpeg, for example:
ffmpeg -f mpeg -i video.pam -i video.0.wav video.mp4
[extractAA3fromPMF.bms.zip](https://xentaxbackup.github.io/file/4790_extractAA3fromPMF.bms.zip)
## Post #2
- Username: masterkivat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 25, 2011 3:03 pm
- Post datetime: 2011-04-25T07:43:09+00:00
- Post Title: Yet Another PAMF (PAM, PMF) Sound (AA3, OMA) Extractor

Thank you for this one   
Worked flawlessly with my Marvel VS Capcom 3 backup ;]
## Post #3
- Username: reboot31
- Rank: MIT cheater
- Number of posts: 10
- Joined date: Mon Apr 18, 2011 2:41 pm
- Post datetime: 2011-04-29T14:00:27+00:00
- Post Title: Yet Another PAMF (PAM, PMF) Sound (AA3, OMA) Extractor

thanks xclusn..!
## Post #4
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2011-10-02T18:16:15+00:00
- Post Title: Yet Another PAMF (PAM, PMF) Sound (AA3, OMA) Extractor

Hi!,

I tried your program on the movies I extracted from FFXIII. So far, so good. But for some, it throws the following error: Unknown AT3PARAM (17493)
What that means?

Thanks and regards,
