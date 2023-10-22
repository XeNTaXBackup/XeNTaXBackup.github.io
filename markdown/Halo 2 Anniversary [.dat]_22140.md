## Post #1
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2020-05-13T15:11:19+00:00
- Post Title: Halo 2 Anniversary [.dat]

Hey everyone, i'm trying to figure out how to get the audio for Halo 2 anniversary, the file format they used is similar to what they employed for Halo Online which was using compressed .dat containers. Cra0 wrote a crude tool which was able to uncompress the data but when trying it on Halo 2 I get this error:

```
   at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
   at System.IO.BinaryReader.ReadUInt32()
   at ..(BinaryReader ,  )
   at ...(BinaryReader ,  )
   at ..()
   at ..()
   at ..()
   at ..(String[] )
```
 

Nothing extracts... 

Halo Online's audio data once extracted, was simply mpeg audio. The Hex viewer however showed FSB strings - but once you decompressed the archive the audio was standard FSB audio format compression without FSB header, so all you had to do was change the extension to .mpeg and done. The same strings are present throughout the Halo 2 files as well. I've included a sample file, if anyone can help me figure out, or if possible write something that can decompress or allow audio extraction i'd greatly appreciate it.
[sounds_remastered.zip](https://xentaxbackup.github.io/file/18141_sounds_remastered.zip)
## Post #2
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2020-05-18T15:20:47+00:00
- Post Title: Halo 2 Anniversary [.dat]

Anybody discover anything, learn anything?
