## Post #1
- Username: DJRehab
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 15, 2011 5:18 am
- Post datetime: 2012-11-09T14:07:39+00:00
- Post Title: creating a new pak file when extracting method is known

I am attempting to create a new battleforge .pak file but I am getting nowhere...the following in the MexScript used to unpack the files

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "PAK\x01"
get INFO_OFF long
get INFO_SIZE long
get INFO_ZSIZE long
clog MEMORY_FILE INFO_OFF INFO_ZSIZE INFO_SIZE

get FILES long MEMORY_FILE
for i = 0 < FILES
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE
    math SIZE -= OFFSET
    log NAME OFFSET SIZE
next i
```


How would I use this information to create a new pak file using the same file structure?
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-10T06:22:00+00:00
- Post Title: creating a new pak file when extracting method is known

Read section 3 (Reimport the extracted files) in QuickBMS readme.
## Post #3
- Username: DJRehab
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 15, 2011 5:18 am
- Post datetime: 2012-11-10T15:43:40+00:00
- Post Title: creating a new pak file when extracting method is known

You misunderstand...I want to create a new pak file implementing completely new files into the game...I know how to inject already but I am not trying to replace an asset, I am trying to add a new one.

EDIT - I could probably just copy this file, change the name of the directory structure/filename sure but this would also limit me on file size and path/filename character length so I would prefer (if possible) to create a new pak file

EDIT2 - Also this:

```
  formats I have decided to not use tricks for modifying the original
  size and compressed_size values (think to those formats that use
  encrypted information tables or the scripts that use MEMORY_FILEs
  for such tables or that use things like "math SIZE *= 0x800")
```

and this: (both from the reimport section of quickbms documentation)

```
  usage of MEMORY_FILEs to perform temporary decryptions then it's NOT
  supported and the same is valid for chunked content (like the usage
  of the command Append)
```
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-11T00:59:09+00:00
- Post Title: creating a new pak file when extracting method is known

If you already know the structure of the format then all you need to do is write a program that will take a bunch of files and put them inside an archive using the format specified in the extract script.

Or write a program that will read the BMS script for the format and then create your archive based on the parsed format.
