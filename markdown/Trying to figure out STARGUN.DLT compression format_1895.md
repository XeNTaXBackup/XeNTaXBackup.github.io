## Post #1
- Username: Wormbo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 09, 2006 7:51 pm
- Post datetime: 2006-05-09T12:53:57+00:00
- Post Title: Trying to figure out STARGUN.DLT compression format

I'm trying to extract music (MOD) and sound (WAV) files from [Stargunner](http://www.3drealms.com/stargunner/)'s STARGUN.DLT data file. I already figured out the basic archive format, but the individual files are somehow compressed.

Archive header:

[4] "DAVE"
[2] unknown; I compared the shareware and "registered full freeware" versions of the file and it was always 0x00 0x01
[2] (short) number of files in archive

then for each file:
[32] filename (see below)
[4] unknown (maybe a checksum?)
[4] size in archive
(compressed file content, see below)

amd at the end of the archive:
[40] 40x ASCII 0


To decode the filename I found the following algorithm useful:
(Java, byte[] header is the filename as read from the archive)

```
  header[i] = (byte) ((header[i-1] + i) ^ header[i]);
```


The compressed file content looks like this:

[4] "PGBP"
[4] uncompressed file size
[?] probably some kind of dictionary
[?] compressed file content

The compression format leaves large parts of the file unchanged. For example the WAV files can be played back after fixing the RIFF WAVE header, but some samples are obviously broken.
## Post #2
- Username: Wormbo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 09, 2006 7:51 pm
- Post datetime: 2006-05-12T15:13:07+00:00
- Post Title: Trying to figure out STARGUN.DLT compression format

Hmm, can anyone help me understanding that "dictionary" data or whatever those bytes are supposed to mean?
They do seem to contain the byte sequences missing in the file, but I can't seem to figure out, how Stargunner determines, which bytes in the compressed file to replace with which byte sequence.
