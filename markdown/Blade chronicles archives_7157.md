## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-11T03:50:45+00:00
- Post Title: Blade chronicles archives

```
#textures archive

get idstring long
get files long
get null long
get null long

for i = 0 < files
   get id short
   get part2 byte
   get part1 byte
   get size long
   get unk long
   get unk long
next i
goto 56 0 SEEK_CUR

#start saving files

```


I don't know how to save those files though. There doesn't seem to be any offsets to work with.
[Blade Chronicles.7z](https://xentaxbackup.github.io/file/4611_Blade Chronicles.7z)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-11T03:56:16+00:00
- Post Title: Blade chronicles archives

Here are a different set of mdn archives that contain model files.
For some reason, some mdl's are unpacked, while others are. I don't know why this is the case, but I've already verified that model files start with "mdl" string.
[model.7z](https://xentaxbackup.github.io/file/4612_model.7z)
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-11T13:37:11+00:00
- Post Title: Blade chronicles archives

the first unknown in the file structure is actually the filename

get fileid short
get part1 byte
get part2 byte

notice the filename is <part2>_<part1>_00000.mbn
the maxlength of a short is 65535 (5 chars)
so
file may be referred to internally as "<part2>_<part1>_<fileid>"

```
print "%FNAME%"

```
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-11T14:35:07+00:00
- Post Title: Blade chronicles archives

nice catch, I didn't think much about those and just assumed they were longs.

So the filename and the filesize is there, but the offsets are still missing.
The long after the size (which...might not be a long I guess)
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-11T16:24:13+00:00
- Post Title: Blade chronicles archives

you dont need offsets when you have the data size

i cant understand one of the texture files i opened - theres 56 bytes of garbage before the first dds header - but the images are corrupted even with manually extracting..

models seem fine though.. and you have another thread on those - so use something like this for now

```
get files long
get DUMMY long
get DUMMY long

savepos offset
set pos long files
math pos *= 16 # size of file record structure
math pos += offset

get filesize asize

for i = 0 < files
  get id short
  get minor byte
  get major byte
  get size long
  get unk long
  get unk long

  string FNAME p= "%03i_%03i_%05i.mdl" major minor id

  log FNAME pos size

  math pos += size # next offset
next i

```
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-11T16:34:49+00:00
- Post Title: Blade chronicles archives

oh yes, for texture archives I just skip 56 bytes.
Only for those archives though, and I'm not sure if there is a way to distinguish between the two.
