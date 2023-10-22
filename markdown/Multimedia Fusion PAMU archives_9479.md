## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-15T01:04:08+00:00
- Post Title: Multimedia Fusion PAMU archives

I've only seen a couple of these games, but they almost follow the same format for the most part.
These games are usually packed into one huge exe. Skipping past the PE stuff, I get to some data.

For this script, I'm sort of just roughly skipping all the PE related stuff to find the start of the actual data I want.
The data begins with the idstring "wwww"

```

# just some rough skipping
startfunction read_PE
  idstring "MZ"
  goto 60
  get PE_HEADER_OFS long
  
  goto PE_HEADER_OFS
  idstring "PE\x00\x00"
  get machine short
  get SECTIONS short
  getdstring skip 12
  get OPT_HEADER_SIZE short
  get characteristics short
  goto OPT_HEADER_SIZE 0 SEEK_CUR
  for i = 0 < SECTIONS
    getdstring name 8
    print %name%
    get virtSize long
    get virtAddr long
    get rawSize long
    get rawOfs long
    getdstring others 16
  next i
  
  math rawOfs += rawSize
  goto rawOfs
endfunction

#skip PE stuff
callfunction read_PE

savepos START
print "data start: %START%"
# now at start of data
comtype unzip_dynamic
idstring "wwww"
get unk long
get table_Ofs long
get PAM_OFS long

math PAM_OFS += START
math PAM_OFS -= 32

get unk long
get null long
get null long
get unk long


print "Main PAMU archive: %PAM_Ofs%"

for i = 0 
  get len short
  math len *= 2
  getdstring UNAME len
  set NAME UNICODE UNAME
  get unk long
  get SIZE long
  savepos OFFSET

  #print "%NAME% %OFFSET%"
  clog NAME OFFSET SIZE SIZE
  
  math OFFSET += SIZE
  print %PAM_OFS%
  if OFFSET == PAM_OFS
    break
  endif
  goto OFFSET
next i

print %OFFSET%
# start PAMU archive

```


There may be multiple files with the "PAMU" idstring. This is likely where the actual game content is stored (everything else is just dll's and stuff, which the above script would've dealt with)

Some archives are different from others. I'm looking at one where there are filenames and the data is totally uncompressed. Others are zlib compressed and it seems like the filename and data are zlib compressed in two streams: first you decompress a chunk to get the file name, then you decompress another chunk to get the actual data with that file.

Though, not sure if that holds for all files.

Sample PAMU archive: [http://www.mediafire.com/?k288j278kfyc7f9](http://www.mediafire.com/?k288j278kfyc7f9)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-15T18:48:32+00:00
- Post Title: Multimedia Fusion PAMU archives

Just downloaded the demo for MMF and it looks like they have different versions of the archive.
The demo project resource files have "PAME" in the idstring intead of "PAMU".

Maybe I can see what's inside the .ccn archive.

[http://www.clickteam.co.uk/resources/GTM/gtm2_6.htm](http://www.clickteam.co.uk/resources/GTM/gtm2_6.htm)
Well, this explains what the ccn files are.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T19:06:23+00:00
- Post Title: Multimedia Fusion PAMU archives

I noticed the EXE parsing code and so I remembered I did something for another project.
I guess you may find the following script interesting and maybe even useful in some occasions:
[http://aluigi.org/papers/bms/others/parse_exe.bms](http://aluigi.org/papers/bms/others/parse_exe.bms)
