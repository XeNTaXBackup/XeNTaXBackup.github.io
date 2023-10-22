## Post #1
- Username: timotaka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 20, 2011 10:33 pm
- Post datetime: 2013-05-15T20:04:09+00:00
- Post Title: Trying to figure out .WV2 file format

The GOG release of Outcast uses .WV2 format for the game's music. I have been able to find no information about such a file format anywhere online. Originally these were CD audio tracks. Opening up the files in a hex editor shows that the file header identifies these as being WAV2 files. All right, that's a fairly common audio format. However, I have tried several multimedia and audio player and converter programs which should be able to process WAV2, but none of those have been able to figure out these files.

I am new to all this audio file stuff, but I did learn about the file headers containing information about the audio file. This appears to be the first 28 bytes or so in this case, as a file which I know has a long stretch of silence at the beginning is all zeroes after that for a good bit. Here's those parts in hex:

Example 1:

57 41 56 32 01 00 00 C0 E8 A3 37 00 02 00 10 00 44 AC 00 00 E8 A3 37 00 FA E8 0D 00

Example 2:

57 41 56 32 01 00 00 C0 00 A0 39 02 02 00 10 00 44 AC 00 00 00 A0 39 02 00 68 8E 00 

Below is a download link for the audio file for the shortest track in the game (which is where the first example is from) if anyone wants to take a look. If anyone has any ideas on what to try or what further information I should share, please do tell me.

[http://www.mediafire.com/?vydghtwwhn3h918](http://www.mediafire.com/?vydghtwwhn3h918)
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-05-17T10:01:27+00:00
- Post Title: Trying to figure out .WV2 file format

Hmm, this is somewhat familiar but I can not place it what game had this same format, will have to check again my research notes I had for this format.

In any case, it has very little in common with normal WAV as this is really one certain game developer custom format and uses adpcm encoding for compress.

EDIT: If use GENH, set format 0x07, header skip 28, interleave 250, channels 2, frequency 44100 and play/decode with vgmstream
