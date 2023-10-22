## Post #1
- Username: qogudwnssla
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 13, 2011 12:02 pm
- Post datetime: 2014-02-21T07:18:55+00:00
- Post Title: [PS3] Twisted metal (2012) - .NGP .VRAM

There are two main files inside twisted metal's main folder.
One is .VRAM and the other is .NGP.
With great effort of barti, .VRAM files are already researched.
they were texture files.  All textures begin and end with 16 00-bytes.
[](http://s825.photobucket.com/user/sweettoothlove/media/Seperation_line_zps0b6e38c4.png.html)
Some of them have normal, specular and even shader mask maps.
Image sizes are ranging from 32 to 2024X2024 (WidthXHeight)

Here is the code for quickbms. Approved by barti for posting.


```
get FSIZE asize
do
   savepos OFFSET
   FindLoc SIZE string "\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0" ""
   
   if SIZE = ""
    get SIZE asize
   endif
   #if SIZE = ""
   #   print "ERROR: No DXT5 data found"
   #   cleanexit
   #else
      math SIZE -= OFFSET
      if SIZE = 5592432
         math RES = 2048
         callfunction exportDDS
      elif SIZE = 1398128
         math RES = 1024
         callfunction exportDDS
      elif SIZE = 349552
         math RES = 512
         callfunction exportDDS
      elif SIZE = 87408
         math RES = 256
         callfunction exportDDS
      elif SIZE = 21872
         math RES = 128
         callfunction exportDDS
      elif SIZE = 5488
         math RES = 64
         callfunction exportDDS
      elif SIZE = 1392
         math RES = 32
         callfunction exportDDS
      else
         # print "Non-standard image size %SIZE% found."
      endif
      math OFFSET += SIZE
      math OFFSET += 16
      goto OFFSET
   #endif
   savepos cur_off
while cur_off < FSIZE

startfunction exportDDS
   set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x01\x00\x00\x00\x01\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x09\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
   log MEMORY_FILE2 OFFSET SIZE

   putvarchr MEMORY_FILE 12 RES long
   putvarchr MEMORY_FILE 16 RES long

   # comment out the line below if you want to keep the alpha channel
   callfunction removeAlphaChannel
   
   append
   get SIZE asize MEMORY_FILE2
   log MEMORY_FILE 0 SIZE MEMORY_FILE2
   append

   string NAME p= "0x%08X_%i.dds" OFFSET SIZE
   get SIZE asize MEMORY_FILE
   log NAME 0 SIZE MEMORY_FILE
endfunction

startfunction removeAlphaChannel
   math LINES = SIZE
   math LINES /= 16
   for i = 0 < LINES do
      put -1 longlong MEMORY_FILE2
      goto 8 MEMORY_FILE2 SEEK_CUR
   next i
endfunction

```


I'am sure that .NGP files contain models for the game.(100%)
Here is the .EGG containing three .NGP files including according .VRAM files(for predicting how many models are inside .NGP files).
[https://www.mediafire.com/?z76os48ri3q44oy](https://www.mediafire.com/?z76os48ri3q44oy)
