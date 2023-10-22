## Post #1
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2010-01-27T13:55:42+00:00
- Post Title: Venetica - XRZ ( XBOX360 )

Hi, 

i have use bms script and xbcompression and all times i have a file call myfiles.unpacked, when i looks header is XPR2 i have try to extract files inside and i got error, can you correct the bmsscript.

here sample of somefiles : [http://www.mirrorcreator.com/files/9CVI ... .rar_links](http://www.mirrorcreator.com/files/9CVIJYZV/VENETICA-XBOX.rar_links) - 4.7 Mo
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-01-28T19:16:50+00:00
- Post Title: Venetica - XRZ ( XBOX360 )

I don't think there is amy problem with your BMS script, you had decompressed the files correctly!
XPR2 is just a header telling XBOX it's a container! The content inside different from game to game!

struct XPR2 {
  char[4]     HeaderID     //XPR2
  dword       XPRsize
  dword       HeaderSize  //usuall indices of resource data here
}

The files you uploaded look to me a skeleton animation files.
## Post #3
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2010-01-28T19:59:05+00:00
- Post Title: Venetica - XRZ ( XBOX360 )

but when i use xpress tools it seem no working : [http://www.teamblackbolt.co.uk/projdetails.php?id=5](http://www.teamblackbolt.co.uk/projdetails.php?id=5)
