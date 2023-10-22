## Post #1
- Username: zhade
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 16, 2011 5:51 am
- Post datetime: 2011-05-16T11:36:54+00:00
- Post Title: Metal Assault (mas.cvf)

Metal Assault
Format for the archive file: mas.cvf

Byte order is Little Endian.

```
char[12] SFILESYSTEM (magic) 
```

Afterwards it goes through the whole archive like this:

```
    int type
    if type = 0 (its a directory)
        char[264]    directory name
        int          from
        int          to (Its a range offset if i am not mistaken, it specifies a range within the data and all the files and other 
                             directories who are inside this range are inside this directory, also this value will be 0 when the
                             directory is the last resource in their respective parent directory and means till end of parent directory)
    
    if type = 1 (its a file)
        char[256]    file name
        int          compressed size
        int          uncompressed size
        int          (unknown data, always 0)
        int          end offset (position where the compressed files data ends, unrelieable: in some cases its 0, its better to use the
                                   compressed size value after this to reach the next file)

        char[compressed size]    data (starting with 78 9C, standard zlib compression)

end of file

```

Also in the data there are the directories ./ and ../ after each new directory. I guess they use some simple listing tool that allows them to add and remove stuff, since the ./ and ../ only exist for easier navigation. Like go one level up =P

But I still have to figure out the correct way of directory order, I guess its right to assume that they just go from top to bottom and everything before is their parent (if its in range), but I havent checked if they are ordered by their `from` value.

Also changing files is no problem at all, just decompress with offzip, change and compress it back. Then overwrite the data and make sure to set the new sizes. You also might want to consider the directory ranges to make sure that the following files are still in their correct directory.
