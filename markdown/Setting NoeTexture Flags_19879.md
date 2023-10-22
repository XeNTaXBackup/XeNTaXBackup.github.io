## Post #1
- Username: dgl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 28, 2019 1:32 pm
- Post datetime: 2019-03-28T05:38:09+00:00
- Post Title: Setting NoeTexture Flags?

I'm playing around with a file format that uses texture wrapping, specifically mirrored mapping (and the occasional y-flipping). 
Can these values be set with noe texture? I noticed there are flags in the NoeTexture file type, but I can't figure out which values
for what flag or what they would do.

```
#for supported pixel types, look at constants exposed by noesis module, such as NOESISTEX_RGB24, NOESISTEX_RGBA32, NOESISTEX_DXT1, etc.
class NoeTexture:
    def __init__(self, name, width, height, pixelData, pixelType = noesis.NOESISTEX_RGBA32):
        self.name = name
        self.width = width
        self.height = height
        self.pixelData = pixelData
        self.pixelType = pixelType
        self.flags = 0
        self.mipCount = 0
    def __repr__(self):
        return "(NoeTexture:" + " w:" + repr(self.width) + " h:" + repr(self.height) + " p:" + repr(self.pixelType) + " f:" + repr(self.flags) + " n:" + repr(self.name) + ")"

    def setFlags(self, flags):
        self.flags = flags

    def setMipCount(self, mipCount):
        self.mipCount = mipCount

```


Edit:

Okay I'm an idiot. After looking around I found the following constants declared in ./plugins/python/__NPReadMe.txt

```
    PYNOECONSTN(NTEXFLAG_ISNORMALMAP),
    PYNOECONSTN(NTEXFLAG_SEGMENTED),
    PYNOECONSTN(NTEXFLAG_STEREO),
    PYNOECONSTN(NTEXFLAG_STEREO_SWAP),
    PYNOECONSTN(NTEXFLAG_FILTER_NEAREST),
    PYNOECONSTN(NTEXFLAG_WRAP_CLAMP),
    PYNOECONSTN(NTEXFLAG_PREVIEWLOAD),
    PYNOECONSTN(NTEXFLAG_CUBEMAP),
    PYNOECONSTN(NTEXFLAG_ISLINEAR),
    PYNOECONSTN(NTEXFLAG_HDRISLINEAR),
    PYNOECONSTN(NTEXFLAG_WANTSEAMLESS),
    PYNOECONSTN(NTEXFLAG_WRAP_MIRROR_REPEAT),
    PYNOECONSTN(NTEXFLAG_WRAP_MIRROR_CLAMP),

```
