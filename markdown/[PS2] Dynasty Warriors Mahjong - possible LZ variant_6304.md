## Post #1
- Username: Rydain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 27, 2011 10:36 am
- Post datetime: 2011-03-27T03:04:39+00:00
- Post Title: [PS2] Dynasty Warriors Mahjong - possible LZ variant?

I'm attempting to rip the images from Dynasty Warriors Mahjong, a.k.a. Jan Sangoku Musou. The relevant data file mostly consists of compressed chunks beginning with the tag LZP2. The command-line file utility of OS X identifies these chunks as MS-DOS executables. My search for the file type led me to [Charles Bloom's decoders](http://www.cbloom.com/src/index_lz.html), which I tried to no avail - I either got an error or a 0-size file.

I've attached a sample which appears to contain some TIM2's. Thanks in advance for any and all input. 
[8.LZP2.zip](https://xentaxbackup.github.io/file/4115_8.LZP2.zip)
## Post #2
- Username: Rydain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 27, 2011 10:36 am
- Post datetime: 2011-04-07T04:41:08+00:00
- Post Title: [PS2] Dynasty Warriors Mahjong - possible LZ variant?

This compression is used in other PS2 Dynasty Warriors games. I'm hoping that plain text might be easier to analyze, so here's a sample thereof from Dynasty Warriors 5: Xtreme Legends. The corresponding uncompressed text is attached to the post.

[Compressed data file (1.4 MB)](http://www.mediafire.com/?rvzobkuo0we759z)


 dw5xl_text_dump.txt.zip
(1.05 KiB) Downloaded 26 times



When reading through the compressed text, I can fill in each symbol-represented area with one or more strings from the text above. Thus, this may be a simple and/or common LZW variant. It certainly isn't an actual LZP2, as I concatenated and compressed the plain text for comparison and got nothing remotely close to the ripped file.

LZP2-tagged data blocks have the following header:

4 bytes - LZP2 tag
4 bytes - AE 47 81 3F (meaning unknown - has the same value in all the samples I checked)
4 bytes - Uncompressed size of data
4 bytes - Compressed size of data (everything after the header)

And that's all I know at the moment. I tried running my sample through the quickbms brute force decompression script with the following alterations:

- 16-byte header removed
- 4-byte LZP2 tag removed
- 4-byte LZP2 tag & following 4 bytes removed

In every case, I got garbage out of the various LZ algorithms. I don't know if there is data past the 16-byte header that should be removed or altered, and I'm finding it difficult to dig up comprehensive information on what the headers of LZ-encoded data blocks should actually contain. More direction or documentation would be great.
