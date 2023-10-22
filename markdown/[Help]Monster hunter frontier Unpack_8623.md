## Post #1
- Username: osama996
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 22, 2012 1:27 am
- Post datetime: 2012-03-23T18:06:47+00:00
- Post Title: [Help]Monster hunter frontier Unpack

Hi guys , i'm trying to open monster hunter frontier's .pac and .bin files.
I don't know what it contains but i need monster hunter's models.
So .pac files are in the models folder ; .bin files are in the weapon/npc folder.

This is one of the .pac files   :  [http://www.mediafire.com/file/pbhd2dr2cchswa7/em034.pac](http://www.mediafire.com/file/pbhd2dr2cchswa7/em034.pac)


This is one of the .bin files    :  [http://www.mediafire.com/file/q71wqjpo2leob9w/wg249.bin](http://www.mediafire.com/file/q71wqjpo2leob9w/wg249.bin)

I hope that you can open this files.

Ps : i'm italian and i love this forum , sorry for not correct English
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-23T19:57:19+00:00
- Post Title: [Help]Monster hunter frontier Unpack

pac file doesn't seem too bad.
There are some offsets at the top that probably link to each file data. But...the offsets don't seem to jump to each file nicely. Relative offsets? Don't know will need more than just a 30 second glance.

There are obviously some png images there.
Model format is probably the one with the JKR idstring. It starts with an index buffer, and then probably the vertex buffer, but they aren't 4-byte floats so maybe half-floats.

Don't know anything about the bin file though.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-23T22:28:02+00:00
- Post Title: [Help]Monster hunter frontier Unpack

The format for the pac file is

```
numFiles {
    int offset
    int size
}

```


It is recursively defined for each file stored in the pac using the same struct as above.

The offset is relative to the beginning of its own file, so the entries at the top are relative to the pac file, whereas each file's offsets are relative to the start of its own offsets.

Since there are no filenames, it might make sense to just parse the pac directly as models/textures.
I don't know if it always follows the pattern that models are followed by textures, repeat.

Will need more pac's to verify.

EDIT: nvm about the JKR, it looks like pretty much every file has the JKR there (looked at sounds and saw the JKR). There are a couple bytes afterwards that are a little different, so maybe that forms the whole idstring.
## Post #4
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2012-09-07T09:02:58+00:00
- Post Title: [Help]Monster hunter frontier Unpack

Bumping this, really wanna have a look inside the files as well, new versions seem to have changed.
