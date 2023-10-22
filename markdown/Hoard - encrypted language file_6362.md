## Post #1
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-04-05T13:32:25+00:00
- Post Title: Hoard - encrypted language file

Hello everyone!
There is an other request from me 
This time i would like to ask for some work about the game called Hoard. 
If someone can do something with the attached file it would be great  The file is in a folder called encrypteddata so i haven't got too good feelings but.  Give it a try. Thank you 
[frontendstrings.rar](https://xentaxbackup.github.io/file/4165_frontendstrings.rar)
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-04-07T05:47:41+00:00
- Post Title: Hoard - encrypted language file

It seems, the game uses some kind of XOR encryption. The password is constructed from the filename (for example ""strings\english\engineerrorstrings.csv").
I'll try to find out the exact details of the decoding procedure.
## Post #3
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-04-07T12:43:48+00:00
- Post Title: Hoard - encrypted language file

thank you, itt would be great
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-04-07T17:33:09+00:00
- Post Title: Hoard - encrypted language file

Here's the HOARD file encoder/decoder.
Copy to the game's directory (for example: "C:\Program Files\HOARD\")
and run it.
It will decode all files inside the "encrypteddata" directory.

The algorithm is reversible (XOR encoding), so if you run the program again, it will encode the files.

Some technical information:
First you have to XOR the relative filename (for example "strings/english/frontendstrings.csv") with the HOARD_XOR_Array,
then you can XOR the file data with this password.

```
  ($6C, $6A, $20, $79, $4F, $01, $47, $57,  $7B, $48, $45, $3A, $76, $6D, $4A, $4E,
   $33, $1A, $76, $69, $29, $63, $73, $1B,  $4B, $33, $28, $69, $76, $31, $65, $51,
   $17, $53, $63, $5E, $34, $68, $2E, $43,  $53, $31, $44, $6A, $19, $74, $44, $7A,
   $57, $43, $71, $6E, $39, $19, $48, $5A,  $36, $4B, $58, $2C);  

```

[bacter_HOARD_decoder_v0_10.rar](https://xentaxbackup.github.io/file/4178_bacter_HOARD_decoder_v0_10.rar)
## Post #5
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-04-08T07:07:15+00:00
- Post Title: Hoard - encrypted language file

Thank you! x100
