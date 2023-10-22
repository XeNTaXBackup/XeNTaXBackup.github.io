## Post #1
- Username: sleet01
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 16, 2010 8:42 am
- Post datetime: 2010-05-23T09:02:39+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

Hi!

I'm trying to get started on a Chromehounds-based Arma2 total conversion, now that the CH servers have been taken down.  It's taken me a bit of time but I finally dumped my disk and found that, although the map files are in readily-accessible .mdl format, almost all of the 3D assets I'm really interested in are in .bnd packages.  I'm looking at the package file tutorial but thought I'd also ask here if anybody knew about the setup of these files, in case this is a solved problem.

Chromehounds is a 360 game written by From and published by Sega, so it almost certainly has some Japanese naming conventions hidden in the source.  It appears that Chromehounds was written almost entirely with 3D Gamestudio version 6 or so, since some of the map data is in .mdl files using the MDL4 header format.  Unfortunately the MDL files held in .bnd packages appear to be compressed, or at least binarized, and I'm not sure I'll be able to access them without some deep magic.  Only a couple of .bnd files used by the menu system or game front end, for 3D objects in some menus, are uncompressed as far as I can tell.

Here's one of the .bnd file headers I'm seeing:

42 4e 44 33 30 35 49 32 39 56 34 38 e4 00 00 00
00 00 00 03 00 00 00 00 00 00 00 00 00 00 00 00
c0 00 00 00 00 0b 66 6c 00 00 00 90 00 00 00 00
00 00 00 68 00 26 30 00 c0 00 00 00 00 04 a1 c5
00 0b 67 00 00 00 00 01 00 00 00 72 00 09 58 00
c0 00 00 00 00 00 34 d9 00 10 08 d0 00 00 00 02
00 00 00 7c 00 00 b2 c0 63 31 30 30 31 2e 6d 64
6c 00 63 31 30 30 31 2e 73 6d 64 00 63 31 30 30
31 2e 6d 32 61 00 00 00 00 00 00 00 00 00 00 00
78 9c ec bd 05 74 1d 47 d2 36 dc c3 cc 33 e6 98

(Cut off at 0090 offset line as this is the start of a .mdl file, if I'm reading this correctly)

The first 16 bytes seem to be the signature; the next 4 bytes appear to be the number of files in the package.
I'm guessing the 8 bytes from offset 0020 are compressed file size with an intro ('c0'), followed by offset to the
start of the first file (00 00 00 90 in this case) and then 12 bytes for uncompressed file size, but I have zero confidence
in this reading.  I do know that after the file names section (offset 0068) it looks like a .mdl file starts at 0090, but
it doesn't conform to the MDL4 format [listed here](http://www.coniserver.net/wiki/index.php/MDL) as far as
I can see.

The signature BND305I29V48ä appears to be the same for all .bnd files in Chromehounds, but I can't find it anywhere on the net
so it may be a custom format as opposed to part of the 3D Gamestudio tools.

[A map geometry data .bnd file](http://www.filefront.com/16518709/m01_001.bnd/)
[A map object data .bnd file](http://www.filefront.com/16518709/m01_001.bnd/)
[A large weapon parts geometry data .bnd file](http://www.filefront.com/16518783/LG_ML062.bnd/)
[An unknown-usage geometry data .bnd file](http://www.filefront.com/16518793/c1001.bnd/) (possibly for non-Chromehound-related units, e.g. tanks, walkers, etc.)
[A packed but not compressed special-effects geometry MDL .bnd file](http://www.filefront.com/16521115/sfx_mdl.bnd)
(Note: these descriptions are all guesses based on the directories I found these files in, their names, and intuition.)

Any help will be deeply appreciated.
## Post #2
- Username: sleet01
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-23T22:43:56+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

Quite a while ago, I came across a PSP game called Armored Core from the same developers, which also used .bnd files. This format is almost identical except that it adds optional zlib-compression to the files (and it's big-endian). Here's how to rip it:

```
{
	BYTE		id[12];
	int			unknownA;
	int			numFiles;
	int			pad[3];
} bnd2Hdr_t;
typedef struct bnd2Entry_s
{
	int			unknownA;
	int			fileSize;
	int			fileOfs;
	int			fileNum;
	int			fnOfs;
	int			decompSize;
} bnd2Entry_t;
bool IsBND2(BYTE *fileBuffer, int bufferLen, bool justChecking)
{
	if (bufferLen < sizeof(bnd2Hdr_t))
	{
		return false;
	}
	bnd2Hdr_t *hdr = (bnd2Hdr_t *)fileBuffer;
	if (memcmp(hdr->id, "BND305I29V48", 12) &&
		memcmp(hdr->id, "BND305I3N51", 11))
	{
		return false;
	}

	if (justChecking)
	{
		return true;
	}

	int entrySize = (int)sizeof(bnd2Entry_t);
	bool noCompression = (!memcmp(hdr->id, "BND305I3N51", 11));
	if (noCompression)
	{ //last field does not exist
		entrySize -= 4;
	}

	bnd2Hdr_t leHdr = *hdr;
	LITTLE_BIG_SWAP(leHdr.numFiles);
	for (int i = 0; i < leHdr.numFiles; i++)
	{
		bnd2Entry_t e = *((bnd2Entry_t *)(fileBuffer + sizeof(bnd2Hdr_t) + i*entrySize));
		LITTLE_BIG_SWAP(e.unknownA);
		LITTLE_BIG_SWAP(e.fileSize);
		LITTLE_BIG_SWAP(e.fileOfs);
		LITTLE_BIG_SWAP(e.fileNum);
		LITTLE_BIG_SWAP(e.fnOfs);
		if (!noCompression)
		{
			LITTLE_BIG_SWAP(e.decompSize);
		}
		char *fileName = (char *)(fileBuffer + e.fnOfs);
		BYTE *fileData = fileBuffer + e.fileOfs;
		BYTE *decompData = NULL;
		if (!noCompression && e.decompSize > 0 && e.fileSize != e.decompSize)
		{
			decompData = (BYTE *)unpooled_malloc(e.decompSize, 221);
			int r = zlib_inflate(fileData, decompData, e.fileSize, e.decompSize);
			if (r != Z_OK)
			{
				unpooled_free(decompData);
				decompData = NULL;
			}
		}

		char fn[4096];
		sprintf(fn, "%s%s", g_outFileName, fileName);
		FILE *fw = fopen(fn, "wb");
		if (!fw)
		{
			MakeDirectoriesForPath(fn);
			fw = fopen(fn, "wb");
		}
		if (fw)
		{
			richprintf("Writing '%s'.\n", fn);
			if (decompData)
			{
				fwrite(decompData, 1, e.decompSize, fw);
				unpooled_free(decompData);
			}
			else
			{
				fwrite(fileData, 1, e.fileSize, fw);
			}
			fclose(fw);
		}
	}

	return true;
}

```

Edit: Tried out your uncompressed file and noticed it has a different header and different entry size (missing the decompSize), so I modified the code to handle those as well.
## Post #3
- Username: sleet01
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 16, 2010 8:42 am
- Post datetime: 2010-05-24T06:54:54+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

Great, I'll give this a shot!  Thanks, MrAdults!
## Post #4
- Username: sleet01
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 16, 2010 8:42 am
- Post datetime: 2010-05-25T08:25:16+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

I was able to use the struct and zlib modules in Python to read out the header information and decompress one entry.  I'll post a working script tomorrow, and hopefully a picture of a model in the next couple of days!  You really saved my bacon, MrAdults!
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-25T22:48:04+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

Good to hear.  I noticed that MDL4 spec you linked dictates that animation is done via vertex morphs, though. It would be totally nuts to animate models in a next-gen title exclusively with vertex morphs, at least one featuring mostly rigidly-weighted things like mechs. So I'm guessing "3D Gamestudio" has nothing to do with Chromehounds, or if it does, it must be a heavily modified format variant that is skeletal in nature. That whole 3D Gamestudio package sounds pretty fishy to me, their formats and storage methods are a little *too* Quake-like.
## Post #6
- Username: sleet01
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 16, 2010 8:42 am
- Post datetime: 2010-05-25T23:52:42+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

Yeah, I dug around in some of the MDL4 files and they're nothing like the 3DGameStudio format.  I'm also seeing some SMD files so these might be modified Source file formats, but it seems more likely From just whipped up their own formats and then named them MDL and SMD as a joke - in fact, a 2006 interview with Toshifumi Nabeshima reports: "The engine in Chromehounds is a combination of our own original engine and another one of our engines that we used in an RPG title."  I'll see what I can dig up there; maybe someone has already unlocked the file format under a different name.
## Post #7
- Username: sleet01
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 16, 2010 8:42 am
- Post datetime: 2010-05-26T08:15:55+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

No luck tracking down any more info on the model file formats.  I'll open up a new discussion in the 3D Models forum on that.
I didn't have time to clean up my python script tonight so I'll post it tomorrow in case anybody else runs across BND files.
## Post #8
- Username: sleet01
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 16, 2010 8:42 am
- Post datetime: 2010-05-28T08:18:42+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

unbnd.py is complete!  Not my cleanest code, but it handles both kinds of BND file (found to date) and has the option to extract to a subdir of the BND file's dir, or to a dir specified by the user.
Works on Linux or Windows.

EDIT: I typed too soon.  Apparently the object files for the mapdata has the "compressed" header but is uncompressed.  I'll figure out a way to determine that based on the actual distance to the filenames or something... tomorrow -_-.

EDIT: What the hey, it's already tomorrow.  Fixed the checkBNDType() function to check both the signature and the first entry's first two bytes to determine which type, compressed or uncompressed, we're dealing with.

```

import zlib
import sys
import os
from struct import *


# Check to see if the file actually exists
def fileExists(targetBND):
    return os.path.isfile(targetBND)

# Make the dump directory, essentially the BND file name minus suffix, alongside
# BND file.
def ensureDir(dirName):
    if not os.path.exists(dirName):
        os.makedirs(dirName)

# Determine BND type:
#   0: Not a known BND file
#   1: Compressed BND file type
#   2: Uncompressed BND file type
def checkBNDType(targetFileObject):

    targetFileObject.seek(0)
    signature=targetFileObject.read(12)

    if ("BND305I29V48"==signature or "BND305I3N51"==signature[0:-1]):
        signature=unpack(">B", targetFileObject.read(1))[0]
        if signature==228:
            return 1
        elif signature==224:
            return 2

    return 0

# Unpacks the file; decides whether to use ZLib decompression based on bndType
# (see chckBNDtype function)
def unpackBND(targetFileObject, dumpDir, bndType):

    targetFileObject.seek(0)
    bndHeader = unpack(">12s5i",targetFileObject.read(32))
    bndEntries=[]

    if bndType==1:
        for entry in range(bndHeader[2]):
            bndEntries.append(unpack(">6I", targetFileObject.read(24)))
    else:
        for entry in range(bndHeader[2]):
            bndEntries.append(unpack(">5I", targetFileObject.read(20)))

    # We currently don't use all the fields, but extract them for clarity
    for i in bndEntries:
        
        fileSize=i[1]
        fileOfs=i[2]
        fileNum=i[3]
        fnOfs=i[4]
        if bndType==1:
            decompSize=i[5]

        targetFileObject.seek(fnOfs)

# Over-read the file name but split off the part before the first null char
        fName=unpack(">21s",targetFileObject.read(21))[0].split('\x00')[0]
        
        targetFileObject.seek(fileOfs)
        print "Writing file", fName, "to", dumpDir, "in path", dumpDir+'/'+fName
        entryFile=open(dumpDir+'/'+fName, "wb")
        if bndType==1:
            entryFile.write(zlib.decompress(targetFileObject.read(fileSize)))
        else:
            entryFile.write(targetFileObject.read(fileSize))
            
        entryFile.close()

def main():

    try:
        fileName = sys.argv[1]
    except:
        print """
Usage: [python] ./unbnd.py file.bnd [optional_output_path]

        Example: './unbnd.py ~/chromehounds/parts/CK_CC032.bnd'
            Writes all files in CK_CC032.bnd into ~/chromehounds/parts/CK_CC032/

        Example: 'python ./unbnd.py boot/Sfx/sfx_mdl.bnd ~/chrome_models/'
            Writes all files in sfx_mdl.bnd to ~/chrome_models/sfx_mdl/
            """
        sys.exit(1)

    if fileExists(fileName):
        
        try:
            outPath = sys.argv[2]
            dumpDir = outPath+fileName[0:-4].split('/')[-1]
        except:
            dumpDir = fileName[0:-4]

        ensureDir(dumpDir)

        bndFile = open(fileName, "rb")
        bndType=checkBNDType(bndFile)
        print "File is type", bndType
        
        if bndType==0:
            print "File", fileName, "is not a recognized BND format."
            sys.exit(1)
        else:
            unpackBND(bndFile, dumpDir, bndType)
            sys.exit(0)
    
    else:
        print "File", fileName, "does not exist."
        sys.exit(1)

if __name__ == "__main__":
    main()

```
## Post #9
- Username: sleet01
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 16, 2010 8:42 am
- Post datetime: 2010-05-28T18:48:01+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

Actually, MrAdults, would you be willing to post some of those AC3 Portable files (I'm assuming it was AC3 Portable) so I can see what other BND formats From has released?  I can probably modify my script to handle them all.
## Post #10
- Username: Acewell
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-28T22:39:51+00:00
- Post Title: Chromehounds .bnd archive / compressed package format

I'm afraid the data is long gone (from my hard drive), but I can show you the code to extract them. It's a very simple format.

```
{
	BYTE		id[4];
	int			unknownA;
	int			unknownB;
	int			unknownC;
	int			numFiles;

	int			moreUnknown[4];
} bndBinHdr_t;

typedef struct bndBinEntry_s
{
	int			dataOfs;
	int			dataSize;
	int			fnOfs;
	int			fileNum;
} bndBinEntry_t;

//armored core shit
bool IsBNDFAT(BYTE *fileBuffer, int bufferLen, bool justChecking)
{
	if (bufferLen <= sizeof(bndBinHdr_t))
	{
		return false;
	}

	BYTE *bndMem = fileBuffer;
	bndBinHdr_t *binHdr = (bndBinHdr_t *)bndMem;
	if (binHdr->id[0] != 'B' ||
		binHdr->id[1] != 'N' ||
		binHdr->id[2] != 'D' ||
		binHdr->id[3] != 0)
	{
		return false;
	}
	if (binHdr->numFiles < 0 || (binHdr->numFiles*(int)sizeof(bndBinEntry_t)) > bufferLen)
	{
		return false;
	}

	if (justChecking)
	{
		return true;
	}

	richprintf("Processing BND bundle.\n");

	bndBinEntry_t *entries = (bndBinEntry_t *)(binHdr+1);
	for (int i = 0; i < binHdr->numFiles; i++)
	{
		bndBinEntry_t *e = entries+i;
		char *fn = (char *)(bndMem+e->fnOfs);
		BYTE *data = bndMem+e->dataOfs;

		char filterFn[4096];
		int j;
		for (j = 0; fn[j]; j++)
		{
			if (fn[j] == ':' || fn[j] == '/' || fn[j] == '\\')
			{
				filterFn[j] = '_';
			}
			else
			{
				filterFn[j] = fn[j];
			}
		}
		filterFn[j] = 0;

		char finalFN[4096];
		sprintf(finalFN, "%s_%s", g_outFileName, filterFn);
		if (e->dataSize > 0)
		{
			FILE *f = fopen(finalFN, "wb");
			if (f)
			{
				richprintf("Writing '%s'.\n", finalFN);
				fwrite(data, 1, e->dataSize, f);
				fclose(f);
			}
		}

	}

	return true;
}

```

(excuse the mess with the file name, it's old code)

That game also had .fat files which I assumed initially had the, well, FAT. But they turned out to be worthless, because all the data one could need is in the BND already. Seemed like the file index was stored similarly in them too, so I don't know what the point was. I might've just overlooked some data in them that stored offsets in a binary tree for fast lookup or something, been a long time so I don't remember too well.

Oh, and if scripts are your thing, you might find it even more worthwhile to look into writing a quickbms script for these formats. I would do it myself, too, but I've been very lazy about adjusting to quickbms syntax (enough to make it a more productive use of my time than writing out C code).
