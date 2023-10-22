## Post #1
- Username: BlackEternity
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jun 15, 2012 1:08 pm
- Post datetime: 2012-08-16T05:22:36+00:00
- Post Title: Golden Land .PAK

Does anyone know if there are any available tools to extract data from the .pak files?
I tried a couple of extractors to see if the file structure could possibly be the same as another game but unfortunately they weren't.

If someone could take a look at it, it would be much appreciated.
[http://www.mediafire.com/?yqzqfbdfznizs69](http://www.mediafire.com/?yqzqfbdfznizs69)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-16T05:54:31+00:00
- Post Title: Golden Land .PAK

```
# Quick BMS script

#comtype unzip_dynamic
idstring "PAK "
get null long
get FILES long
for i = 0 < FILES
  get LEN long
  getdstring NAME LEN
  get SIZE long
  get OFFSET long
  savepos CURR
  
  goto OFFSET
  get unk long
  get ZSIZE long
  savepos OFS
  if unk == 1
    clog NAME OFS ZSIZE SIZE
  else
    print "unknown unk: %unk%"
  endif
  goto CURR
next i
```


I don't know what the itm files are. They seem to references some other files.
There are also file entries that point to an offset with just a bunch of nulls.
