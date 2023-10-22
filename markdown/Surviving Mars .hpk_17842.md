## Post #1
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2018-03-20T16:30:25+00:00
- Post Title: Surviving Mars .hpk

hpk format:

```
char magick[4]; // "BPUL"
uint unk1;      // 36 (header size or data offset??)
uint unk2[5];   // 1, -1, 0, 0, 1

uint entry_offset;  // absolute
uint entry_size;    // entry_offset + entry_size = EOF

// data
char filedata[xxx];

// file desc
struct dir_entry[xxx] {
    uint ptr;   // entry[ptr] -> next item
    uint attr;  // 0 - directory, 1 - file
    short sz;
    char name[sz]   // name of current dir or file
}

// entry_offset
struct entry[xxx] {   // xxx = entry_size >> 3
    uint offset;        // absolute, pointer to dir_entry (included dir, file or filedata)
    uint size;          // size of dir_entry or zsize of file
}
```


LZ4 packed file:

```
uint size;              // unpacked size
uint block_size;        // 2^17
uint h_size;            // header size; if size==0, then EOF here
uint chunk_offset[xxx]; // xxx = (h_size - 16) >> 2, absolute offsets of chunk begins

struct chunk[xxx] {     // offset = h_size
    char lz_data[];     // full LZ4 block (unpacked == block_size)
}
char lz_data_tail[];    // partial LZ4 block (unpacked < block_size)
```


for unpack used LZ4_decompress_safe (src, dst, zsize, size). if (entry.size == size - h_size) then file content is not packed.

implementation in Lua [here](https://github.com/hhrhhr/Lua-utils-for-Surviving-Mars).
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-03-20T20:10:41+00:00
- Post Title: Surviving Mars .hpk

Or you can use HPK Archiver, modded by Atom0s

[https://github.com/atom0s/HpkArchiver](https://github.com/atom0s/HpkArchiver)

Win build: 

 HPK_archiver_1_0_14_mod.7z
(175.74 KiB) Downloaded 41 times
