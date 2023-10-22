## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2020-05-09T16:36:02+00:00
- Post Title: Disney Infinity 3 (*.zip)

Well there exists a bms script for most of the 'zip' files in this game, however, it fails to extract any of the assets from the 'Force Unleashed' related material. I was hoping someone could find a way to extract these specific files properly. They clearly contain the usual Disney Infinity files, but getting them out has so far been impossible.

[https://www.dropbox.com/s/pe5tx4swhzu7x ... m.zip?dl=0](https://www.dropbox.com/s/pe5tx4swhzu7xaa/psx_grimm.zip?dl=0)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-05-10T00:57:52+00:00
- Post Title: Disney Infinity 3 (*.zip)

From a quick look at the file, I can't see anything recognisable.  It looks to be encrypted, so you would need to know the method and the key to decrypt it first.
## Post #3
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2020-05-15T20:42:57+00:00
- Post Title: Disney Infinity 3 (*.zip)

Typically in these files they contain two sub-folders 'characters' and 'textures'. The formats are all proprietary except the textures which are just re-named DDS files. The easiest files to recognize in them are '.vbuf' '.ibuf' and '.oct'. These are not normal ZIP files, they are specific to Disney Infinity's file structure. There exists a quickbms script for them which opens them all except those used for Force Unleashed content.
