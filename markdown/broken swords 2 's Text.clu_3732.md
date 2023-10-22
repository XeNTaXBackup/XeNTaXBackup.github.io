## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-09-23T01:29:02+00:00
- Post Title: broken swords 2 's Text.clu

I want to extract the broken swords 2 's Text.clu file.
I wrote a quickbms script like

```
	findloc TAG_START string "Text Resource"
	goto TAG_START+13
	findloc TAG_START_NEXT string "Text Resource"
	set SIZE long TAG_START_NEXT
	math SIZE -=TAG_START
	
	log TAG_START TAG_START SIZE

next i
```


but something wrong at math SIZE -=TAG_START.
Anyone can give me some advice?
[Text.rar](https://xentaxbackup.github.io/file/2366_Text.rar)
