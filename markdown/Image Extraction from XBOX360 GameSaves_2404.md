## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-01-16T12:07:36+00:00
- Post Title: Image Extraction from XBOX360 GameSaves

Some games on the 360 have a camera mode, which allows you to take screenshots in that game, save them to HD and share them in as sort of a online 360 community.

these image are kept in the 360 save path in a PTC file.

apon opening a PTC in a hex editor, it shows 2 different types of image headers. PNG and MDI; 2 PNG's are in the upper part of the files as thumnails, then the MDI which hold the 1024x1024 full image at the end.

extraction of the PNG is fine, but the MDI seems to be compressed. MDI is a PDA format used by microsoft, which is a rip off of TGA's compression method.

the PTC is quite simple, just looking for someone who can uncompress the new MDI's

the smallest PTC extracted from doax2
[ptc_samp.rar](https://xentaxbackup.github.io/file/1033_ptc_samp.rar)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-15T01:59:50+00:00
- Post Title: Image Extraction from XBOX360 GameSaves

I dont understand how they would compress down a full resolution
1024x1024 image into that PTC file. the both PNG thumbnails in it
eats up 14kb of the 80kb PTC file, and they are 64x64 each.

or am i out completely in the blue?
