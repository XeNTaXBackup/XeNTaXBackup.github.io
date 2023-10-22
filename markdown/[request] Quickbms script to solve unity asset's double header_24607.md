## Post #1
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-10-16T14:19:53+00:00
- Post Title: [request] Quickbms script to solve unity asset's double header

```
set Name string "new\\"
string Name + ArcName
get Size asize
math Size - 0x4
log Name 0x4 Size
```


i got this script from alicegear thread but it can only remove 0x* which is good for alicegear but not work on some game that hv random size of padding header b4 the real "UnityFS"
could someone please make a script that be able to automatically detect next "UnityFS" and delete everything b4 that? thanks
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-10-16T15:19:31+00:00
- Post Title: [request] Quickbms script to solve unity asset's double header

@wansf: Something like this should work:

```
string NAME p "new/%s" NAME
findloc OFFSET string "UnityFS" 0 ""
if OFFSET == ""
	print "Header not found!"
	cleanexit
else
	get SIZE asize
	math SIZE - OFFSET
	log NAME OFFSET SIZE
endif
```

and in case there are doubled UnityFS headers (for example, like in Seven Deadly Sins: Grand Cross assets), you'll need to add something like "goto 7" at the beginning of the script to skip the first header.
## Post #3
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-10-17T01:00:18+00:00
- Post Title: [request] Quickbms script to solve unity asset's double header

it works POGCHAMP
thanks x1000000
