## Post #1
- Username: Lozzano
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 29, 2012 2:52 am
- Post datetime: 2012-02-28T18:58:03+00:00
- Post Title: [REQ] Tera Online

Hi,

So I was thinking of creating some sort of DB over the items in Tera, this would however require an insight in the gamefiles (I think). Does anyone know how to access them, or how to mine them and extract the information in a XML, CSV, SQL or some other sensible format? I am good with programming languages in generel, as well as datamanipulation etc., but the whole mining it seems not to be my area of expertiese. I have spent allmost all of today looking into the area, as well as looking into the gamefiles of Tera, but I seem to need help.

I hope someone can point me in the right direction, or if someone wants, join my "project" of creating a Tera Online Database for when the game launches. As there is no DB at this present time, there might even be a penny or two to be earned by this. 

In any case, help is apriciated and welcomed! Look me up if you've got something to say 

Best regards,
Lozzano
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-28T22:14:39+00:00
- Post Title: [REQ] Tera Online

So all this info contained in "Client\S1Game\DataCenter_Final.dat" file and encrypted with AES-128-CFB.
To decrypt is required key & iv hidden inside main executable and which protected by Themida.
Unpacked game client you can found -> [here](http://www.progamercity.net/other-mmo/3101-dev-tera-exiled-realm-arborea-themida-unpacked.html). Code for work DataCenter files obfuscated with Virtual Machine 

From another forum -> Example in openssl

[Encryption is AES-128-CFB]

```
openssl enc -aes-128-cfb -e -in data1.txt -out data2.txt
```

[Decryption is AES-128-CFB]

```
openssl enc -aes-128-cfb -d -in data2.txt -out data1.txt
```


```
openssl enc -aes-128-cfb -d  -K 123456789 -iv 128 -in data2.txt -out data1.txt
```


Search correct key & iv and will be decrypted
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-03T22:56:23+00:00
- Post Title: [REQ] Tera Online

1 - S1Data Loading -> 00D8A5A0
2 - AES Decrypting 00401880 -> 0044C680
3 - Additional Operations with DAT  Function Protected (Virtual Machine) -> 004A7D38
4 - Zlib Uncompress

Result



Decrypted and Decompressed [here](http://www.mediafire.com/?gw3pmj0llq08r50)
## Post #4
- Username: SystemIsGod
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 04, 2012 2:09 pm
- Post datetime: 2012-03-04T06:11:24+00:00
- Post Title: [REQ] Tera Online

What was the program you used to open the dat? Notepad doesn't work 100% so if you wouldn't mind shedding some insight, please.
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-04T10:18:28+00:00
- Post Title: [REQ] Tera Online

> Reply from SystemIsGod
>
> What was the program you used to open the dat? Notepad doesn't work 100% so if you wouldn't mind shedding some insight, please.
Use Hex editor. Text in Unicode format.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-04T10:30:19+00:00
- Post Title: [REQ] Tera Online

Use notepad++
Or any text editor that supports more than just ASCII........................
## Post #7
- Username: SystemIsGod
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 04, 2012 2:09 pm
- Post datetime: 2012-03-04T16:10:12+00:00
- Post Title: [REQ] Tera Online

Neither programs or anything similar you 2 listed really seem to help. Notepadd++ didn't and neither did any hex edit program I used.
## Post #8
- Username: Kritiker
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 18, 2009 8:30 pm
- Post datetime: 2012-03-14T13:53:32+00:00
- Post Title: [REQ] Tera Online

HexWorkshop works just fine.

I would like to know more about that file structure, i can read strings but to get anything more out of it is pretty much impossible. So maybe this file is still packed or whatever
## Post #9
- Username: cypeh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 15, 2012 6:44 am
- Post datetime: 2012-03-14T22:58:40+00:00
- Post Title: [REQ] Tera Online

Hey Ekey,

thanks a lot for pointing this out. But could you (or anyone else) explain how exactly did you find and retrieve the key&iv from the exe? I wanted to try the whole process myself but I'm kinda lost. :/
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-15T09:21:41+00:00
- Post Title: [REQ] Tera Online

@Kritiker
DC itself is a heavily-indexed XML-based database of some custom format. It consists of key-value sets, value and key arrays, tree structure and several index and hashing blocks.

@cypeh
Debugging
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-19T19:36:47+00:00
- Post Title: [REQ] Tera Online

Tool for decrypting -> [here](http://forum.xentax.com/viewtopic.php?f=32&t=8954)
