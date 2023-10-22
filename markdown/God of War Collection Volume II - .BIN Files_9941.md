## Post #1
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-12-10T05:45:25+00:00
- Post Title: God of War Collection Volume II - .BIN Files

Hello friends,

I would appreciate your help, I'm translating for ops3 this game and I need help with a tool to edit text or via Hexa help if necessary.

Ja researched a lot on the internet and thought it was done for the PSP, PS3 files are a bit different.

Here in xentax friend had the caws that creiu one tool to extract the text, and do not encounter more paker put it.

Please find attached the link below, the texts of asl 2 games and all languages, languages ​​sever any file in another language.

Here is the post link caws: [viewtopic.php?f=10&t=4548](http://forum.xentax.com/viewtopic.php?f=10&t=4548)
Here's a link to a Russian forum who also translated the game: [http://shedevr.org.ru/forum/viewtopic.php?t=3892](http://shedevr.org.ru/forum/viewtopic.php?t=3892)

Here is a brief explanation of how it should be done in the psp.

```
Look, what we have is a pointer. The first pointer to the address we have is 0x000000FE 0x0000013C. Then go at the beginning of the text block - 0x00000248. Plyusuem our resolve to text block pointer - 0x00000248 = 0x00000346 + 0x000000FE - here is our address line for the first pointer. All you can repeat the process and find the address of the starting line for the second asked. All the same, only the pointer is not equal 0x000000FE, and 0x00000211. Reading the text as the time until a byte indicating the end of the chain in this case is 0x00.
```


Links:
[http://www.mediafire.com/download.php?nxwsf3994fidhfb](http://www.mediafire.com/download.php?nxwsf3994fidhfb)
[http://www.mediafire.com/download.php?m22gbu1j178dnst](http://www.mediafire.com/download.php?m22gbu1j178dnst)
Hope I'm not asking for much, plus who knows how to please be sure to help.
## Post #2
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-01-24T13:22:35+00:00
- Post Title: God of War Collection Volume II - .BIN Files

friends,

As I did not find any tool or someone to help me with the texts of the God of War: Chains of Olympus and God of War: Ghost of Sparta I'm doing the hex translation is not very good however is what I can do.

I'm also carrying this translation to the PSP, the Chains of Olympus I managed to edit the file containing the sources game.bin game, found on a Russian forum to put the information in Tile molest.

However the ghost of sparta I found on a website however put the information and the result is quite different.

I will show to get better.

That's Chains of Olympus
Archive game.bin
Setting Tile Molest
8bpp linear codec, Mode-> Dimensional 2, Block Size-> Custom = 4 * 1.
Palette-> Import From-> File This offset = 128, 32bpp, Intel, size = 256.
you will see the image below: [http://i50.tinypic.com/30nivid.png](http://i50.tinypic.com/30nivid.png)

This beauty put on alright Ghost Of Sparta I found this link [http://ximwix.net/mirrors/rhdn/index.ph ... 683.0.html](http://ximwix.net/mirrors/rhdn/index.php@topic=11683.0.html) , only putting this information:

Archive game.bin
4bpp linear codec, Mode-> Dimensional, offset 0x00000060, Block Size-> Custom = 4 * 1.
Palette-> Import From-> File This offset = 32, 32bpp, Intel, size = 256.

The result was to be this: [http://s011.radikal.ru/i317/1011/8e/3533ccd1033c.jpg](http://s011.radikal.ru/i317/1011/8e/3533ccd1033c.jpg)

However what I have is this: [http://i45.tinypic.com/33bfm0g.png](http://i45.tinypic.com/33bfm0g.png)

Can anyone help me?

The file "game.bin" are attached. Files.rar
[files.rar](https://xentaxbackup.github.io/file/6143_files.rar)
## Post #3
- Username: Rkpaarsa
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 20, 2018 11:58 pm
- Post datetime: 2020-12-15T18:28:35+00:00
- Post Title: God of War Collection Volume II - .BIN Files

Can anybody help me extract The Mp3 File Out of .DAT File From GOD OF WAR GHOST OF SPARTA?
Here is The Sample.

Note> I Want BMS SCRIPT TO EXTRACT AND RE-IMPORT.
Thank You


Sample Files [https://zenhax.com/viewtopic.php?f=9&t=14596](https://zenhax.com/viewtopic.php?f=9&t=14596)
