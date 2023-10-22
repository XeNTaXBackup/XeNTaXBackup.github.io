## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-07-27T17:10:22+00:00
- Post Title: Counter-Strike Online 2 (.VTF) Modified with LZMA

Hey, I've been trying to figure this out but have had no luck at all I'm not sure if ekeys unpacker is at blame or something is going on weird but Counter-Strike Online 2's VTF textures just refuse to decompress. Well the VTF header + all the mips do successfully decompress however the largest mip LZMA block fails 

Here is what the files look like


it uses LZMA in the format of

```
uint32 size
uint32 zsize
byte   Lzmaprops[5]

```


So for example the first LZMA block decompresses to this and each MIP of the texture follows which is another LZMA block.

Get to the last LZMA block and it just fails. I dump the buffer before the lzma bad data exception and the result is an image chopped up here is what i mean look.
The first 2 Mips are broken but the rest are fine



The function which decompresses the lzma seems normal I don't understand whats going on why is it failing 

```
{
  vtf_lzma_header *lzmaHeader2; // ebx@1
  unsigned int uncompressedLength; // ebp@4
  unsigned int *probs; // esi@5
  signed int decodeResult; // edi@5
  vtf_lzma_header *result; // eax@6
  CLzmaDecoderState state; // [sp+10h] [bp-14h]@5

  lzmaHeader2 = lzmaHeader;
  if ( !lzmaHeader
    || !outputBuffer
    || lzmaHeader->lzmaMagic != 0x414D5A4C
    || (uncompressedLength = lzmaHeader->uncompressedLength) == 0 )
    goto LABEL_8;
  LzmaDecodeProperties(&state.Properties, lzmaHeader->decoderProperties);
  probs = (unsigned int *)(*(int (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)&byte_14F5E214[140] + 4))(
                            *(_DWORD *)&byte_14F5E214[140],
                            4 * (768 << (LOBYTE(state.Properties.lp) + state.Properties.lc)) + 0x1CD8);// allocFunc & LzmaGetNumProbs
  state.Probs = probs;
  decodeResult = LzmaDecode(
                   &state,
                   lzmaHeader2->data,
                   lzmaHeader2->compressedLength,
                   (unsigned int *)&outputBuffer,
                   outputBuffer,
                   uncompressedLength,
                   (unsigned int *)&lzmaHeader);
  (*(void (__stdcall **)(_DWORD))(**(_DWORD **)&byte_14F5E214[140] + 20))(probs);// freeFunc
  if ( decodeResult || (result = lzmaHeader, lzmaHeader != (vtf_lzma_header *)uncompressedLength) )
  {
    (*(void (**)(const char *, ...))&byte_14F5E214[24])("Decompress Fail. %d", decodeResult);
LABEL_8:
    result = 0;
  }
  return result;
}

```


Sample files (source engine shared files not only found in CSO2 but alienswarm/dota2/tf2 free2play game)
[https://www.dropbox.com/sh/f8jmz3ppqefp ... wGUMF0LVJa](https://www.dropbox.com/sh/f8jmz3ppqefp23c/AADjsI6In-0bJfCwGUMF0LVJa)

Here are more Samples (since CSO2 runs the Source Engine i found some files in CSS that are the same in CSO2)
[https://dl.dropboxusercontent.com/u/107 ... samples.7z](https://dl.dropboxusercontent.com/u/10798900/DUMPBOX/lzma_samples.7z)

PM me if you want the filesystem dll
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-26T16:21:45+00:00
- Post Title: Counter-Strike Online 2 (.VTF) Modified with LZMA

Bump
alyxblock.dat 1 of the lzma blocks

[https://www.dropbox.com/s/zgnpqpdpngs0vvi/alyxblock.dat](https://www.dropbox.com/s/zgnpqpdpngs0vvi/alyxblock.dat)

//Read 0->18932 (zsize)
//Can decode 25892bytes (Glitched output size) about 142 bytes worth of glitch pixels
## Post #3
- Username: rackio
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 28, 2014 6:29 am
- Post datetime: 2015-06-06T12:30:36+00:00
- Post Title: Counter-Strike Online 2 (.VTF) Modified with LZMA

---------------------------
VTFEdit
---------------------------
Error loading VTF texture:

Error:
File signature does not match 'VTF'.
---------------------------
Aceptar   
---------------------------

help!!
## Post #4
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2023-08-16T08:37:15+00:00
- Post Title: Counter-Strike Online 2 (.VTF) Modified with LZMA

Did you ever get any further with this? I know that Source on the Xbox 360 uses LZMA too but the normal decompression seems to work.
