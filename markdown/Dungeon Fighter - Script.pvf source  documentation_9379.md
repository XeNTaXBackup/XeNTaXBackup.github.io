## Post #1
- Username: Fiel
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Dec 17, 2007 1:29 am
- Post datetime: 2012-08-01T00:22:27+00:00
- Post Title: Dungeon Fighter - Script.pvf source / documentation

Introduction
Script.pvf is a file which contains all of the client-side information for DFO. In this thread I'll cover every single little thing I know regarding the format and how to read it. This thread will contain source code and documentation regarding how to parse and unpack script.pvf.

THIS DOCUMENTATION DOES NOT CONTAIN HOW TO REPACK THE GAME OR HOW TO CREATE A REPACKER.

Purpose
There's one part of the decryption procedure that I'm stuck on and can't figure it out. Since I can't figure it out, I thought I would engage the community in figuring it out.

Script.pvf

```
{
    int sizeGUID; //Always 0x24
    char GUID[sizeGUID]
    int fileVersion
    int dirTreeLength;
    int dirTreeChecksum;
    int numFilesInDirTree;
}

```


From here, read header.dirTreeLength number of bytes. This is the encrypted directory tree. Then, perform the following procedure on the directory tree:

```
{
	int each32bit;
	int i;

	for(i = 0; i < lengthOfBlock; i += 4)
	{
		//Decryption procedure

		// mov  eax, [ecx]
		each32bit = *((unsigned int*) fileBlock);

		// xor  eax, ebx
		each32bit = each32bit ^ decryptionKey;

		// mov  edx, eax
		// shl  edx, 1Ah
		// shr  eax, 6
		// or   eax, edx
		each32bit = _rotl(each32bit, 0x1A);

		// mov  [ecx], eax
		memcpy(fileBlock, &each32bit, 4);

		// add  ecx, 4
		fileBlock += 4;
	}
}

```


The third argument (decryptionKey) is header.dirTreeChecksum.

Now you have the decrypted directory tree. The decrypted directory tree contains header.numFiles number of files.

```
	int fileNumber;
	int filePathLength;
	char filePath[filePathLength];
	int fileLength;
	int fileChecksum;
	int relativeOffset;
}

```


After reading one file, use fileInDirTree.relativeOffset to jump to the relevant file.

The file is 32-bit aligned so it will work with the DecryptBlock function above. However, fileInDirTree.fileLength shows the actual length of the file, not the 32-bit aligned length. Use the following to calculate the byte-aligned length:

```
	{
		fileInDirTree.byteAlignedLength = ((fileInDirTree.fileLength / 4) + 1) * 4;
	}
	else
	{
		fileInDirTree.byteAlignedLength = fileInDirTree.fileLength;
	}

```


Read fileInDirTree.byteAlignedLength number of bytes. Then send the file to the DecryptBlock function with fileInDirTree.byteAlignedLength as the second argument and fileInDirTree.fileChecksum as the third argument. After the block is decrypted, take fileInDirTree.fileLength bytes from the buffer and write that to the hard drive given by location fileInDirTree.filePath. Then jump back to the directory tree and read another file. Wash, rinse, repeat.

Checksums
Calculating the checksum is shown in PVFChecksum within Checksum.c. I have copied there the assembly instructions which were used to calculate the checksums for these files. To this day I have not managed to write a higher level version. For the directory tree checksum I believe you pass in header.fileVersion and header.dirTreeLength. I don't remember which variables go where, though, as I was unable to fully determine how it worked. The translated assembly has been tested and it is functional.

The version which my unpacker cannot unpack
There are two different encryptions used for Script.pvf of which this unpacker can only do one of them. It's very easy to tell the difference between the versions. Open up Script.pvf in a hex editor. If a Microsoft GUID is human-readable at offset 0x04, then this unpacker will be able to decrypt the file. If there is no Microsoft-GUID present (it's random bytes), then this is a version that this unpacker cannot do.

Here is everything I know about this other encryption:
- It uses AES-128-CBC to write over the file header and directory tree. The AES-128-CBC cipher does NOT apply to the individual files in the Script.pvf archive. The individual files still use the _rotl + xor algorithm.
- The AES-128-CBC cipher is populated by an MD5 hash of a computed string.
- The AES-128-CBC cipher is used from the Botan cryptographic library which is open-source - [Botan: Class List](http://botan.randombit.net/doxygen/annotated.html)
- Other than the AES-128-CBC encryption on the file header and directory tree, all other reading mechanisms and such discussed here are still present. This was obvious to me when I looked at the assembly in the EXE file.
- The header is padded to be 64-bytes long to be 16-byte aligned with the AES block cipher. I assume that the 64-byte header also contains the length of the directory tree to decrypt the rest of the tree.
- I think it uses a constant encryption - it's not dynamic. From what I saw, it took a string "foealg" and then used an MD5 hash on the string, then fed that into the AES-128 CBC cipher. I tried this and it didn't work. I didn't get too far in figuring out the new encryption

If you're using Nexon America's Dungeon Fighter

In this case, the checksums are encrypted. There is a secret, constant key that all checksums (header.checksum and dirFile.checksum) are XORed by. Unfortunately, to figure out what the key is requires a little bit of legwork. There is currently no known way to generate the key without performing cryptanalysis.

The way to defeat the checksum encryption is to use a KPA ([Known-plaintext attack - Wikipedia, the free encyclopedia](http://en.wikipedia.org/wiki/Known-plaintext_attack)). As part of the file format, you know that after the directory tree there are two INTs. The second INT is dirFile.pathLength. Nexon utilizes Windows as a development platform, so the maximum value that dirFile.pathLength can be is MAX_PATH (260). Therefore, the second INT must be less than 260, and there exists a high probability that this INT is between the values of 25 - 75.

So, it's time to generate possible keys using this knowledge. To generate a candidate key, we use the inverse of the DecryptBlock function on a possible length using the encrypted value of dirFile.pathLength as the key.

```
{
  unsigned int encryptionKey;
  
  encryptionKey = _rotr(pathLength, 0x1A);
  encryptionKey ^= encryptedPathLength;

  return encryptionKey;
}

```


With the candidate key this function returns, XOR the header.checksum and then decrypt the rest of the dirTree. View the result in a hex editor to see if the strings are garbled in any way. If the strings are not garbled, then you have found the candidate key.

Take the candidate key and XOR it against header.checksum and dirFile.checksum before sending the checksum as the decryptionKey parameter in the DecryptBlock function. Tada! The encryption is now cracked.

ScriptPVF.exe
Source Code: [http://www.sendspace.com/file/uega0s](http://www.sendspace.com/file/uega0s)

I will be honest. I haven't touched this code in a LONG time. So there could be random snippets of code that don't work or really shoddy programming. I don't know. But it's all in there - everything you need - which includes an executable.

The ScriptPVF.exe executable only looks for a file called "Script.pvf". So make sure that's in the same directory.

CDnF.pvf uses the OLD encryption, so it should work without a hassle with ScriptPVF.exe.
DFO.pvf uses a NEWER encryption with encrypted checksums (see above), so ScriptPVF will fail if you try to read it. You'll have to do the legwork and change the appropriate part of the code to make it decrypt properly.

If you want to know how to parse the unpacked files, I've already started this for you. Check out here --> [http://www.southperry.net/showthread.php?t=43626](http://www.southperry.net/showthread.php?t=43626)
## Post #2
- Username: bellonna
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 29, 2016 10:10 pm
- Post datetime: 2016-07-14T13:18:55+00:00
- Post Title: Dungeon Fighter - Script.pvf source / documentation

CDnF.pvf uses the OLD encryption, so it should work without a hassle with ScriptPVF.exe.
DFO.pvf uses a NEWER encryption with encrypted checksums (see above), so ScriptPVF will fail if you try to read it. You'll have to do the legwork and change the appropriate part of the code to make it decrypt properly.

PVFEditor is NEW encryption decrypt complete.
Download file: [https://drive.google.com/file/d/0B-FBbg ... sp=sharing](https://drive.google.com/file/d/0B-FBbgCqrGTIcThtWVFlSmVIN3c/view?usp=sharing)

PVFEditor.exe Decompile C++ Source code please.
