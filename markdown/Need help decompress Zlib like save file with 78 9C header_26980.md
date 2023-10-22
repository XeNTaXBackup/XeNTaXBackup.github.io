## Post #1
- Username: Reifuku
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 10, 2021 9:25 pm
- Post datetime: 2023-07-15T19:59:00+00:00
- Post Title: Need help decompress Zlib like save file with 78 9C header

Hi,

I've been trying to edit a save file from a game made with RPG Maker MZ (Nyaruru Fishy Fight), but all solution I tried didn't work.
When I inspect the file (along with other saves) with HxD it appear to have 78 9C header instead of 78 01 (which might imply that it is compressed with Zlib) however trying Offzip also didn't work:

```

+------------+-----+----------------------------+----------------------+
| hex_offset | ... | zip -> unzip size / offset | spaces before | info |
+------------+-----+----------------------------+----------------------+
  0x00001800

- no valid full zip data found
```


could this be compressed with a custom MZ plugin?
If anyone can take a look, any help is appreciated. 

Thanks,
[file3.zip](https://xentaxbackup.github.io/file/24076_file3.zip)
## Post #2
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-07-16T18:46:53+00:00
- Post Title: Need help decompress Zlib like save file with 78 9C header

Nope, doesn't decompress with Zlib under normal conditions.  Returns Z_DATA_ERROR.

Maybe include more than one sample, so files can be compared.
