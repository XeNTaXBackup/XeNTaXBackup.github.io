## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2014-04-02T10:59:36+00:00
- Post Title: New version of MS-ADPCM?

Batman Arkham Origins Blackgate Deluxe Edition and Cabela's Hunting are using this "new" code, i can play  Cabela's files with Vgmstream, but the game can't play the pcm files and Batman Arkham Origins Blackgate files can't be played.

Here is how looks

```
   /å)Q¨€ºš’If„ñ|Šˆ˜CÉ¯aÚ£®ûþ(  ˜r‚œ12°ŠEÛ%ˆ°	Ÿ"©"¸Ü«
š ’	¼þ5   ‹!‘(Á2‚Ë!DÁžcª)#€
¨¬@C¸Ï$ª)„ÿ ù‰º(2è¼;ñŒÀ›Ð"ˆp0ûgª)€ˆh0 ¨"ª’ÝŠ(Ù«Š)B0g‚:£<Âx„ª0¡Œ‚1 ˆ™Ý¹2Ê™˜)…m¡0Å[£‰x•ºA3ÀšÈ(!„þ + ‘ûxô 	€ˆ¨À¯ š˜h”[ðaÁ:†ªh‚«‹: ›˜48¢
“­	%ý¸¬ ‰#¨Xàª	‚+…(æF €¹ª(2#€Ë¬‰	Äž4ÊH‚	›)Gû" Ø«"ˆ Ió0 »S0‚@3ÊH¬ òg»A#¨Cš€‰Xòš	ø= è«@“ˆ"3¸(€›˜™	6˜ˆ s¡q‘–2 ¾œŠ€¨™ëÉœr²*ëŠ Êª	¹"f: !¸#Ùª’«È<²œwÊË	©gÊD¨$¹‹ê1 '˜‰’C½’i°‹¹*#0e$™1ƒœ’ßªÚ9wí= +7©‰¼#¹`ÁI©ª  Œ5É
$©	€­B‘«S‘	žô2 !4±9)©»(!E‰sØ›ˆ(R$w¡«14óõ9 0’9›’ÏB¡5‚ˆCÐ¾8ƒ½3¸‹S‘žÊÆ&6 04²¼»¼¼Ë‰€B1R€ßš™1ºQ©‚íš¸ù1 9F°"˜2±-ƒ	#2º©Z5ÈÿIÉ	# 	&ø: ˜	 sÑœˆB„¿)“®8„ÌC‚Ìš €‹1 8 
```
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-04-02T13:51:28+00:00
- Post Title: New version of MS-ADPCM?

Nope, just wwise variant of ima adpcm, same used in payday 2, and others. according to me, I am dumb! here's his tool for it.

[http://hcs64.com/files/ima_rejigger2.zip](http://hcs64.com/files/ima_rejigger2.zip)
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2014-04-02T14:46:38+00:00
- Post Title: New version of MS-ADPCM?

Aah WWise again...

Works great, thanks
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2014-04-03T13:26:16+00:00
- Post Title: New version of MS-ADPCM?

> Reply from Pepper
>
> Nope, just wwise variant of ima adpcm, same used in payday 2, and others. according to hcs, it's just messed up blocks or something.

Two points:
1. It is most similar to MS IMA, with lots of redundant data in frame headers to allow frame-accurate seeking.
2. I am not confident that decoding it as MS IMA, after rejiggering, is completely correct.
## Post #5
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-04-03T18:24:21+00:00
- Post Title: New version of MS-ADPCM?

> Reply from hcs
>
> Pepper wrote:Nope, just wwise variant of ima adpcm, same used in payday 2, and others. according to hcs, it's just messed up blocks or something.

Two points:
1. It is most similar to MS IMA, with lots of redundant data in frame headers to allow frame-accurate seeking.
2. I am not confident that decoding it as MS IMA, after rejiggering, is completely correct.
Sorry! thanks for the correction.
