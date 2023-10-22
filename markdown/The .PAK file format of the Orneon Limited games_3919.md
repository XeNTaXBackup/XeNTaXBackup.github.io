## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-12-02T21:01:21+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: ubrax
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-03T10:10:06+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

Rapidshare is awful and banned. So I can't download the game. Is this a trial version of some kind by the way? 

Concerning the file, it looks like it is Zlib compressed.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-03T10:38:49+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

```

idstring "\xcf\x01"
get ZSIZE short
savepos OFFSET
clog MEMORY_FILE OFFSET ZSIZE 0x10000

get DUMMY byte MEMORY_FILE  # zip?
get FILES short MEMORY_FILE
for i = 0 < FILES
    math OFFSET += ZSIZE
    get NAMESZ byte MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get SIZE long MEMORY_FILE
    clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #4
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-12-03T17:24:19+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

Thanks Mr.Mouse and aluigi. I appreciate your help. Wish I had your wisdom! have a great weekend.
I can upload the game to one of my sites if you want to downlaod it. Sorry for the rapidshare links, I'll remember not to use it here next time.
regards
## Post #5
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2011-08-03T03:33:47+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

This bms can unpack the *.PAK file format of the Orneon Limited games ("Echoes of the Past - Royal House of Stone")
But can not unpack the *.PAK file format of the Orneon Limited games ("Secrets of the Dark Temple of Night")



007.jpg (228.06 KiB) Viewed 385 times


I guess need to revamp 
clog MEMORY_FILE OFFSET ZSIZE 0x10000
get DUMMY byte MEMORY_FILE  # zip?
Can anyone help me unpack the "Secrets of the Dark Temple of Night",thanks.
The game is [http://www.bigfishgames.com/download-ga ... index.html](http://www.bigfishgames.com/download-games/12927/secrets-of-the-dark-temple-of-night-ce/index.html)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-24T16:54:27+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

stop using rapidshare use mediafire or sendspace.
## Post #7
- Username: Bum61e
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 29, 2011 9:51 pm
- Post datetime: 2011-09-29T15:20:48+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

> Reply from aluigi
>
> Code: Select all# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "\xcf\x01"
get ZSIZE short
savepos OFFSET
clog MEMORY_FILE OFFSET ZSIZE 0x10000

get DUMMY byte MEMORY_FILE  # zip?
get FILES short MEMORY_FILE
for i = 0 < FILES
    math OFFSET += ZSIZE
    get NAMESZ byte MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get SIZE long MEMORY_FILE
    clog NAME OFFSET ZSIZE SIZE
next i
Didn't work with data.pak (460Mb) in Echoes of the Past 3 - The Citadels of Time CE:



Please help
## Post #8
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-09-30T05:34:29+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

Every file data is encrypted (with a simple XOR encryption), so first need to decrypt before we can decompess it with zlib.
Here are two passwords I found:
"Echoes of the Past 3- The Citadels of Time CE"  -> Xor password = 'e34596'
"Secrets of the Dark - Temple of Night CE"  -> Xor password = 'tm7224'

If someone finds another problematic Orneon Limited game, just let me know, and I'll try to find the appropriate password for that.

The modified lines for the QuickBMS script:

```
    clog NAME OFFSET ZSIZE SIZE
    filexor ""

Or:

    filexor  "0x74 0x6D 0x37 0x32 0x32 0x34" OFFSET   # Secrets of the Dark - Temple of Night CE
    clog NAME OFFSET ZSIZE SIZE
    filexor ""

```
## Post #9
- Username: Bum61e
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 29, 2011 9:51 pm
- Post datetime: 2011-09-30T11:12:34+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

Thanks man!
## Post #10
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-04-16T15:47:49+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

```
filexor  "0x65 0x34 0x31 0x33 0x33 0x39" OFFSET   # Echoes of the Past 4 - The Revenge of the Witch
```
## Post #11
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2012-04-16T16:11:22+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

Thank you Bacter, I appreciate it.
## Post #12
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-05-29T05:51:17+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

Here's the password for the QuickBMS script:

```
    clog NAME OFFSET ZSIZE SIZE
    filexor ""
```
## Post #13
- Username: fordisi
- Rank: Banned
- Number of posts: 11
- Joined date: Tue Aug 02, 2011 7:18 pm
- Post datetime: 2012-05-30T02:03:24+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

Thank you Bacter!
## Post #14
- Username: brandiw
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 20, 2012 6:57 pm
- Post datetime: 2012-07-19T05:36:49+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

> Reply from bacter
>
> Code: Select allfilexor  "0x65 0x34 0x31 0x33 0x33 0x39" OFFSET   # Echoes of the Past 4 - The Revenge of the Witch
doesn't work on 4
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-19T09:33:03+00:00
- Post Title: The *.PAK file format of the Orneon Limited games

try with "ufed80c5":

```
  filexor  "0x75 0x66 0x65 0x64 0x38 0x30 0x63 0x35" OFFSET
```
## Post #16
- Username: brandiw
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 20, 2012 6:57 pm
- Post datetime: 2012-07-19T10:26:13+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

thx a lot,aluigi,i'll try this later.
## Post #17
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-07-20T03:13:39+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

<Echoes of the Past 4 - The Revenge of the Witch> with
filexor  "0x65 0x34 0x31 0x33 0x33 0x39" OFFSET 
or     
filexor  "0x75 0x66 0x65 0x64 0x38 0x30 0x63 0x35" OFFSET
doesn't work on 4
Why??
## Post #18
- Username: amdl
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Apr 16, 2012 8:38 pm
- Post datetime: 2012-07-20T11:07:23+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

Echoes of the Past 4 - The Revenge of the Witch CE

I found Xor pass "ufed8Oc5"
instead of zero is an O

would be:

filexor  "0x75 0x66 0x65 0x64 0x38 0x4F 0x63 0x35" OFFSET

but neither opens.

well I have the bms

```
get ZSIZE short
savepos OFFSET
clog MEMORY_FILE OFFSET ZSIZE 0x10000

get DUMMY byte MEMORY_FILE  # zip?
get FILES short MEMORY_FILE
for i = 0 < FILES
    math OFFSET += ZSIZE
    get NAMESZ byte MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get SIZE long MEMORY_FILE

    # thanx bacter
    filexor  "0x75 0x66 0x65 0x64 0x38 0x4F 0x63 0x35" OFFSET
    clog NAME OFFSET ZSIZE SIZE
    filexor ""
next i
```


What am I doing wrong?

Thanks
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-20T11:47:23+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

ops for the 'O/0' :)

can you put the following line before the clog command?

```
print "XXX %SIZE% %ZSIZE%"
```
and then tell me what get reported by quickbms.
just to be sure that the file is compressed
## Post #20
- Username: amdl
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Apr 16, 2012 8:38 pm
- Post datetime: 2012-07-20T13:23:19+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

Thanks luigi, I hope I have done well

```
get ZSIZE short
savepos OFFSET
print "XXX %SIZE% %ZSIZE%"
clog MEMORY_FILE OFFSET ZSIZE 0x10000

get DUMMY byte MEMORY_FILE  # zip?
get FILES short MEMORY_FILE
for i = 0 < FILES
    math OFFSET += ZSIZE
    get NAMESZ byte MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get SIZE long MEMORY_FILE

    # thanx bacter
    filexor  "0x75 0x66 0x65 0x64 0x38 0x4F 0x63 0x35" OFFSET
    print "XXX %SIZE% %ZSIZE%"
	clog NAME OFFSET ZSIZE SIZE
    filexor ""
next i
```
## Post #21
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-20T17:58:40+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

I have found it: e43037

```
filexor  "0x65 0x34 0x33 0x30 0x33 0x37" OFFSET
```
## Post #22
- Username: amdl
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Apr 16, 2012 8:38 pm
- Post datetime: 2012-07-20T22:24:31+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

yeeeeeeeeeeees!!!!

aluigi thank you very much, you're amazing!
## Post #23
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-09-14T14:00:13+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

New game
The Agency of Anomalies: The Last Performance
Whok know the Xor pass?? Please help me.
Thanks
## Post #24
- Username: Marry
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2011 7:30 pm
- Post datetime: 2013-08-15T20:48:17+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

Hi everyone!
Help me, please   
New game from Orneorn limited's game - Echoes Of The Past 5: Kingdom Of Despair
Who know the Xor pass?

Download:  [http://www.mediafire.com/?kdl39nr4nmaib4q](http://www.mediafire.com/?kdl39nr4nmaib4q)

Thanks
## Post #25
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-16T07:59:46+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

> Reply from Marry
>
> Hi everyone!
Help me, please   
New game from Orneorn limited's game - Echoes Of The Past 5: Kingdom Of Despair
Who know the Xor pass?

Download:  http://www.mediafire.com/?kdl39nr4nmaib4q

Thanks

e53485

```
filexor  "0x65, 0x35, 0x33, 0x34, 0x38, 0x35" OFFSET
```
## Post #26
- Username: Marry
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jan 25, 2011 7:30 pm
- Post datetime: 2013-08-16T14:41:06+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

Ekey, thank you very much!!
## Post #27
- Username: Jreen
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 26, 2012 10:09 am
- Post datetime: 2013-12-08T02:07:14+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

Hi guys!
Help me, please  
New game from Orneorn limited's game:

The Agency of Anomalies Mind Invasion Collectors Edition
Who know the Xor pass?

Download:[http://www.downturk.net/1702645-the-age ... -0-te.html](http://www.downturk.net/1702645-the-agency-of-anomalies-mind-invasion-collectors-edition-v1-0-5342-0-te.html)
Thanks
## Post #28
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-09T17:08:16+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

> Reply from Jreen
>
> Hi guys!
Help me, please  
New game from Orneorn limited's game:

The Agency of Anomalies Mind Invasion Collectors Edition
Who know the Xor pass?

Download:http://www.downturk.net/1702645-the-age ... -0-te.html
Thanks

a45342

```
filexor  "0x61, 0x34, 0x35, 0x33, 0x34, 0x32" OFFSET
```
## Post #29
- Username: Jreen
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 26, 2012 10:09 am
- Post datetime: 2013-12-10T12:15:09+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

Thanks Ekey.
## Post #30
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2014-02-07T08:47:28+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

Hi guys!
Help me, please 
A New game from Orneorn limited's game:
Fatal Passion - Art Prison Collector's Edition
Who know the Xor pass?

Download:
[http://uploaded.net/file/wkk92b79/Fatal ... Prison.rar](http://uploaded.net/file/wkk92b79/FatalPassionArtPrison.rar) 
OR
[http://www.filefactory.com/file/6v9tr6c ... Prison.rar](http://www.filefactory.com/file/6v9tr6cw3mgx/FatalPassionArtPrison.rar) 

Thanks
## Post #31
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-07T12:12:23+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

> Reply from warwar
>
> Hi guys!
Help me, please 
A New game from Orneorn limited's game:
Fatal Passion - Art Prison Collector's Edition
Who know the Xor pass?

Download:
http://uploaded.net/file/wkk92b79/Fatal ... Prison.rar 
OR
http://www.filefactory.com/file/6v9tr6c ... Prison.rar 

Thanks

a35149

```
filexor  "0x61, 0x33, 0x35, 0x31, 0x34, 0x39" OFFSET
```
## Post #32
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2014-02-13T08:25:30+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

> Reply from Ekey
>
> warwar wrote:Hi guys!
Help me, please 
A New game from Orneorn limited's game:
Fatal Passion - Art Prison Collector's Edition
Who know the Xor pass?

Download:
http://uploaded.net/file/wkk92b79/Fatal ... Prison.rar 
OR
http://www.filefactory.com/file/6v9tr6c ... Prison.rar 

Thanks

a35149
Code: Select allfilexor  "0x61, 0x33, 0x35, 0x31, 0x34, 0x39" OFFSET

Thanks Ekey
## Post #33
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2014-12-12T07:46:17+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

Hi guys!
Help me, please 
A New game from Orneorn limited's game:
Echoes of the Past 6: Wolf Healer CE [FINAL]
Who know the Xor pass?

download:
[http://www.usearchmedia.com/download/?k ... ction=home](http://www.usearchmedia.com/download/?kw=Echoes%20Of%20The%20Past%206&ad_domain=ads.ad-center.com&ad_path=/smart_ad/display&prod=1&ref=4953782&sf=eone&adserver=0.7.0-rc11&sfv=20&system_controller=signup&system_action=home)
## Post #34
- Username: caterno
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 28, 2014 10:38 pm
- Post datetime: 2015-10-23T12:30:24+00:00
- Post Title: Re: The *.PAK file format of the Orneon Limited games

```
 filexor  "0x65 0x36 0x34 0x33 0x38 0x39" OFFSET # Echoes Of The Past 6: Wolf Healer
```
