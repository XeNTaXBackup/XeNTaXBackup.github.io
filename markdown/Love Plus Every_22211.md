## Post #1
- Username: karorogunso
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 20, 2018 8:21 pm
- Post datetime: 2020-05-27T16:13:49+00:00
- Post Title: Love Plus Every

I need help with this game. 
to extract a model, voices, and stuff

So far I know
 - Unity 2018.4 version
 - The cache is a streaming asset
 - They using CloudFront as a streaming asset server.

I use Wireshark + Fiddler to find a server and got

```
 - d3i80m0speg6x3.cloudfront.net
 - awj-web.mo.konami.net
 - pjlv-prd-alb-1-363683390.ap-northeast-1.elb.amazonaws.com
```


The Game has an Obb file that can extract but it really hard to view a game file with asset studio & utinyripper (a lot of bugs on software that crash a lot)

Grab all file in

```
main.31.jp.konami.loveplusevery\assets\bin\Data
```

and merge to

```
jp.konami.loveplusevery\files\asset\**Put a Obb extracted file here**
```


ps. I need help to working around before the game closed
## Post #2
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2020-06-01T05:44:02+00:00
- Post Title: Love Plus Every

I only got chibi models on asset/bin/data

3D models, voices, and stuff data probably on asset/AssetBundles/
but I have no idea how to get it, Some data probably encrypted
## Post #3
- Username: Moonstone1024
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 16, 2020 6:41 pm
- Post datetime: 2020-06-19T06:00:39+00:00
- Post Title: Love Plus Every

After poking around in the file list in Android, I noticed that there are a lot of unity3D assets but all of them appear to be encrypted with a hash and a time value specific to each asset. Some assets even have a lock file but they don't appear to do anything since opening them up in a hex editor shows absolutely nothing. 

This is what I found out: 
1. The hash values are 64 bytes long. 
2. The time values are 8 bytes long. 

This means that given the correct decryption method there is a way to decode everything and open it in Asset Studio as usual, but we need to find the correct decryption method.
## Post #4
- Username: Moonstone1024
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 16, 2020 6:41 pm
- Post datetime: 2020-06-19T15:46:10+00:00
- Post Title: Love Plus Every

With the help of @Yretenai and @akderebur in the Discord server in analysing the assets files, the encryption has been broken somewhat for the 2D assets, sprites and text. 

@akderebur found out that by using the working from the standard Unity header, it was found out that the asset files were only protected using a static XOR key (which is 32 30 31 36 30 39 31 35 78 78) which is common for all the 2D assets, sprites and text. 

The QuickBMS script for decrypting the assets, sprites and text are as below. 

```

Get OUTPUT_NAME basename
String OUTPUT_NAME + "_decode"

FileXOR "\x32\x30\x31\x36\x30\x39\x31\x35\x78\x78"
get SIZE asize
log OUTPUT_NAME 0 SIZE

```


Once decrypted using the system above, the assets can be extracted by Asset Studio, though some pictures are distorted for some unknown reason. I have created a new blog ([https://lovepluseveryhozon.blogspot.com/](https://lovepluseveryhozon.blogspot.com/)) to post up selected assets I have found in the game that would be of interest.
## Post #5
- Username: Moonstone1024
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 16, 2020 6:41 pm
- Post datetime: 2020-06-20T09:28:18+00:00
- Post Title: Love Plus Every

After further consultation with @Yrentenai I was able to make a comprehensive guide for fetching assets from LovePlus EVERY. 

LovePlus EVERY data assets are in two parts: 
Internal Storage/Android/data/jp.konami.loveplusevery/
Internal Storage/Android/obb/jp.konami.loveplusevery/

The OBB file can be extracted as a zip file, then the contents inspected with Asset Studio. No pre-processing is needed to make extract the assets. 

Special treatment is required for all assets in the main LovePlus EVERY code. 
2D, sprite and normal text assets are encoded using a constant 10-byte XOR key. The key can be found by assuming that the first 10 bytes are from the standard UnityFS header. (55 6E 69 74 79 46 53 00 00 00 00)
Audio assets need to be extracted from Asset Studio first before they can be XOR-decoded. Once extracted from Asset Studio, they need to be XOR-decoded, then extracted from Asset Studio once again using the same method as the aforementioned assets. 
In-game pictures are XOR-encoded with a constant XOR key as well, but instead of 10 bytes the key is 8 bytes. By XOR-ing the in-game picture with a standard JPG header (first 16 bytes are FF D8 FF E0 00 10 4A 46 49 46 00 01 01 00 00 01) the 8-byte XOR key can be found. 

To save space in the player's phone, sound clips are only downloaded and saved when needed. There is no option to download everything from the server, so I cannot provide any sound clips for Rinko or Nene. 


QuickBMS script for all LovePlus EVERY assets except for in-game photos

```
######Copy the lines below to a .txt file, then rename ext to .bms######

Get OUTPUT_NAME basename
String OUTPUT_NAME + "_decode.unity3d" #final file name

#Obtain key

filexor "\x55\x6E\x69\x74\x79\x46\x53\x00\x00\x00\x00"
getdstring KEY 0x0A
set KEYBUFFER string ""
for i = 0 < 0x0A
    getvarchr C KEY i byte
    string KEYBUFFER + C
    string KEYBUFFER + " "
next i

#Use key to unlock file

filexor KEYBUFFER

get SIZE asize
log OUTPUT_NAME 0 SIZE

#############End of Love Plus EVERY assets decoding script#############
```

QuickBMS script for all LovePlus EVERY in-game photos

```
######Copy the lines below to a .txt file, then rename ext to .bms######

# Decryption for Love Plus EVERY ingame pictures

Get OUTPUT_NAME basename
String OUTPUT_NAME + ".jpg"

#Obtain key

FileXOR "\xFF\xD8\xFF\xE0\x00\x10\x4A\x46\x49\x46\x00\x01\x01\x00\x00\x01"
getdstring KEY 0x08
set KEYBUFFER string ""
for i = 0 < 0x08
    getvarchr C KEY i byte
    string KEYBUFFER + C
    string KEYBUFFER + " "
next i

#Use key to unlock file

filexor KEYBUFFER

get SIZE asize
log OUTPUT_NAME 0 SIZE

##########End of LovePlus EVERY in-game photos decoding script#########
```
## Post #6
- Username: g1379075
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 19, 2023 2:05 pm
- Post datetime: 2023-08-19T06:12:56+00:00
- Post Title: Love Plus Every

Thanks to Moonstone1024 for his groundbreaking work, but the second code doesn't seem to work. Fortunately, I successfully extracted the model file in it, based on this, I hope someone can bring us something new. here is the download link:
[https://mega.nz/file/tKYQ3Rxa#ihQsNLuV- ... 2YNMGwn72Q](https://mega.nz/file/tKYQ3Rxa#ihQsNLuV-RryKvF3CUCmbwMAncYZkcZIh2YNMGwn72Q)

[https://mega.nz/file/AG5UhQKC#0Gp6mmsME ... 9p_bsjxfN4](https://mega.nz/file/AG5UhQKC#0Gp6mmsMEGlQeR3G1HNw1TobIa_m5vIT79p_bsjxfN4)

[https://mega.nz/file/pOxXlA4B#8GIWUpI8W ... z3ScWtL2Ck](https://mega.nz/file/pOxXlA4B#8GIWUpI8WScSiuDbC-YGocUq9OX0D1-Wfz3ScWtL2Ck)
