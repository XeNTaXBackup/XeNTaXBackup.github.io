## Post #1
- Username: darkprince
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 29, 2011 8:44 pm
- Post datetime: 2011-07-29T12:55:55+00:00
- Post Title: Reimport help required :D

Well, I was just modding some necessary files compressed through Nayapack using the script for Dirftcity Online from here:
[http://aluigi.org/papers/bms/drift_city.bms](http://aluigi.org/papers/bms/drift_city.bms)

My first question is, how this script can be modified to extract chunks (each with unique name, such as an incrementing a number at the end of filename) individually?

2nd question: How this script be further modified to make the reimporter work.

currently the error is:
quickbms -w -r dc.bms option.agt Option

```
QuickBMS generic files extractor and reimporter 0.5.2
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- REIMPORT mode enabled!
- open input file Option.agt
- open script dc.bms
- set output folder Option

  offset   filesize   filename
------------------------------

- 0 files reimported in 0 seconds
```

I have attached the folder and the agt archive into which the folder has to be reimported.


The trouble for me is, since the chunks are appended into one file, its impossible to get the files reimported back to the archive. I am sure that the community will be really helpful.

Thank You for your concern
[Option.rar](https://xentaxbackup.github.io/file/4552_Option.rar)
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-07-29T20:21:36+00:00
- Post Title: Reimport help required :D

> Reply from darkprince
>
> 
2nd question: How this script be further modified to make the reimporter work.

Reimporting works good.
[](http://uploadpic.org/v.php?img=YjtJHl3F8)
## Post #3
- Username: darkprince
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 29, 2011 8:44 pm
- Post datetime: 2011-07-30T06:38:37+00:00
- Post Title: Reimport help required :D

I guess I cant get reimporter to work either way.

Thats how I did it,
1. Run REIMPORT
2. Select bms script
3. Select option.agt
4. openned Option folder
5. Clicked Save

And I get again 0 files imported error

huge edit: I can reimport of filesize lesser than 16KB but not the ones greater than 16KB, just as shader.agt has some below

And also, if the file is greater than 16KB, its written in chunks in the agt archive, each of 16KB. The script appends the chunks into one big file. And I guess it might fail to reimport there.

For instance, I have attached shader.agt with a modified AGC_shader.fx which is 64KB in the shader folder. Please experiment and post back.


Tell me if this commandline is correct

```
"

QuickBMS generic files extractor and reimporter 0.5.2
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- REIMPORT mode enabled!
- open input file c:\BMS\shader.agt
- open script c:\BMS\drift_city.bms
- set output folder c:\BMS\shader

  offset   filesize   filename
------------------------------

- 0 files reimported in 0 seconds
```


Thanks alot once again!
[shader.rar](https://xentaxbackup.github.io/file/4556_shader.rar)
## Post #4
- Username: darkprince
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 29, 2011 8:44 pm
- Post datetime: 2011-07-30T08:15:12+00:00
- Post Title: Reimport help required :D

OK I have managed to reimport, but it gives the size mismatch error for files bigger than 16KB

```
------------------------------

Error: file "shader\Pe_Shader.fx"
       the reimport option acts as a reimporter and so you cannot reinsert a
       file if it's bigger than the original otherwise it will overwrite the
       rest of the archive:
         new size: 3783
         old size: 2984

- do you want to skip this file? (y/N)
  n
       now it's suggested to restore the backup of the original archive
       because the current one could have been corrupted due to the
       incomplete operation

Press RETURN to quit
```

And the AGC shader remains the original 

As I see, the files are packed in chunks of 16KB, with XOR key. Why not extract the chunks with a recursive name like, abc.ext1, abc.ext2, abc.ext3 and so on till file ABC.EXT ends? and later we reimport them? or is there any way to extract chunks without the plan I am proposing?

Do try the shader.agt I have attached above. I need to modify the script so that it extracts the chunks without appending them, each with a unique name in the manner I have stated above.

Thank You
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-07-30T10:05:20+00:00
- Post Title: Reimport help required :D

This modification extracts chunks, but it can't reimport files back.   

```
get DUMMY long
get DUMMY long
get FILES long

goto 0x20
savepos INFO_OFFSET

filexor "0x01 0x05 0x06 0x02 0x04 0x03 0x07 0x08 0x01 0x05 0x06 0x0f 0x04 0x03 0x07 0x0c 0x31 0x85 0x76 0x39 0x34 0x3d 0x30 0xe8 0x67 0x36 0x36 0x32 0x3e 0x33 0x34 0x3b 0x11 0x15 0x16 0x16 0x14 0x13 0x1d 0x18 0x11 0x03 0x06 0x0c 0x04 0x03 0x06 0x08 0x2e 0x55 0x26 0x23 0x2a 0x23 0x2e 0x28 0x21 0x21 0x26 0x27 0x2e 0x00 0x2d 0x2d 0xcf 0xa5 0x06 0x02 0x04 0x0f 0x07 0x18 0xe1 0x15 0x36 0x18 0x60 0x13 0x1a 0x19 0x11 0x15 0x16 0x10 0x12 0x13 0x17 0x38 0xf1 0x25" 0
append

for i = 0 < FILES
    goto INFO_OFFSET
    get CHUNKS_OFFSET long
    get CHUNKS long
    get SIZE long
    get NAMESZ long
    getdstring NAME NAMESZ
    savepos INFO_OFFSET

    set OFFSET long CHUNKS
    math OFFSET *= 2
    math OFFSET += CHUNKS_OFFSET

    goto CHUNKS_OFFSET
    for j = 0 < CHUNKS
        set NAME0 = NAME
	set NAMECNT j
        string NAME += NAMECNT
        get ZSIZE short
        clog NAME OFFSET ZSIZE 16384
	set NAME = NAME0
        math OFFSET += ZSIZE
    next j
next i
```
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-30T12:37:22+00:00
- Post Title: Reimport help required :D

The readme mentions that you can't re-import files that are larger than the original.
## Post #7
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2011-07-30T13:28:46+00:00
- Post Title: Reimport help required :D

That's right, but the file size is not a problem in this case.
## Post #8
- Username: darkprince
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 29, 2011 8:44 pm
- Post datetime: 2011-07-31T16:40:40+00:00
- Post Title: Reimport help required :D

> - if the original archive uses complex encryptions that require the
>
>   usage of MEMORY_FILEs to perform temporary decryptions then it's NOT
>
>   supported and the same is valid for chunked content (like the usage
>
>   of the command Append)

I guess its the dead end then
