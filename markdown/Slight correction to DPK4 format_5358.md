## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2010-11-06T02:08:09+00:00
- Post Title: Slight correction to DPK4 format

Looking at a cached version of its page on the wiki, I think I have found a detail that's overlooked: if the compressed file size and the uncompressed file size is the same, the file is not actually compressed. Before I looked at the format for it here, I manually researched the file format and made an extractor. I found that some files had an arbitrary number of nulls as its content. Looking back in the archive, I found that the files were plaintext. Apparently files that are really small (something like less than 100 bytes, or if the zlibbed file is bigger than the original), would be stored as plaintext.

I am absolutely oblivious to BMS, so I can't help fix it.
