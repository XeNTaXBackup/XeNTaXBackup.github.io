## Post #1
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-07T20:24:23+00:00
- Post Title: LZSS Compression?

I'm looking into making a program that opens and allows editing of the .FSYS files from Pokémon Colosseum. The compression, LZSS, is confusing and I can't make heads or tails of it. Any help would be awesome.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-07-07T21:39:40+00:00
- Post Title: LZSS Compression?

I found this on the wiki
[http://wiki.xentax.com/index.php/LZSS](http://wiki.xentax.com/index.php/LZSS)
## Post #3
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-07T21:43:46+00:00
- Post Title: LZSS Compression?

Well, that's extremely useful, thank you, but I don't know any of the parameters. I'll have to look through the files again and look for similarities.
Edit: The second link on the wiki doesn't work.
## Post #4
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-07T22:04:51+00:00
- Post Title: LZSS Compression?

A question, what programming language is this?

while InputPos < InputSize do
begin
  FlagByte := Input[InputPos++]
  for i := 1 to 8 do
  begin
    if (FlagByte and 1) = 0 then
    begin
      OfsLen := Input[InputPos] + Input[InputPos + 1] shl 8
      InputPos += 2
      if OfsLen = 0 then
        Exit;
      Length := OfsLen and LengthMask + Threshold
      Offset := (BufPos - (OfsLen shr LengthBits)) and (N - 1)
      { copy Length bytes from Buffer[Offset] onwards while increasing BufPos }
    end
    else
    begin
      { copy 1 byte from Input[InputPos] }
      InputPos += 1
    end
    FlagByte := FlagByte shr 1
  end
end
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-07-08T01:14:38+00:00
- Post Title: LZSS Compression?

that is a general outline of what has to be translated into whatever language you program with.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-08T17:00:56+00:00
- Post Title: LZSS Compression?

Quickbms has a couple lz77 variants if you're not interested in figuring out how lz77 works (eg: doing it yourself) and just throwing a bunch of different algorithms at it.
## Post #7
- Username: Cyndaquil
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jun 04, 2012 6:12 pm
- Post datetime: 2012-07-08T20:28:30+00:00
- Post Title: LZSS Compression?

> Reply from finale00
>
> Quickbms has a couple lz77 variants if you're not interested in figuring out how lz77 works (eg: doing it yourself) and just throwing a bunch of different algorithms at it.
Quickbms? I haven't heard of that program...
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-08T20:42:17+00:00
- Post Title: LZSS Compression?

You're missing out lol

[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-09T09:04:21+00:00
- Post Title: LZSS Compression?

> Reply from Cyndaquil
>
> A question, what programming language is this?

while InputPos < InputSize do
begin
  FlagByte := Input[InputPos++]
  for i := 1 to 8 do
  begin
    if (FlagByte and 1) = 0 then
    begin
      OfsLen := Input[InputPos] + Input[InputPos + 1] shl 8
      InputPos += 2
      if OfsLen = 0 then
        Exit;
      Length := OfsLen and LengthMask + Threshold
      Offset := (BufPos - (OfsLen shr LengthBits)) and (N - 1)
      { copy Length bytes from Buffer[Offset] onwards while increasing BufPos }
    end
    else
    begin
      { copy 1 byte from Input[InputPos] }
      InputPos += 1
    end
    FlagByte := FlagByte shr 1
  end
end

Delphi
