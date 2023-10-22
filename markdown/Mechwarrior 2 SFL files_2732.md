## Post #1
- Username: Splynncryth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 31, 2007 12:39 pm
- Post datetime: 2007-08-01T02:47:02+00:00
- Post Title: Mechwarrior 2 SFL files

I'm trying to figure out the MW2 SFL file format. Some of the files appear to be a header with PCM data and what maybe cure points in the data (very odd looking ticks that look like they would be safe to discard). Others must be something else, but I don't have enough expertise to recognize what. I have a few sample files in the zip attached to this post.

Here is what I think I have worked out so far, it's not much 
char[4]=SFLX;
uint16 EOFOffset; //add this to the current address to get pointer to the next file
uint16 EOHOffset; // end of header offset? For files containing PCM data, points to start of PCM data.
uint16? unknown1=0x0080; //Flags? It's been 0x0080 in all the fiels I've check so far.
uint16? unknown2; //I have no idea what this is for

Optional data appears to follow this in some cases. This is the set of offsets between the last value in the header and start of data so it could be a stripped down header for another audio format, cue information, etc. 

The PCM data may also have cue points, there are odd ticks, typically one sample and no regular patter of distribution I can discern that can be safely removed. I'd liek to figure out is there is any ryme or reason to these as they will be harder to figure out in the encoded data unless they conform to a standard.
[sfl files.zip](https://xentaxbackup.github.io/file/1297_sfl files.zip)
