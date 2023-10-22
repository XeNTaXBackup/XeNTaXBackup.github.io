## Post #1
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2011-12-20T15:04:19+00:00
- Post Title: Star Wars Battlefront II audio bank

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2011-12-21T13:29:46+00:00
- Post Title: Star Wars Battlefront II audio bank

More information:

The top section appears to be a table of contents. The following hex sequences are repeated the same number of times as there are sounds in a given archive:

B4 9F 78 2E A7 82 E3 96 E0 6A 38 37

Following those 8 bytes there are four more bytes that correspond with an ID from an alternate file. This is how the game pairs the "config" for the sound with the raw sound data in the bnk file. The next four are always:

01 1C B3 2F

followed by

[varying byte code] 56 00 00 5C D9 A0 23 --the varying code is *usually* 22, indicating a 22050 khz sound?

followed by four more bytes I don't understand, then:

EF FE 48 1D

There's a bit more to that pattern, but I don't understand it anyway - I just hope it helps. There's also significant padding before the next section, which I assume are the actual sounds.
