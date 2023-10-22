## Post #1
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2016-06-10T13:58:32+00:00
- Post Title: Made Man *.mfs

Hello

Please help in researching of game format. 
I can't figure where's can be pointers and sizes for each file, and how files determine their filenames. 

My progress in research:

```
Long - Always 01 00 00 00
Long - Beginning of files Pointer
Long - Magic MFS
Long - Always 00 08 00 00
Next 28 bytes for current MFS archive name
Long - null
Long - EXT block Pointer
Long - EXT block Size
Long - null
Long - Unkn
Long - Unkn
Long - Size of file?
Long - Same ?
Long - Unkn
Long - Unkn
Long - Unkn
Long - Unkn
Long - Size of file 2?
Long - same number?
...


EXT block:
Long - EXT header
Long - Unkn
Long - Pointer to build.pc path
Long - File Name 1 pointer
Long - Unkn
...

Full size for each file 2048 bytes or more (multiply two?)
```


Samples of archives with shaders: [http://www.mediafire.com/download/snfxs ... /global.7z](http://www.mediafire.com/download/snfxs2t00n07l0y/global.7z)

Main game archive: [http://www.mediafire.com/download/azldl ... pis/imm.7z](http://www.mediafire.com/download/azldlbl9i11upis/imm.7z) (349 mb uncompressed)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-06-19T16:18:47+00:00
- Post Title: Made Man *.mfs

[http://zenhax.com/viewtopic.php?f=9&t=2595](http://zenhax.com/viewtopic.php?f=9&t=2595)
