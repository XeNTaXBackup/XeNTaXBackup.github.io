## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-29T19:56:55+00:00
- Post Title: Away3D decompression

I've been looking into Away3D models from [Honda 3D Design Archives](http://www.honda-3d.com/). The .awd files are compressed, and this format seems to use zlib or lzma.
I'm attaching a quickbms script I made for decompression.

The same engine is used by Nissan for their personalization pages - [Juke](http://www.nissan.co.uk/GB/en/vehicles/crossovers/new-juke/personalisation.html) and other models. Only this time the awd files are embedded in swf along with what appear to be compressed [ATF textures](http://away3d.com/tutorials/Introduction_to_ATF_Textures).
Unfortunately I haven't been able to extract these textures; I can't even open them with ATFViewer from Adobe's Gaming SDK.

Update: For now I made a conversion script for quickbms.
[Collection of scripts](https://www.mediafire.com/folder/fsis1fzc0l4aa/Away3D) (sorry, I can only attach one file here)
- awd decompressor
- atf convertor
- abg decompressor
- abg to obj decompressor & converter
- maxscript for loading GarageFuse scenes
[awd.zip](https://xentaxbackup.github.io/file/7615_awd.zip)
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-30T08:57:08+00:00
- Post Title: Away3D decompression

[out]
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-30T09:29:17+00:00
- Post Title: Away3D decompression

Damn, that does sound awful.

Any idea where I could find the source code for this old encoder?
Is it by any chance the one on github? [https://github.com/adobe/dds2atf](https://github.com/adobe/dds2atf) It seems somewhat old, from 2 years ago.
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-30T11:24:53+00:00
- Post Title: Away3D decompression

[out]
## Post #5
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-30T11:37:39+00:00
- Post Title: Away3D decompression

Unfortuantely that doesn't match the samples I uploaded. Some would have format 4 or 5, others wold have height = 0.

To me it looks like everything after "ATF" is compressed, header included.
## Post #6
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-30T12:01:25+00:00
- Post Title: Away3D decompression

[out]
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-30T13:01:48+00:00
- Post Title: Away3D decompression

[out]
## Post #8
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-30T15:02:18+00:00
- Post Title: Away3D decompression

Thanks, that really helped! It turns out only the first image (mip) is compressed, the rest are in Jpeg XR format like you said.
The structure is something like this (big endian):

```
//
// U8[3] - signature - 'ATF'
// U24 - total file size
// U8 - format - 0=RGB888, 1=RGBA8888 (straight alpha), 2=Compressed(dxt1+pvrtc+etc1)
// U8 - width - texture size (2^n) (max n=11)
// U8 - height - texture size (2^n) (max n=11)
// U8 - count - total texture count (main + mip maps, max n=12)
// U24 - main texture size (compressed)
// lzma stream
// U24 - mip_2 size (uncompressed)
// mip_2 stream
// ...
// U24 - mip_n size
// mip_n stream

```


Binary 19 - mip 2:


I'm now trying to extract the first texture, assuming it's also JXR, but I can't seem to get it working.
quickbms test script:

```
endian big
get NAME basename
string NAME += "_main.jpg"
get FSIZE threebyte
get FORMAT byte
get WIDTH byte
get HEIGHT byte
get COUNT byte

comtype lzma
get ZSIZE threebyte
savepos OFFSET
clog NAME OFFSET ZSIZE ZSIZE
```


Error: the compressed LZMA input is wrong or incomplete (2)
       stream was not finished

Error: there is an error with the decompression
       the returned output size is negative (-102)
## Post #9
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-30T16:28:46+00:00
- Post Title: Away3D decompression

[out]
## Post #10
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-30T16:35:21+00:00
- Post Title: Away3D decompression

Ah, thanks, I forgot to look into atf.h.
That's really f*ed up, but I won't give up yet, first I want to see that stream unpacked.

I was under the impression that quickbms doesn't need the uncompressed size for lzma.

Edit: never mind, I used lzma_dynamic instead and it worked.
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-30T17:55:23+00:00
- Post Title: Away3D decompression

[out]
## Post #12
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-30T20:55:16+00:00
- Post Title: Away3D decompression

Thanks for the info, but for now I think I'm gonna settle with a quickbms converter from the old format to the new.
It turned out quite a bit complex because it's not just the main header that needs to be converted, but also every U24 length from every stream. Maybe that's why those files came up empty for you?

```
endian big
get NAME basename
string NAME += "_v2.atf"
get FSIZE threebyte

if FSIZE == 0 #double check if new ATF format
   print "ATF file is already up to date"
   cleanexit
endif

get FORMAT byte
get WIDTH byte
get HEIGHT byte
get COUNT byte

if FORMAT == 0
   set SUBSTREAMS 1
elif FORMAT == 1
   set SUBSTREAMS 1
elif FORMAT == 2
   set SUBSTREAMS 8
endif

log MEMORY_FILE 0 0
putct "ATF" string -1 MEMORY_FILE
put 0xFF long MEMORY_FILE #reserved
put 0x2 byte MEMORY_FILE #version
Xmath FSIZE "FSIZE + (COUNT * SUBSTREAMS)"
put FSIZE long MEMORY_FILE
put FORMAT byte MEMORY_FILE
put WIDTH byte MEMORY_FILE
put HEIGHT byte MEMORY_FILE
put COUNT byte MEMORY_FILE

set MOFFSET 16
append
for i = 0 < COUNT
   for j = 0 < SUBSTREAMS
      get SIZE threebyte
      PutVarChr MEMORY_FILE MOFFSET SIZE long
      savepos OFFSET
      log MEMORY_FILE OFFSET SIZE
      goto SIZE 0 SEEK_CUR
      math MOFFSET += 4
      math MOFFSET += SIZE
   next j
next i
append

math FSIZE += 12
log NAME 0 FSIZE MEMORY_FILE
```

It should work with types 0 and 1 as well, but I don't have any to test. Too bad this ATFviewer doesn't have a save/export function.
## Post #13
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-31T16:57:13+00:00
- Post Title: Away3D decompression

[out]
## Post #14
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-31T17:22:29+00:00
- Post Title: Away3D decompression

I'm gonna leave textures on hold for now, as I've found yet another container and 3D format used by Away3D.
The files bear a .abg extension and can be found in models from GarageFuse.com.

Here's a quickbms script to unpack them

```
getdstring VER LEN
get UNK long
get NAME basename
string name += "_unpacked.abg"
savepos OFFSET
get ZSIZE asize
math ZSIZE -= 6
math ZSIZE -= LEN

comtype lzma86head
clog NAME OFFSET ZSIZE ZSIZE
```


Inside there's a mix of plain-text and binary data, and the format looks similar to OBJ. I hope to have an importing maxscript ready soon.
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-31T19:02:57+00:00
- Post Title: Away3D decompression

[out]
## Post #16
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-31T19:12:05+00:00
- Post Title: Re: Away3D decompression

> Reply from Wobble
>
> Away3D has its own format, .awd, for models.  I've never seen or heard of .abg.  May be only related to GarrageFuse.com
Maybe. But GarageFuse definitely works on Away3D, you can see it in the right-click menu. Either way, the format is pretty simple, I'm almost done with it.
I have also seen Away3D pages that were loading obj or 3ds models.
## Post #17
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-31T22:34:23+00:00
- Post Title: Re: Away3D decompression

[out]
## Post #18
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-01T05:59:47+00:00
- Post Title: Re: Away3D decompression

I don't think it's related to 3dg, it really looks like it's from Away3D. The version string from each abg file is "4.1.0a", which matches the version of Away3D they use.


Anyway, the format is like OBJ but with a mix of binary and text data. No idea why they did that, becaue the text part seems redundant.
Another really strange thing is that it uses double floats to store vertex components.
Here are some freely-accessible samples. I also uploaded a script to convert abg to obj - only works with quickbms_4gb_files.exe because of the double floats.

```
http://garagefuse.com/configurator/assets/xml/audi_a3_3door.xml
http://garagefuse.com/configurator/assets/audi_a3_3door-data/audi_a3_3door_body_24.abg
http://garagefuse.com/configurator/assets/audi_a3_3door-data/audi_a3_3door_body_30.abg
http://garagefuse.com/configurator/assets/audi_a3_3door-data/audi_a3_3door_body_01.abg
```


Now all there's left for me is to make a maxscript for that XML file that scales and places every mesh in position. - DONE
## Post #19
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-08-03T02:30:45+00:00
- Post Title: Re: Away3D decompression

> Reply from Chipicao
>
> I don't think it's related to 3dg, it really looks like it's from Away3D. The version string from each abg file is "4.1.0a", which matches the version of Away3D they use.


Anyway, the format is like OBJ but with a mix of binary and text data. No idea why they did that, becaue the text part seems redundant.
Another really strange thing is that it uses double floats to store vertex components.
Here are some freely-accessible samples. I also uploaded a script to convert abg to obj - only works with quickbms_4gb_files.exe because of the double floats.
Code: Select allhttp://garagefuse.com/configurator/assets/xml/audi_a3_3door_assets.xml
http://garagefuse.com/configurator/assets/xml/audi_a3_3door.xml
http://garagefuse.com/configurator/assets/audi_a3_3door-data/audi_a3_3door_body_24.abg
http://garagefuse.com/configurator/assets/audi_a3_3door-data/audi_a3_3door_body_30.abg
http://garagefuse.com/configurator/assets/audi_a3_3door-data/audi_a3_3door_body_01.abg

Now all there's left for me is to make a maxscript for that XML file that scales and places every mesh in position. - DONE
I've done projects with away3d before. these abg files aren't one of the standard formats it supports, but one of the benefits of the open source nature is that writing support for new formats is easy compared to something like, flare3d.  It does seem weird they version the headers, as if to prevent issues with the changing source code, but stuck with a now outdated version.
