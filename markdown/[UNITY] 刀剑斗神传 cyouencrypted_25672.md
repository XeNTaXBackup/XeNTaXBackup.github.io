## Post #1
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2022-08-06T22:06:43+00:00
- Post Title: [UNITY] 刀剑斗神传 cyouencrypted

Here a nice game using unity, BTW content seems encrypted. Could anyone take a look?



SIte: [http://djdsz.cy.com](http://djdsz.cy.com)

Download: [http://yddjdsz.the3.changyou.com/pc/mld ... 220542.exe](http://yddjdsz.the3.changyou.com/pc/mldj-officalBilling-2022-03-31-22-03-58-1.19.0_220542.exe)

Sample: [https://www.mediafire.com/file/mrorooq5 ... e.rar/file](https://www.mediafire.com/file/mrorooq5i3rkilv/sample.rar/file)
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-08-07T01:52:01+00:00
- Post Title: [UNITY] 刀剑斗神传 cyouencrypted

As for the DES(0x01) type, you should now be able to decrypt it.

```
set Name string "dec\\"
String Name + OUTPUT_NAME

math OFFSET = 12
get SIZE asize
math SIZE - OFFSET

encryption des "uEn8Th_:" "Th_:uEn8"
log Name OFFSET SIZE

```

As for AES(0x02), I can decrypt it on C# but don't know how to apply it to quickbms.
