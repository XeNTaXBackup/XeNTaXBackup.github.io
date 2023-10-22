## Post #1
- Username: GDL
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-04-28T17:53:12+00:00
- Post Title: Reverse simple decryption.

We will look at the game Valkyrie Crusade.
ID com.nubee.valkyriecrusade
we look at the games files and they are engrypted.


So 1st step is load it up in IDA pro or ghidra.
This is a custom game engine so a good place to start is with a file open instruction
if we search for that we find nb::File::openRead.

```
/* nb::File::openRead(char const*, unsigned int*, nb::Drive::Base, nb::File::Filter) */

void * nb::File::openRead(char *param_1,uint *param_2,Base param_3,Filter param_4)

{
  void *pvVar1;
  int iVar2;
  void *__ptr;
  void *local_50;
  Info aIStack76 [8];
  void *local_44;
  File aFStack64 [8];
  int local_38;
  void *local_34;
  
  local_50 = (void *)0x0;
  File(aFStack64);
  open(aFStack64,param_1,1,param_3);
  if (local_38 == 0) {
    __ptr = (void *)0x0;
  }
  else {
    local_50 = local_34;
    pvVar1 = malloc((size_t)local_34);
    if (pvVar1 == (void *)0x0) {
      iVar2 = Compress::getInfo((void *)0x0,(uint)local_34,aIStack76);
    }
    else {
      read(aFStack64,pvVar1,(uint)local_34);
      iVar2 = Compress::getInfo(pvVar1,(uint)local_50,aIStack76);
    }
    __ptr = pvVar1;
    if (iVar2 != 0) {
      __ptr = (void *)Compress::uncompress(aIStack76);
      local_50 = local_44;
      free(pvVar1);
    }
    if ((param_4 == 1) || ((param_4 == 2 && (iVar2 = Coder::isCode(__ptr), iVar2 != 0)))) {
      pvVar1 = (void *)Coder::decode(__ptr,(uint)local_50,(uint *)&local_50);
      free(__ptr);
      __ptr = pvVar1;
      if (pvVar1 == (void *)0x0) {
        local_50 = pvVar1;
      }
    }
  }
  if (param_2 != (uint *)0x0) {
    *param_2 = (uint)local_50;
  }
  ~File(aFStack64);
  return __ptr;
}

```


So if we look at this we notice something interesting.

```
pvVar1 = (void *)Coder::decode(__ptr,(uint)local_50,(uint *)&local_50);
```


So in our decompiler lets look at Coder::decode function.

```
/* nb::Coder::decode(void const*, unsigned int, unsigned int*) */

int * nb::Coder::decode(void *param_1,uint param_2,uint *param_3)

{
  uint *puVar1;
  int iVar2;
  uint uVar3;
  uint __size;
  uint *__src;
  int *piVar4;
  uint uVar5;
  int *local_2c;
  
  iVar2 = isCode(param_1);
  if (iVar2 == 0) {
    return (int *)0x0;
  }
  __size = param_2 - 0x10;
  local_2c = (int *)malloc(__size);
  __src = (uint *)((int)param_1 + 0x10);
  memcpy(local_2c,__src,__size);
  iVar2 = *(int *)((int)param_1 + 0xc);
  uVar3 = 4;
  if (3 < __size) {
    uVar5 = (param_2 - 0x11) * 0x8000000 >> 0x1d;
    piVar4 = local_2c;
    if (uVar5 != 0) {
      *local_2c = (*__src ^ 0x45af6e5d) - iVar2;
      piVar4 = local_2c + 1;
      __src = (uint *)((int)param_1 + 0x14);
      if ((__size < 5) || (uVar3 = 8, __size < 8)) goto LAB_005fe4fe;
      if (uVar5 != 1) {
        if (uVar5 != 2) {
          if (uVar5 != 3) {
            if (uVar5 != 4) {
              if (uVar5 != 5) {
                if (uVar5 != 6) {
                  uVar5 = *__src;
                  __src = (uint *)((int)param_1 + 0x18);
                  uVar3 = 0xc;
                  *piVar4 = (uVar5 ^ 0x45af6e5d) - iVar2;
                  piVar4 = local_2c + 2;
                  if (__size < 0xc) goto LAB_005fe4fe;
                }
                uVar5 = *__src;
                __src = __src + 1;
                uVar3 = uVar3 + 4;
                *piVar4 = (uVar5 ^ 0x45af6e5d) - iVar2;
                piVar4 = piVar4 + 1;
                if (__size < uVar3) goto LAB_005fe4fe;
              }
              uVar5 = *__src;
              __src = __src + 1;
              uVar3 = uVar3 + 4;
              *piVar4 = (uVar5 ^ 0x45af6e5d) - iVar2;
              piVar4 = piVar4 + 1;
              if (__size < uVar3) goto LAB_005fe4fe;
            }
            uVar5 = *__src;
            __src = __src + 1;
            uVar3 = uVar3 + 4;
            *piVar4 = (uVar5 ^ 0x45af6e5d) - iVar2;
            piVar4 = piVar4 + 1;
            if (__size < uVar3) goto LAB_005fe4fe;
          }
          uVar5 = *__src;
          __src = __src + 1;
          uVar3 = uVar3 + 4;
          *piVar4 = (uVar5 ^ 0x45af6e5d) - iVar2;
          piVar4 = piVar4 + 1;
          if (__size < uVar3) goto LAB_005fe4fe;
        }
        uVar5 = *__src;
        __src = __src + 1;
        uVar3 = uVar3 + 4;
        *piVar4 = (uVar5 ^ 0x45af6e5d) - iVar2;
        piVar4 = piVar4 + 1;
        if (__size < uVar3) goto LAB_005fe4fe;
      }
    }
    do {
      *piVar4 = (*__src ^ 0x45af6e5d) - iVar2;
      if (((((__size <= uVar3) || (__size < uVar3 + 4)) ||
           (piVar4[1] = (__src[1] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 8)) ||
          ((piVar4[2] = (__src[2] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0xc ||
           (piVar4[3] = (__src[3] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0x10)))) ||
         ((piVar4[4] = (__src[4] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0x14 ||
          ((piVar4[5] = (__src[5] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0x18 ||
           (piVar4[6] = (__src[6] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0x1c)))))) break;
      puVar1 = __src + 7;
      uVar3 = uVar3 + 0x20;
      __src = __src + 8;
      piVar4[7] = (*puVar1 ^ 0x45af6e5d) - iVar2;
      piVar4 = piVar4 + 8;
    } while (uVar3 <= __size);
  }
LAB_005fe4fe:
  iVar2 = makeCheckSum((uchar *)local_2c,__size);
  if (*(int *)((int)param_1 + 8) != iVar2) {
    free(local_2c);
    local_2c = (int *)0x0;
    __size = 0;
  }
  if (param_3 != (uint *)0x0) {
    *param_3 = __size;
  }
  return local_2c;
}

```


This look very long and complicated but its not too bad if we break it down.

The start

```
  if (iVar2 == 0) {
    return (int *)0x0;
  }
```

the isCode function checks for the valid file header.

So as we can see its checking if it starts with CODE
then 0x100 as a short.

```
43 4F 44 45 00 01
```


Then the next few variables are defined

```
  __size = param_2 - 0x10;
```
 - sets __size to file size - 16

```
  local_2c = (int *)malloc(__size);
```
 - creates a buffer with the size of __size

```
  __src = (uint *)((int)param_1 + 0x10);
```
 sets __src to the input file starting at offset 16

```
  memcpy(local_2c,__src,__size);
```
 copies __src into local_2c buffer

```
iVar2 = *(int *)((int)param_1 + 0xc);
```
 read an int from offset 0xC in the file

We can skip all the checks in the middle for file size and just go do the actual decryption portion.

```
      *piVar4 = (*__src ^ 0x45af6e5d) - iVar2;
      if (((((__size <= uVar3) || (__size < uVar3 + 4)) ||
           (piVar4[1] = (__src[1] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 8)) ||
          ((piVar4[2] = (__src[2] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0xc ||
           (piVar4[3] = (__src[3] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0x10)))) ||
         ((piVar4[4] = (__src[4] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0x14 ||
          ((piVar4[5] = (__src[5] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0x18 ||
           (piVar4[6] = (__src[6] ^ 0x45af6e5d) - iVar2, __size < uVar3 + 0x1c)))))) break;
      puVar1 = __src + 7;
      uVar3 = uVar3 + 0x20;
      __src = __src + 8;
      piVar4[7] = (*puVar1 ^ 0x45af6e5d) - iVar2;
      piVar4 = piVar4 + 8;
    } while (uVar3 <= __size);
```

This can be simplified down all this code is doing is xoring 4 bytes with 0x45af6e5d then subtracting the seed value iVar2
from the result the program is just doing it 0x20 bytes at a time but we can just do it 4 bytes at a time.
so we only need

> *piVar4 = (*__src ^ 0x45af6e5d) - iVar2;
which is basically

```
buffer[i] = (buffer[i] ^ secretKey) - seed;
```


working bms script to show the code in action.
[viewtopic.php?f=10&t=23806](https://forum.xentax.com/viewtopic.php?f=10&t=23806)

The file header is.
magic 4 : CODE
short 0x100
short 0x7755
u32 CRC32
u32 random seed & 0xFFFF

(obtained with encrypt function that is also in the executable)

```
  *puVar1 = 0x45444f43;
  *(undefined2 *)((int)puVar1 + 6) = 0x7755;
  *(undefined2 *)(puVar1 + 1) = 0x100;
  __dest = puVar1 + 4;
  memcpy(__dest,param_1,param_2);
  lVar2 = lrand48();
  __aeabi_idivmod(lVar2,0xffff);

```

[18.zip](https://xentaxbackup.github.io/file/19975_18.zip)
## Post #2
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2021-06-15T22:12:30+00:00
- Post Title: Reverse simple decryption.

...Try to find and learn some basic stuff before asking. I'm get stuck with "start is with a file open instruction". Don't know how to able to display and read function in Ghidra or IDA properly. Sorry I'm very noobs at this, but want to learn it

> All function just undefined.

> This have more than 008231b3...why attachment 18.enc file end with 000635ac?

.
## Post #3
- Username: UuPhan
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-06-18T03:07:47+00:00
- Post Title: Reverse simple decryption.

just type open in the filter on the left under symbol tree.

008231AC is just a placeholder value used to reference a file in memory not a size.
