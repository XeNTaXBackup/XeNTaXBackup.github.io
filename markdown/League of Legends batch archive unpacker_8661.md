## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-29T21:01:18+00:00
- Post Title: League of Legends batch archive unpacker

I'm looking for a batch unpacker for this game's archives.

The source code for the current modding tool can be found at
[http://code.google.com/p/siu-lgg/source ... y%2FRAFLib](http://code.google.com/p/siu-lgg/source/browse/#hg%2FThirdParty%2FRAFLib)

This includes the algorithms for unpacking the data.

For each update, they just create a new folder for that release and put all the data as a new archive.
Current tools are for modding purposes and are unfeasible for mass data dumps. If you just want to see all the data, it is better to just dump everything rather than dump things one at a time. Maybe there is a function to dump everything, but I couldn't find it...

Essentially, all you have to do is walk through the data folder, grab each archive, and unpack it.
