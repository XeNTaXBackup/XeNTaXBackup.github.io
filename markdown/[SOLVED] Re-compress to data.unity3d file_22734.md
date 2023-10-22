## Post #1
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2020-09-22T13:31:28+00:00
- Post Title: [SOLVED] Re-compress to data.unity3d file?

How can I recompress a Unity game to data.unity3d etc. files, once decompressed to single files: resources.assets, resources.resource, sharedassets0.assets etc.?

I'm working on a Flashback (classic) re-translation (horrible Google Translation for non-english languages), but found the Steam version was packed to data.unity3d... files, and GOG version instead was uncompressed. I can uncompress it with UABE I guess, but how can I re-compress them back to data.unity3d? I'd like to release a simple final diff-patch for the original Steam format files.
## Post #2
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2020-10-10T08:07:03+00:00
- Post Title: [SOLVED] Re-compress to data.unity3d file?

Ooops, I missed it is already built-in in UABE (Unity Assets Bundle Extractor):
File menu > Open (also .unity3d files),
then choose Yes to decompress it on request,
finally you can Import back a modified resources.assets file overwriting original,
then you can Save an uncompressed .unity3d file,
finally you can simply File > Compress the new .unity3d file.
