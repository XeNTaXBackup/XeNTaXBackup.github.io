## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-08T00:35:14+00:00
- Post Title: [Resolved] Spritesheets in DS

Currently I'm using GlycerinMapViewer to load up images from an unpacked DS rom.
It asks for the NSCR/NCER file (the mapping?), a NCRG file (tiles and stuff), as well as a NCLR (the palette)

Which works and I'm getting nice images.
But then I found the spritesheets, and they have some PAL file instead of an NCLR. I'm guessing the PAL file is the palette.

Has anyone tried to grab spritesheets off DS roms? What can I use?
I grabbed some other NCLR file and confirmed that it is a spritesheet...looking image, but the palette was wrong so the color was kind of funny.

EDIT: resolved it after asking about how to use crystal tile and working with those palettes.
[mpc003.7z](https://xentaxbackup.github.io/file/4697_mpc003.7z)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-08T12:21:12+00:00
- Post Title: [Resolved] Spritesheets in DS

Actually, could this .pal file be what nintendo used for their older and/or maybe smaller stuff? I found a pal editor and it showed a palette of 3 colors, so maybe if I can just create an NCLR file...
## Post #3
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-08T15:51:47+00:00
- Post Title: [Resolved] Spritesheets in DS

> Reply from finale00
>
> Actually, could this .pal file be what nintendo used for their older and/or maybe smaller stuff? I found a pal editor and it showed a palette of 3 colors, so maybe if I can just create an NCLR file...
Isn't it a bit big for having just 3 colors?

In case you want to recreate a NCLR: [http://llref.emutalk.net/docs/](http://llref.emutalk.net/docs/)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-08T15:55:45+00:00
- Post Title: [Resolved] Spritesheets in DS

I don't know, it's ~40 bytes. Not sure if that is considered big =/
## Post #5
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-09-09T11:14:27+00:00
- Post Title: [Resolved] Spritesheets in DS

> Reply from finale00
>
> EDIT: resolved it after asking about how to use crystal tile and working with those palettes.
Could you post any information just to let others know whats going on with these .pal files pls?
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-09T13:33:15+00:00
- Post Title: [Resolved] Spritesheets in DS

[http://gbatemp.net/t307866-exporting-sp ... data-files](http://gbatemp.net/t307866-exporting-spritesheets-from-data-files)

Tinke can load pal files and then view the maps, tiles, or animations.

For crystal tile, you'd have to convert hex data to a palette, export it, then import it to the image of choice and then apply the palette.
