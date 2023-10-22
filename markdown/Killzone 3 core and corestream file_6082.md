## Post #1
- Username: Charkes
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 16, 2010 8:37 am
- Post datetime: 2011-02-16T09:44:05+00:00
- Post Title: Killzone 3 core and corestream file

Hi there,

I've recently managed to extract some files from the "data_ps3.psarc" of Killzone 3.
After the extraction I've found a "lumps" folder with many "core" and "corestream" files inside.

I really don't know how to open/extract those file. They seems to be encrypted.

Is there someone who can help me to find how to open them ?

Sample file : [http://dl.dropbox.com/u/1812933/assets_ ... opship.rar](http://dl.dropbox.com/u/1812933/assets_description.vehicles.hgh_dropship_hgh_dropship.rar)

Regards

( Sorry for my bad English )
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-02-16T21:16:27+00:00
- Post Title: Killzone 3 core and corestream file

Looking or on how to extract also.
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2011-02-17T13:04:35+00:00
- Post Title: Killzone 3 core and corestream file

Core and corestream files is a something like a packeges with hard internal structure(but not a fact).

Big part of core files is a small and have descriptions for corestream files. Several core files have data while corestream with the identical names can not have size(0 KB).

Streamcore files is a main game data files. For any levels(single and multiplayer) uses several corestream files.

Simple core and corestream files is audio data files. Audio data in the majority can not be extracted\unpacked, so as vgmstream(plugin for winamp) can play it.

Almost audio data have XVAG header, but Nova Extractor 2.5 can unpack all XVAG header audio data as .mp3.

Music contains in ten files(eight with music in name, two have menu basement in name). Files with ambient in name contain ambient for levels. Files with sound in name contain compressed sound data, which at present cannot be extracted\unpacked.
## Post #4
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-31T15:42:14+00:00
- Post Title: Killzone 3 core and corestream file

and how many audio can converted ? for know
