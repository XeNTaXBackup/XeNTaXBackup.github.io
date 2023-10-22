## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-03-08T00:04:10+00:00
- Post Title: M2 online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Emir
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 10, 2010 5:37 pm
- Post datetime: 2010-03-10T10:06:10+00:00
- Post Title: M2 online

Magic World 2 packfile .mw2
Game Website: [http://db.12ha.com/](http://db.12ha.com/)

Pack Header 

string DLOG 14 / / file header 
DWORD CRC / / CRC?? 
DWORD ZSIZE / / compressed size
DWORD SIZE / / decompressed size
DWORD FILENAMESIZE / / file name length 
string FILENAME FILENAMESIZE / / file name 
filedata .... / / file compression data 

------------------------------------------------------------------- 

```
# Initialize the offset address of the variable OFFSET 
set OFFSET long 0 

# Loop
for 

# Jump to the offset address 
GOTO OFFSET 

# Read the file header in the variable 
getdstring DLOG 14 
get CRC long 
get ZSIZE long 
get SIZE long 
get FILENAMESIZE long 
getdstring FILENAME FILENAMESIZE 

# Define compression decompression format 
# ComType uncompress 

# Calculate offset address + header length + file name length
math OFFSET + = 30 
math OFFSET + = FILENAMESIZE 

# Read file data 
# clog FILENAME OFFSET ZSIZE SIZE 
log FILENAME OFFSET ZSIZE 

# Calculate offset address + file data length 
math OFFSET + = ZSIZE 

next 


```


Mw2 file compression in the file mw_pack.rar. 

Expert analysis of the current assistance package compressed format (non-encrypted ZIP or have been) ComType what you can decrypt the file data? ?

Chinese friend add QQ:16381780 POST:解包
[mw_pack.rar](https://xentaxbackup.github.io/file/2859_mw_pack.rar)
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-10T12:04:29+00:00
- Post Title: M2 online

no luck with the compression.
I have scanned all the compression algorithms supported by quickbms and I have also tried to apply the CryptDecrypt encryption with the key "#4sldfWERx*(^^*3" but still no luck
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-03-11T11:02:24+00:00
- Post Title: M2 online

there was some info in one of the dll about some kind of packing i think...like bcpacker...bgpacker or something. I am at work and cannot see the files now but look in the dll also
## Post #5
- Username: Emir
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 10, 2010 5:37 pm
- Post datetime: 2010-04-30T09:15:06+00:00
- Post Title: M2 online

> Reply from aluigi
>
> no luck with the compression.
I have scanned all the compression algorithms supported by quickbms and I have also tried to apply the CryptDecrypt encryption with the key "#4sldfWERx*(^^*3" but still no luck

I debug and found the zlib password in MwEngine_Shipping_dll.dll, How to use in my bms scripts ??
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-30T09:48:10+00:00
- Post Title: M2 online

depends by the algorithm, personally I can't test it because the sample file no longer exists.
anyway if only the archived file is encrypted then use:

```
log FILENAME OFFSET ZSIZE 
encryption "" ""
```
instead of the only "log FILENAME OFFSET ZSIZE"
but I don't remember if cryptdecrypt wanted different parameters (default is md5+rc4)
## Post #7
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-04-30T18:17:44+00:00
- Post Title: M2 online

the script emir provides 1 file but then it seems to extract that same file infinite times, so only one 1 file is extracted but quickbms keeps working

the encryption thingy did not do any difference
