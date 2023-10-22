## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-27T22:15:37+00:00
- Post Title: Trinity online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-31T04:27:29+00:00
- Post Title: Trinity online

Here is the outline of the KCP index file.
Each entry defines the number of subfolders and files, and then specifies them in that order.

There are still unknowns, but fortunately not too many. Data is most likely compressed.

The problem with this script right now is that it just prints out all of the names, and then goes through each archive, which is not useful.

It should probably keep one pointer for the archive number, and another pointer to the current folder is it reading, Then jump to the next archive for every n files read or something (I don't know if it's stored in the same order that it appears.

```

get one long
get one long
get numArchives long
get totalFolder long
get unkbyte byte #just some odd byte

for x = 0 < totalFolder
	get one long
	get files long
	get folders long
	
	#the folder name is composed of everything before the basename, and then the basename itself
	get root long #length of root path
	get base long #length of folder name
	math length = root
	math length += base
	getdstring folder length
	print "%x% %folder%"

	#Create subfolders
	for i = 0 < folders
		get length long
		getdstring folderName length
	next i

	#create files.
	for j = 0 < files
		get one long
		get two long
		get null long
		get unk8 long
		get null long
		get null long

		get kcs_id long
		get length short
		get usize long	#unpacked size
		get size long		#compressed size
		get kcs_offset long
		getdstring name length
		string archive = "Trinity_PackFile_"
		string archive += kcs_id
		string archive += ".KCS"
		
		#we will need to prepend the current folder's name to this file's name
		#TO DO 
		string outName = folder
		string outName += "/"
		string outName += name
		
		#open specified archive and save file
		open . archive 1
		clog outName kcs_offset size usize 1
	next j
next x

```
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-03T16:08:33+00:00
- Post Title: Trinity online

hi

the kcs files have the deflate signature - and can indeed be extracted with offzip - [http://aluigi.altervista.org/mytoolz.htm#offzip](http://aluigi.altervista.org/mytoolz.htm#offzip)


 edit 2 
removed sample plaintext file and file id/offset/size/usize/filename dump - see script

i've added stuff to your files structure, which should be enough to finish your script:

```
   for j = 0 < files
      get one long
      get two long
      get null long
      get unk8 long
      get null long
      get null long

      get kcs_id long      # sprintf like: Trinity_PackFile_%i.KCS

      get length short
      
      get usize long       # unpacked size
      get size long        # packed (compressed) size
      get kcs_offset long  # fseek to this in the KCS file

      getdstring name length
      
      #we will need to prepend the current folder's name to this file's name
      #TO DO 
   next j

```


the compression is deflate (default comtype anyway)


the highest kcs_id value is 460 (as you said to expect)
the folders span multiple KCS files - might make it difficult to write an efficient script
kcs offsets start from 16 (not sure what the first 16 bytes are)


CAMERA_EFFECT.MLA (770 bytes, 242 compressed, offset to Trinity_PackFile_0.KCS is 63456)

> EMERS ENGINE ASCII EXPORT FORMAT
>
>      Version 1 0 0
>
> 
>
> @CAMERA_EFFECT_COUNT 5
>
> 
>
> @CAMERA_EFFECT
>
>     @NAME "Shake_CriticalCollision"
>
>     @TYPE Shake
>
>     @LIFE_TIME 0.5
>
>     @RANGE 15
>
>     @AXIS X
>
> @CAMERA_EFFECT_END
>
> 
>
> @CAMERA_EFFECT
>
>     @NAME "ZoomIn_Test"
>
>     @TYPE ZoomIn
>
>     @LIFE_TIME 2
>
>     @RANGE 1000
>
>     @ZOOMSPEED 5.0
>
> @CAMERA_EFFECT_END
>
> 
>
> @CAMERA_EFFECT
>
>     @NAME "ZoomOut_Test"
>
>     @TYPE ZoomOut
>
>     @LIFE_TIME 2
>
>     @RANGE 1000
>
>     @ZOOMSPEED 5.0
>
> @CAMERA_EFFECT_END
>
> 
>
> @CAMERA_EFFECT
>
>     @NAME "Shake_Fallingrock"
>
>     @TYPE Shake
>
>     @LIFE_TIME 2.0
>
>     @RANGE 15
>
>     @AXIS X
>
> @CAMERA_EFFECT_END
>
> 
>
> @CAMERA_EFFECT
>
>     @NAME "Shake_Crash"
>
>     @TYPE Shake
>
>     @LIFE_TIME 0.5
>
>     @RANGE 15
>
>     @AXIS Y
>
> @CAMERA_EFFECT_END
>
> 
>
> @END_OF_FILE
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-03T22:43:27+00:00
- Post Title: Trinity online

As long as it works 

I don't really like how I made the names though, and I didn't do anything about those subfolders inside each folder cause it seemed complicated to figure out which goes where (though for some reason they are still created and files put into them, and I don't know how that happened!)

But it gets the files out and the models are recognizable.
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2011-08-12T17:17:37+00:00
- Post Title: Trinity online

I get bored on my own work so I come across here just for fun!
I don't even download the game so I'm not sure if this BMS works or lot!

```
# Official WebSite: http://trinity.goorm.com/
# by Fatduck     Aug2011
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get EXT extension
if EXT != KCP
   open FDSE PackFile.KCP 0
endif
get UKN longlong
get NUMKCS long
get NUMDIR long
get NULL byte

math REFPACK = -1

for DIR = 0 < NUMDIR
   get DUKN long
   get NUMRES long
   get NUMSUBDIR long
   get BASELEN long
   get EXTLEN long
   math BASELEN += EXTLEN
   getdstring DIRNAME BASELEN
   string DIRNAME += /
   
   #Just Skip to the resource Table
   for SUB = 0 < NUMSUBDIR
      get LEN long
      getdstring SUBNAME LEN
   next SUB
   
   for i = 0 < NUMRES
      getdstring UKNSKIP 24
      get KCSIDX long
      get LEN word
      get USIZE long
      get CSIZE long
      get OFS long
      getdstring RESNAME LEN
      set OUTNAME string DIRNAME
      string OUTNAME += RESNAME
      
      if KCSIDX != REFPACK
         set KCSNAME string Trinity_PackFile_
         string KCSNAME += KCSIDX
         string KCSNAME += .KCS
         open FDSE KCSNAME 1
         math REFPACK = KCSIDX
      endif
      clog OUTNAME OFS CSIZE USIZE 1     
   next i

next DIR
```


PS: I think the subdirectories inside the first loop is for the engine to pre-create directorices, if you follow the loop carefully, you'll found some loop don't have resource table inside, just subdirectories. And you will found alll those subdirectories strings used in the following loop!!!
