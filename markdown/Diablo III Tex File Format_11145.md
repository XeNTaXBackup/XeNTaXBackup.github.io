## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-18T22:52:17+00:00
- Post Title: Diablo III Tex File Format

Hi guys, been figuring out how to convert the C++ data into c#

this is for coverting the .tex files (Diablo III Tex(tures)) to dds format.

up till the code below everything was just going well ( being not a C++ guy and all)

but now I ran into a huge problem, I don't understand what is happening in the part that starts with

```
if(nPixelSize == 8) 
```


In c# I have a BinaryReader object, that is used to read the bytes (and stuff) but I just can't seem to get that part of code... need help plz .

(code is originally taken from the C++ D3TEX2DDS converter)

```
	int nDecodeMethod, int nDecodeMethodEx, 
	uint8_t* pDst, uint8_t* pSrc, size_t nDstSize, 
	size_t nWidth, size_t nHeight, size_t nMipLevel, size_t nCalcPitch, size_t nTexPitch)
{

	//DecodeTexPixelData( nFormat, nFormat, pBuffer, pStart, nSize, nWidth ,nHeight, 0, nPitch, nPitch);

	//First Pass Decode
	uint8_t* pBuffer = NULL;
	if(nDecodeMethod <= 12 && nDecodeMethod >= 9)
	{
		size_t nPixels = ((nWidth >> nMipLevel) * (nHeight >> nMipLevel)) / 16;
		int nPixelSize = GetDecodeSize(nDecodeMethod);
		if(nPixelSize == -1)
			return 0;

		size_t nSize = nPixels * nPixelSize;
		pBuffer = (uint8_t*)malloc(nSize);



		if(nPixelSize == 8)
		{
			uint32_t* pDest = (uint32_t*)pBuffer;
			uint32_t* r = (uint32_t*)pSrc;
			uint32_t* g = (uint32_t*)(pSrc + (nPixels * 4));
			for(size_t i = nPixels; i != 0; i--)
			{
				pDest[0] = *r++;
				pDest[1] = *g++;
				pDest += 2;
			}
		}



```


Thnx
T.
## Post #2
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-21T08:32:23+00:00
- Post Title: Diablo III Tex File Format

looks like pixels stored in 2 different sources, column 0,2,4,6,...,n and column 1,3,5,7,...n+1 

```
      {
         uint32_t* pDest = (uint32_t*)pBuffer;
         uint32_t* r = (uint32_t*)pSrc;                          //pixels source 1
         uint32_t* g = (uint32_t*)(pSrc + (nPixels * 4));  //pixels source 2 8bit per color+8bit alpha = 32 or 4 bytes
         for(size_t i = nPixels; i != 0; i--)
         {
            pDest[0] = *r++;                                          //place first pixel from source 1, pDest[0] = *r; r = r + 1;
            pDest[1] = *g++;                                         //place second pixel from source 2, pDest[1] = *g; g = g + 1;
            pDest += 2;                                                //increment pDest,  pDest = pDest + 2;
         }
      }

```
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-29T07:47:51+00:00
- Post Title: Diablo III Tex File Format

aaaah, it starts to make sence... thnx

T.
