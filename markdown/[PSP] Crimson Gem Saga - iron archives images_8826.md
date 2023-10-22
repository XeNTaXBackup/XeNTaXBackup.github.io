## Post #1
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-04-24T16:18:39+00:00
- Post Title: [PSP] Crimson Gem Saga - iron archives images

With some [help](http://forum.xentax.com/viewtopic.php?f=10&t=8811) I was able to write a quickbms script that can extract the ar2 archives of Crimson Gem Saga. After some fiddling around with the extracted files I was able to convert them into a standard format. Id like to share with you how the images of the game are assembled in case somebody wants to get some cool sprites 

After extracting an nr2 archive (kind of a sprites only archive) with the following script:

```

idstring "iron"
endian little
get FSNOHEADER long
getdstring FILENAME 0x40
set FILENAME unicode FILENAME
goto 0x358
for i = 1 to 9999
   get ZSIZE long
   SavePos OFFSET
   clog i OFFSET ZSIZE 999999
   math OFFSET + ZSIZE
   goto OFFSET
next i
```

You get at least two files. The first file is some information for the game I guess, so that it knows how to animate the sprites and other info. All other files are images (sprites) with the following specifications: 8bit per pixel, littleendian, indexed color. The palette is NOT stored in one of the extracted files, its still in the nr2 archive starting at offset 0x58 with a size of 0x300 bytes. The palette is also littleendian and in BGR colour order with 3 bytes per colour.

Unfortunately I was not able to get information about the height/width of the images from the files I saw so far. Maybe its in the ELF or in another game archive. If anyone has a clue about this it would be nice to know.
To view and save the images I used [TileGGD](http://code.google.com/p/tiledggd/). Its easy with it to change the size of the image till it shows a good result like this:
[](http://www.apload.de/display-i173670bxvxqs.html)
## Post #2
- Username: LordSith
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 16, 2012 2:55 am
- Post datetime: 2012-09-04T15:08:42+00:00
- Post Title: [PSP] Crimson Gem Saga - iron archives images

Yes but with your settings in TileGGD I wasn't able to get the good setting to see some to the extrated .nr2 file. I have extract this file: ui_bonus_card.nr2 and got some 27 element form it and as you said the first file is some info and the others are sprites but I with TileCGD I cant get the good setting, I tried what you said with no good result I switch to 32 bit per pixel and then the image revealed but scabled... could point me were I have done something wrong?


See the attachement,

Thanks in advance for your works
[file_2.png](https://xentaxbackup.github.io/file/5761_file_2.png)
## Post #3
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-09-16T16:21:27+00:00
- Post Title: [PSP] Crimson Gem Saga - iron archives images

Did you used the palette data? Copy 0x300 bytes starting from the offset 0x58 from the nr2 file and save it as a new file. This file is your palette now. Open it separately in Tileggd. To chance the size of the image use the arrow left and right keys till it looks alright.
Maybe there are other imageformats used but I don't know. Good luck.
