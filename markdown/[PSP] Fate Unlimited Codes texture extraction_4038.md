## Post #1
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-01-11T15:43:46+00:00
- Post Title: [PSP] Fate Unlimited Codes texture extraction

first you need to unpack the fpk using the fpk unpacker (copy it where the fpk is and run the exe)
so when you unpack the fpk's you get loads of folders and files including ttd ones, ttd are textures packages
so copy the ttd extractor in any folder containing ttd files and run it, it will extract all of them as tim2 psp textures (viewable using Xnview soft)
[Fate_unlimited_codes_psp_ttd_to_tim2_extractor.rar](https://xentaxbackup.github.io/file/2712_Fate_unlimited_codes_psp_ttd_to_tim2_extractor.rar)
## Post #2
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-01-11T16:51:02+00:00
- Post Title: [PSP] Fate Unlimited Codes texture extraction

so some others format infos :
the .gmo contains the skeleton + 3d model decomposed in sub mesh :

vertex format i have found :

```
!nx
!ny
!nz
!tu
!tv
!x
!y
!z
!w
End Type

i tried on a data block and got a character hand in point rendering mode

```
## Post #3
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-05-06T08:14:23+00:00
- Post Title: [PSP] Fate Unlimited Codes texture extraction

Hi shadowmoy i think we should ask mr adult because he can extract gmo files from final fantasy dissidia and its in obj and it got its texture
## Post #4
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-05-06T08:23:42+00:00
- Post Title: [PSP] Fate Unlimited Codes texture extraction

I really like this game because i really love the anime.I hope we can extract the model of fate stay night and if possible i hope we can mod the game and replace its model
## Post #5
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-05-06T10:13:16+00:00
- Post Title: [PSP] Fate Unlimited Codes texture extraction

thanks for the info but i already knowed it ^^
## Post #6
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-05-06T14:17:43+00:00
- Post Title: [PSP] Fate Unlimited Codes texture extraction

i get all my friend to come to this thread so that we can identify it
## Post #7
- Username: valvoga
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-08T00:40:40+00:00
- Post Title: [PSP] Fate Unlimited Codes texture extraction

Oh, I hadn't noticed this topic. Well, you can use mesh2rdm (latest version is always on richwhitehouse.com) to extract fpk's like:

mesh2rdm file.fpk outpath

And then you can use it to convert or preview the GMO's that come out of the fpk's (run mesh2rdm with no cmd line for instructions). You can also drag the ttd files onto the mesh2rdm preview window to apply the textures. mesh2rdm doesn't support extracting TTD's though, as they are just collections of TIM2's and I was too lazy to add a proper path for them. You can iterate them with something like this.

```
{
	int				numEntries;
	int				unknownB;
	int				unknownC;
	int				unknownD;
} ttdHdr_t;

typedef struct ttdEntry_s
{
	int				fileSize;
	int				unknownA;
	int				unknownB;
	int				unknownC;
	char			fileName[64];
} ttdEntry_t;

//load a ttd file
static void Model_GMO_LoadTTD(char *ttdFile, int numMaterials, gmoMat_t *materials)
{
	FILE *f = fopen(ttdFile, "rb");
	if (!f)
	{
		return;
	}

	int len = _filelength(f->_file);
	BYTE *ttdBuf = (BYTE *)unpooled_malloc(len, 392);
	fread(ttdBuf, 1, len, f);
	fclose(f);

	ttdHdr_t *hdr = (ttdHdr_t *)ttdBuf;
	if (hdr->numEntries <= 0)
	{
		unpooled_free(ttdBuf);
		return;
	}

	ttdEntry_t *entries = (ttdEntry_t *)(hdr+1);
	for (int i = 0; i < hdr->numEntries; i++)
	{
		ttdEntry_t *e = entries;
		BYTE *data = (BYTE *)(e+1);
		if (Image_IsTIM2(data, e->fileSize))
		{
			for (int j = 0; j < numMaterials; j++)
			{
				gmoMat_t *mat = materials+j;
				if (mat->texName &&
					!stricmp(mat->texName, e->fileName))
				{
					Image_PreviewTIM2(data, e->fileSize, NULL, mat->texNum+1);
					mat->texUploaded = true;
				}
			}
		}

		BYTE *b = (BYTE *)entries;
		b = b + e->fileSize + sizeof(ttdEntry_t);
		entries = (ttdEntry_t *)b;
	}

	unpooled_free(ttdBuf);
}
```
## Post #8
- Username: Aerow
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 05, 2010 4:32 pm
- Post datetime: 2010-09-06T09:39:14+00:00
- Post Title: [PSP] Fate Unlimited Codes texture extraction

is there any tool to pack the tm2's into a ttd?
## Post #9
- Username: firecraft
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 04, 2015 6:06 pm
- Post datetime: 2015-09-04T10:16:31+00:00
- Post Title: [PSP] Fate Unlimited Codes texture extraction

> Reply from Aerow
>
> is there any tool to pack the tm2's into a ttd?

im looking for same thing too ><

I Want to translate the game but I cant find way to repack the tm2 file's
