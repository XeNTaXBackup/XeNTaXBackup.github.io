## Post #1
- Username: Samchongsa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 20, 2021 3:13 am
- Post datetime: 2021-09-19T20:02:32+00:00
- Post Title: New Fortress - .spr and .i16 files

Good evening. I am very new in reverse engineriing and I need assistance trying to obtain sprites from an old online game called New Fortress. The game is defunct since 2005 and is no longer operative (so its hard to get uncompressed sprites from RAM since we can't run it), but I still have the original files saved from back then. 

Files
[https://www.mediafire.com/file/37wsojdr ... e.zip/file](https://www.mediafire.com/file/37wsojdrn6y5xg2/FortressAdventure.zip/file)

Some examples of how the sprites are supossed to look like are the following (as posted originally from an old blog back in 2008)



I believe these are saved as .spr and .i16 files, although I do not know this format.  The only thing which I could use in order to have a clue in how to obtain the correct format is the .pdb file contained in the directory.

PDB File
[https://www.mediafire.com/file/y0hdic4d ... C.pdb/file](https://www.mediafire.com/file/y0hdic4dvswowzl/FC.pdb/file)

Some of the .spr files

[https://www.mediafire.com/file/ha5lh8wp ... e.spr/file](https://www.mediafire.com/file/ha5lh8wp9uqwbjh/dkpunch_a_fire.spr/file)
[https://www.mediafire.com/file/nt82jcrm ... x.spr/file](https://www.mediafire.com/file/nt82jcrmphmk7at/dkpunch_a_fix.spr/file)
[https://www.mediafire.com/file/z0we407m ... t.spr/file](https://www.mediafire.com/file/z0we407mlurt240/dkpunch_a_hit.spr/file)

When checking one of them, i've got the following result:



As you can notice, there is something saying "Plus File Format" but i don't know how usefull can this be for. I feel maybe Huffman compression method might be needed in order to reverse these files but i've never tried it myself before.

Only useful info I could obtain from the .pdb has been this

```
CCompress::Encode
CCompress::Decode
CCompress::SpriteEncode
CCompress::SpriteDecode
CCompress::HuffEncodeStart
CCompress::HuffEncodeEnd
CCompress::HuffDecodeStart
CCompress::HuffDecodeEnd
CCompress::EncodeP
CCompress::DecodeP
CCompress::MakeTable
```


Thank you in advance for your assistance!
## Post #2
- Username: Samchongsa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 20, 2021 3:13 am
- Post datetime: 2021-09-19T20:58:54+00:00
- Post Title: New Fortress - .spr and .i16 files

Alright, i've run signsrch over the .exe file, and i've obtained the following.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-19T21:33:00+00:00
- Post Title: New Fortress - .spr and .i16 files

Maybe info from this topic will help you a little
[viewtopic.php?f=18&t=10332](https://forum.xentax.com/viewtopic.php?f=18&t=10332)
