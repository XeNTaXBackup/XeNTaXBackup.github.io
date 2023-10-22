## Post #1
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-09-24T09:27:25+00:00
- Post Title: Help me not be stupid with QuickBMS please.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-09-24T15:00:21+00:00
- Post Title: Help me not be stupid with QuickBMS please.

so the first attribute is the ascii signatures. this is our "id string" which helps identify the format

as there are 2 possible strings of the same length (the size of a dword - or 4 bytes) we can use this:

```
getdstring IDSTR 4
```


which gets the first 4 characters in the file. we can now do an optional check that this string is correct

```
elif IDSTR == "Jpng"
else
  # matched neither of these id strings
  cleanexit
endif

```


then we can continue getting the values you've listed:

```
get FILENUM long
get WIDTH long
get HEIGHT long
get NULL long

```


next is the image data, and we can just use the "log" function to save it out from the current file position. something like this:

```
log "" CURPOS IMGSIZE

```


notice the blank filename. quickbms will identify the dds signature and give it a relevant filename for us! this is really helpful when formats like this dont store names!

we need to skip to the next image.. so we can add the image size to the current position and seek to it

```
goto CURPOS

```


now we're at the next image. because we don't really know how many images are here, we can wrap this into an infinite loop using FOR and NEXT like so:

```

getdstring IDSTR 4

if IDSTR == "Jdds"
elif IDSTR == "Jpng"
else
  # matched neither of these id strings
  cleanexit
endif

get IMGSIZE long
get FILENUM long
get WIDTH long
get HEIGHT long
get NULL long

savepos CURPOS
log "" CURPOS IMGSIZE

math CURPOS += IMGSIZE
goto CURPOS

next

```


there is an error at the end of this script because we don't check for the end of the file. quickbms doesn't crash but we can avoid this by adding a filesize check:

```

for

getdstring IDSTR 4

if IDSTR == "Jdds"
elif IDSTR == "Jpng"
else
  # matched neither of these id strings
  cleanexit
endif

get IMGSIZE long
get FILENUM long
get WIDTH long
get HEIGHT long
get NULL long

savepos CURPOS
log "" CURPOS IMGSIZE

math CURPOS += IMGSIZE

if CURPOS == SIZE
  cleanexit
endif

goto CURPOS
 
next

```


try commenting each line against the quickbms documentation if you need more understanding


[00000006.png](https://xentaxbackup.github.io/file/4733_00000006.png)
## Post #3
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-09-26T19:19:00+00:00
- Post Title: Help me not be stupid with QuickBMS please.

Thanks for the help, that's a lot easier to understand than the way the documentation is set up. I'm going to try to work with a more complicated format soon, but I'll probably get confused trying to work with the filenames, so I'll probably be back to ask for more help soon.
