## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T04:29:44+00:00
- Post Title: [Request] Cloud Nine

Hello xentax, first of all I wanna say thanks for fatduck for unpacker script of this game, ok now about format of this game think see before, but not remember.

Models: xskin
Textures: xtex

[Cloud Nine](http://cloudnine.netgame.com/)
[Client (Need log)](http://cloudnine.netgame.com/support/download)

[Cloud Nine 2D-3D Samples](http://www.mediafire.com/download.php?68pkdiu7bjakc75)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T04:51:51+00:00
- Post Title: [Request] Cloud Nine

Hmm ok so I'm guessing it's from the same developer has valiant/argos/DK/War of Dragon considering how the xtex format has the exact same idstring, but the formats are different.

Anyways I've updated the DK online texture plugin and added a new one for this one.
I didn't check enough of the DK online files to verify that my additional checks actually work though.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T05:39:55+00:00
- Post Title: [Request] Cloud Nine

yeah I see finale00, thanks a lot for support, now remaning models, keep working mate.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T05:53:18+00:00
- Post Title: [Request] Cloud Nine

The stuff after the material section I can parse, but I'm not sure what they are for.
I've commented them out but the functions are there.

Weights and vertex morphs I think, since it references a morph file.

Noesis texture finding seems to search for the specified path, and then current directory, so you can place the textures in a folder called "texture" or in the same folder as the model.

[http://db.tt/RMgIGTZ8](http://db.tt/RMgIGTZ8)
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T06:20:53+00:00
- Post Title: [Request] Cloud Nine

this is really cool, well I try test other files and take a look.

01_10310_01_2 (in folder boy m_a_03)



01_10410_01_1 (in folder boy m_a_04)



01_10610_01_1 (in folder boy m_a_06)



01_10720_02_1 (in folder boy m_b_07)



in folder boy m_a_07 not loaded models give error.

```
Traceback (most recent call last):
  File "C:\Program Files\Noesis 3.81\plugins\python\fmt_CloudNine_xskin.py", line 71, in noepyLoadModel
    load_all_models(mdlList)
  File "C:\Program Files\Noesis 3.81\plugins\python\fmt_CloudNine_xskin.py", line 49, in load_all_models
    parser.parse_file(filename)
  File "C:\Program Files\Noesis 3.81\plugins\python\fmt_CloudNine_xskin.py", line 156, in parse_file
    matName = self.parse_material()
  File "C:\Program Files\Noesis 3.81\plugins\python\fmt_CloudNine_xskin.py", line 115, in parse_material
    blend = self.read_name()
  File "C:\Program Files\Noesis 3.81\plugins\python\fmt_CloudNine_xskin.py", line 92, in read_name
    return noeStrFromBytes(string)
  File "C:\Program Files\Noesis 3.81\plugins\python\inc_noesis.py", line 924, in noeStrFromBytes
    return str(bar, enc).rstrip("\0")
UnicodeDecodeError: 'ascii' codec can't decode byte 0x80 in position 115: ordinal not in range(128)
Cleaned 8.00MB (in 2 pools).
```
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T06:21:47+00:00
- Post Title: [Request] Cloud Nine

I don't have 06 or 07.

Textures are kind of interesting. Upload those folders.
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T06:29:14+00:00
- Post Title: [Request] Cloud Nine

ok then.

[Cloud Nine boy 2D-3D Samples](http://www.mediafire.com/download.php?otsaqjq5trlolso)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T06:55:30+00:00
- Post Title: [Request] Cloud Nine

Turns out that some of the texture files have an extra 8 bytes before the start of the pixel data.
I am not sure how to check this, so I just took one of the shorts at the top and used that as the "type"

So far it seems to work for the samples. I've added an extra print statement to the debug log if you saw an unknown type, so if it says "unknown type" you can just upload the file and say what type it is. Until I find a better way to determine whether there are extra bytes or not.

I don't know what is wrong with the legs that are out of place.

I've also modified the model parser since the stuff I thought were just random nulls actually indicated whether there were specular and normal maps or not.
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-18T07:44:54+00:00
- Post Title: [Request] Cloud Nine

OOOOOOOO, Very Nice stuff, from hour new master Finale rapid and furious man.
## Post #10
- Username: wimmeke001
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 13, 2012 2:23 am
- Post datetime: 2012-09-12T12:37:27+00:00
- Post Title: [Request] Cloud Nine

request plz waepen models xgeom files 
sample [http://www.mediafire.com/?lbz168yro4v2xla](http://www.mediafire.com/?lbz168yro4v2xla)
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-12T14:39:10+00:00
- Post Title: [Request] Cloud Nine

Cloud nine has xgeom files? Never noticed them.
Or maybe I'm thinking Continent of the ninth...lol

Need some textures.
Send me "Item\Weapon\Bow\Texture\00_39001_14_0.xTex"
[cloudNine_xgeom.jpg](https://xentaxbackup.github.io/file/5809_cloudNine_xgeom.jpg)
## Post #12
- Username: wimmeke001
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 13, 2012 2:23 am
- Post datetime: 2012-09-12T16:41:33+00:00
- Post Title: [Request] Cloud Nine

texture work fine but here if you need it
[http://www.mediafire.com/?b7uw44xx4a47w8s](http://www.mediafire.com/?b7uw44xx4a47w8s)
btw ty for the script
## Post #13
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-11-30T05:26:28+00:00
- Post Title: [Request] Cloud Nine

Valiant have .xgeom files and Noesis cant load with the finale plugin, some idea?

Valiant samples:
[http://www.mediafire.com/?43pffhwi8f7m7](http://www.mediafire.com/?43pffhwi8f7m7)
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-12-01T02:53:36+00:00
- Post Title: [Request] Cloud Nine

Is this game Valiant or Cloud Nine???
## Post #15
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-12-01T03:45:28+00:00
- Post Title: [Request] Cloud Nine

> Reply from finale00
>
> Is this game Valiant or Cloud Nine???

Its valiant xgeom files.
