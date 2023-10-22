## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-04T07:07:03+00:00
- Post Title: Legend Of Wukong (悟空传)

Hello guys, well I got a old unpacker of this game, after try use bms script,  I got that.



so well maybe somebody can take a look into files? many thanks here I leave old bms script just in case.

> get idstring long
>
> goto 0x19
>
> get offset long
>
> get size long
>
> get zsize long
>
> get baseoff long
>
> get datasize long
>
> get arcsize long
>
> clog MEMORY_FILE offset zsize size
>
> get unk01 long MEMORY_FILE
>
> get unk02 long MEMORY_FILE
>
> get files short MEMORY_FILE
>
> goto 0x12 MEMORY_FILE
>
> get folder3 string MEMORY_FILE
>
> For tmp = tmp != size
>
> get offset long MEMORY_FILE
>
> get size2 long MEMORY_FILE
>
> math offset + baseoff
>
> if size2 == 0
>
> get folder string MEMORY_FILE
>
> else if size2 == 1
>
> get folder2 string MEMORY_FILE
>
> string folder + \
>
> string folder + folder2
>
> else
>
> get name2 string MEMORY_FILE
>
> set name folder
>
> string name + \
>
> string name + name2
>
> log name offset size2
>
> endif
>
> savepos tmp MEMORY_FILE
>
> next

Samples

[http://puu.sh/bkITY/468a745a94.7z](http://puu.sh/bkITY/468a745a94.7z)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-04T10:36:55+00:00
- Post Title: Legend Of Wukong (悟空传)

Encrypted.
