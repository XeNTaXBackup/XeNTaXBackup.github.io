## Post #1
- Username: StaticSaltByte
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 16, 2019 4:06 pm
- Post datetime: 2019-10-16T08:43:04+00:00
- Post Title: [Help] Repacking Torchlight 2 .mod files.

I’m trying to reverse-engineer the packing format Torchlight 2 uses for .mod files. For some reason the developers designed the game to only allow 10 mods to be installed at once. I’m trying to put together a tool that can automatically combine mods to get around this restriction.

The .mod format is reasonably well understood and [documented at the fan wiki](http://torchmodders.com/wiki/doku.php?id=file_formats#archive_formats), but there are 4 unknown bytes in the .pak section of .mod files that are stopping me from getting it working. Unlike other unknown bytes that seem to have a “magic value,” these bytes prevent Torchlight 2 and its modding tool GUTS from opening it because it is “corrupt” or “doesn’t have files”.

In an attempt to find a pattern, I exported information of a few mods (694) to [a spreadsheet](https://docs.google.com/spreadsheets/d/1Xwk_RoBdFBH8oE3SaKYIijf2QFge5KLUom3iWbDalDk/edit#gid=965485919). However, the values of the unknown bytes all arbitrarily range from min (0) to max (255). My best guess is it’s a CRC32 value (similar to the CRC32 in the .pak.man section) but so far I haven't been able to match it to anything.

It’s also worth noting that if I create two different mods from scratch using GUTS that have identical files, the unknown bytes will be identical between the two mods. But if I add, move, or modify any of the files then the unknown bytes change.

Any help would be greatly appreciated.
## Post #2
- Username: Awkward
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 07, 2020 7:19 pm
- Post datetime: 2020-11-15T09:18:03+00:00
- Post Title: [Help] Repacking Torchlight 2 .mod files.

Is any progress since year?
