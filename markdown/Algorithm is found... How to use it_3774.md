## Post #1
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-10T01:03:30+00:00
- Post Title: Algorithm is found... How to use it?

Hello...
I've spent about a week with IDA pro, and... YES, i've finally discovered the possible uncompression function used in "my" game. 

Pseudocode by hexrays (  )

```
{
  int *v1; // esi@1
  char v2; // al@2

  v1 = (int *)a1;
  if ( *(_BYTE *)a1 )
  {
    do
    {
      *(_BYTE *)v1 = tolower(*(_BYTE *)v1);
      v2 = *((_BYTE *)v1 + 1);
      v1 = (int *)((char *)v1 + 1);
    }
    while ( v2 );
  }
}

```


Now i stuck..... How to use it? Any strategies? Ideas?
I've heard there is a way to use program functions by adding your own and modifying the exe.. Ida can modify the file but i've no idea what to do actually...

More clear way is to understand the algorithm, but i'm tired, in panic and already hate all search engines...

In short: help!
Or at least kick in right direction...
Thanks.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-10T04:02:51+00:00
- Post Title: Algorithm is found... How to use it?

any compression algorithm has at least 3 fields:
- input data
- size of the input data
- output buffer

so it's clear that the function you found is only a minimal part of the whole algorithm :)
if it's a xbox game there are good chances that it's a block of data compressed with XMemCompress (quickbms supports the decompression function).

when you encounter an unknown algorithm and want to use it immediately there are 2 choices:
- reversing it (asm->your_language)
- trying to use it directly

in the second case you could do it just exporting the bytes of the function and using them in your program but that's possible only if the function is only one (not your case) and there is no usage of static fields.
the second option is to use LoadLibrary for loading the executable in memory and then using the function from there like a dll and it should work.
obviously you must ever find the real main function, so algorithm(input, input_len, output, ...) and in same cases even an init function
## Post #3
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-10T08:18:53+00:00
- Post Title: Algorithm is found... How to use it?

Thanks for reply.)
This game is multiplatform - xbox is main i guess. (because function for reading files refers to XBoxFileHAL.cpp)
I tried XMemDecompress, didn't work.
(I still hope to get this game easyly....)  
Maybe you'll take a quick look at the attached file? Some strings are readable, so looks like it's simple plain text xml.
[havok.zip](https://xentaxbackup.github.io/file/2433_havok.zip)
## Post #4
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-12T20:14:39+00:00
- Post Title: Algorithm is found... How to use it?

As i just discovered the said function only reads strings like 'data/Textures/blabla.texpack' letter-by-letter and converts them to lowercase. I'm LOL x)

Nevermind. i've finally found the right function.
Here it is, in all its glory:
(its C)

```
{
  int start;
  int end;
  unsigned int v0;
  char v1;
  char v2;
  unsigned int i;
  int v3;
  int v4;
  int v5;
  int v6;
  unsigned int k;
  int v7;
  unsigned int v8;
  int v9;
  signed int v10;
  int v11;
  int v12;
  char v13;
  int v14;
  int v15;
  char v16;
  int j;
  char v17;

  end = END;
  start = START;
  do
  {
LABEL_1:
    v8 = *(_BYTE *)end;
    v9 = *(_BYTE *)end++ & 7;
    v0 = v8 >> 3;
    j = v9 + 1;
    if ( (signed int)v0 < 30 )
      goto LABEL_2;
    if ( v0 == 30 )
    {
      v0 = *(_BYTE *)end++ + 30;
LABEL_2:
      if ( !v0 )
        continue;
      goto LABEL_3;
    }
    v0 += *(_BYTE *)end + (*(_BYTE *)(end + 1) << 8) + 255;
    end += 2;
    if ( v0 != 65821 )
      goto LABEL_2;
    --j;
LABEL_3:
    v1 = *(_BYTE *)end;
    LOBYTE(END) = *(_BYTE *)(end + 1);
    v17 = *(_BYTE *)(end + 2);
    v2 = *(_BYTE *)(end + 3);
    if ( (signed int)v0 >= 4 )
    {
      i = v0 >> 2;
      v0 += -4 * (v0 >> 2);
      do
      {
        *(_BYTE *)start = v1;
        *(_BYTE *)(start + 1) = END;
        end += 4;
        *(_BYTE *)(start + 2) = v17;
        *(_BYTE *)(start + 3) = v2;
        v1 = *(_BYTE *)end;
        LOBYTE(END) = *(_BYTE *)(end + 1);
        start += 4;
        --i;
        v17 = *(_BYTE *)(end + 2);
        v2 = *(_BYTE *)(end + 3);
      }
      while ( i );
    }
    if ( (signed int)v0 > 0 )
    {
      end += v0;
      *(_BYTE *)start++ = v1;
      if ( (signed int)v0 > 1 )
      {
        *(_BYTE *)start++ = END;
        if ( (signed int)v0 > 2 )
          *(_BYTE *)start++ = v17;
      }
    }
  }
  while ( !j );
  while ( 1 )
  {
    v10 = *(_BYTE *)end;
    --j;
    v4 = v10 & 7;
    ++end;
    v3 = v10 >> 3;
    if ( v4 )
      goto LABEL_4;
    v5 = *(_BYTE *)end++;
    if ( !v5 )
      return start - START;
    v4 = v5 + 7;
LABEL_4:
    if ( v3 >= 30 )
    {
      if ( v3 == 30 )
      {
        v3 = *(_BYTE *)end + 30;
      }
      else
      {
        v11 = *(_BYTE *)end + v3;
        v12 = *(_BYTE *)(end++ + 1);
        v3 = v11 + (v12 << 8) + 255;
      }
      ++end;
    }
    v6 = start - v3 - 1;
    if ( v4 >= 4 )
    {
      k = (unsigned int)v4 >> 2;
      v4 += -4 * ((unsigned int)v4 >> 2);
      do
      {
        *(_BYTE *)start = *(_BYTE *)v6;
        v13 = *(_BYTE *)(v6 + 1);
        v14 = start + 1;
        v15 = v6 + 1;
        *(_BYTE *)v14 = v13;
        v16 = *(_BYTE *)(v15 + 1);
        ++v14;
        ++v15;
        *(_BYTE *)v14++ = v16;
        *(_BYTE *)v14 = *(_BYTE *)(v15 + 1);
        start = v14 + 1;
        v6 = v15 + 2;
        --k;
      }
      while ( k );
    }
    if ( v4 > 0 )
    {
      *(_BYTE *)start++ = *(_BYTE *)v6;
      v7 = v6 + 1;
      if ( v4 > 1 )
      {
        *(_BYTE *)start++ = *(_BYTE *)v7;
        if ( v4 > 2 )
          *(_BYTE *)start++ = *(_BYTE *)(v7 + 1);
      }
    }
    if ( !j )
      goto LABEL_1;
  }
}

```

First the program places file in memory. START and END are pointers. START points to the beginning of a file in memory, END points to the end. That's all parameters this algorithm needs. Looks like it doesn't even calculate file size.

The rest is easy.     

P.S.
I wonder if this algorithm is some modifyed popular algorithm. I've no enough experience to find it out...
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-12T21:07:17+00:00
- Post Title: Algorithm is found... How to use it?

nice, in attachment there is the clean C algorithm and a quick tool to test it:
test.exe input_file output_file

do you have also one of those compressed data blocks to test?
anyway I don't remember to have seen a similar algorithm in the past, never seen constants like 0x1011d and 0x1e in a decompression function so don't know what could be the real name of the algorithm.
[test.zip](https://xentaxbackup.github.io/file/2437_test.zip)
## Post #6
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-13T03:55:34+00:00
- Post Title: Algorithm is found... How to use it?

Working! I don't believe i just did it. ^_^
So much thank you for clean C.
Now i only need to understand the format of meshes. Hope it will be easier.
[compressed_examples.zip](https://xentaxbackup.github.io/file/2439_compressed_examples.zip)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-13T10:40:13+00:00
- Post Title: Algorithm is found... How to use it?

oh I have noticed that some of the dds you posted have a compression ratio bigger than the 10x I used to calculate the max output size, so I have updated a bit the code so that now if the uncompressed data is bigger then the output memory is increased and reallocated automatically.
[test2.zip](https://xentaxbackup.github.io/file/2440_test2.zip)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-14T00:31:46+00:00
- Post Title: Algorithm is found... How to use it?

I have checked also in the executable of Shrek SuperSlam but there is no trace of the name of the algorithm.
the only reference is to the name of the file IO_xbox_MemFileHAL.cpp which contains the function but doesn't help much.
another mistery unresolved...
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-14T19:27:12+00:00
- Post Title: Algorithm is found... How to use it?

Nice going, Corwin and others!
## Post #10
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-14T21:26:26+00:00
- Post Title: Algorithm is found... How to use it?

Ouch... Looks like i'm busted    
Ahh, whatever   Not so many people will go so far to put their hands on these models.  

Anyway, thanks again ^_^
## Post #11
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-10-17T17:45:33+00:00
- Post Title: Algorithm is found... How to use it?

I have rewritten the algorithm. It's much easier to understand and has less than half lines of code   .

With this, it should be much easier to write a tool to compress the files again, or calculate the file size without trial and error.

[http://pastebin.com/f5a2c25ac](http://pastebin.com/f5a2c25ac)

It worked for the files that I tried it with, if anyone has a file that doesn't work, tell me.
## Post #12
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2009-11-04T23:56:15+00:00
- Post Title: Algorithm is found... How to use it?

What is the game? PM if you are shy
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-05T03:36:29+00:00
- Post Title: Algorithm is found... How to use it?

it could be Shrek SuperSlam
