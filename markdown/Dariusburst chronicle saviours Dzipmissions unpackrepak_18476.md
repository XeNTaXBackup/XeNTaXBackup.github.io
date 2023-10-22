## Post #1
- Username: Clayone02
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 22, 2018 1:10 am
- Post datetime: 2018-07-21T17:15:22+00:00
- Post Title: Dariusburst chronicle saviours Dzip/missions unpack/repak

Attempting to unpack and repack, some daruisbrust game files, to hopefully be able to edit the mission mode 

using quickbms Current code is

```
idstring DZIP
get archiveSize long
get uk1 long
get uk2 short
get uk3 short
get uk4 short
get uk5 short

```


missiontable example in hex.

```

```

everything after this point in hex is the encoded text

I know the file, is going to be a single file inside the archive however, i am not quite sure how to determine how i should uncompressed it besides the strings iv found comparing different files in the folder 
anyone with any assistance would be awsome
[chronicle.ZIP](https://xentaxbackup.github.io/file/14637_chronicle.ZIP)
## Post #2
- Username: Clayone02
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 22, 2018 1:10 am
- Post datetime: 2018-07-22T18:02:12+00:00
- Post Title: Dariusburst chronicle saviours Dzip/missions unpack/repak

Update, Found out using the brutefrocetools 

If you remove 8 bytes form the file
1st 4 bytes, Words DZIP
2nd 4 bytes TotalUnpacked Filesize

Then run test algo 65 
test algorithm number 65: ZSIZE 60002, SIZE 1200040

It will properly unzip the file

Now I have to figure out how to make a working scirpt to automate it, and let me repack it.
