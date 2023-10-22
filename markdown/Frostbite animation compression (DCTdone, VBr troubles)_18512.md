## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-07-29T05:44:12+00:00
- Post Title: Frostbite animation compression (DCTdone, VBr troubles)

Does anyone know how DCT is applied to an animation?

I vaguely understand how it is applied to an image but this is a little confusing
Luckily i have access to the structures but still it doesnt make much sense

```
		public UInt8 QuantizeMultSubblock; 
		public UInt8 CatchAllBitCount;


		public FArray<UInt8> DofTableDescBytes; //No idea what this is but it matches the size of the delta's below

               //these are probably the coefficients (AC)
		public FArray<Int16> DeltaBaseX; 
		public FArray<Int16> DeltaBaseY;
		public FArray<Int16> DeltaBaseZ;
		public FArray<Int16> DeltaBaseW; 

               //no idea
		public FArray<UInt16> BitsPerSubblock;
		public UInt32 DataSize; 

                //actual data
		public FArray<UInt8> Data;

```


I included a sample file and a 010 template 

 18.zip
(1.68 KiB) Downloaded 18 times
## Post #2
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-05-18T21:27:53+00:00
- Post Title: Frostbite animation compression (DCTdone, VBr troubles)

DCT is done thanks to critical files from Highflex
The coefficients are in the executable and change per game

I did not figure out the mapping from transform ( position/ rotation) to bone

It turns out I should have been more worried about the vbr animations instead

```
    public class VbrAnimationAsset : FIFAData
    {
        public Key __key; //sz 8, pos 72, datSz 8, idx 1, sigID 5256
        public String __name; //sz 16, pos 48, datSz 8, idx 1, sigID 5128
        public DataRef __base; //sz 8, pos 64, datSz 8, idx 1, sigID 5208
        public Float QuatMin; //sz 4, pos 80, datSz 4, idx 11, sigID 4464
        public Float TrajMin; //sz 4, pos 84, datSz 4, idx 10, sigID 4464
        public Float Vec3Min; //sz 4, pos 88, datSz 4, idx 9, sigID 4464
        public Float FloatMin; //sz 4, pos 92, datSz 4, idx 8, sigID 4464
        public Float QuatMax; //sz 4, pos 96, datSz 4, idx 7, sigID 4464
        public Float TrajMax; //sz 4, pos 100, datSz 4, idx 6, sigID 4464
        public Float Vec3Max; //sz 4, pos 104, datSz 4, idx 5, sigID 4464
        public Float FloatMax; //sz 4, pos 108, datSz 4, idx 4, sigID 4464
        public Float VectorOffsetScale; //sz 4, pos 112, datSz 4, idx 3, sigID 4464
        public Float FloatOffsetScale; //sz 4, pos 116, datSz 4, idx 2, sigID 4464
        public Float Dct; //sz 4, pos 120, datSz 4, idx 1, sigID 4464
        public UInt16 QuaternionCount; //sz 2, pos 124, datSz 2, idx 13, sigID 4304
        public UInt16 Vector3Count; //sz 2, pos 126, datSz 2, idx 12, sigID 4304
        public UInt16 FloatCount; //sz 2, pos 128, datSz 2, idx 11, sigID 4304
        public UInt16 ConstQuaternionCount; //sz 2, pos 130, datSz 2, idx 10, sigID 4304
        public UInt16 ConstVector3Count; //sz 2, pos 132, datSz 2, idx 9, sigID 4304
        public UInt16 ConstFloatCount; //sz 2, pos 134, datSz 2, idx 8, sigID 4304
        public UInt16 KeyTimeSize; //sz 2, pos 136, datSz 2, idx 7, sigID 4304
        public UInt16 NumKeys; //sz 2, pos 138, datSz 2, idx 6, sigID 4304
        public UInt16 ConstChanMapSize; //sz 2, pos 140, datSz 2, idx 5, sigID 4304
        public UInt16 ConstPaletteSize; //sz 2, pos 142, datSz 2, idx 4, sigID 4304
        public UInt16 VectorOffsetSize; //sz 2, pos 144, datSz 2, idx 3, sigID 4304
        public UInt16 FloatOffsetSize; //sz 2, pos 146, datSz 2, idx 2, sigID 4304
        public UInt16 Flags; //sz 2, pos 148, datSz 2, idx 1, sigID 4304
        public FArray<Float> ConstantPalette; //sz 16, pos 32, datSz 8, idx 1, sigID 4464
        public FArray<UInt16> FrameBlockSizes; //sz 16, pos 16, datSz 8, idx 1, sigID 4304
        public FArray<UInt8> Data; //sz 16, pos 0, datSz 8, idx 1, sigID 4224
    }


```

[v.zip](https://xentaxbackup.github.io/file/16257_v.zip)
