## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-21T06:10:38+00:00
- Post Title: [Request] God Man .PAK Files

Hope somebody can give a hand with that file its .pak file from this game

Game: God Man
[http://www.godman.com.tw/](http://www.godman.com.tw/)
Container: PAK

Sample in repository
[http://www.mediafire.com/download.php?g5az21ij3qxvql5](http://www.mediafire.com/download.php?g5az21ij3qxvql5)

This its small .PAK file other are something huge but if need i can upload in parts
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-21T13:43:52+00:00
- Post Title: [Request] God Man .PAK Files

looks like they are zip files protected with password and probably using a sort of obfuscation on the filenames
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-22T06:31:26+00:00
- Post Title: [Request] God Man .PAK Files

Then we can do unpack?'
## Post #4
- Username: runaum
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 03, 2012 8:24 am
- Post datetime: 2012-07-22T16:54:18+00:00
- Post Title: [Request] God Man .PAK Files

> Reply from Rimbros
>
> Then we can do unpack?'

I'll try to help you. It's a ZIP archive with replaced signs (504B -> 555A) and encrypted file names and content (it's not a classic ZIP password encryption, may be some byte modification like 'xor'). STUNS cannot extract anything from it, so we need to understand what algo used and decrypt this content.

UPD1
I found a key for name encryption: $B2, it's primitive xor'ing.

UPD2
Content compressed via Deflate, but encrypted w/ something different 'xor'. I'll try to brute xor-key (byte) - no results.

UPD3
To open this Archive w/ WinRAR (for example) we need to do few steps:
1. Replace $04035a55 -> $04034b50, $08075a55 -> $08074b50, $02015a55 -> $02014b50, $06055a55 -> $06054b50;
2. XOR all filenames in local file headers w/ $B2;
3. Delete four 'junky' bytes from the end of every central records (this 4 bytes is not extra field or file comment, all lengths are nulled. So, as i understand, there is a passwords for some encryption algo, not original PKWARE ofc);
4. Replace names in central records w/ names from local file headers;
5. Fix end record w/ correct central record offset;
6. Fix end record w/ correct central records size.
I analyze this file w/o executable before. At this moment I understand that it's really needed to complete this work 

Guys, i'm sorry for my primitive English.
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-23T04:26:49+00:00
- Post Title: [Request] God Man .PAK Files

Thanks runaum its good advance. Hope aluigui can read this and made one .bms with this info u found..
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-24T10:15:24+00:00
- Post Title: [Request] God Man .PAK Files

I'm trying this script: [viewtopic.php?p=67440#p67440](http://forum.xentax.com/viewtopic.php?p=67440#p67440)

I modified it to use deflate (when the flag == 9), but it's just giving an error. Not sure if I am missing something.
Doesn't look wrong: the file entry starts with UZ\x03\x04, followed by some stuff and then the name.

Right after the name is the start of the data, and after the data is finished you would see UZ\x07\x08, followed by some integer and the compressed and uncompressed sizes.

Haven't tried to manual replacing and stuff cause it seems kind of tedious, but if that works and data is just normal zip compression not sure where I'm messing up.
## Post #7
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-25T07:21:13+00:00
- Post Title: [Request] God Man .PAK Files

Sounds complicate really, but its good advance finale. btw i dont think can be posible maybe, aluigui already see this format and i think he cant decompress too, then we need search another skills to decompress.
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-30T21:02:07+00:00
- Post Title: [Request] God Man .PAK Files

any news?
