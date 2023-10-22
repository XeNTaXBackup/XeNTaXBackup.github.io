## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-17T17:02:22+00:00
- Post Title: C# type to C++

I'm rly bad know Sharp but maybe someone can explain what this?

```
private uint[][] pTransparent;
```


It's something like this ?

```
DWORD ** pTransparent
```
 or 
```
DWORD ** pTransparent []
```


?
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-06-18T08:59:17+00:00
- Post Title: C# type to C++

```
private uint[][] pTransparent;
```

This is called jagged arrays in c#. (array of arrays)

And afaik this can be set up to function like jagged arrays.

```
DWORD ** pTransparent
```
 

or you can use a 2d array in c++.

```
uint[5][] pTransparent;
```
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-18T20:56:57+00:00
- Post Title: C# type to C++

Thanks I figured out

```
unsigned int pT2[] = { 0, 0, 0, 0 };
static unsigned int *pTransparent[2] = { *pT1, *pT2, };
```


It works!
