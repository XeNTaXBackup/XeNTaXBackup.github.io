## Post #1
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2022-09-06T19:18:31+00:00
- Post Title: Commandos 3 HD PAK compressed files

Hi,
does anyone know what compression algorithm was used for those files?
I understand the general concept of the compression but can't figure out the details.

This is the overall file structure:
SDPC -- magic word
97 00 00 00 -- size of the uncompressed file
<compressed content>
11 00 00 -- EOF marker?

compressed file:

```
00000010  4C 49 42 52 45 52 49 41 20 53 55 42 4D 41 52 53  LIBRERIA SUBMARS
00000020  42 2E 47 52 4C 0D 0A 20 20 2E 53 45 43 55 45 4E  B.GRL..  .SECUEN
00000030  43 49 41 53 79 01 28 73 00 20 20 5B B8 00 0B 20  CIASy.(s.  [¸.. 
00000040  20 2E 4E 4F 4D 42 52 45 20 42 41 53 45 27 4C 00   .NOMBRE BASE'L.
00000050  02 46 52 41 4D 45 99 05 20 40 00 C8 06 44 01 0F  .FRAME™. @.È.D..
00000060  20 28 20 53 75 62 6D 61 72 69 6E 6F 5F 39 30 20   ( Submarino_90 
00000070  20 29 E8 06 C0 01 08 5D 0D 0A 20 20 29 0D 0A 5D   )è.À..]..  )..]
00000080  0D 0A 11 00 00                                   .....
```


uncompressed file:

```
00000010  55 42 4D 41 52 53 42 2E 47 52 4C 0D 0A 20 20 2E  UBMARSB.GRL..  .
00000020  53 45 43 55 45 4E 43 49 41 53 0D 0A 20 20 28 0D  SECUENCIAS..  (.
00000030  0A 20 20 20 20 5B 0D 0A 20 20 20 20 20 20 2E 4E  .    [..      .N
00000040  4F 4D 42 52 45 20 42 41 53 45 0D 0A 20 20 20 20  OMBRE BASE..    
00000050  20 20 2E 46 52 41 4D 45 53 0D 0A 20 20 20 20 20    .FRAMES..     
00000060  20 28 0D 0A 20 20 20 20 20 20 20 20 28 20 53 75   (..        ( Su
00000070  62 6D 61 72 69 6E 6F 5F 39 30 20 20 29 0D 0A 20  bmarino_90  ).. 
00000080  20 20 20 20 20 29 0D 0A 20 20 20 20 5D 0D 0A 20       )..    ].. 
00000090  20 29 0D 0A 5D 0D 0A                              )..]..
```


Here are a few samples and their uncompressed counterparts:


 C3HD_samples.zip
(6.54 KiB) Downloaded 15 times
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2022-09-06T21:03:29+00:00
- Post Title: Commandos 3 HD PAK compressed files

Praise the almighty aluigi! 
I used his guide to run through all compression algorithms and was able to identify the correct one.   
COMP_LZO1X in this case.
[https://zenhax.com/viewtopic.php?t=23](https://zenhax.com/viewtopic.php?t=23)
