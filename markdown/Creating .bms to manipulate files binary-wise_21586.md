## Post #1
- Username: Tan33
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 02, 2017 4:36 pm
- Post datetime: 2020-01-09T00:47:04+00:00
- Post Title: Creating .bms to manipulate files binary-wise

Hello pals.
I hope I don't sound too newbie, this .bms script I have the idea but cannot implement, so I need help & tha's why I came here, so bear with me please.
The "program" should do the following job, mostly an extraction process:

input files:
NAME_1.EXT, NAME_2.EXT, ..., NAME_#.EXT
 ('#' can be any INT; '.EXT' is any extension, all input files HAVE the SAME extension -mandatory)

output file:
NAME.EXT2
 (The output file name shares the common part of the input files, but without number/index, and a different or absent extension)

The process:

1º
[DWORD1] at [offset-0] in file 'NAME_1.EXT' must be REPLACED with [DWORD2] (LONG data type, from what I know)
 ( '[offset-0]' is any position in file).
//Example: at offset [0x40], there are the bytes [00 10 02 A0]; I want them replaced with [02 40 00 A0] and overwritten in the file.
NOTE: JUST THIS FIRST FILE have to have its bytes replaced.

2º
For files: NAME_2.EXT, NAME_3.EXT ..., NAME_#.EXT  (i.e. the REST of input files, IN ORDER!) do:
   Remove bytes from [offset1] with size [size1]  (or equivalently, remove bytes from [offset1] to [offset2])
next
...
... or alternatively
For files: NAME_2.EXT, NAME_3.EXT ..., NAME_#.EXT  do:
   LOG bytes from [offset1] to [e.o.f.] //concatenating with following portions //at final step, this blob will be appended to first file.
next

3º /final step
Binary concatenate (modified) NAME_1.EXT + { NAME_[k].EXT } / from k=2...# (from step 2º)

With this algorithm, I hope to merge data extracts coming from different files. Quickbms can do the LOGging part, but I do not know how to program the replace part.
Hope the attached picture (pretty basic, hm) can help understand, well, the picture. Yellow color means data to be LOGged. The small pink rectangle in file 1 is dword replaced. Little black & orange squares mean (fixed) offsets.
Thank you in advance. Cheers.
[data_concat.png](https://xentaxbackup.github.io/file/17315_data_concat.png)
