## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-08-25T13:47:40+00:00
- Post Title: Sacred Legend Online

Hello, well as far remember aluigi do this unpacker for IDX files, so my question is if possible update it? the new files no work with this old bms script, maybe can take a look into this files to update this old bms script? well I hope yes many thanks to all community for all support and in special to aluigi for this fully support.

> math OFFSET = 0x124
>
> open FDSE pkg.idx
>
> get files asize
>
> math files - OFFSET
>
> math files / 0x250
>
> goto OFFSET
>
> math MYPACKFILE = -1
>
> for i = 0 < files
>
>     get FILENUM long
>
>     get OFFSET long
>
>     get unk02 long
>
>     get ZSIZE long
>
>     getdstring DUMMY 40
>
>     get SIZE long
>
>     getdstring file 0x104
>
>     getdstring NAME 0x108
>
>     string NAME + file
>
>     get packfile long
>
>     get unk15 long
>
> 
>
>     if PACKFILE != MYPACKFILE
>
>         string PCK p= "pkg%03d.pkg" PACKFILE
>
>         open FDSE PCK 1
>
>         math MYPACKFILE = PACKFILE
>
>     endif
>
>     if ZSIZE != SIZE
>
>         clog NAME OFFSET ZSIZE SIZE 1
>
>     else
>
>         log NAME OFFSET ZSIZE 1
>
>     endif
>
> next i

Error:



Pck 323 give error.

[http://puu.sh/b7pqx/91977b0d80.7z](http://puu.sh/b7pqx/91977b0d80.7z)

Samples

[http://puu.sh/b7ghw/5ea9eb7339.7z](http://puu.sh/b7ghw/5ea9eb7339.7z)
