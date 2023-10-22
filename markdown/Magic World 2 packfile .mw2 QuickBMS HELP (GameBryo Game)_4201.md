## Post #1
- Username: Emir
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 10, 2010 5:37 pm
- Post datetime: 2010-03-10T10:01:16+00:00
- Post Title: Magic World 2 packfile .mw2 QuickBMS HELP (GameBryo Game)

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
[mw_pack.rar](https://xentaxbackup.github.io/file/2858_mw_pack.rar)
