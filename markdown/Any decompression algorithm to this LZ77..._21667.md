## Post #1
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2020-01-26T04:36:43+00:00
- Post Title: Any decompression algorithm to this LZ77...?

Guys, i'm trying decompress a texture, the chunk of the texture begin with LZ77 magic,
But I tried at least 3 lz77 decompression algorithms and not worked...


```
0010h: 00 40 00 00 00 00 10 08 37 76 00 00 00 01 00 01  .@......7v...... 
0020h: 4C 5A 37 37 00 00 04 00 81 41 00 00 41 08 00 00  LZ77....A..A... 
0030h: 0F FD 6B AB AA BB D5 5B EB BB AA F5 F5 55 56 AA  .ýk«ª»Õ[ë»ªõõUVª 
0040h: BD 55 AF 75 55 57 AF B5 6B 55 AB 5A AF F4 AD 7A  ½U¯uUW¯µkU«Z¯ô­z 
```


Game: Utawarerumono Mask of Deception [Steam version]

I'm not very good in C, if possible I want a algorithm in C# or a command line tool that I can use to do the decompression automatically
[font.tex.zip](https://xentaxbackup.github.io/file/17420_font.tex.zip)
## Post #2
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2020-01-27T04:19:52+00:00
- Post Title: Any decompression algorithm to this LZ77...?

Not in C#, but Python (Noesis), maybe [this](https://forum.xentax.com/viewtopic.php?p=148642#p148642) could guide you.
## Post #3
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2020-01-27T07:12:14+00:00
- Post Title: Any decompression algorithm to this LZ77...?

> Reply from TheUkrainianBard ↑Mon Jan 27, 2020 12:19 pm at Mon Jan 27, 2020 12:19 pm
>
> 
Not in C#, but Python (Noesis), maybe this could guide you.

Thank you, this will help
## Post #4
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2020-01-27T08:40:06+00:00
- Post Title: Any decompression algorithm to this LZ77...?

Worked, I wrote this algorithm based on that python:

```
            var Reader = new BinaryReader(Input);

            if (Reader.ReadUInt32() != 0x37375A4C)
                throw new Exception("Unexpected Compression Header");

            uint Size = Reader.ReadUInt32();

            uint OPCount = Reader.ReadUInt32();
            uint DataOffset = Reader.ReadUInt32();
            uint TotalFlags = DataOffset - (ExNameSize + 4);

            byte[] dst = new byte[Size];

            Queue<byte> FlagsBuffer = new Queue<byte>();
            for (int i = 0; i < TotalFlags; i++)
                FlagsBuffer.Enqueue(Reader.ReadByte());

            for (uint o = 0, FLAGS = 0, BitCount = 0, x = 0; o < OPCount; o++) { 
                if (BitCount == 0) {
                    BitCount = 8;
                    FLAGS = FlagsBuffer.Dequeue();
                }

                if ((FLAGS & 0x80) != 0)
                {
                    byte Offset = Reader.ReadByte();
                    byte Amount = (byte)(Reader.ReadByte() + 3);

                    for (int i = 0; i < Amount; i++)
                        dst[x + i] = dst[x - Offset + i];

                    x += Amount;
                }
                else
                    dst[x++] = Reader.ReadByte();

                FLAGS <<= 1;
                BitCount--;
            }

            return dst;
        }
```
