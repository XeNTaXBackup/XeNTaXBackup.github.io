## Post #1
- Username: sanderson169
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 04, 2022 1:24 am
- Post datetime: 2022-09-27T17:36:33+00:00
- Post Title: [Help] I need to add something to the renamer parser UE4 script

```
# script type: parser
# note 1: all *.wem files must be in the same folder as this script and the txt
# note 2: script will maintain the original folder structure
#
# (c) by AlphaTwentyThree of Zenhax
# script for QuickBMS http://quickbms.aluigi.org

get EXT extension
if EXT == "xml"
	callfunction soundbanks 1
else
	print "script only for xml"
endif

startfunction soundbanks
	for i = 1
		FindLoc SEARCH string "<File Id="
		if SEARCH == ""
			cleanexit
		endif
		goto SEARCH
		getDstring DUMMY 10
		getCT DIDX string 0x22
		string DIDX += ".wem"
		getDstring TEST 3 # sometimes the file id tag is empty
		if TEST != " />"
			math SEARCH += 12
			goto SEARCH
			FindLoc SEARCH string "<Path>"
			goto SEARCH
			getDstring DUMMY 6
			getCT FNAME string 0x3c
			string FNAME -= 13
			open FDSE DIDX 1 EXIST
			if EXIST == 1
				get SIZE asize 1
				log MEMORY_FILE 0 0
				log MEMORY_FILE 0 SIZE 1
				string FNAME += ".wem"
				log FNAME 0 SIZE MEMORY_FILE
			endif
		endif
		math SEARCH += 12
		goto SEARCH
	next i
endfunction
```


I don't know if someone could help me, I was looking to add a couple of things to it, but I don't really understand it.

The thing is to add if you don't find the "wem" audio file in the "xml" file because it doesn't exist or isn't there, put that specific file "unknown.wem"
