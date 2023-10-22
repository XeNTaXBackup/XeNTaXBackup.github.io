## Post #1
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-05-28T18:51:57+00:00
- Post Title: Bunch of assets mixed in one folder

I'm trying to get the textures for an android game, and there are a bunch of files with random 32 character names and no extensions.

I've sorted through them and some of them are .png files, but these are just the loading icon.
Some are .xml files, and some of these xml files contain image data base64 encoded. Decoding the data gives me a MRCI compressed pngs (I would like help on how to uncompress these too), but these only seem like particle images.
Some are .ttf fonts, and some are .json files.

The rest I cannot figure out and they are included here:
[https://mega.nz/#!u1cBBB7A!621qxowHhSD7 ... ZqANQMyKas](https://mega.nz/#!u1cBBB7A!621qxowHhSD7e9PpccdY7jykz2OODNGwOZqANQMyKas)

Most of the files have the same beginning: here I took the first two characters in utf-8.
3035 files begin with tp (maybe textures, since there are so many.)
75 files begin with MA (contain .png names of each frame of animated sprite?)
71 files begin with 4L
18 files begin with ~_
8 files begin with Ex
43 files begin with RS

This seems like each of those are a "type" of file, like audio, texture, etc, but not sure.

An example of each one of these are:
tp: 0011a9a511f1cc85cb1ad3c18705eb29
MA: 054c8de61ec410259477b3e490bec486
4L: 05a8f7650537792a50f086ff1606a78e
~_: 06002049d5dbbfe928d3aa0668bb5987
Ex: 144a26e8d0e75d09eb674c13b6162f9f
RS: 18e99a46745a722fbed14efc812a503b

There's 3 separate files that I could only find one of each, d5d1ed3dc06689073a1c047609b6bb08 (which only contains the number 1) 4d2b37eb64da8f9071b2cddcbed71b75, and f6374a3ba9ab5cda87e0a4998709c496

All that might not even be relevant, but I thought I would share my findings.

Any help would be nice!

EDIT: the "4L" ones are mrci compressed as well, so it seems those are the textures. So help with a quickbms script would be appreciated.
## Post #2
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-06-04T16:41:40+00:00
- Post Title: Bunch of assets mixed in one folder

I can see that the game textures were packed with TexturePacker, and the game was created in cocos2d. The header of some files are 'opencrypt' backwards (tpyrcnepo). Any ideas??
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-05T00:47:14+00:00
- Post Title: Bunch of assets mixed in one folder

> Reply from Mikeee
>
> Any ideas??
i didn't look at them all but they look encrypted to me, maybe run them by aluigi
