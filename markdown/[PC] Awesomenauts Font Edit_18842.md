## Post #1
- Username: DaveRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 11, 2017 10:58 am
- Post datetime: 2018-09-22T10:12:18+00:00
- Post Title: [PC] Awesomenauts Font Edit

Hello, I'm trying to localize Awesomenauts into Korean. Sorry for my bad English 

I can dump game files and modify the language file using Nodja's File Modder. ([https://github.com/Nodja/NautsFileModder](https://github.com/Nodja/NautsFileModder))
So I need to add Korean font to the game.


In Fonts folder, there are config files of each font. For example, Ethnocentric font's config file is this.

```
useBitmapFont	defaultFontButtons      0.85
useTrueTypeFont	ethnocentric_cyrillic.ttf	0.75	innerOutline
useTrueTypeFont	Chinese-Bold.ttf	0.75	innerOutline
```


For test, I changed font of this file to another one. But when I run the game with modified config file, that ethnocentric font is crashed and not shown. Just blank 

So, I replaced font file to another one. But when I run the game, it's crashed and isn't run.


What I should do..? Everything I tried was failed. Please help me
## Post #2
- Username: DaveRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 11, 2017 10:58 am
- Post datetime: 2018-09-24T04:57:51+00:00
- Post Title: [PC] Awesomenauts Font Edit

Oh, I solved this for myself 
Although font and config files are not compressed, File Modder compressed all game files.
I fixed this and works VERY WELL!!
