## Post #1
- Username: dsasmblr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 20, 2017 10:53 pm
- Post datetime: 2017-07-20T15:47:54+00:00
- Post Title: Need help with .FLT (Magic: LIB_PACKDATA)--File samples incl

This is a file format I've been working on for a week now but I've exhausted my current knowledge on the subject and I've reached a dead end.

I've tried a number of approaches to try to make sense of the bytes. Out of 3 files used to compare, there's clearly a header containing a magic number, some sort of count of files/filenames, and...that's about where I'm at. There appears to be no size data, but there are a bunch of zeroes making me think this is compressed.

But on top of that, the only readable characters are the magic number. Everything else appears to be encrypted. I'm not seeing signs of XOR, but I tried a few combinations of XOR and ROT* (including ROT47) to no avail. I also tried other bitwise operations just to see if anything stuck out. That's not to discount those as potential options still, though.

Out of curiosity, I created a memory dump of the game while running it so as to compare some of how these files look unpacked. They retain their header bytes, so I was able to just search for the magic number in the dump to find these files in memory. There are, indeed, things that show as plain text, such as internal paths to resources (including extensions for those resources) as well as individual strings of dialogue for characters; however, there are some anomalies with how the data is lined up as compared to the compressed/encoded/encrypted versions.

Interestingly, there is a clear correlation between the number of bytes of certain filenames/paths in the compressed file and the uncompressed version. I XOR'd those bytes and ended up building a partial a-z legend, of which I search for 3 consecutive bytes of and DID find something in the uncompressed version of the file. I built out the rest of the legend based on my findings, but oddly, a few of the characters don't pan out. This could very well be a dead end.

To note, the game is Purino Party. Below are direct links (so you can right-click, save as) to files that I've uploaded on my site:

Link 1: [update00.FLT](http://dsasmblr.com/download/xentax/update00.FLT) - This is the file in its entirety from the game directory. It's tiny (24KB).
Link 2: [update00(FROM-LIVE-DMP).FLT](http://dsasmblr.com/download/xentax/update00%28FROM-LIVE-DMP%29.FLT) - A small, 17KB sample dump of update00.FLT as it appears in memory while the game is running.
Link 3: [data(2MB-SAMPLE).FLT](http://dsasmblr.com/download/xentax/data%282MB-SAMPLE%29.FLT) - A 2MB sample of data.FLT. If useful, the full file size is noted as 878MB (920,986,238 bytes) with size on disk being noted as 878MB (920,989,696).
Link 4: [data(FROM-LIVE-DMP).FLT](http://dsasmblr.com/download/xentax/data%28FROM-LIVE-DMP%29.FLT) - A 2MB sample of data.FLT as it appears in memory while the game is running.

And finally, there's a patch that can be applied to the game to make it the "adult" version. It's tiny and is also of the same format as the files above. Unlike the links above, this isn't a direct download, but you'll see the file on the page:
Link: [http://download.frontwing.jp/en/games/purino-party/](http://download.frontwing.jp/en/games/purino-party/) - A small patch for the game.

Another thing I think I've established is that the update and patch FLT files are loaded inline with the main data.FLT, so the result is a mixed amalgamation of each of the file instead of seeing ALL of data.FLT, then ALL of update00.FLT after that, etc. But here again, I could be off base.

My next attempt is going to be using a debugger to try to find how/where the game exe loads these files, but that will be new territory for me.

Anyway, just to clarify, I'm not looking for a script or unpacker here. I'm looking for knowledge and what the thought processes are along the way to reverse this format. It may be really simple for some of you, but I'd really like to hone in on picking up even the smallest things from that seem really simple or second-nature in thought. Maybe this would be worthy of a video for your Let's MultiEx series, Mr. Mouse? I've really enjoyed that series thus far, so thanks for those videos. =)

Thanks for any help, everyone!
