## Post #1
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2010-12-16T19:29:48+00:00
- Post Title: [Wii] Sonic the Hedgehog 4 Episode 1 - .AMB file

These files appears to have all of the games graphics inside. The header appears to be "#AMB" (without quotes).

Could anyone help me with this file?

Download: [http://www.mediafire.com/?wjb34ly8io5mgq8](http://www.mediafire.com/?wjb34ly8io5mgq8)
## Post #2
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-01-03T17:42:50+00:00
- Post Title: [Wii] Sonic the Hedgehog 4 Episode 1 - .AMB file

If you somehow didn't find the unpackers that are already released within the 17 days you've had here's the specs.

```

0x04 to 0x0F = unknown, seems to be part of the header.

0x10 dword = number of files

0x14 dword = unknown

0x1C dword = address to the filenames

0x20 dword = address to beginning of the first file

0x24 dword = size of file

Followed by FF FF FF FF 00 00 00 00, then new file start address, and file size, check the dword at 0x10 for amount of files.
```


And [extraction](http://endri.webs.com/AMB%20Tools%20v1.02.rar) tools.

Though if you're just after the visuals you're better off with either the PS3 or 360 versions as they have the same art in higher res.
## Post #3
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2011-01-04T00:56:34+00:00
- Post Title: [Wii] Sonic the Hedgehog 4 Episode 1 - .AMB file

Thanks! The tools worked perfectly!
