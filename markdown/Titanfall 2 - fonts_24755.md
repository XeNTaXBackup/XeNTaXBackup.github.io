## Post #1
- Username: sumilek86
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 04, 2021 5:16 am
- Post datetime: 2021-11-20T09:47:18+00:00
- Post Title: Titanfall 2 - fonts

Hi, I've a question. I need some advice on where to find the font files for the menu and dialogues of Titanfall 2? In our country we use diacritics and we need to add to it. I don't know it properly and I'm translating it for my technician. Alternatively, what thread to post a query about this in. Thanks 

If anyone wants to look and search,  we can agree on the files for the search. Thank you very much

The fonts that are in englishclient_frontend.bsp.pak000_dir.vpk are not used for menu and dilogues.

see screen.

[https://ulozto.cz/file/SVkosvc5NkqW/tit ... b1HwEuAj==](https://ulozto.cz/file/SVkosvc5NkqW/titanfall2-png#!ZGtmMGR2AmEvMJZ3LzRmZGN3ZGN2Myqkn042EHWMFUb1HwEuAj==)

another finding:
I set the language to czech cz_CS - but nothing.
When I put turkish characters, it works with en texts in en environment.
Czech characters don't have those fonts for menu and dialogues, but where to find those fonts?
## Post #2
- Username: sumilek86
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 04, 2021 5:16 am
- Post datetime: 2021-11-24T15:53:50+00:00
- Post Title: Titanfall 2 - fonts

We need to find and replace font for the menu with segoesc.ttf. This is to add Czech characters.

Files in vfont englishclient_frontend
titanfall-regular.vfont, notosanstc-regular.vfont,notosansjp-regular.vfont,metronicpro-semibold.vfont, metronicpro-regular.vfont.
The font's appearance in the menu will not change after replacement.

Files in the link:
[https://ulozto.cz/tamhle/4mIyU8FQXcsY/n ... xhKmt4ZD==](https://ulozto.cz/tamhle/4mIyU8FQXcsY/name/Nahrano-24-11-2021-v-16-50-59#!ZJDlAGR2AQL4MGZ5AzWxZTEyAQH1Z1ymL1uKBSScpSxhKmt4ZD==)

Can someone solve the technical problem? Thank you very much
## Post #3
- Username: sumilek86
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 04, 2021 5:16 am
- Post datetime: 2021-11-24T19:27:55+00:00
- Post Title: Titanfall 2 - fonts

Hi, I have a question again. We finally found the fonts, but we need advice again. How to get the texture back into the files
ui.rpak. What is the compression there. Does anyone have any experience? Thanks
## Post #4
- Username: sumilek86
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 04, 2021 5:16 am
- Post datetime: 2021-12-21T18:42:38+00:00
- Post Title: Titanfall 2 - fonts

Is it possible to save a decompressed file? Or is it possible to put the fontAtlas texture back into the ui(09).rpak file?

the fontAtlas.dds texture (0x152972b4df80e436.dds) is extracted by Legion.exe and it is a dds 8bit -R8 compression. Isn't there any way to at least decompress the ui(09).rpak file?

Texture 0x152972b4df80e436.dds is extracted by another pogram on rpak
files from ui(09).rpak .
It's a Legion.exe program and it displays the name like this.
When I open ui(09).rpak with program the texture is called fontAtlas.dds
fontAtlas.dds =0x152972b4df80e436.dds

link download with the file:
[https://www.mediafire.com/file/tgyqjqgt ... i.zip/file](https://www.mediafire.com/file/tgyqjqgtf2hrwun/ui.zip/file)

We need to export raw data file fontAtlas and how to decompress it and then compress it back.
Can you help? Thanks
