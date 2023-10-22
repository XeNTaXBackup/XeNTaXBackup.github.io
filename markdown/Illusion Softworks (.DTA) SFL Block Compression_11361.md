## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-25T15:44:13+00:00
- Post Title: Illusion Softworks (*.DTA) SFL Block Compression

Hi every one. I try make generic unpacker for old games by Illusion Softworks such as:

* Mafia - (DTA version ISD0) - Encrypted
* Chameleon - (DTA version ISD1) - Encrypted
* Hidden & Dangerous 2 - (DTA version ISD0) - Encrypted
* Hidden & Dangerous 2 : Sabre Squadron - (DTA version ISD0 + ISD1) - Encrypted
* Wings of War - (DTA version ISD1) - Not Encrypted


but need help with decompressing file datas. With comptype scanner i found compression method - it's SFL Block (#34). Ok here general info about structure DTA's , quick and crappy code.

```
{
   DWORD dwID; //Can be ISD0 and ISD1
   DWORD dwTotalFiles;
   DWORD dwTableOffset;
   DWORD dwTableSize;
};

struct t_DTATableEntry
{
   DWORD dwUnknown;
   DWORD dwOffsetAH;  // Offset for additional header
   DWORD dwOffsetFD;  // Offset for compressed file data
   char pFileNameHint[16];
};

// Additional header
struct t_DTA_AC_ISD1
{
    DWORD dwExtra1;
    DWORD dwExtra2;
    DWORD dwExtra3;
    DWORD dwExtra4;
    DWORD dwSize; // Decompressed size
    DWORD dwBlocksCount; // Nums of compressed block for current file data
    DWORD pExtra5;
    DWORD pFNameLength; // &0x7FFF (or you can use 2x short)
};
  
   DWORD dwTempPos = 0;
   t_DTAHeader pDTAHeader;
   t_DTATableEntry pDTATableEntry;
   t_DTA_AC_ISD1 pDTAACISD1;
   
   // Reading header
   fread(&pDTAHeader, sizeof(pDTAHeader), 1, fi);
   fseek(fi, pDTAHeader.dwTableOffset, SEEK_SET);
   
   for(int i = 0; i < pDTAHeader.dwTotalFiles; i++)
   {
      fread(&pDTATableEntry, sizeof(pDTATableEntry), 1, fi);
      fseek(fi, pDTATableEntry.dwOffsetAH, SEEK_SET);
	  

      // Read additional header
      fread(&pDTAACISD1, sizeof(pDTAACISD1), 1, fi);
      unsigned char* pFileName = new unsigned char[pDTAACISD0.pFNameLength & 0x7FFF];
      memset(pFileName, 0, pDTAACISD1.pFNameLength & 0x7FFF);
      fread(pFileName, sizeof(char), pDTAACISD1.pFNameLength & 0x7FFF, fi);
      dwTempPos = ftel(fi);
		 
      WORD wZSize;
      WORD wOSize = 0;
      WORD wUnknown;
		 
      unsigned char* pDstBuffer = new unsigned char[pDTAACISD1.dwSize];
      memset(pDstBuffer, 0, pDTAACISD1.dwSize);
      
      int pResult = 0;	 
      for(int j = 0; j < pDTAACISD1.dwBlocksCount; j++)
      {
            //Read compressed sizes after filename in additional header
            fseek(fi, dwTempPos, SEEK_SET);
            fread(&wZSize, 2, 1, fi);
            fread(&wUnknown, 2, 1, fi);
            dwTempPos = ftel(fi);
            
            unsigned char* pScrBuffer = new unsigned char[wZSize];
            memset(pScrBuffer, 0, wZSize);
            fseek(fi, pDTATableEntry.dwOffsetFD, SEEK_SET);
            fread(pScrBuffer, wZSize, 1, fi);
            pDTATableEntry.dwOffsetFD = ftel(fi);
			
            //https://github.com/imatix/gsl/blob/master/src/sflcomp.c
            wOSize = expand_block(pScrBuffer, pDstBuffer[pResult], wZSize);
            pResult = pResult + wOSize;
            free((void*) pScrBuffer);
      }
      //Save file... bla bla bla.....
   }
}
  
```
 
Well, 1st block decompressed fine, but with next blocks something wrong  . Can someone help? Top secret files [here](http://www.sendspace.com/file/p3s6wc) from Wings of War.

Thanks advance for any hint
## Post #2
- Username: hdmaster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 03, 2011 5:05 am
- Post datetime: 2014-05-07T11:51:49+00:00
- Post Title: Illusion Softworks (*.DTA) SFL Block Compression

I already wrote a working generic unpacker but actually never released the sources   . I'll post a link to source code here soon.
Although the DTA compression looks similar to SFL Block to me, it is a little bit different. Both use LZSS and RLE but DTA also uses some kind of differential pulse code modulation (DPCM) for WAV files.

EDIT: I've uploaded a quick & dirty VC++ 2013 sample project (uncommented): [https://dl.dropboxusercontent.com/u/321 ... w_data.rar](https://dl.dropboxusercontent.com/u/32112219/Upload/rw_data.rar)
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-09T13:27:00+00:00
- Post Title: Illusion Softworks (*.DTA) SFL Block Compression

Interesting. Thanks for share 

btw: 

Chameleon

```
bilboard1.dta    0xDE75DDF2      0xDEDC644B
bilboard2.dta    0xDE75DDF2      0xDEDC644B
isdata.dta       0xDE75DDF2      0xDEDC644B
```

Mafia

```
bilboard1.dta   0xA1B2C3D4      0x23463458
bilboard2.dta   0xA1B2C3D4      0x23463458
isdata.dta      0xA1B2C3D4      0x23463458
```
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-06-25T13:22:57+00:00
- Post Title: Illusion Softworks (*.DTA) SFL Block Compression

What kind of encryption did Illusion use for Mafia and some of their other LS3D games? Also, what exactly does the Mafia DTA Extractor do to rw_data.dll, besides allowing loose archives to be read of course? Does it disable whatever signature or encryption flag the game imposes on things?
## Post #5
- Username: Habanero
- Rank: n00b
- Number of posts: 19
- Joined date: Thu May 02, 2019 2:36 am
- Post datetime: 2020-05-25T22:01:34+00:00
- Post Title: Illusion Softworks (*.DTA) SFL Block Compression

Edit: Nevermind, I didn't see [this thread](https://forum.xentax.com/viewtopic.php?t=9135) when I searched (it showed up in Google instead). Thank you!

Oh nice, there's already a thread up for this. I wanted to extract Chameleon's music and sound (just started playing it -- nice game so far, underrated). I got a compiled EXE of huckleberrypie's unpacker that was posted by Ekey way back in 2015, but I'm getting a PATH error. How do I set the directory? Or is there another mistake I made? Additionally, if someone could reupload the source code for the unpacker for posterity's sake, that'd be appreciated. Thank you.



By the way, here's some documentation on the format if anyone's interested.

[http://www.kamalook.de/Mafia/DTA.html](http://www.kamalook.de/Mafia/DTA.html)
