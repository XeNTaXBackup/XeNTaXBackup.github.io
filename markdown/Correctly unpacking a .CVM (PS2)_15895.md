## Post #1
- Username: namine207
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 16, 2017 11:04 am
- Post datetime: 2017-02-18T14:58:38+00:00
- Post Title: Correctly unpacking a .CVM (PS2)

Hello!

I have a Data.CVM that I'm looking to extract files from. I was told that it's basically an ISO with extra code added, so I Just need to strip the file header in a hex editor. Then I should be able to open it from 7zip. However, I'm not very experienced with hex so this is proving tricky for me. I was able to extract the files using Xpert's CVM plugin, but no matter how I extract it from there,the files always come out differently, more often than not missing info. Would anyone be willing to offer advice for getting the file header stripped from this file?

Thanks in advance!
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-02-20T17:46:57+00:00
- Post Title: Correctly unpacking a .CVM (PS2)

Try using this
[ROFS CVM To ISO Converter](http://www.tankraider.com/userup/1259801960.zip)

If that doesn't work, you can try and remove the first 0x1800 bytes, then rename the extension from .cvs to .iso and mount it with daemon tools.
## Post #3
- Username: namine207
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 16, 2017 11:04 am
- Post datetime: 2017-02-20T17:51:41+00:00
- Post Title: Correctly unpacking a .CVM (PS2)

> Reply from brendan19
>
> Try using this
ROFS CVM To ISO Converter

If that doesn't work, you can try and remove the first 0x1800 bytes, then rename the extension from .cvs to .iso and mount it with daemon tools.

Thank you so much!!! I wound up finding out that while one of the games I was doing this on (.hack GU Volume 1) was giving me just one file inside of it (that largely seems to not do anything), Volume 3 gives me the CCS files inside that I've been looking for without any trouble!  Now if only I could get ahold of Forte's documentation on the CCS format to see if I could work on it a bit with a friend who's capable of reverse engineering. The CCS2OBJ tool only seems to extract a good 60% of area models from each resource package.
