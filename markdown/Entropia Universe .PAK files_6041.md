## Post #1
- Username: iller
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 13, 2011 12:30 am
- Post datetime: 2011-02-12T16:35:53+00:00
- Post Title: Entropia Universe .PAK files

I need to extract this type of file but i have tried everything and cant get it to work.
Anyone able to help out perhaps?

Couldnt attach the file but you can find one here on my dropbox [http://db.tt/bPdhsVQ](http://db.tt/bPdhsVQ)
You can also download the game for free and get a free account here. [http://www.planetcalypso.com/home/](http://www.planetcalypso.com/home/)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-14T18:15:04+00:00
- Post Title: Entropia Universe .PAK files

its a zip format with compression type "2" (ref: [http://aluigi.altervista.org/papers/bms/zip.bms](http://aluigi.altervista.org/papers/bms/zip.bms))

such a compression type would need the client downloaded.
## Post #3
- Username: iller
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 13, 2011 12:30 am
- Post datetime: 2011-02-14T19:50:26+00:00
- Post Title: Entropia Universe .PAK files

> Reply from WRS
>
> its a zip format with compression type "2" (ref: http://aluigi.altervista.org/papers/bms/zip.bms)

such a compression type would need the client downloaded.

thanks for the info but since i'm quite new to this with game extraction could you perhaps 
explain a bit more in detail? Is it possible to crack it so i can extract them etc?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-15T00:06:31+00:00
- Post Title: Entropia Universe .PAK files

> Reply from iller
>
> thanks for the info but since i'm quite new to this with game extraction could you perhaps 
explain a bit more in detail? Is it possible to crack it so i can extract them etc?

the pak is a standard format (zip) with a non-standard compression flag (2)

the next step would be to either lookup this compression type (if it exists) or reverse the method from the client exe
## Post #5
- Username: iller
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 13, 2011 12:30 am
- Post datetime: 2011-02-15T12:48:01+00:00
- Post Title: Entropia Universe .PAK files

> Reply from WRS
>
> iller wrote:thanks for the info but since i'm quite new to this with game extraction could you perhaps 
explain a bit more in detail? Is it possible to crack it so i can extract them etc?

the pak is a standard format (zip) with a non-standard compression flag (2)

the next step would be to either lookup this compression type (if it exists) or reverse the method from the client exe

Would it be possible to get help with that? I'm no where near capable of doing it myself.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-21T22:03:49+00:00
- Post Title: Entropia Universe .PAK files

as quick test I have tried my comtype2_scan with the compressed data and found nothing so the algorithm is not one of those supported by quickbms or (enough probable) there is an encryption in use
## Post #7
- Username: iller
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 13, 2011 12:30 am
- Post datetime: 2011-02-22T06:33:52+00:00
- Post Title: Entropia Universe .PAK files

> Reply from aluigi
>
> as quick test I have tried my comtype2_scan with the compressed data and found nothing so the algorithm is not one of those supported by quickbms or (enough probable) there is an encryption in use

As i thought then
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-07T15:05:13+00:00
- Post Title: Entropia Universe .PAK files

I did it, shoot it in quickbms:
[http://aluigi.org/papers/bms/entropia.bms](http://aluigi.org/papers/bms/entropia.bms)

the key is the md5 of a fixed key plus the crc of the file
the algorithm is rc4 plus 0x300 rounds before doing the decryption
## Post #9
- Username: iller
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 13, 2011 12:30 am
- Post datetime: 2011-03-07T15:56:19+00:00
- Post Title: Entropia Universe .PAK files

> Reply from aluigi
>
> I did it, shoot it in quickbms:
http://aluigi.org/papers/bms/entropia.bms

the key is the md5 of a fixed key plus the crc of the file
the algorithm is rc4 plus 0x300 rounds before doing the decryption

I LOVE you!!!
## Post #10
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-09-01T01:55:09+00:00
- Post Title: Entropia Universe .PAK files

> Reply from aluigi
>
> I did it, shoot it in quickbms:
http://aluigi.org/papers/bms/entropia.bms

the key is the md5 of a fixed key plus the crc of the file
the algorithm is rc4 plus 0x300 rounds before doing the decryption

This is truly awesome!

Is there any chance to modify an extracted file and inject it back into the .pak archive?
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-11-14T07:31:46+00:00
- Post Title: Entropia Universe .PAK files

I have just updated the script so that now it's a 100% valid script for the reimport mode:

[http://aluigi.org/papers/bms/entropia.bms](http://aluigi.org/papers/bms/entropia.bms)

you need to have the latest version of quickbms to use it.
## Post #12
- Username: Mazaraika
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 14, 2012 8:52 am
- Post datetime: 2012-12-14T11:24:51+00:00
- Post Title: Entropia Universe .PAK files

Awesome work aluigi! Ive been working with the cryengine 3 and this helped a lot just for some experimenting work! After seeing all the different types of files in there im finding it somewhat difficult to piece the 'puzzle' as to how everything fits in together. Can you give a summary of which files work together and what they achieve in game, and what that would mean in terms of getting it all to work in synergy? and maybe what conversions need to be done? I know the basic cryengine 2 to cryengine 3 conversion off dds files but opening and getting the rest of the files to work is rather confusing! thanks a lot!
## Post #13
- Username: JustinWaters
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 25, 2014 4:29 am
- Post datetime: 2015-01-29T04:46:04+00:00
- Post Title: Entropia Universe .PAK files

I know this thread is really old but I've been working with these Entropia files.

I can extract them but all the files look weird

A jpg from the from territories_arkadia_01.pak
[https://www.dropbox.com/s/0nhsjvp4le2ml ... 1.jpg?dl=0](https://www.dropbox.com/s/0nhsjvp4le2ml8e/01_01.jpg?dl=0)

The entire territories_arkadia_01.pak file
[https://www.dropbox.com/s/m5gqqgwk0rk0b ... 1.pak?dl=0](https://www.dropbox.com/s/m5gqqgwk0rk0bb4/territories_arkadia_01.pak?dl=0)

I was reading that there is a md5 somewhere and a file offset but not sure if this is still relevant.

I couldn't download your entropia.bms file as it doesn't exist anymore. Though I did download the latest version of quickbms.
