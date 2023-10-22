## Post #1
- Username: Toren
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 25, 2011 8:37 am
- Post datetime: 2011-11-29T02:18:43+00:00
- Post Title: Corpse Party PSP image.bin file

First off, I'm sorry if this is completely simple and I should feel bad for asking this, but I was curious if anyone knew how to extract the contents of the image.bin file from Corpse Party on the PSP. I have the English version, but I assume the Japanese one would be virtually the same.

I opened up the file with a hex editor and here is the beginning. It seems that it lists all the files it contains in plain text, but I'm not sure if that makes any difference. So, if anyone can help with this file, it would be greatly appreciated. Thank you.
## Post #2
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-11-29T20:36:00+00:00
- Post Title: Corpse Party PSP image.bin file

im just looking aswell,i know theres 8091 Files .vag files,2 pmfs,some .at3...........hope theres a tool to extract and rebuild
you can extract these files using this tool

[viewtopic.php?f=13&t=6572](http://forum.xentax.com/viewtopic.php?f=13&t=6572)
## Post #3
- Username: Toren
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 25, 2011 8:37 am
- Post datetime: 2011-11-29T21:57:15+00:00
- Post Title: Corpse Party PSP image.bin file

Yes, this works well. Thanks. However, it looks like there are many more .gim files in the file than it extracted. There are also .bmp.ata and .dat files. Is there a way to get at those as well?
## Post #4
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-29T22:05:53+00:00
- Post Title: Corpse Party PSP image.bin file

Please upload the first 10 MB of the file (use the filecutter ([http://www.xentax.com/downloads/tools/filecutter.zip](http://www.xentax.com/downloads/tools/filecutter.zip)) or pretty much any hex editor)

It seems fairly simple. (if the data itself isn't compressed)
## Post #5
- Username: Toren
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 25, 2011 8:37 am
- Post datetime: 2011-11-29T23:00:50+00:00
- Post Title: Corpse Party PSP image.bin file

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-30T10:12:18+00:00
- Post Title: Corpse Party PSP image.bin file

A LZSS compression is used (don't know if they use a standard implementation (will look at it in the evening))

Will post all I have found tomorrow.
## Post #7
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-30T23:19:41+00:00
- Post Title: Corpse Party PSP image.bin file

How big is the file? (in bytes)
Is there a smaller one of the same filetype (the first 4 bytes are PACK) that you can upload completly? (don't bother if your connection is slow or the file is bigger than around 20 MB)

What I have found so far:
PSP -> LITTLE ENDIAN

HEADER (12 bytes)
4 bytes, string 'PACK'
4 bytes nOfEntries
4 bytes maybe filesize?

METADATA (144 bytes)
16 bytes stuff
128 bytes path + filename

DATA
See metadata for info

Compression used:
LZSS

Metadata entries: 1551888 bytes / 144 = 0x2A19 matches nOfEntries

First file starts at 0x17 b0 00 / 2048 (see below) = 0x2f6
Has a compressed length of probably 4586 = 11EA or 4588 = 11EC

Blocksize: 2048 bytes (offset should be a multiple of this)

LZSS:
0xFF = keep the next 8 bytes intact
## Post #8
- Username: Toren
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 25, 2011 8:37 am
- Post datetime: 2011-12-01T00:08:03+00:00
- Post Title: Corpse Party PSP image.bin file

Thank you for looking at the file. The file is 665,439,151 bytes, and there are no other files with the same file type. The game itself is about 742 MB, so the majority of the game's data is contained in this 634 MB file.
## Post #9
- Username: brainfog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 01, 2011 6:35 pm
- Post datetime: 2011-12-01T11:20:18+00:00
- Post Title: Corpse Party PSP image.bin file

Hi there. I'm noobish to quickbms and stuff, but this game intrigued me, so I made a bms script while ago. It's really lame, but seems working. At least it should give you a hint

```
comtype lzss "12 4 2 0 0"
goto 0x00000004
get FCOUNT long
goto 0x00000014
for i = 0 < FCOUNT
	savepos CPOS
	get OFFSET long
	get SIZE long
	get NAME string
	goto OFFSET
	getdstring IDSTR 4
	if IDSTR == "LZSS"
		get FSIZE long
		math OFFSET += 8
		math SIZE -= 8
		clog NAME OFFSET SIZE FSIZE
	else
		log NAME OFFSET SIZE
	endif
	math CPOS += 144
	goto CPOS
next i
```
## Post #10
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-12-01T16:33:30+00:00
- Post Title: Corpse Party PSP image.bin file

@ Brainfog seems to extract ok,but when i use qbm to repack some of the files are bigger than the original...so it wont repack 
at least we are getting some where..
thanx
## Post #11
- Username: brainfog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 01, 2011 6:35 pm
- Post datetime: 2011-12-02T06:08:58+00:00
- Post Title: Corpse Party PSP image.bin file

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-12-02T19:26:43+00:00
- Post Title: Corpse Party PSP image.bin file

Decompression algorithm by me:

```
        {
            int i, j, k, r, c, flags;

            for (i = 0; i < N - F; i++) text_buf[i] = 0x00;
            r = N - F; flags = 0;
            for (; ; )
            {
                if (((flags >>= 1) & 256) == 0)
                {
                    if (infile.Position == infile.Length) break;
                    c = infile.ReadByte();
                    flags = c | 0xff00;
                }
                if ((flags & 1) != 0)
                {
                    if (infile.Position == infile.Length) break;
                    c = infile.ReadByte();
                    outfile.WriteByte((byte)(c)); text_buf[r++] = (byte)(c); r &= (N - 1);
                }
                else
                {
                    if (infile.Position == infile.Length) break;
                    i = infile.ReadByte();
                    if (infile.Position == infile.Length) break;
                    j = infile.ReadByte();
                    i |= ((j & 0xf0) << 4); j = (j & 0x0f) + THRESHOLD;
                    i -= 2;
                    for (k = 0; k <= j; k++)
                    {
                        c = text_buf[(i + k) & (N - 1)];
                        outfile.WriteByte((byte)(c)); text_buf[r++] = (byte)(c); r &= (N - 1);
                    }
                }
            }
        }
```


Kepp in mid that this is only for the raw data chunk (offset 0x08 on).

Regards:

~Sky

PD: Also, I have built a tool for both unpacking and repacking, it just needs to be buffered a little up! 

EDIT: Recompression seems to work OK too.
## Post #13
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-12-03T08:12:13+00:00
- Post Title: Corpse Party PSP image.bin file

NIce one Sky.I`ll speak to you on MSN when i get chance,
## Post #14
- Username: brainfog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 01, 2011 6:35 pm
- Post datetime: 2011-12-03T10:20:58+00:00
- Post Title: Corpse Party PSP image.bin file

> Reply from SkyBladeCloud
>
> PD: Also, I have built a tool for both unpacking and repacking, it just needs to be buffered a little up! 

EDIT: Recompression seems to work OK too.
nice  , can you share it with us? will be much helpful
## Post #15
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-12-03T13:46:10+00:00
- Post Title: Corpse Party PSP image.bin file

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: brainfog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 01, 2011 6:35 pm
- Post datetime: 2011-12-03T17:16:40+00:00
- Post Title: Re: Corpse Party PSP image.bin file

Thank you, good sir! Extractor works nicely.
Wouldn't you mind to share recompression alg code?
Don't have much patience to wait fully functioning tool
## Post #17
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-12-03T20:40:16+00:00
- Post Title: Re: Corpse Party PSP image.bin file

The contents of this post was deleted because of possible forum rules violation.
## Post #18
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-12-03T21:54:30+00:00
- Post Title: Re: Corpse Party PSP image.bin file

This is the complete code I'm using to decompress and recompress; it is a pretty standard implementation, with a top of 16 byte os compressed strings:

```
using System.IO;
using System.Runtime.InteropServices;

namespace LZSS
{
    unsafe static class LZSS
    {
        const int N = 4096;
        const int F = 16;
        const int THRESHOLD = 2;

        const int NIL = N;

        static int textsize = 0, codesize = 0;

        static byte* text_buf = (byte*)Marshal.AllocHGlobal(N + F - 1);

        static int match_position, match_length;
        static int[] lson = new int[N + 1], rson = new int[N + 257], dad = new int[N + 1];

        static Stream infile, outfile;

        private static void InitTree()
        {
            int i;

            for (i = N + 1; i <= N + 256; i++) rson[i] = NIL;
            for (i = 0; i < N; i++) dad[i] = NIL;
        }

        private static void InsertNode(int r)
        {
            int i, p, cmp;
            byte* key;

            cmp = 1; key = &text_buf[r]; p = N + 1 + key[0];
            rson[r] = lson[r] = NIL; match_length = 0;
            for (; ; )
            {
                if (cmp >= 0)
                {
                    if (rson[p] != NIL) p = rson[p];
                    else { rson[p] = r; dad[r] = p; return; }
                }
                else
                {
                    if (lson[p] != NIL) p = lson[p];
                    else { lson[p] = r; dad[r] = p; return; }
                }
                for (i = 1; i < F; i++)
                    if ((cmp = key[i] - text_buf[p + i]) != 0) break;
                if (i > match_length)
                {
                    match_position = p;
                    if ((match_length = i) >= F) break;
                }
            }
            dad[r] = dad[p]; lson[r] = lson[p]; rson[r] = rson[p];
            dad[lson[p]] = r; dad[rson[p]] = r;
            if (rson[dad[p]] == p) rson[dad[p]] = r;
            else lson[dad[p]] = r;
            dad[p] = NIL;
        }

        private static void DeleteNode(int p)
        {
            int q;

            if (dad[p] == NIL) return;
            if (rson[p] == NIL) q = lson[p];
            else if (lson[p] == NIL) q = rson[p];
            else
            {
                q = lson[p];
                if (rson[q] != NIL)
                {
                    do { q = rson[q]; } while (rson[q] != NIL);
                    rson[dad[q]] = lson[q]; dad[lson[q]] = dad[q];
                    lson[q] = lson[p]; dad[lson[p]] = q;
                }
                rson[q] = rson[p]; dad[rson[p]] = q;
            }
            dad[q] = dad[p];
            if (rson[dad[p]] == p) rson[dad[p]] = q; else lson[dad[p]] = q;
            dad[p] = NIL;
        }

        private static void Encode()
        {
            int i, c, len, r, s, last_match_length, code_buf_ptr;
            byte[] code_buf = new byte[17];
            byte mask;

            InitTree();
            code_buf[0] = 0;
            code_buf_ptr = mask = 1;
            s = 0; r = N - F;
            for (i = s; i < r; i++) text_buf[i] = 0x00;
            for (len = 0; len < F && infile.Position != infile.Length; len++)
            {
                c = infile.ReadByte();
                text_buf[r + len] = (byte)c;
            }
            if ((textsize = len) == 0) return;
            for (i = 1; i <= F; i++) InsertNode(r - i);
            InsertNode(r);
            do
            {
                if (match_length > len) match_length = len;
                if (match_length <= THRESHOLD)
                {
                    match_length = 1;
                    code_buf[0] |= mask;
                    code_buf[code_buf_ptr++] = text_buf[r];
                }
                else
                {
                    code_buf[code_buf_ptr++] = (byte)match_position;
                    code_buf[code_buf_ptr++] = (byte)
                            (((match_position >> 4) & 0xf0)
                      | (match_length - (THRESHOLD + 1)));
                }
                if ((mask <<= 1) == 0)
                {
                    for (i = 0; i < code_buf_ptr; i++)
                        outfile.WriteByte(code_buf[i]);
                    codesize += code_buf_ptr;
                    code_buf[0] = 0; code_buf_ptr = mask = 1;
                }
                last_match_length = match_length;
                for (i = 0; i < last_match_length && infile.Position != infile.Length; i++)
                {
                    c = infile.ReadByte();
                    DeleteNode(s);
                    text_buf[s] = (byte)c;
                    if (s < F - 1) text_buf[s + N] = (byte)c;
                    s = (s + 1) & (N - 1); r = (r + 1) & (N - 1);

                    InsertNode(r);
                }
                while (i++ < last_match_length)
                {
                    DeleteNode(s);
                    s = (s + 1) & (N - 1); r = (r + 1) & (N - 1);
                    if (--len != 0) InsertNode(r);
                }
            } while (len > 0);
            if (code_buf_ptr > 1)
            {
                for (i = 0; i < code_buf_ptr; i++) outfile.WriteByte(code_buf[i]);
                codesize += code_buf_ptr;
            }
        }

        private static void Decode()
        {
            int i, j, k, r, c, flags;

            for (i = 0; i < N - F; i++) text_buf[i] = 0x00;
            r = N - F; flags = 0;
            for (; ; )
            {
                if (((flags >>= 1) & 256) == 0)
                {
                    if (infile.Position == infile.Length) break;
                    c = infile.ReadByte();
                    flags = c | 0xff00;
                }
                if ((flags & 1) != 0)
                {
                    if (infile.Position == infile.Length) break;
                    c = infile.ReadByte();
                    outfile.WriteByte((byte)(c)); text_buf[r++] = (byte)(c); r &= (N - 1);
                }
                else
                {
                    if (infile.Position == infile.Length) break;
                    i = infile.ReadByte();
                    if (infile.Position == infile.Length) break;
                    j = infile.ReadByte();
                    i |= ((j & 0xf0) << 4); j = (j & 0x0f) + THRESHOLD;
                    for (k = 0; k <= j; k++)
                    {
                        c = text_buf[(i + k) & (N - 1)];
                        outfile.WriteByte((byte)(c)); text_buf[r++] = (byte)(c); r &= (N - 1);
                    }
                }
            }
        }

        public static byte[] Decompress(byte[] inBuffer)
        {
            MemoryStream inStream = new MemoryStream(inBuffer);
            BinaryReader reader = new BinaryReader(inStream);
            reader.BaseStream.Seek(0x04, SeekOrigin.Begin);
            int decSize = reader.ReadInt32();
            infile = new MemoryStream(reader.ReadBytes(inBuffer.Length - 0x08));
            outfile = new MemoryStream();
            Decode();
            if (outfile.Length == decSize)
                return (outfile as MemoryStream).ToArray();
            else throw new InvalidDataException("Decompression Error");
        }

        public static byte[] Compress(byte[] inBuffer)
        {
            int decSize = inBuffer.Length;
            infile = new MemoryStream(inBuffer);
            outfile = new MemoryStream();
            Encode();
            MemoryStream outStream = new MemoryStream();
            BinaryWriter writer = new BinaryWriter(outStream);
            writer.Write(0x53535a4c);
            writer.Write(decSize);
            writer.Write((outfile as MemoryStream).ToArray());
            return outStream.ToArray();
        }

        public static void Decompress(String inFile, String outFile)
        {
            infile = new FileStream(inFile, FileMode.Open, FileAccess.Read);
            outfile = new FileStream(outFile, FileMode.Create, FileAccess.Write);
            Decode();
        }

        public static void Compress(String inFile, String outFile)
        {
            infile = new FileStream(inFile, FileMode.Open, FileAccess.Read);
            outfile = new FileStream(outFile, FileMode.Create, FileAccess.Write);
            Encode();
        }

        public static void Decompress(Stream inFileStream, Stream outFileStream)
        {
            infile = inFileStream;
            outfile = outFileStream;
            Decode();
        }

        public static void Compress(Stream inFileStream, Stream outFileStream)
        {
            infile = inFileStream;
            outfile = outFileStream;
            Encode();
        }
    }
}
```


Regards:

~Sky
## Post #19
- Username: brainfog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Dec 01, 2011 6:35 pm
- Post datetime: 2011-12-03T22:36:17+00:00
- Post Title: Re: Corpse Party PSP image.bin file

Thanx again
## Post #20
- Username: Toren
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 25, 2011 8:37 am
- Post datetime: 2011-12-04T23:04:45+00:00
- Post Title: Re: Corpse Party PSP image.bin file

This is great. Thank you all for your help.
## Post #21
- Username: Demoniiiik
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 09, 2011 3:25 am
- Post datetime: 2011-12-08T19:31:36+00:00
- Post Title: Re: Corpse Party PSP image.bin file

I'm sorry. But you can do the opposite? That is archiving folder IMAGE in image.bin?
I want to replace some of the texture.
## Post #22
- Username: magarcan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 22, 2011 4:06 am
- Post datetime: 2011-12-21T20:09:29+00:00
- Post Title: Re: Corpse Party PSP image.bin file

Thanks for the code and for the app, but I'm having a problem.

I've tested your app with the 10Mb file that other user has uploaded and I get an exception. Can´t a partial file be used?

I'm interested in traslate game into my language, spanish, do aby of you know how can I get string??

Thanks!!
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-22T01:19:02+00:00
- Post Title: Re: Corpse Party PSP image.bin file

The 10 MB sample most likely won't work cause it's trying to decompress or go to some offset that may or may not exist.
## Post #24
- Username: magarcan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 22, 2011 4:06 am
- Post datetime: 2011-12-22T07:39:40+00:00
- Post Title: Re: Corpse Party PSP image.bin file

> Reply from finale00
>
> The 10 MB sample most likely won't work cause it's trying to decompress or go to some offset that may or may not exist.
You are right, I've tested it with full file and works O.K.

Any idea about were can I find text's files??
## Post #25
- Username: cierpa
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 09, 2009 4:26 am
- Post datetime: 2011-12-26T20:27:49+00:00
- Post Title: Re: Corpse Party PSP image.bin file

> Any idea about were can I find text's files??
They're stored in SCRIPT folder. Check file SCRIPT_MAP5 (CHAP1) - these one have introduction of chapter 1.
As I checked they're seems compressed and contains bitmaps / voice acting/ avatars.
