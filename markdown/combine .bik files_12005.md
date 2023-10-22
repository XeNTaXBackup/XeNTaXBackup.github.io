## Post #1
- Username: ojo987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 12, 2014 9:59 pm
- Post datetime: 2014-09-25T01:12:06+00:00
- Post Title: combine .bik files?

Hi folks,

I was able to extract some .vib files from the .arch01 files from my favorite Steam game, Gotham City Impostors. Turns out these are Bink videos, and by simply renaming them from .vib to .bik, they become playable (with RAD Video Tools). For some reason however, several of the videos are broken up into multiple .bik files --- like alarm_01.bik, alarm_02.bik, etc. 

I'm still trying to figure out how to convert these to .avi in some way that doesn't end up with .avi files much larger than the original .bik; but in the meantime, I'm wondering if there is a way to combine the multiple .bik files into one file first. Any suggestions?
## Post #2
- Username: ojo987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 12, 2014 9:59 pm
- Post datetime: 2014-10-01T19:57:43+00:00
- Post Title: combine .bik files?

Hi there,

Just wanted to let everyone know that I figured out a workaround to this, in case anyone else runs into a similar issue. 

For combining the .bik files, I discovered the best way really was to use the RAD Video Tools, to convert the .bik files to uncompressed AVI. This does result in gigantic AVI files, but then other programs (such as Virtualdub) can be used to compress the .avi's to a more reasonable size. I used the x264vfw codec (video) and AC3ACM codec (audio) in Virtualdub to do this.

I also found the FFMPeg Plugins for Virtualdub, which allow Vdub to import .bik files. Virtualdub isn't able to combine .bik files, but this was helpful for those .bik files that weren't part of a sequence. I also used this method to load and convert multiple .bik files that were part of a sequence into .avi's, then used Virtualdub's Append feature to combine them, but I found that combining them in RAD Video Tools first really worked out better in the long run. 

Anyhoo just FYI.
