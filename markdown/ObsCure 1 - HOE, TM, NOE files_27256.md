## Post #1
- Username: sangrento55
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 24, 2022 9:38 am
- Post datetime: 2023-09-27T21:41:57+00:00
- Post Title: ObsCure 1 - HOE, TM, NOE files

I have the follow custom text files .hoe and .tm and .noe.

I need some help to extract the text of thouse files. they are from obscure 1 game.

Here are the files:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1PSEr3_SV1zR_Me1SybX12GRcoKMdMeKj?usp=sharing)
## Post #2
- Username: sangrento55
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 24, 2022 9:38 am
- Post datetime: 2023-09-28T12:37:03+00:00
- Post Title: ObsCure 1 - HOE, TM, NOE files

I was analizing the music.hoe file.

I know so far that is a little-endian.
The file has the same if compare to others hoe files.

this is the header:

40 03 33 33 00 00 05 40 80 00 00 00 00 00 05
6F 75 73 69 63 00 00 00 00 00 00 04 00 00 00

and ends the same way.

6D 75 73 69 63 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 3F 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 

It apperas to have some optional keys like 54 4D 5F 4D 55 53 49 43 5F 4C 65 6F 54 51 70 65 45 66 66 65 63 74, converting is TM_MUSIC_LeoTapeEffect.
aftert this key we have like 00 00 00 01 02 00 00 00 65.

The Following Data: 00 00 00 01 02 00 00 00 65 :
This sequence of bytes seems to represent data associated with the key. While the specific meaning of these bytes may require further analysis and understanding of the file format, it should be like:
00 00 00 01: This could be an indicator or flag.
02: This might represent a data type or length.
00 00 00 65: This appears to be a numeric value, possibly an integer or floating-point number.

There is more keys like 54 4D 5F 45 55 53 49 43 5F 52 65 73 65 74 4D 75 73 69 63 that is TM_MUSIC_ResetMusic but again follow by 00 00 00 01 02 00 00 00 65

It's becoming clearer that the file format uses a key-value pair structure.

I found someting before the file ends there is a name that appear in header 6D 75 73 69 63 that is music. 

This is follow by a constant 00 00 00 05 65 76 65 6E 74 00 00 00 after that we have some int and string values and ends with 62 5F 73 63 72 69 70 74 65 64 5F 31 that means b_scripted_1.
