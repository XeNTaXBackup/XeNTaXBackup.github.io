## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-28T14:02:35+00:00
- Post Title: [PS3] Condemned 2: Bloodshot model import maxscript

Hi guys! Here's maxscript to import Condemned 2: Bloodshot [PS3] models with bones and weights (3ds max 2009-2012).
Inside archive maxscript for models+Noesis plugin for textures



P.S. Report bugs
[Condemned_2.7z](https://xentaxbackup.github.io/file/10845_Condemned_2.7z)
## Post #2
- Username: GENTEK
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 26, 2015 12:22 pm
- Post datetime: 2016-04-28T23:14:26+00:00
- Post Title: [PS3] Condemned 2: Bloodshot model import maxscript

I have extracted Layer.Arch02!
After the extraction... I've using the QuickBMS to Unpack the Layer.Arch02 files!
So now I have all ressources from the game... 
.Snd
.Mdl
.Bndl
Etc...
How I could convert these files ? The FEAR 2 Tool seem not work.
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-29T07:21:31+00:00
- Post Title: [PS3] Condemned 2: Bloodshot model import maxscript

Here's BMS script to extract .bndl archives. All models and textures are in those (world folder if a remember, right -sp, mp and fc sub-folders)
[bndl_ldnb.7z](https://xentaxbackup.github.io/file/10847_bndl_ldnb.7z)
## Post #4
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2017-02-23T17:25:14+00:00
- Post Title: [PS3] Condemned 2: Bloodshot model import maxscript

Sorry to resurrect this old thread, but I've encountered an error with the Noesis texture script. Whenever I try importing the "pants_d" of most characters, I'll usually get this error. 



Linked the sample if anyone wants to check out and see what the issue is.

[http://www.mediafire.com/file/i6gxa34qi ... ants_d.tex](http://www.mediafire.com/file/i6gxa34qiv0ra1c/magic_assistant_pants_d.tex)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-23T20:23:26+00:00
- Post Title: [PS3] Condemned 2: Bloodshot model import maxscript

here ya go  


 fmt_Condemned_2_TEX.zip
(821 Bytes) Downloaded 67 times



i added this to the script

```
elif TexID == 135:
    texFmt = noesis.NOESISTEX_DXT3
```

and turned off the log popup for you
## Post #6
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2017-02-23T22:28:40+00:00
- Post Title: [PS3] Condemned 2: Bloodshot model import maxscript

> Reply from AceWell
>
> here ya go  
fmt_Condemned_2_TEX.zip

i added this to the script
Code: Select all#DXT3
elif TexID == 135:
    texFmt = noesis.NOESISTEX_DXT3
and turned off the log popup for you

Worked like a charm, thank you very much!
