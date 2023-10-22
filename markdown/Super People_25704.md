## Post #1
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-08-16T16:40:12+00:00
- Post Title: Super People

[https://store.steampowered.com/app/1190 ... ER_PEOPLE/](https://store.steampowered.com/app/1190340/SUPER_PEOPLE/)

The game uses Unreal but it seems some of the files are customized, probably xored or encrypted but I'm not sure, I wonder if anyone can figure it out; when I extracted all the contents I found some duplicates and some of them are in plain UE4 format and others look different:

Regular UE4 format for a character:

```
0000h: 1F 01 00 00 00 00 00 00 F7 00 00 00 00 00 00 00  ........÷....... 
0010h: 04 00 00 00 00 00 00 00 00 F2 FF FF FF DA 00 00  .........òÿÿÿÚ.. 
0020h: 00 00 00 00 00 0C 00 00 00 00 00 00 00 14 4C 00  ..............L. 
0030h: 00 00 00 00 00 36 01 00 00 00 00 00 00 00 04 00  .....6.......... 
0040h: 00 00 DA 00 00 00 00 00 00 00 36 01 00 00 00 00  ..Ú.......6..... 
0050h: 00 00 DF 4B 00 00 00 00 00 00 17 01 00 00 00 00  ..ßK............ 
0060h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0070h: 00 00 00 10 01 00 00 00 00 00 00 36 01 00 00 00  ...........6.... 
0080h: 00 00 00 08 00 00 00 00 00 00 00 FB 00 00 00 00  ...........û.... 
0090h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
00A0h: 00 00 00 00 01 00 00 00 00 00 80 3F D9 00 00 00  ..........€?Ù... 
00B0h: 00 00 00 00 73 00 00 00 00 00 00 00 04 00 00 00  ....s........... 
00C0h: 00 00 00 00 00 00 00 00 00 DB 00 00 00 00 00 00  .........Û...... 
00D0h: 00 0C 00 00 00 00 00 00 00 04 00 00 00 00 00 00  ................ 
00E0h: 00 CE 00 00 00 00 00 00 00 00 00 00 00 00 29 00  .Î............). 
00F0h: 00 00 00 00 00 00 36 01 00 00 00 00 00 00 4C 01  ......6.......L. 
0100h: 00 00 00 00 00 00 16 01 00 00 00 00 00 00 00 00  ................ 
0110h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 24  ...............$ 
0120h: 00 00 00 00 00 00 00 22 00 00 00 00 00 00 00 00  ......."........ 
0130h: 00 00 00 00 00 00 00 00 00 25 00 00 00 00 00 00  .........%...... 
0140h: 00 22 00 00 00 00 00 00 00 00 00 00 00 00 00 00  .".............. 
0150h: 00 00 00 2D 00 00 00 00 00 00 00 22 00 00 00 00  ...-.......".... 
0160h: 00 00 00 00 00 00 00 00 00 00 00 00 00 18 00 00  ................ 
0170h: 00 00 00 00 00 22 00 00 00 00 00 00 00 00 00 00  .....".......... 
0180h: 00 00 00 00 00 00 00 27 00 00 00 00 00 00 00 22  .......'......." 
0190h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01  ................ 
01A0h: 00 2C 00 00 00 00 00 00 00 22 00 00 00 00 00 00  .,......."...... 
01B0h: 00 00 00 00 00 00 00 00 00 00 00 2B 00 00 00 00  ...........+.... 
01C0h: 00 00 00 22 00 00 00 00 00 00 00 00 00 00 00 00  ..."............ 
01D0h: 00 00 00 00 00 17 00 00 00 00 00 00 00 22 00 00  .............".. 
01E0h: 00 00 00 00 00 00 00 00 00 00 00 00 00 01 00 3D  ...............= 
01F0h: 01 00 00 00 00 00 00 73 00 00 00 00 00 00 00 04  .......s........ 
```


Other format found for the same character:

```
0000h: E8 8A C8 82 E7 B7 BF FF E8 8A C8 82 FD FD FF F7  èŠÈ‚ç·¿ÿèŠÈ‚ýýÿ÷ 
0010h: E8 8A C8 82 FF FF FF FE E8 8A C8 82 FF FF FF EF  èŠÈ‚ÿÿÿþèŠÈ‚ÿÿÿï 
0020h: C8 82 C8 82 00 00 00 00 C8 82 C8 82 AA AA 6A A9  È‚È‚....È‚È‚ªªj© 
0030h: E8 82 C8 82 D5 55 55 F5 E8 8A C8 82 F7 7F FF FF  è‚È‚ÕUUõèŠÈ‚÷ÿÿ 
0040h: E8 8A C8 82 FD FD FF FF E8 8A C8 82 FE FE FE FA  èŠÈ‚ýýÿÿèŠÈ‚þþþú 
0050h: C8 82 C8 82 00 00 00 00 E8 8A C8 82 F7 7D DF FF  È‚È‚....èŠÈ‚÷}ßÿ 
0060h: C8 8A C8 82 FF D7 FF FF E8 8A C8 82 7F FD FF DF  ÈŠÈ‚ÿ×ÿÿèŠÈ‚ýÿß 
0070h: E8 8A C8 82 FD DF FF FF E8 8A C8 82 EF EF EF FF  èŠÈ‚ýßÿÿèŠÈ‚ïïïÿ 
0080h: C8 8A C8 82 FF FF BF FF E8 8A C8 82 F7 D7 D7 F7  ÈŠÈ‚ÿÿ¿ÿèŠÈ‚÷××÷ 
0090h: E8 8A C8 82 FF 7F FF FF C8 82 A8 82 02 0A 00 00  èŠÈ‚ÿÿÿÈ‚¨‚.... 
00A0h: C8 82 C8 82 00 00 00 00 C8 8A C8 82 DF FF FF FF  È‚È‚....ÈŠÈ‚ßÿÿÿ 
00B0h: C8 8A C8 82 FF FF FB FF C8 8A C8 82 FF 7F F7 FF  ÈŠÈ‚ÿÿûÿÈŠÈ‚ÿ÷ÿ 
00C0h: C8 8A C8 82 FF FF FF F5 C8 8A C8 82 FF FF FF FE  ÈŠÈ‚ÿÿÿõÈŠÈ‚ÿÿÿþ 
00D0h: C8 8A C8 82 FF FF F9 FD E8 8A A8 82 FF FF FE DF  ÈŠÈ‚ÿÿùýèŠ¨‚ÿÿþß 
00E0h: C8 8A C8 82 FF FF FF FE C8 8A C8 82 FF FF FE FA  ÈŠÈ‚ÿÿÿþÈŠÈ‚ÿÿþú 
00F0h: C8 82 A8 82 AF AF AF BF C8 89 48 83 FF FF FF FF  È‚¨‚¯¯¯¿È‰Hƒÿÿÿÿ 
0100h: C8 8A C8 82 7F 7F FF 7F C8 82 A7 82 AA AA AA A8  ÈŠÈ‚ÿÈ‚§‚ªªª¨ 
0110h: C8 82 A8 82 FE FE FA EA A8 8A A8 82 75 55 5F 55  È‚¨‚þþúê¨Š¨‚uU_U 
0120h: C8 82 A7 82 AA BA AA AA C8 82 A7 82 2A AA AA AA  È‚§‚ªºªªÈ‚§‚*ªªª 
0130h: C8 8A A8 82 FF FF FE FF A8 8A C8 82 55 5D 7F 7D  ÈŠ¨‚ÿÿþÿ¨ŠÈ‚U]} 
0140h: C8 82 A7 82 AA AA AA 22 C7 82 A8 82 7F FF FF FF  È‚§‚ªªª"Ç‚¨‚ÿÿÿ 
0150h: A8 82 A7 82 AA A2 A2 AA C7 82 A8 82 EB EF FF FF  ¨‚§‚ª¢¢ªÇ‚¨‚ëïÿÿ 
0160h: A8 82 A7 82 AA AA AA AB C8 82 A7 82 0A 2A AA AA  ¨‚§‚ªªª«È‚§‚.*ªª 
0170h: C8 82 A7 82 A0 80 00 02 C8 82 A8 82 AE AA AA A8  È‚§‚ €..È‚¨‚®ªª¨ 
0180h: E8 8A C8 82 55 55 55 FD 08 8B C8 82 FF FD F5 F5  èŠÈ‚UUUý.‹È‚ÿýõõ 
0190h: 08 8B C8 82 AA AA AA AB 09 8B E8 8A FF BF BF BF  .‹È‚ªªª«.‹èŠÿ¿¿¿ 
01A0h: 29 8B E8 8A BF BF BF AB 29 8B 08 8B AB AB AB AB  )‹èŠ¿¿¿«)‹.‹«««« 
01B0h: 29 8B 09 8B AF AF AE AA 2A 8B 29 8B F5 F5 FD FD  )‹.‹¯¯®ª*‹)‹õõýý 
01C0h: 09 8B 29 8B AA A9 A5 99 29 8B 09 8B EA EF AA AB  .‹)‹ª©¥™)‹.‹êïª« 
01D0h: 29 8B 09 8B BE AB FF FF 29 8B 09 8B FE FB EF BF  )‹.‹¾«ÿÿ)‹.‹þûï¿ 
01E0h: 29 8B 09 8B AF FF FF FE 4A 8B 09 8B FF FF FD F5  )‹.‹¯ÿÿþJ‹.‹ÿÿýõ 
01F0h: 29 8B 09 8B FF FF FE EA 09 93 09 8B F5 FF 55 55  )‹.‹ÿÿþê.“.‹õÿUU 
0200h: 09 93 09 8B 7D FF 55 55 09 93 09 8B 57 FF 55 55  .“.‹}ÿUU.“.‹WÿUU 

```


There are a few samples here, I think all of them are supposed to be the same file but with different xor/encryption maybe:

[https://mega.nz/folder/db4hTJAA#PwAQ5FfpgXAwFDfjwIXo5g](https://mega.nz/folder/db4hTJAA#PwAQ5FfpgXAwFDfjwIXo5g)
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-08-21T19:51:19+00:00
- Post Title: Super People

@GDL: It's issue with the script, combined with internal quickbms problems. You can try to use latest beta versions (0.11.1) without -o option and observe results. The game is using modified package format, but output is being mislabeled for some entries or corrupted due to mislabeling and automatic overwriting, that's what -o option is doing (only uexp and ubulk are affected). I just postponed further research on it.

Update: I took some time and fixed the script, it should now extract assets with correct names, which solves most issues.
