## Post #1
- Username: impactxamazy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 22, 2023 12:18 am
- Post datetime: 2023-07-21T16:33:17+00:00
- Post Title: Help decrypting .ab and .xyasset Unity files

Hi all,

I'm trying to decrypt these files: [https://mega.nz/file/lnJVERpa#3RciMU3qL ... yklMey4VKA](https://mega.nz/file/lnJVERpa#3RciMU3qLis9-B99x_OvIz88m7LFNYiLzyklMey4VKA)

I'm using this script for the .ab file but have had no luck so far, I'm getting the same archives:

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


Thank you.

EDIT: I managed to decrypt the .ab file.
