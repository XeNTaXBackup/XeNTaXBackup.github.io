## Post #1
- Username: burango
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 06, 2009 12:13 am
- Post datetime: 2009-12-05T20:48:24+00:00
- Post Title: Compressed text on MH2 (PS2)

Hy everyone  during Monster Hunter Dos translation I ran into some portion of text I wasn't able to modify  
I'm using Mad Edit, an Hex Editor set on CP932 and this is what I mean

村のPﾍれｱＵA
~B00ボタンで｢ｹ。
気ｈ   ﾂけて忽ｫて
-)ｶAり待ｇﾜ～す

All the dialogue section is so messed up   

I did some tries on ~B00ボタンで｢ｹ。
Actually in the hex it is as

7E 42 30 30 83 7B 83 5E 83 93 82 C5 A2 12 B9 10 81 42

instead of how I see it in the game ~B00ボタンで出発です。
It should be in the hex as

7E 42 30 30 83 7B 83 5E 83 93 82 C5 A2 12 8F 6F 94 AD 82 C5 82 B7 81 42

so A2 12 B9 10 is the compression for 8F 6F 94 AD 82 C5 82 B7 but I can't consider this section apart... I found something about LZSS but I saw that the variants are a lot
the file I tried to translate is a data.bin and is named AFS... 
any suggestions  thanks
## Post #2
- Username: burango
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 06, 2009 12:13 am
- Post datetime: 2009-12-08T11:08:00+00:00
- Post Title: Compressed text on MH2 (PS2)

To tell the truth I don't know if this is a compressed text... from what I saw the game in some portions doesn't save any byte with this 'encoding'  still I can't touch this encoded section without altering the rest of the dialogue structure... can I call this encryption? However I attached the beginning of the dialogue section in text format; actually the dialogue text starts from the 00000370 offset... thanks any help is appreciated 
[Dialogue Section.rar](https://xentaxbackup.github.io/file/2601_Dialogue Section.rar)
