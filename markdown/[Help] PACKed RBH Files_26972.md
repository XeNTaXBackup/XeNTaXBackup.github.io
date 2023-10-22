## Post #1
- Username: LudaX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 01, 2021 6:23 am
- Post datetime: 2023-07-11T17:53:41+00:00
- Post Title: [Help] PACKed RBH Files

Hi all! I'm looking for some help with some RBH files, which seems to be the file format used by [Tantalus](https://en.wikipedia.org/wiki/Tantalus_Media) in many of their games. I have found several posts talking about RBH files in general, but the posts that I've found seem to focus on RBH files with BODY chunks. The RBH files that I'm exploring currently have PACK chunks instead, and I'm trying to figure out how to extract the contents from these.

I'll start with what I know so far... The PIFF format seems to be Tantalus's take on RIFF files. Each .rbh file starts with a 'PIFF' magic number, followed by the file size and then 'RBHFRBHH'. The RBHH chunk contains information about each chunk, including the decompressed size (or at least, I think they're compressed). Then, we get to the chunks of data themselves. As mentioned, these can be BODY chunks, but in my case, are PACK chunks instead.

To save describing the whole format in a long paragraph, here's the Kaitai struct I've worked out so far:

```
  id: rbh
  title: Tantalus RBH File
  file-extension: rbh
  endian: le
doc: |
  Compressed file used by Tantalus Media games
seq:
  - id: header
    type: header
  - id: chunks
    type: chunk
    repeat: eos
types:
  header:
    seq:
      - id: magic
        contents: 'PIFF'
      - id: file_size # Not including the magic number and this file size field...
        type: u4
      - id: rbhf
        contents: 'RBHF'
  chunk:
    seq:
      - id: chunk_type
        type: str
        size: 4
        encoding: UTF-8
      - id: chunk_size
        type: u4
      - id: data
        type:
          switch-on: chunk_type
          cases:
            '"RBHH"': rbhh_data(chunk_size)
            '"BODY"': body_data(chunk_size)
            '"PACK"': pack_data(chunk_size)
            '"RELC"': relc_data(chunk_size)
            '"GLOB"': glob_data(chunk_size)
            
  # Data types for each chunk type
  rbhh_data:
    params:
      - id: data_size
        type: u4
    seq:
      - id: chunk_entries
        type: chunk_entry
        repeat: expr
        repeat-expr: data_size / 12 # each chunk entry takes up 12 bytes
  chunk_entry:
    seq:
      - id: zeros
        type: u4
      - id: decompressed_size
        type: u2
      - id: unk2
        type: u2
      - id: unk3
        type: u2
      - id: unk4
        type: u2
  body_data:
    params:
      - id: data_size
        type: u4
    seq:
      - id: raw_data
        size: data_size
  pack_data:
    params:
      - id: data_size
        type: u4
    seq:
      - id: size_decompressed
        type: u2
      - id: size_compressed
        type: u2
      - id: raw_data
        size: data_size - 4
  relc_data:
    params:
      - id: data_size
        type: u4
    seq:
      - id: unknown_ints
        type: u4
        repeat: expr
        repeat-expr: data_size / 4
  glob_data:
    params:
      - id: data_size
        type: u4
    seq:
      - id: num_entries
        type: u4
      - id: unknown # usually 1
        type: u4
      - id: entries
        type: glob_entry
        repeat: expr
        repeat-expr: num_entries
  glob_entry:
    seq:
      - id: offset
        type: u4
      - id: unknown
        type: u4
```


Using this structure with a file like Date.text.rbh (downloadable [here](https://mega.nz/folder/GSoEDK6A#6GKtPJRyvp4dpGvKQXv7nw)), the corresponding structure might look something like:



Note the PACK chunks... That's what I'm puzzled by at the moment. How do you decompress or decode this PACKed data? It doesn't look like any compression I've seen before (but my experience is mostly limited to looking for zlib headers ). Has anyone encountered a packing technique like this before? Any suggestions for decompression methods to look into?

If it helps, by stepping through a game using this format with a debugger, I can identify the decompressed data for some loaded chunks, like the above Date.text.rbh file:



The games that I have observed these PACK chunk RBH files within includes MX vs. ATV Untamed and SpongeBob SquarePants: The Yellow Avenger, but I believe this PACK chunk is used in other games as well.

Sample RBH files with PACK chunks: [https://mega.nz/folder/GSoEDK6A#6GKtPJRyvp4dpGvKQXv7nw](https://mega.nz/folder/GSoEDK6A#6GKtPJRyvp4dpGvKQXv7nw)

Some of the existing posts I found on RBH files for reference:
viewtopic.php?t=14571
viewtopic.php?t=14469
viewtopic.php?t=14623
https://www.youtube.com/watch?v=CMJWit4wLfE
https://web.archive.org/web/20080331031 ... /wiki/.RBH
https://github.com/wattostudios/GameExt ... _PIFF.java
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-11T18:49:18+00:00
- Post Title: [Help] PACKed RBH Files

> How do you decompress or decode this PACKed data?

I've checked your sample and I've used compression scanner from aluigi to scan for known compressions.
Unfortunately no results have been found with expected decompressed size, so it's either custom compression or it is compressed and encrypted at the same time.

I'm afraid nothing more can be done without debugging.
## Post #3
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2023-07-15T00:13:41+00:00
- Post Title: [Help] PACKed RBH Files

[https://github.com/leeao/RORPSPTOOL](https://github.com/leeao/RORPSPTOOL)
