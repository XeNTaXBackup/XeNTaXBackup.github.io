## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2008-07-14T05:57:59+00:00
- Post Title: Xbox 360 - Smackdown 2008 pac files

I've managed to access the pac files from the disc but rrunpack does not seem to work with these archives. I've also notice that there are 92 pac files instead of three pac files like in the previous versions. This leads me to believe that each model is contain in it's own pac archive. 

Opening the pac file in a hex editor reveals a header stating :epac", previous smackdown pac archive were "dpac"

Here's one of the entire pac files, it's about 2mb big. any help uncompressing the archive would be appreciated. 

[http://ifile.it/ly14a5g](http://ifile.it/ly14a5g)
## Post #2
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2008-07-19T01:18:58+00:00
- Post Title: Xbox 360 - Smackdown 2008 pac files

All the X360 SvR games have had about the same number of PAC files, you must be comparing to the PS2 version, but to answer your question, they started using a different format on the PAC files when they made the X360 version, and there are BPE files contained inside the PAC files, which are Byte-Pair Encoded.  Extracting the BPE files is the easy part, it's finding the correct offset and other factors used for BPE to properly decode them.  

Here is a link which will take you to the encoding and decoding source code: [http://www.csse.monash.edu.au/cluster/R ... oblem.html](http://www.csse.monash.edu.au/cluster/RJK/Compress/problem.html)

If you get it figured out, let us know, I don't have the time anymore to work on this enough to solve it, and I know others have gotten close but no cigar.
## Post #3
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2008-07-22T10:52:12+00:00
- Post Title: Xbox 360 - Smackdown 2008 pac files

Thanks for the response. How are you extracting the bep files from the pac archive? I was using rrunpack to extract, but it doesnt work with the xbox360 format pac files.
## Post #4
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2009-11-16T22:18:08+00:00
- Post Title: Xbox 360 - Smackdown 2008 pac files

what tool do u use to extract the pac files from the .iso of the game? ive tired a few xbox 360 iso tools and have had no success
