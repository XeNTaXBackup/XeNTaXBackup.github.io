## Post #1
- Username: WSSDude
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2015 6:49 pm
- Post datetime: 2018-06-09T12:58:38+00:00
- Post Title: Indiana Jones and the Emperor's Tomb (.RPE extractor)

Hi!

I was trying to decompress .RPE files of this game and managed to do so in fairly short time.
Though, I stumbled upon one big issue - I cannot for whatever reason play the IMA ADPCM files that came out of the archive.

They seem to be modified in some way, I don't know how exactly. 
There are two extra chunks at the end (probably some extra data for the game engine) and size of data chunk seems to be garbage value in every extracted file for whatever reason.

If somebody could help me get the playback working, I would really appreciate it!

Findings about .RPE files:
1..4 - seems to always be uint32 = 1
5..8 - number of files in archive (lets call this N)
9..32 - all nulls
33..N*44 - file information table
rest - uncompressed data

Each file information table chunk has following structure:
1..32 - null-terminated string, ID
33..36 - offset to data
37..40 - size of data
41..44 - unknown (seems to be floating point value, duration of audio file possibly?)

All files contained within .RPE files seems to be encoded with some variation of IMA ADPCM.

In attachment is compiled tool for extraction along with source code.
Its console only, usage is printed when run without any arguments.
(creation of RPE files is currently not implemented, as there are still few unknowns to be cleared out...)
[rpe-extractor.7z](https://xentaxbackup.github.io/file/14454_rpe-extractor.7z)
## Post #2
- Username: WSSDude
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 26, 2015 6:49 pm
- Post datetime: 2018-06-09T13:21:08+00:00
- Post Title: Indiana Jones and the Emperor's Tomb (.RPE extractor)

I just realized that I didn't give any example file that is outputted. 
Here are few...
[out-examples.7z](https://xentaxbackup.github.io/file/14455_out-examples.7z)
