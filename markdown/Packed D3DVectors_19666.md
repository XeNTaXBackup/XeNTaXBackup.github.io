## Post #1
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2019-03-16T14:32:36+00:00
- Post Title: Packed D3DVectors

Hello
I have some format of anims, where position floats are packed in '16 bit' :

Frames: [X, Y, Z]

```
[0x0, 0x0, 0xC91B] [0x0, 0x0, 0xCA16] [0x0, 0x0, 0xCAE3] [0x0, 0x0, 0xCB6E] [0x0, 0x0, 0xCBA1] ...
```


Source floats is known, and it's:

```
[0.0, 0.0, 334.667] [0.0, 0.0, 399.000] [0.0, 0.0, 451.556] [0.0, 0.0, 487.000] [0.0, 0.0, 500.000] ...
```


The question is - how to translate back 'int16' to floats? Get back 500.0f from 0xCBA1(or -13407).

Part of pseudocode from engine:

```
{
  unsigned __int16 v3; // di
  unsigned int v4; // esi
  unsigned int v5; // edx
  int v6; // edx
  int v7; // eax
  unsigned __int16 v8; // bx
  unsigned int v9; // edi
  unsigned int v10; // esi
  int v11; // esi
  int v12; // edx
  unsigned int v13; // edi
  unsigned int v14; // esi
  int v15; // esi

  v3 = LOWORD(result->y);
  v4 = ((unsigned int)v3 >> 10) & 0x1F;
  v5 = v3 & 0x3FF;
  if ( (signed int)(10 - v4) <= 0 )
    v6 = v5 << (v4 - 10);
  else
    v6 = v5 >> (10 - v4);
  v7 = v6;
  if ( v4 )
    v7 = (1 << v4) | v6;
  if ( LOWORD(result->y) & 0x8000 )
    v7 = -v7;
  v8 = HIWORD(result->x);
  v9 = ((unsigned int)v8 >> 10) & 0x1F;
  v10 = v8 & 0x3FF;
  if ( (signed int)(10 - v9) <= 0 )
    v11 = v10 << (v9 - 10);
  else
    v11 = v10 >> (10 - v9);
  v12 = v11;
  if ( v9 )
    v12 = (1 << v9) | v11;
  if ( (v8 & 0x8000u) != 0 )
    v12 = -v12;
  v13 = ((unsigned int)LOWORD(result->coord[0]) >> 10) & 0x1F;
  v14 = LOWORD(result->coord[0]) & 0x3FF;
  if ( (signed int)(10 - v13) <= 0 )
    v15 = v14 << (v13 - 10);
  else
    v15 = v14 >> (10 - v13);
  if ( v13 )
    v15 |= 1 << v13;
  if ( ((LOWORD(result->coord[0]) >> 8) & 0x80u) != 0 )
    v15 = -v15;
  *a3 = (float)v15 * 0.001;
  a3[1] = (float)v12 * 0.001;
  a3[2] = (float)v7 * 0.001;
  return (T3DVECTOR *)a3;
}
```
