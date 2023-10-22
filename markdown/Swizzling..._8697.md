## Post #1
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-04-05T19:28:15+00:00
- Post Title: Swizzling...

Hi, i'm working on a tool and got some problems with swizzling...
i found small swizzle function, but not unswizzle. could anyone help me with unswizzle?

```
{
   unsigned int i,j;
   unsigned int rowblocks = (width / 16);

   for (j = 0; j < height; ++j)
   {
      for (i = 0; i < width; ++i)
      {
         unsigned int blockx = i / 16;
         unsigned int blocky = j / 8;

         unsigned int x = (i - blockx*16);
         unsigned int y = (j - blocky*8);
         unsigned int block_index = blockx + ((blocky) * rowblocks);
         unsigned int block_address = block_index * 16 * 8;

         out[block_address + x + y * 16] = in[i+j*width];
      }
   }
}
```
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-04-06T00:32:07+00:00
- Post Title: Swizzling...

Isnt unswizzle the same as swizzle again?

Anyway: [http://code.google.com/p/puyotools/sour ... le.cs?r=93](http://code.google.com/p/puyotools/source/browse/trunk/PTImgLib/VrSharp/Svr/SvrSwizzle.cs?r=93)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T00:53:22+00:00
- Post Title: Swizzling...

Hmm, I would imagine you could come up with an algorithm that isn't "symmetrical" like that.
I would just take the algorithm and then do the opposite of what it's doing, in reverse order.

What format is it for though?
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-06T06:24:38+00:00
- Post Title: Swizzling...

there are different swizzle algorithms; the one I use I ripped from Rich and some IEEE journal article...

```
** MORTON COORDINATE FUNCTIONS
*/

inline uint32 dilate_2(uint32 r)
{
 r = (r | (r << 8)) & 0x00FF00FF;
 r = (r | (r << 4)) & 0x0F0F0F0F;
 r = (r | (r << 2)) & 0x33333333;
 r = (r | (r << 1)) & 0x55555555;
 return r;
}

inline uint32 array_to_morton(uint32 row, uint32 col) 
{
 return (dilate_2(col) | (dilate_2(row) << 1));
}

data is an 32-bit BGRA buffer. (source)
copy is an empty 32-bit BGRA buffer. (destination)

void deswizzle(const char* data, const char* copy, uint32 dx, uint32 dy)
{
    // deswizzle
    for(uint32 r = 0; r < dy; r++) {
        for(uint32 c = 0; c < dx; c++) {
            uint32 morton = array_to_morton(r, c);
            uint32 copy_position = 4*r*dx + 4*c;
            uint32 data_position = 4*morton;
            copy[copy_position++] = data[data_position + 0]; // b
            copy[copy_position++] = data[data_position + 1]; // g
            copy[copy_position++] = data[data_position + 2]; // r
            copy[copy_position++] = data[data_position + 3]; // a
           }
       }
}

```
## Post #5
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-04-06T11:01:33+00:00
- Post Title: Swizzling...

this algo is for 8 bit, but you always can add depth for higher bpp.
i actually solved it for now using another guy's dll, but would be great to implement it w/o external files.
