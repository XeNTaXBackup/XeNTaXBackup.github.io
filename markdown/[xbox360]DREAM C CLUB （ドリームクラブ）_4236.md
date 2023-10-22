## Post #1
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-03-17T18:16:05+00:00
- Post Title: [xbox360]DREAM C CLUB （ドリームクラブ）

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-03-30T02:42:14+00:00
- Post Title: [xbox360]DREAM C CLUB （ドリームクラブ）

*edit: removed the wip*

see my post below for update
## Post #3
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-03-30T12:43:32+00:00
- Post Title: [xbox360]DREAM C CLUB （ドリームクラブ）

> Reply from WRS
>
> as i'm spending way too much time on this script already, i'll post my incomplete script

BTW: not getting any model data at this stage, just textures (eyes, clothes, faces)


[/code]

I have ISO game!!

I want your msn contacts please?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-03-31T16:19:27+00:00
- Post Title: [xbox360]DREAM C CLUB （ドリームクラブ）

i dont use msn.

here's the bms script to extract all files from all containers (you read that right)

```
#    xentax.com

endian big

get FILES long			# number of file containers

for i = 1 to FILES

  get CPOINTER long		# container pointer
  get CSIZE long		# container size
  
  savepos OFFSET
  goto CPOINTER
  
  for j = 0
  
    get FPOINTER long		# pointer to file
	
	if FPOINTER == -1
	  break
	endif
	
    get FSIZE long		# size of file
    get FNPOINTER long		# pointer to filename
  
    math FNPOINTER += CPOINTER
	math FPOINTER  += CPOINTER
  
    savepos COFFSET
	goto FNPOINTER
  
    get NAME string 		# get the filename
  
    goto COFFSET
  
    log NAME FPOINTER FSIZE
	
  next j
  
  goto OFFSET

next i

```


as a bonus, you can use this to extract textures from the CAN containers it extracts:

```
#    xentax.com
#   .can BMS script (typically tex?.can)

endian big

for i = 0

  get FPOINTER long
  
  if FPOINTER == -1
    cleanexit
  endif
  
  get FSIZE long
  get FNPOINTER long
  
  savepos OFFSET
  goto FNPOINTER
  
  get NAME string
  
  goto OFFSET
  
  log NAME FPOINTER FSIZE

next i

```


you might want to post the SHD/ TGF files in the 3d section - i think those are the 3d data you want
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-31T20:14:36+00:00
- Post Title: [xbox360]DREAM C CLUB （ドリームクラブ）

Nice going
## Post #6
- Username: pceengied
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Jan 23, 2010 2:55 am
- Post datetime: 2010-04-02T15:01:02+00:00
- Post Title: [xbox360]DREAM C CLUB （ドリームクラブ）

Are you guys going to do any ripping tools for [DREAM C CLUB （ドリームクラブ） ]??
 
who can give me  extractor TOOL sofe of [DREAM C CLUB （ドリームクラブ） ] !
