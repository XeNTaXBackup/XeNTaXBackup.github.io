## Post #1
- Username: Scorpion2k7
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 18, 2013 12:39 am
- Post datetime: 2015-12-15T18:27:49+00:00
- Post Title: Captain Tsubasa ftx text help (PS2)

Who can make coder/decoder or info for this text file?
[ftx_file.rar](https://xentaxbackup.github.io/file/10157_ftx_file.rar)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-18T17:47:39+00:00
- Post Title: Captain Tsubasa ftx text help (PS2)

interesting encoding.

xor key (?) seems to swap after so many bytes:

> Ended 0x1c, total = 18  Swapped to 0x1d @ 567
>
> Ended 0x1d, total = 17  Swapped to 0x1e @ 1593
>
> Ended 0x1e, total = 13  Swapped to 0x1f @ 2123
>
> Ended 0x1f, total = 24  Swapped to 0x20 @ 3141
>
> Ended 0x20, total = 21  Swapped to 0x21 @ 4159
>
> Ended 0x21, total = 24  Swapped to 0x22 @ 5187
>
> Ended 0x22, total = 8  Swapped to 0x23 @ 5697
>
> Ended 0x23, total = 18  Swapped to 0x24 @ 6715
>
> Ended 0x24, total = 9  Swapped to 0x25 @ 7235

not sure how yet. also initial key is based from the original filename.



messy wip:


```
byte b = 0x1c;

int off = 0x30;
int cnt = 0;

byte r;

i = 1;
while( i < 64 )
{
  r = (byte)(ReadByte(off + i) & 0xFF);

  if( r == b )
  {
    ++cnt;
    i += 2;
  }
  else if( r == 0 )
  {
    off += 64;
    i = 1;
  }
  else
  {
    Printf("Ended 0x%02x, total = %u  ",b&0xFF, cnt );

    // keys increment by 1
    if( r-b != 1 ) Assert(false);

    b = r;

    Printf("Swapped to 0x%02x @ %u\n", b&0xFF, (off + i));

    off += 64;
    i = 1;
    cnt = 0;
  }

    if( off > 0x2000 )
      Assert(false);
}


```
