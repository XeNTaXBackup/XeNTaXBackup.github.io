## Post #1
- Username: gooms9
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 27, 2012 8:30 am
- Post datetime: 2012-04-08T17:03:49+00:00
- Post Title: MS-OXRTFCP compression format

Hello, I'm trying to decompress a block of data from an XBox 360 archive (Kinect Disneyland Adventures). I've run the data through quickbms, but didn't find any solid matches. However, the output created by COMP_LZFU_RAW did seem to provide some interesting results. I noticed some strings in the decompressed output like 
```
\fdecor MS ... and \fmodtbl....{\rtf1\ans !MS Sans SerifSym.oman \f.
```
 I googled fdecor MS and the first link was to a microsoft compression protocol called MS-OXRTFCP. [http://msdn.microsoft.com/en-us/library ... g.80).aspx](http://msdn.microsoft.com/en-us/library/ee200688%28v=exchg.80%29.aspx) Does anyone have any experience with this format or know of a tool that I can run my data through to verify weather it's the compression algorithm I'm looking for?


Here is a sample of the files i'm trying to decompress in case anyone else has any good ideas! [http://cl.ly/1R411l2e1u2L3N1l0U03](http://cl.ly/1R411l2e1u2L3N1l0U03) 
Thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-09T09:17:17+00:00
- Post Title: MS-OXRTFCP compression format

don't consider the lzfu compression.
it's specifical for rtf output, that's why you see those text strings in it

I have scanned the file but I don't see interesting output but I don't know what's the original content (text, image or raw) so this doesn't help.
## Post #3
- Username: gooms9
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 27, 2012 8:30 am
- Post datetime: 2012-04-10T02:22:22+00:00
- Post Title: MS-OXRTFCP compression format

Thanks, you just saved me from a wild goose chase. I think I'll decompile the binary and see if I can figure out what's going on from that.
