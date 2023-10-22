## Post #1
- Username: weling2010
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Feb 10, 2012 3:35 pm
- Post datetime: 2013-05-31T02:49:44+00:00
- Post Title: Sword Art Online psp OFS3

OFS3 header (16-bytes)
0x00: [4-bytes] OFS3 file signature (it's always 4F46 5333) 
0x04: [4-bytes] OFS3 Header size (it's always 1000 0000) 
0x08: [4-bytes] Unknown value 
0x0c: [4-bytes] Nametable Start address (this points to the end of the file if nametable doesnt exist)

OFS3 Filetable (variable size)
data table starts with a 4-byte value indicating file count. 
each file entry consists of 12-bytes 

0x10: [4-bytes] Number of files 

0x14: [4-bytes] File Start Address 
0x18: [4-bytes] File Length 
0x1c: [4-bytes] Filename Position 

[the pattern of 0x14 -> 0x1C repeats as many times as there are files inside the container] 

texture files seem to be .tm2 (TIM2) image format and model data is psp generic gmo.
[sao ofs3.7z](https://xentaxbackup.github.io/file/6437_sao ofs3.7z)
