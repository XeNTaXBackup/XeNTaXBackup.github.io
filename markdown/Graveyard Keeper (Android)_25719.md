## Post #1
- Username: Vii
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 10, 2022 9:16 pm
- Post datetime: 2022-08-20T22:02:11+00:00
- Post Title: Graveyard Keeper (Android)

Hello. I'd like to translate a android game called Graveyard Keeper. I used UnityEX and AssetStudioGUI but i can't find localization file. I could only find the font. Can someone help me please?
Sorry for bad English.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-21T13:08:27+00:00
- Post Title: Graveyard Keeper (Android)

Try this [https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
## Post #3
- Username: luatsenpai
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 21, 2020 8:08 am
- Post datetime: 2022-08-23T09:44:34+00:00
- Post Title: Graveyard Keeper (Android)

text file is c11a5b4263a68544192ba3c175e91953 in obb
for font file: use NGUI, it paid in assets store of unity
For dump text:
1. Use il2cppdumper GUI, then dar and drop .apk file into window Il2cppdummper
2. Extract .obb file, then copy all file in \assets\bin\Data\ in apk file, then copy to extract obb folder
3. Copy all dump dll in step 1 into Manage Folder
4. Use UABE, then choose tools > Get Script
5. Export Dump


Edit: I write wiki tutorial for dump monobehaviour with image, here is link [https://github.com/luatsenpai/Unity-Mon ... orial/wiki](https://github.com/luatsenpai/Unity-Monobehaviour-Dump-Tutorial/wiki)
