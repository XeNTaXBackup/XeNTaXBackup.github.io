## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-19T02:39:29+00:00
- Post Title: Yakuza 3

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Acewell
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-09-22T09:58:44+00:00
- Post Title: Yakuza 3

I took a shot at getting this figured out tonight, but I failed. It does appear to be some kind of LZ77-based algorithm, with the 16-byte SLLZ header at the start of all compressed data. However, the control bits confuse me and I think the highest bit has some special meaning. I'm not sure if this is related to keeping a running dictionary in addition to or instead of the standard sliding window for reference bits.

I really wanted to get it done tonight since tomorrow I've gotta get back to some other things and I told Surveyor I would look at Bayonetta anims which I have continually failed to do. I will let you know once I get a chance to get back on this though, if no one else figures it out in the mean time. Here is also some code that handles writing files with folder names, in case it's any use to you. Don't know if you have the folder stuff figured out or not.

```
{
	BYTE			id[4];
	int				unknownA;
	int				unknownB;
	int				unknownC;
	int				numFolders;
	int				foldersOfs;
	int				numFiles;
	int				filesOfs;
} parcHdr_t;
typedef struct parcFileName_s
{
	char			p[64];
} parcFileName_t;
typedef struct parcFileInfo_s
{
	int				comprFlags;
	int				fileSize;
	int				fileSizeComp;
	int				fileOfs;
	int				unknownE;
	int				unknownF;
	int				unknownG;
	DWORD			chkSum; //guessing
} parcFileInfo_t;
typedef struct parcFoldInfo_s
{
	int				unknownA;
	int				unknownB;
	int				numFiles;
	int				fileOfs;
	int				unknownE;
	int				unknownF;
	int				unknownG;
	int				unknownH;
} parcFoldInfo_t;

//used by yakuza 3
bool IsPARC(BYTE *fileBuffer, int bufferLen, bool justChecking)
{
	if (bufferLen < sizeof(parcHdr_t))
	{
		return false;
	}
	parcHdr_t hdr = *((parcHdr_t *)fileBuffer);
	LITTLE_BIG_SWAP(hdr.unknownA);
	LITTLE_BIG_SWAP(hdr.unknownB);
	LITTLE_BIG_SWAP(hdr.unknownC);
	LITTLE_BIG_SWAP(hdr.numFolders);
	LITTLE_BIG_SWAP(hdr.foldersOfs);
	LITTLE_BIG_SWAP(hdr.numFiles);
	LITTLE_BIG_SWAP(hdr.filesOfs);

	if (memcmp(hdr.id, "PARC", 4))
	{
		return false;
	}
	if (hdr.numFiles <= 0 || hdr.numFolders < 0)
	{
		return false;
	}
	if (hdr.foldersOfs < 0 || hdr.foldersOfs >= bufferLen)
	{
		return false;
	}
	if (hdr.filesOfs <= 0 || hdr.filesOfs >= bufferLen)
	{
		return false;
	}
	if ((size_t)hdr.numFiles*sizeof(parcFileName_t) > (size_t)bufferLen)
	{
		return false;
	}

	if (justChecking)
	{
		return true;
	}

	parcFileName_t *foldNames = (hdr.numFolders > 0) ? (parcFileName_t *)(fileBuffer + sizeof(parcHdr_t)) : NULL;
	parcFileName_t *fileNames = (parcFileName_t *)(fileBuffer + sizeof(parcHdr_t) + sizeof(parcFileName_t)*hdr.numFolders);
	parcFoldInfo_t *foldInfos = (hdr.numFolders > 0) ? (parcFoldInfo_t *)(fileBuffer + hdr.foldersOfs) : NULL;
	parcFileInfo_t *fileInfos = (parcFileInfo_t *)(fileBuffer + hdr.filesOfs);
	for (int i = 0; i < hdr.numFolders; i++)
	{
		parcFoldInfo_t foi = *(foldInfos+i);
		parcFileName_t *foiName = foldNames+i;
		LITTLE_BIG_SWAP(foi.unknownA);
		LITTLE_BIG_SWAP(foi.unknownB);
		LITTLE_BIG_SWAP(foi.numFiles);
		LITTLE_BIG_SWAP(foi.fileOfs);
		LITTLE_BIG_SWAP(foi.unknownE);
		LITTLE_BIG_SWAP(foi.unknownF);
		LITTLE_BIG_SWAP(foi.unknownG);
		LITTLE_BIG_SWAP(foi.unknownH);
		if (foi.numFiles <= 0)
		{
			continue;
		}
		for (int j = 0; j < foi.numFiles; j++)
		{
			parcFileInfo_t fi = *(fileInfos+foi.fileOfs+j);
			parcFileName_t *fiName = (fileNames+foi.fileOfs+j);
			LITTLE_BIG_SWAP(fi.comprFlags);
			LITTLE_BIG_SWAP(fi.fileSize);
			LITTLE_BIG_SWAP(fi.fileSizeComp);
			LITTLE_BIG_SWAP(fi.fileOfs);
			LITTLE_BIG_SWAP(fi.unknownE);
			LITTLE_BIG_SWAP(fi.unknownF);
			LITTLE_BIG_SWAP(fi.unknownG);
			LITTLE_BIG_SWAP(fi.chkSum);
			if (fi.fileOfs <= 0 || fi.fileOfs > bufferLen)
			{
				richprintf("WARNING: Out of range file offset.\n");
				continue;
			}

			BYTE *fileData = fileBuffer + fi.fileOfs;
			int fileSize = fi.fileSizeComp;
			bool freeFileData = false;
			if (fi.comprFlags & (1<<31))
			{ //compressed data
				if (fi.fileSizeComp < 16 || memcmp(fileData, "SLLZ", 4))
				{
					richprintf("WARNING: Not valid compression data!\n");
					continue;
				}
				BYTE *dcmpBuf = (BYTE *)unpooled_malloc(fi.fileSize);
				UnSLLZ(dcmpBuf, fi.fileSize, fileData+16, fi.fileSizeComp); //<-- doesn't work
				fileSize = fi.fileSize;
				fileData = dcmpBuf;
				freeFileData = true;
			}
			else if (fi.fileSize != fi.fileSizeComp)
			{
				richprintf("WARNING: Unexpected size mismatch without compression flag.\n");
				continue;
			}

			char fn[4096];
			sprintf(fn, "%s%s\\%s", g_outFileName, foiName->p, fiName->p);
			FILE *fw = fopen(fn, "wb");
			if (!fw)
			{
				MakeDirectoriesForPath(fn);
				fw = fopen(fn, "wb");
			}
			if (fw)
			{
				richprintf("Writing '%s'.\n", fn);
				fwrite(fileData, 1, fileSize, fw);
				fclose(fw);
			}
			if (freeFileData)
			{
				unpooled_free(fileData);
			}
		}
	}

	return true;
}
```
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-22T10:24:17+00:00
- Post Title: Yakuza 3

Thanks for looking into this 
ill be on the lookout for a release and ill make a model import er once i get a hold of the files.
Thanks for the folder info.
## Post #4
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-11-18T16:03:44+00:00
- Post Title: Yakuza 3

> Reply from chrrox
>
> Thanks for looking into this 
ill be on the lookout for a release and ill make a model import er once i get a hold of the files.
Thanks for the folder info.
PS3のソフトは暗号化されているので、まずは復号化した状態でリッピングをする必要があります。(ググればヒントがあると思います)
１体のモデルは独自のアイカーブ形式でテクスチャと一緒に連結されLZSS系かと思われる圧縮がされていました。
見たところ一般的なLZSSではないと思います。
多分、圧縮フラグのビットを反転させれば行けそうな気がしますがやってみないとわかりません。
テクスチャはDDSファイルのようです。モデルはPS系標準フォーマット？のGMDフォーマットのようです。
あとはダンプエディタで16進数を眺め変換プログラムを書くと良いでしょう。
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-18T17:12:52+00:00
- Post Title: Yakuza 3

Sounds like he's managed to decompress some data. Where did you get this?

LZSS sounds right, the only thing that still had me guessing was that the initial dictionary seemed to be initialized from somewhere. (and I'm still only guessing at the rest of the encoding, my predicted sizes tended to be off by 100-500 bytes, yet I couldn't find what looked like a dictionary embedded in the file itself) It's on my todo list to disassemble one of the PS2 Yakuza games to figure the rest out, since chrrox informed me that the compression method was the same back then. But if someone has already cracked it, it would be great to avoid that trouble.
## Post #6
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-11-19T10:16:10+00:00
- Post Title: Yakuza 3

> Reply from MrAdults
>
> Sounds like he's managed to decompress some data. Where did you get this?

LZSS sounds right, the only thing that still had me guessing was that the initial dictionary seemed to be initialized from somewhere. (and I'm still only guessing at the rest of the encoding, my predicted sizes tended to be off by 100-500 bytes, yet I couldn't find what looked like a dictionary embedded in the file itself) It's on my todo list to disassemble one of the PS2 Yakuza games to figure the rest out, since chrrox informed me that the compression method was the same back then. But if someone has already cracked it, it would be great to avoid that trouble.
look at 
[http://www.cute.or.jp/~makuchan/cgi/bbs ... de=msgview](http://www.cute.or.jp/~makuchan/cgi/bbs.cgi?no=753&reno=752&oya=747&mode=msgview)
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-28T05:21:49+00:00
- Post Title: Yakuza 3

I think he is just saying to look at the dds textures that are compressed because you know what the outcome should be.
i ran some tests and these algorithms produced some resemblance of how the file should look

COMP_LZ77WII_RAW30,
COMP_PGLZ,
COMP_PUYO_CXLZ, 
COMP_PUYO_LZSS,

the best looking one was COMP_LZ77WII_RAW30,
it must be close to this not sure what is off tho.
## Post #8
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2011-01-13T19:50:44+00:00
- Post Title: Yakuza 3

what about PAR archives?
[http://narod.ru/disk/3384745001/font.par.html](http://narod.ru/disk/3384745001/font.par.html)
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-30T19:52:28+00:00
- Post Title: Yakuza 3

I will release the new version of quickbms and the script tomorrow.
the link for the script will be: [http://aluigi.org/papers/bms/parc.bms](http://aluigi.org/papers/bms/parc.bms)
