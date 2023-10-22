## Post #1
- Username: UltimateXeallar
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 27, 2015 3:30 am
- Post datetime: 2015-07-26T19:38:04+00:00
- Post Title: Metal Slug 3 PS2 Port ".pak" files help

Hi Hello, I come from a distant part of the internet looking for some assistance.
So Metal Slug 3 was ported to the PS2.  Kinda common knowledge.  All the files are kept inside 6 ".afs" files (I'm able to extract these easily), but inside the AFS files are .pal, .pak, and .adx files (including a SND file.)
I'm able to play the ADX and SND files fine with PSound, but not do anything with the pak files.  Most of them have a "CHRD" header, and seem to be compressed with various formats.  Any help on how to decompress these?
Here's a Example file (and incidentally the one I'm most interested in as it's the biggest file inside the AFS archive):
[https://www.dropbox.com/s/x7yn6bfb6yukr ... p.pak?dl=0](https://www.dropbox.com/s/x7yn6bfb6yukr44/chr_allp.pak?dl=0)

Anyone got any ideas on this?
## Post #2
- Username: UltimateXeallar
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 27, 2015 3:30 am
- Post datetime: 2015-07-28T00:19:09+00:00
- Post Title: Metal Slug 3 PS2 Port ".pak" files help

So I did some experimentation,  apparently the file in my link is looking like a LZ77 compressed (Or a specific version of LZ77, either way) file, so that's looking like a good start, at least. 
I wouldn't be surprised if it's not a common form of LZ77.  Most PS1/PS2 ports of game don't really have a standard compression format.
