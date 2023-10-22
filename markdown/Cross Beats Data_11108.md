## Post #1
- Username: simple
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Sep 29, 2007 6:52 am
- Post datetime: 2014-01-04T04:17:19+00:00
- Post Title: Cross Beats Data

An iOS music rhythm game by Capcom currently available in Japan only. My friends and I have been looking around the files and found out some of the following details:

The extension is .arc, but when we looked that up we couldn't find anything that can open them. 

There's a pattern to the names and file headers: Each song has a 10-digit ID, and there are 3 files per song, named ID_m.arc, ID_p.arc, and ID_w.arc.
The _m files range between 33 and 52 KB, the _p files range between 90 and 470 KB, and the _w files mostly range between 1.4 to 2 MB except for three odd ones out which are really small (one's 90KB, the other two are 221KB).
All the files start with the same 8 bytes: 0x415243430700XX00 where XX is 06 for the _m files, 05 for the _p, and 02 for the _w files.

A couple observations:
The first four bytes of each file, 0x41524343, spells "ARCC".
Each ID appears to have a couple common 8-byte strings, which appear very frequently in the header for all 3 files with that ID. These vary from ID to ID.
The files appear to have variable-length headers, but are padded out by 00 bytes until the total length of the header is 0x8000 bytes. After that comes a bunch of random-looking data.
Each header is comprised of a series of 64-byte blocks, in the general pattern "AB??CCCC" where A, B, and C are 8-byte strings and the two ?'s are 8 bytes each. Sometimes they repeat between header blocks, sometimes the second ? is the same as C. A, B, and C are the same for all 3 files with the same ID, but differ between IDs.

There's one last file out named "messageText.arc". It starts with 0x4152430007006A00 -- similar to the others, but the 4th and 7th bytes differ. The first 3 bytes spell "ARC", but the second 'C' is missing. There are a bunch of readable strings inside, zero-padded to 64 bytes in length and each followed by 16 bytes of unknown data before the next string. Each string follows the pattern "music\X\X_jpn" where X is a readable string, usually 6 bytes but some have a '2' concatenated to the end for a total of 7 bytes. (For example, one is "music\azitat\azitat_jpn" and the next one is "music\azitat2\azitat2_jpn") Then there's a bunch of zero padding until address 0x8000 then a bunch of seemingly random bytes, like the others. Upon further investigation one of my friend is able to decipher the file which basically contains the full song list and song comments.

My friend also noted that the ARC files with a second C are scrambled as if there's a particular byte-mapping ... but it's different per song so it's very hard to find a pattern...

Further looking through the files we noticed all the files are stored online in a CDN server. If anyone interested in helping me and my friend I can send the CDN link with the list of song IDs for you to look at.
