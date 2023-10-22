## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-01T09:46:38+00:00
- Post Title: Rift (*.Assets)

With version 1.9+ format changed. I try make unpacker but have some problems. Here description assets format:

```
{
   DWORD dwID;  // TWAD
   DWORD dwVersion;
   DWORD dwHeaderSize;  // 20
   DWORD dwMaxFiles;  // Maximum number of files that can be stored in the archive > 1489
   DWORD dwTotalFiles;
};
```


```
{
   DWORD dwIDMask1;
   DWORD dwIDMask2;
   DWORD dwOffset;
   DWORD dwZSize1;
   DWORD dwZSize2;
   WORD wFileNum;
   WORD wFlag;  // 1 - Compressed , 0 - not compressed
   BYTE pSHA1Hash[20];
};
```


Ok. ID mask's used for search entry in manifest - it contains real file size and file name hash (used FNV1a). 

Here description for manifest. 

```
{
   DWORD dwID;  // TWAM
   DWORD dwUnknown1;
   DWORD dwUnknown2;
   DWORD dwUnknown3;
   DWORD dwUnknown4;
   DWORD dwUnknown5;
   DWORD dwUnknown6;
   DWORD dwUnknown7;
   DWORD dwTableOffset;  // Table offset with ID mask, real file size and file name hash
   DWORD dwUnknown9;
   DWORD dwEntriesCount;
};
```


```
{
   DWORD dwIDMask1;  // Same ID from AssetsEntry
   DWORD dwIDMask2;  // Same ID from AssetsEntry
   DWORD dwFileNameHash;  //FNV1a
   DWORD dwSize1;
   DWORD dwSize2;
   DWORD dwUnknown2;
   DWORD dwUnknown3;
   BYTE pSHA1Hash[20];
   DWORD dwNulls;
};
```


Manifest does not contain info about num's assets. I read each Assets entry and compare ID's with Manifest entry for search real size and real hash, it works but this is a very long time. 200 entres processed by 20min+   

Pascal code

```
    begin
        pAssetFile.Read(pAssetsEntry.dwIDMask1, 4);
        pAssetFile.Read(pAssetsEntry.dwIDMask2, 4);
        pAssetFile.Read(pAssetsEntry.dwOffset, 4);
        pAssetFile.Read(pAssetsEntry.dwZSize1, 4);
        pAssetFile.Read(pAssetsEntry.dwZSize2, 4);
        pAssetFile.Read(pAssetsEntry.wFileNum, 2);
        pAssetFile.Read(pAssetsEntry.wFlag, 2);
        pAssetFile.Read(pAssetsEntry.dwSHA1Hash, 20);

      repeat
        pManifestFile.Read(pAssetsManifestEntry.dwIDMask1, 4);
        pManifestFile.Read(pAssetsManifestEntry.dwIDMask2, 4);
        pManifestFile.Read(pAssetsManifestEntry.dwFileNameHash, 4);
        pManifestFile.Read(pAssetsManifestEntry.dwUnknown1, 4);
        pManifestFile.Read(pAssetsManifestEntry.dwZSize, 4);
        pManifestFile.Read(pAssetsManifestEntry.dwSize, 4);
        pManifestFile.Read(pAssetsManifestEntry.dwUnknown2, 4);
        pManifestFile.Read(pAssetsManifestEntry.dwUnknown3, 4);
        pManifestFile.Read(pAssetsManifestEntry.dwSHA1Hash, 20);
        pManifestFile.Read(pAssetsManifestEntry.dwNulls, 4);

      until (pAssetsEntry.dwIDMask1 = pAssetsManifestEntry.dwIDMask1) and (pAssetsEntry.dwIDMask2 = pAssetsManifestEntry.dwIDMask2);
   end;

```

[here](http://www.sendspace.com/file/thqlkz) manifest and some assets. Maybe someone knows how to make it easier?  

Edited1: One more hint: Entres in manifest can be repeated, if pAssetsManifestEntry.dwUnknown1 = 0 file moved in other archive or deleted
