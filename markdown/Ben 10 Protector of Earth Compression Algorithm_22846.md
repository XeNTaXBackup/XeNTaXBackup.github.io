## Post #1
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2020-10-16T23:21:15+00:00
- Post Title: Ben 10 Protector of Earth Compression Algorithm

If anyone is still interested in this game i found the compression algorithm in the game code i just dont know how to reverse it. This game doesnt use encryption by the way
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-17T01:45:29+00:00
- Post Title: Ben 10 Protector of Earth Compression Algorithm

> i found the compression algorithm in the game code
Oh, can you share with us?
## Post #3
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2020-10-17T06:03:41+00:00
- Post Title: Ben 10 Protector of Earth Compression Algorithm

open up ida or ghidra or ida and go to address 1973E8 and that is the decompression routine if you set a break point on pcsx2 debugger at that address you can literally see the game decompressing the .wad file in your face
## Post #4
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2021-01-26T00:12:20+00:00
- Post Title: Ben 10 Protector of Earth Compression Algorithm

If anyone is still interested in unpacking the compressed .wal file for ben 10 protector of earth this is the decompression routine as im not very good at reversing so maybe someone can give this a look and reverse it themselves i guess

```

{
  undefined *puVar1;
  byte bVar2;
  byte bVar3;
  int iVar4;
  uint uVar5;
  bool bVar6;
  int iVar7;
  byte *pbVar8;
  byte *pbVar9;
  byte *pbVar10;
  byte *pbVar11;
  int iVar12;
  undefined auStack80 [16];
  byte *pbStack64;
  byte *pbStack60;
  undefined auStack48 [16];
  
  pbVar9 = *(byte **)(param_1 + 0x44);
  iVar12 = *(int *)(param_1 + 4) - (int)(pbVar9 + -0x10000);
  iVar7 = iVar12 + -0x41;
  if (*(int *)(param_1 + 0x3c) <= iVar12) {
    iVar7 = *(int *)(param_1 + 0x3c);
  }
  pbVar11 = pbVar9 + iVar7;
  pbVar10 = *(byte **)(param_1 + 0x40);
  if (pbVar9 < pbVar11) {
    bVar2 = *pbVar9;
    while( true ) {
      bVar3 = *pbVar9;
      if ((char)bVar2 < '\0') {
        pbVar8 = pbVar9 + 1;
        pbVar9 = pbVar9 + 2;
        iVar7 = ((*pbVar8 & 0xf) + 1) * 0x10000;
        pbVar8 = pbVar10 + ((int)((uint)CONCAT11(bVar3,*pbVar8) << 0x10) >> 0x14) + -1;
        do {
          iVar7 = iVar7 + -0x10000;
          bVar2 = *pbVar8;
          pbVar8 = pbVar8 + 1;
          *pbVar10 = bVar2;
          pbVar10 = pbVar10 + 1;
        } while (-1 < iVar7);
        bVar6 = pbVar9 < pbVar11;
      }
      else {
        iVar7 = (char)bVar2 * 0x1000000;
        if ((char)bVar2 < '@') {
          pbVar9 = pbVar9 + 1;
          do {
            iVar7 = iVar7 + -0x1000000;
            bVar2 = *pbVar9;
            pbVar9 = pbVar9 + 1;
            *pbVar10 = bVar2;
            pbVar10 = pbVar10 + 1;
          } while (-1 < iVar7);
          bVar6 = pbVar9 < pbVar11;
        }
        else {
          bVar2 = pbVar9[1];
          iVar7 = (bVar3 - 0x3e) * 0x1000000;
          pbVar9 = pbVar9 + 2;
          do {
            iVar7 = iVar7 + -0x1000000;
            *pbVar10 = bVar2;
            pbVar10 = pbVar10 + 1;
          } while (0 < iVar7 >> 0x18);
          bVar6 = pbVar9 < pbVar11;
        }
      }
      if (!bVar6) break;
      bVar2 = *pbVar9;
    }
  }
  puVar1 = auStack48 + 7;
  uVar5 = (uint)puVar1 & 7;
  *(ulong *)(puVar1 + -uVar5) =
       *(ulong *)(puVar1 + -uVar5) & -1 << (uVar5 + 1) * 8 |
       CONCAT44(pbVar10,pbVar9) >> (7 - uVar5) * 8;
  auStack48._0_8_ = CONCAT44(pbVar10,pbVar9);
  iVar7 = *(int *)(param_1 + 0x3c);
  iVar4 = *(int *)(param_1 + 0x44);
  pbStack64 = pbVar9;
  pbStack60 = pbVar10;
  auStack80._0_8_ = CONCAT44(pbVar10,pbVar9);
  puVar1 = auStack80 + 7;
  uVar5 = (uint)puVar1 & 7;
  *(ulong *)(puVar1 + -uVar5) =
       *(ulong *)(puVar1 + -uVar5) & -1 << (uVar5 + 1) * 8 | auStack80._0_8_ >> (7 - uVar5) * 8;
  pbVar9 = pbVar9 + -iVar4;
  iVar7 = iVar7 - (int)pbVar9;
  iVar12 = iVar12 - (int)pbVar9;
  *(byte **)(param_1 + 0x40) = pbVar10;
  *(int *)(param_1 + 0x3c) = iVar7;
  if (iVar7 == 0) {
    pbVar9 = pbVar9 + iVar4;
  }
  else {
    if (iVar12 != 0) {
      FUN_001f927c(*(int *)(param_1 + 4) - iVar12,pbVar9 + iVar4,iVar12);
    }
    pbVar9 = (byte *)(*(int *)(param_1 + 4) - iVar12);
  }
  *(byte **)(param_1 + 0x44) = pbVar9;
  return;
}


```
## Post #5
- Username: sameidandpw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 29, 2020 8:27 pm
- Post datetime: 2023-10-14T07:25:33+00:00
- Post Title: Ben 10 Protector of Earth Compression Algorithm

> Reply from theclub654 ↑Tue Jan 26, 2021 8:12 am at Tue Jan 26, 2021 8:12 am
>
> 

Any updates? I was trying to decompress the GAME.WAD file.
