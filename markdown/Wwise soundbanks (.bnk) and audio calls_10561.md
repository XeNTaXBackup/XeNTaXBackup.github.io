## Post #1
- Username: Kung Fu Man
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Jul 14, 2011 1:34 pm
- Post datetime: 2013-06-30T14:23:01+00:00
- Post Title: Wwise soundbanks (.bnk) and audio calls

So I've been doing some modding work on Splatterhouse still, and while my xbox is getting repaired I've been looking at trying to restore audio lines to the game that aren't included in the soundbanks, but a few interesting hassles have come up, one of which being uncertainty on just how the game knows what soundfile(s) to look for. The audio call strings are in very plain-text format, like "vox_lvl11_homestretch_play", but I can't find what tells the game 'when you encounter this, look for this'.

The only file that seems to offer any indication is wwise_ids.h, and the xex when converted back into the EXE doesn't seem to look for this particular file nor does it contain the list of strings the file itself uses. Has anyone experimented with trying to create custom soundbanks for games at this point that might be able to shed some light?
