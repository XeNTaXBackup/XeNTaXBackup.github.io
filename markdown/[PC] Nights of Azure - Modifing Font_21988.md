## Post #1
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2020-04-10T01:40:32+00:00
- Post Title: [PC] Nights of Azure - Modifing Font

I'm trying modify the font of the Nights of Azure, I take a look in the russian translation and I found a thing,
the glyph coordinates are in the game exe, I tried discovery by myself about the font table structure, and I know this:

```
struct Glyph {
	public uint UTF8;//Reversed
	public ushort X;
	public ushort Y;
	public ushort Width;
	public ushort Height;
	public uint Unk2;//1?
	public uint Unk3;//2?
	public uint Unk4;//Padding? Width+1
	public uint Unk5;//0
}
```

It's probabbly 99% of sure that all unk values are padding, but I don't understand how padding works very well... is there any tool, or someone can see what is those unks to help me Write something?
## Post #2
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2020-04-10T18:53:35+00:00
- Post Title: [PC] Nights of Azure - Modifing Font

After sleep my brain worked again and I finished the tool, sorry for this post.
My final Strcuture

```
        struct Glyph
        {
            public uint UTF8;
            public ushort X;
            public ushort Y;
            public ushort Width;
            public ushort Height;
            public int PaddingLeft;
            public int PaddingTop;
            public int PaddingRigth;
            public int PaddingBottom;

            public Bitmap Texture;
            public char Char {
                get {
                    if (UTF8 == 0)
                        return char.MinValue;
                    var Bytes = BitConverter.GetBytes(UTF8);
                    while (Bytes.Last() == 0)
                        Array.Resize(ref Bytes, Bytes.Length - 1);
                    Bytes = Bytes.Reverse().ToArray();

                    return Encoding.UTF8.GetString(Bytes).Single();
                } set {
                    var Bytes = Encoding.UTF8.GetBytes(value.ToString());
                    Bytes = Bytes.Reverse().ToArray();

                    byte[] DW = new byte[4];
                    Bytes.CopyTo(DW, 0);

                    UTF8 = BitConverter.ToUInt32(DW, 0);
                }
            }
        }
        
```
