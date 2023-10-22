## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-03-07T15:02:58+00:00
- Post Title: Empire: Total War .PACK archives

Support would be cool, here's the format:

```
uint uk;
uint uk2;
uint uk3;
uint numFiles;
uint uk5;

struct Entry
{
    uint size;
    string name;
} directory[numFiles]<optimize=false>;
```
## Post #2
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-03-08T11:22:44+00:00
- Post Title: Empire: Total War .PACK archives

Nice find, but are you sure that you cant find that unknown dwords ?:P did you tested if game works with unpacked archives ?:P if not then these values may be important for rebuilding archives 

Maybe I can help and make unpacked if somebody will send me some archive examples
## Post #3
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2009-03-12T05:41:19+00:00
- Post Title: Empire: Total War .PACK archives

```
//pack file, file head format

//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
//				PHF0					>>>>
//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
//		(DWORD) 01 or 00	unknow 		>>>>
//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
//		(ULONG64) 00		no use		>>>>
//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
//		(DWORD)	Num of file				>>>>
//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
//		(DWORD)	Size of index			>>>>
//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
//pack file, file index format

//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
//			(DWORD)	Size of file		>>>>
//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
//				(char) file name 		>>>>
//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
```


it is a very simple format,no encrypt,no pack,you can visit total war center to find the unpacker,i have found two version,one is written by delphi,the other is written by python
