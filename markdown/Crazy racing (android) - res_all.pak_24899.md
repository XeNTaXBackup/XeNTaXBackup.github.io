## Post #1
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-12-30T14:12:52+00:00
- Post Title: Crazy racing (android) - res_all.pak

there should be a script to unpack the archive
## Post #2
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2022-07-11T06:47:33+00:00
- Post Title: Crazy racing (android) - res_all.pak

bump, here is the link [https://drive.google.com/file/d/1sR1i5B ... p=drivesdk](https://drive.google.com/file/d/1sR1i5BcOaujWpDRq_UuSZq59mfhMyz_1/view?usp=drivesdk)
## Post #3
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-12T17:13:10+00:00
- Post Title: Crazy racing (android) - res_all.pak

The files inside this archive are all LZMA compressed. The header starts with a list of file information entries that contain their offset (divided by 4), compressed size and a hash of their filename. The game references entries by their filename so they're available but not easily. 

I've run a quick [dump](https://pastebin.com/4HgKJPZD) from v1.9.9.9 and generated some names however it is only about 40% of what's in the archive. Depending on your needs you might need to work out the rest.

```
{
    uint FileCount;
    FileInfo FileInfos[FileCount];
    byte Data[x];
}

struct FileInfo
{
    uint Hash;
    int Offset;         // multiply by 4
    int CompressedSize; // LZMA
}

uint Hash(string value)
{
    // append suffix and lowercase 
    // e.g. Res\ALight.mesh => res\res\alight.mesh
    value = (@"res\" + value).ToLower();

    uint h = 0u;
    for (int i = 0; i < value.Length; i++)
        h = 31 * h + (byte)value[i];

    return h;
}

```
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-13T10:58:02+00:00
- Post Title: Crazy racing (android) - res_all.pak

And here's the wiki article for future reference
[http://wiki.xentax.com/index.php/Crazy_Racing_PAK](http://wiki.xentax.com/index.php/Crazy_Racing_PAK)

Thanks for sharing, barncastle
## Post #5
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2022-08-16T18:22:42+00:00
- Post Title: Crazy racing (android) - res_all.pak

great, but are the mesh files ogre
also, does this work with urban chaser
## Post #6
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2022-12-07T10:00:48+00:00
- Post Title: Crazy racing (android) - res_all.pak

hmm, bumping this
