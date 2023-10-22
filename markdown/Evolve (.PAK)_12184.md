## Post #1
- Username: Splasher9
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 04, 2013 10:57 pm
- Post datetime: 2014-11-02T07:50:07+00:00
- Post Title: Evolve (.PAK)

Hello there, Xentax veterans.  :D 

As you probably know there was an open alpha run of the game Evolve made by Turtle Rock Studios, which also made Left 4 Dead. Pretty interesting content though. It's been only an alpha, but if anyone already wish try to open game archives .pak files, here they are:

<removed due forum rules>

As i get it the developers promise to add content to the game gradually. 

And here is some pics from the game, if someone is interested:
[https://mega.co.nz/#F!khoVmQAa!o3puUf8pVBKHKhwzHhJvLQ](https://mega.co.nz/#F!khoVmQAa!o3puUf8pVBKHKhwzHhJvLQ)
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2014-11-02T09:23:41+00:00
- Post Title: Evolve (.PAK)

It's almost identical to Crysis 3.
## Post #3
- Username: Splasher9
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 04, 2013 10:57 pm
- Post datetime: 2014-11-02T10:54:10+00:00
- Post Title: Evolve (.PAK)

So, it's a good news then, right? 

I've tried Crysis 3 pak extractor, CryUnpack and PakDecrypt on archives, but it didn't work out. So I guessing we need some fixed crysis 3 bms script for Evolve. Maybe someone good with coding will give us a hand then.
## Post #4
- Username: ProdigySim
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 06, 2014 12:40 pm
- Post datetime: 2014-11-06T04:42:44+00:00
- Post Title: Evolve (.PAK)

I would also be interested in this. If we assume that it's just a different decryption key, is there any documentation/references for how the key was found for other cryengine games? I've got some RE background and might be able to work on this with a little background information to jump start the process.
## Post #5
- Username: Splasher9
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 04, 2013 10:57 pm
- Post datetime: 2014-11-06T12:16:03+00:00
- Post Title: Evolve (.PAK)

From this topic [viewtopic.php?f=10&t=9818&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=9818&start=15):

>They keys (there's 16 of them) and IV are the PAK. But they're RSA encrypted with a fixed key (found inside the exe).

>As said Aluigi, author of quickbms, encryption key was stored in CrySystem.dll

Don't know, may help. If needed, I can upload any other files from alpha.
## Post #6
- Username: fu0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 06, 2014 11:47 pm
- Post datetime: 2014-11-06T15:57:23+00:00
- Post Title: Evolve (.PAK)

There's what looks to be a 140 word encryption key in Bin64_SteamRetail/StaticLauncher64.exe at the address $02B1D450, not gonna post it here because that's against the rules. Using that key in the Crysis 3 PakDecrypt just gives me 0kb zip files when they're extracted though, so I'm probably missing something else.
## Post #7
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2014-11-06T16:13:46+00:00
- Post Title: Evolve (.PAK)

Bumping this one. Interested as well
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-11-07T16:15:50+00:00
- Post Title: Evolve (.PAK)

> Reply from fu0
>
> Using that key in the Crysis 3 PakDecrypt just gives me 0kb zip files when they're extracted though, so I'm probably missing something else.
Because modified ZIP structure and modified XXTea Keys.

1) [ASR yeK](http://pastebin.com/eA7xqp2W)

2)

```

XXTea_Keys:
sub     ecx, 4E0AD646h
add     eax, 1691828Dh
add     ecx, 1A09D20Ch
add     eax, 171B8BBCh
```
## Post #9
- Username: Flackjack
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 08, 2014 4:12 am
- Post datetime: 2014-11-07T20:17:22+00:00
- Post Title: Evolve (.PAK)

Ok guys,I'm new here ,I love this game and would love to get my hands on some of the sound files for ringtones and whatnot for ex
I have tried these so called .Pak extractors and the thing I noticed is these extractors don't work. It has to be something made for the specific game,I bet you all know this since I'm the noob here.

Is there a way or software that would let me view and open this games files? I was assuming since it uses cry engine the crysis extractor would work but that failed also.

Keeping an eye out for this since I cannot do anything by myself yet due to lack of knowledge.
Any help from you guys would be awesome and if I can help in any way let me know.
## Post #10
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2014-11-07T20:53:20+00:00
- Post Title: Evolve (.PAK)

As far as I understood it is encrypted so there is no way to unpack it.
## Post #11
- Username: Flackjack
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 08, 2014 4:12 am
- Post datetime: 2014-11-09T18:55:57+00:00
- Post Title: Evolve (.PAK)

Isn't that true for most game releases nowadays?
Somehow people get around it.
## Post #12
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-11-09T23:13:34+00:00
- Post Title: Evolve (.PAK)

As stated it's Cryengine 3, so you just need to recompile the PakDecrypter from Cryengine 3 ([viewtopic.php?f=10&t=9818&start=30](http://forum.xentax.com/viewtopic.php?f=10&t=9818&start=30) )  but using the key Ekey provided. (and a small code change I guess per Item 2)
## Post #13
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2014-11-09T23:45:11+00:00
- Post Title: Evolve (.PAK)

Anyone up to the task if it is not that hard as volfin mentioned?

I don't have VistualStudio or any suitable compiler installed and even if I did i have no idea what changes required anyway.
## Post #14
- Username: Splasher9
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 04, 2013 10:57 pm
- Post datetime: 2014-11-10T16:34:13+00:00
- Post Title: Evolve (.PAK)

Yeah, agree with Kein.

I can barely into coding, so if anyone can help with the PakDecrypt for Evolve, will be grateful.
## Post #15
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2014-11-20T07:20:14+00:00
- Post Title: Evolve (.PAK)

bump?
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-20T10:15:19+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from Kein
>
> bump?

Well not easy modification if you are not C++ person. Change the key is easy but change the code it is not however.
## Post #17
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2015-01-15T11:55:30+00:00
- Post Title: Re: Evolve (.PAK)

Bump again.

Game will go into closed "public" beta in 1 day. New content will be available.
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-15T12:13:53+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from Kein
>
> Bump again.

Game will go into closed "public" beta in 1 day. New content will be available.
available only pre-load.
## Post #19
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2015-01-15T13:07:07+00:00
- Post Title: Re: Evolve (.PAK)

Have you tried to read whole message?
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-15T13:35:18+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from Kein
>
> Have you tried to read whole message?
So what?
## Post #21
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-01-18T04:20:23+00:00
- Post Title: Re: Evolve (.PAK)

Games out in beta now can be played anyone going to take a look?
## Post #22
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2015-01-18T22:36:12+00:00
- Post Title: Re: Evolve (.PAK)

Well I compiled pakdecrypt with Ekey's changes as specified. I Have no idea if it works or not as I don't have the game.  Good luck.
[PakDecryptEvolve.zip](https://xentaxbackup.github.io/file/8514_PakDecryptEvolve.zip)
## Post #23
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2015-01-19T02:01:04+00:00
- Post Title: Re: Evolve (.PAK)

thank you. but unfortunately it's still spitting out 0kb .zip files.
## Post #24
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2015-01-19T23:11:43+00:00
- Post Title: Re: Evolve (.PAK)

Yeah, it seems like encryption is too strong for anyone to bother without payment and extensive weeks of work.

Whatever then.
## Post #25
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2015-02-10T11:01:00+00:00
- Post Title: Re: Evolve (.PAK)

fyi game has been officially released. I have tried replace the old encryption key with ekey's key and compile but it seems not works for the full game.
## Post #26
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-02-11T16:46:22+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from Ekey
>
> 
Because modified ZIP structure
## Post #27
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2015-02-13T01:01:46+00:00
- Post Title: Re: Evolve (.PAK)

[http://sktest.aruarose.com/PakDecrypt_Evolve.7z](http://sktest.aruarose.com/PakDecrypt_Evolve.7z)

Fill RSAKeyData.bin with the key from the release version (should be 140 bytes).
## Post #28
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-02-13T05:27:52+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from Sir Kane
>
> http://sktest.aruarose.com/PakDecrypt_Evolve.7z

Fill RSAKeyData.bin with the key from the release version (should be 140 bytes).

I tried the closed beta key and no luck did you hardcode the other keys?
<link removed>
## Post #29
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2015-02-13T05:37:47+00:00
- Post Title: Re: Evolve (.PAK)

The key changed from the closed beta. Didn't hardcore/provide any keys to avoid potential problems.
## Post #30
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-02-13T05:39:03+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from Sir Kane
>
> The key changed from the closed beta. Didn't hardcore/provide any keys to avoid potential problems.
-snip- works now there was 2 keys inside staticlauncher the one you want to be looking for is here
## Post #31
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-02-23T09:10:20+00:00
- Post Title: Re: Evolve (.PAK)

can you please share key with me on PM ??
## Post #32
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2015-02-23T15:27:57+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from michalss
>
> can you please share key with me on PM ??
If he does - let me know too?
## Post #33
- Username: StuKKa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 21, 2011 11:41 pm
- Post datetime: 2015-02-24T22:04:03+00:00
- Post Title: Re: Evolve (.PAK)

I need the key too. Would be nice ... Thank you
## Post #34
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-02-25T08:19:58+00:00
- Post Title: Re: Evolve (.PAK)

Guys seriously it's not even hard

Download the 64bit version of this
[http://www.ntcore.com/exsuite.php](http://www.ntcore.com/exsuite.php)

find the running process then go into the modules of it

rightclick the module Evolve.exe or what ever the retail one is called

"Dump PE" save it somewhere


Open it inside of IDA and look for what i posted before.
## Post #35
- Username: StuKKa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 21, 2011 11:41 pm
- Post datetime: 2015-02-25T18:58:26+00:00
- Post Title: Re: Evolve (.PAK)

If you never worked this way, it's a bit confusing. 
I found the point in the file, but what do you mean "load into rax register"? 
A little bit more context would help.
## Post #36
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-02-26T07:56:16+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from StuKKa
>
> If you never worked this way, it's a bit confusing. 
I found the point in the file, but what do you mean "load into rax register"? 
A little bit more context would help.

  lea     rax, unk_142643C10

lea == load effective address in the register

it loads the address of the byte[] so unk_142643C10 if you look in IDA you can see the byte array values
 etc etc

There are two keys note
## Post #37
- Username: StuKKa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 21, 2011 11:41 pm
- Post datetime: 2015-02-26T19:28:26+00:00
- Post Title: Re: Evolve (.PAK)

Thank you, but it doesn't really worked out as expected (still could not extract, rsa error). Maybe I'm waiting for the models and skins to be published by someone, to create good render images of them for a small wiki (i don't like this ingame screenshots where you could see nothing of the details).
But thanks for the help, nice to see how to get into the file. Never thought about such a way.
## Post #38
- Username: dss539
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 22, 2015 6:02 am
- Post datetime: 2015-03-21T22:12:40+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from Sir Kane
>
> http://sktest.aruarose.com/PakDecrypt_Evolve.7z

Fill RSAKeyData.bin with the key from the release version (should be 140 bytes).

What did you have to change to make this support Evolve's format?
I recompiled the Crysis 3 PakDecrypt with the correct 140 byte key and the correct XXTea keys, but just like volfin's attempt, this yielded 0B zip files.
The extraction failed in ProcessCDR when checking the ehdr.Size.
Actual value 6, expected value 8.

Furthermore, I also tried your modified exe. This was more successful. Your version outputs .pak.zip files that are ~2kb smaller than the original .pak files.
However, 7-Zip is unable to open this file.
Have I misunderstood something?
## Post #39
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2015-03-23T21:30:44+00:00
- Post Title: Re: Evolve (.PAK)

The format of the encryption and signature data in the header comment changed (the 2kb or whatever less is that data). Also be aware that XXTEA isn't actually used.

7zip opens the decrypted files just fine for me.
## Post #40
- Username: dss539
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 22, 2015 6:02 am
- Post datetime: 2015-03-24T04:09:22+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from Sir Kane
>
> The format of the encryption and signature data in the header comment changed (the 2kb or whatever less is that data). Also be aware that XXTEA isn't actually used.

7zip opens the decrypted files just fine for me.

You're right.
I was stupidly using the wrong key.
Got it all sorted out, now. Thanks very much!

I am still curious about the exact source code you used, if you are interested in sharing.
## Post #41
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2015-04-04T18:07:14+00:00
- Post Title: Re: Evolve (.PAK)

Hmm....Only Closed Beta Should Work Right?
## Post #42
- Username: dss539
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 22, 2015 6:02 am
- Post datetime: 2015-04-04T18:55:16+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from lumekano
>
> Hmm....Only Closed Beta Should Work Right?
No, retail also works if you use the correct key.
## Post #43
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2015-04-05T00:12:23+00:00
- Post Title: Re: Evolve (.PAK)

ok Thx if That So...

btw , This is my Key ( rax, unk_14008C9B6 ) I'm Really Getting Stuck if I Try Looking For Key ( hex View ) in The IDA, Anyways Can U Gave Example Where's I Put The Key And How I Put Keys in the RSAKeyData.bin or Anyone Plz, Srry About Noobs, cuz This is My First Time  Use That Program ( I Know is Super Easy )

address in the register ???

array values ???

What is Worst Shame...
## Post #44
- Username: dss539
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 22, 2015 6:02 am
- Post datetime: 2015-04-05T05:05:31+00:00
- Post Title: Re: Evolve (.PAK)

Use a hex editor to write 140 bytes in the bin file.
As for finding the key, I really just lucked into it.
I spent a long time looking for it. The previously posted instructions weren't much help, even though theoretically they should have been.
Clearly I don't know what I'm doing.

However, I searched the entire dump for a string of bytes that looked similar to the previously mentioned key.
## Post #45
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2015-04-05T08:32:41+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from dss539
>
> Use a hex editor to write 140 bytes in the bin file.
As for finding the key, I really just lucked into it.
I spent a long time looking for it. The previously posted instructions weren't much help, even though theoretically they should have been.
Clearly I don't know what I'm doing.

However, I searched the entire dump for a string of bytes that looked similar to the previously mentioned key.

Huh?????? I thought Was impossible, Anyways thx to u cra0 and dss539 it Works.

So Hmm... Maybe I Will Update All Char Soon If Someone Ask Me About Download.
## Post #46
- Username: The009
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 06, 2015 1:38 am
- Post datetime: 2015-06-05T17:43:20+00:00
- Post Title: Re: Evolve (.PAK)

So going over this I got totally lost, if anyone is willing to pm me with a bit more info on getting this going or even updating the post with a bit clearer instructions that would be amazing.
## Post #47
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-06-06T09:18:45+00:00
- Post Title: Re: Evolve (.PAK)

SMT i dont get it ppl already have a key and decryptor, why someone cannot put it in here?! Personally dont need it but i simple dont get it...
## Post #48
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2015-06-09T13:05:36+00:00
- Post Title: Re: Evolve (.PAK)

Some Guys Seriously   ....

Whatever, Here Link :

warez links is not allowed here! You posted whole game..

And Have Fun  .
## Post #49
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2015-06-10T12:52:37+00:00
- Post Title: Re: Evolve (.PAK)

warez links is not allowed here! You posted whole game.. 

Lol This is Not Games Really , All I Upload Mega File is a 3ds Model And To Big For The Size 6.8GB . I Know The rules And Don,t Worry  .
## Post #50
- Username: FoxSingle
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 21, 2015 1:32 am
- Post datetime: 2015-08-20T17:35:52+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from lumekano
>
> warez links is not allowed here! You posted whole game.. 

Lol This is Not Games Really , All I Upload Mega File is a 3ds Model And To Big For The Size 6.8GB . I Know The rules And Don,t Worry  .

Maybe you have to re-write the link?
## Post #51
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2015-08-22T03:29:23+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from FoxSingle
>
> lumekano wrote:warez links is not allowed here! You posted whole game.. 

Lol This is Not Games Really , All I Upload Mega File is a 3ds Model And To Big For The Size 6.8GB . I Know The rules And Don,t Worry  .

Maybe you have to re-write the link?

U Should Ask Permission To Admins much as you can...
## Post #52
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-08-23T12:08:05+00:00
- Post Title: Re: Evolve (.PAK)

Scripts and other tools is not a problem, but extracted models in 6.8Gb of size could lead to copyright issues. Over PM that is completely OK.
## Post #53
- Username: FoxSingle
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 21, 2015 1:32 am
- Post datetime: 2015-09-08T16:21:36+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from michalss
>
> Scripts and other tools is not a problem, but extracted models in 6.8Gb of size could lead to copyright issues. Over PM that is completely OK.

Can you give a link only decryptor? I find it difficult to download as many GB, I'll unpack)
## Post #54
- Username: FoxSingle
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 21, 2015 1:32 am
- Post datetime: 2015-09-14T16:27:44+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from michalss
>
> Scripts and other tools is not a problem, but extracted models in 6.8Gb of size could lead to copyright issues. Over PM that is completely OK.

so what?
## Post #55
- Username: quill
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 03, 2015 8:18 pm
- Post datetime: 2015-10-08T12:20:10+00:00
- Post Title: Re: Evolve (.PAK)

dear gentlemen,
Is there someone  who can help me in decrypted the xml files present in the pc game Ryse son of rome? I am only a poor graphic and totally noob in coding:):)
it will be very very helpfull and i assure that is for education only. thanks
## Post #56
- Username: EinarTheRed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 22, 2015 5:00 am
- Post datetime: 2015-11-27T16:59:48+00:00
- Post Title: Re: Evolve (.PAK)

Did we get any progress with this? Someone have a .exe file they can/have posted to successfully unpacks the stuff?
## Post #57
- Username: MusicMantis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 19, 2015 7:07 pm
- Post datetime: 2016-02-17T09:03:22+00:00
- Post Title: Re: Evolve (.PAK)

The method described earlier works rather well. If you're not as proficient in this field then there are a couple of shortcuts you can take. I'll try to consolidate it all into this one post for convenience, but none of this is my thinking, it's all from the rest of this topic so far (specifically, this is me trying to write a very user-friendly version of cra0's already-thorough explanation).

First, you'll need the modified .pak decrypter. volfin posted it on the second page of this thread, I believe. It'll decrypt the .pak files but needs the encryption key first. To do all this, you'll also need a working copy of the game, a hex editor and this (get the multi-platform, recommended one):
[http://www.ntcore.com/exsuite.php](http://www.ntcore.com/exsuite.php)

1) Run the game exe. I did this with the release exe.
2) Alt tab out of it and run NTCore's Explorer Suite.
3) Find the evolve process in Explorer Suite. Right click, hit "Dump PE". You can now close the game and this program.
4) Open the dump in a hex editor and search for hex values (in HxD that's Search > Find > Data Type set to Hex-Values)
5) Search for 3081890281. There are multiple keys in the file, but this is how they all begin. I've found it's the second one that allows you to unpack the .pak files.
6) When you've found a value copy it from the start of the text you searched for 140 bytes. The length of the selection in HxD is 8C.
7) Open RSAKeyData.bin in your hex editor and paste the data. Double check the file size is 140 bytes.

If everything went well, dragging and dropping a .pak file onto PakDecrypt will result in a command window popping up. If it disappears instantly then your key was either too long, too short or didn't start at the right place. If the window pops up, you've correctly found a key. The decrypter will produce a .zip file in the same directory as the source and it'll be roughly the same size. 7zip and WinRAR should both open it. If you've got this file but those programs cannot open it, then you've used the wrong key. Go back to the 5th step and search again but this time use a different key. There are several in the file as previously mentioned.

Hopefully this explanation helps a few of the people who didn't quite get it still and thank you to those who actually did the heavy lifting here.
## Post #58
- Username: Shockwave98
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 25, 2016 4:58 am
- Post datetime: 2016-07-24T21:32:41+00:00
- Post Title: Re: Evolve (.PAK)

Hello, i literally registered here to join this Thread lol - anyways.
I've got so far that i've found 2 Keys in the Evolve Dump - but they both give me files that i cannot unzip with anything, both Keys arent working for me.
They are both 8C long so i'm kinda lost as to what i did wrong.

Would gladly appreciate any help c:
## Post #59
- Username: dss539
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 22, 2015 6:02 am
- Post datetime: 2016-07-24T21:47:44+00:00
- Post Title: Re: Evolve (.PAK)

Turtle Rock seems to have changed some things with the free to play release.
## Post #60
- Username: Shockwave98
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 25, 2016 4:58 am
- Post datetime: 2016-07-24T21:50:17+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from dss539
>
> Turtle Rock seems to have changed some things with the free to play release.

Could it possibly just be a new Key for the .pak files ? I still dont understand where the whole 3081890281 story comes from :I
## Post #61
- Username: Shockwave98
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 25, 2016 4:58 am
- Post datetime: 2016-08-01T22:43:44+00:00
- Post Title: Re: Evolve (.PAK)

Bump. Anyone ?
## Post #62
- Username: skills4u2envy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 27, 2016 2:17 am
- Post datetime: 2016-08-06T02:04:32+00:00
- Post Title: Re: Evolve (.PAK)

I'd also be interested in getting some updated files
## Post #63
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-08-06T07:33:01+00:00
- Post Title: Re: Evolve (.PAK)

Also interested!
I tried thecoreyburton's method, but no luck. I think the way to find the key is different now?

I have uploaded the EXE I dumped with NTCore's Explorer Suite.

[https://www.dropbox.com/s/fzb49x71e5fu7 ... d.rar?dl=0](https://www.dropbox.com/s/fzb49x71e5fu7bd/Evolve_Dumped.rar?dl=0)

If anyone wishes to have a look...
## Post #64
- Username: skills4u2envy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 27, 2016 2:17 am
- Post datetime: 2016-08-06T07:44:16+00:00
- Post Title: Re: Evolve (.PAK)

I'm fairly new to ripping, and don't have a lot of experience with pak files, but I found these in the .exe
Not sure if they'll help someone or not, I'll post them anyways.

```
30 82 01 0A 02 82 01 01 00 B1 AC B3 49 54 4B 97 1C 12 0A D8 25 79 91 22 57 2A 6F DC B8 26 C4 43 73 6B C2 BF 2E 50 5A FB 14 C2 76 8E 43 01 25 43 B4 A1 E2 45 F4 E8 B7 7B C3 74 CC 22 D7 B4 94 00 02 F7 4D ED BF B4 B7 44 24 6B CD 5F 45 3B D1 44 CE 43 12 73 17 82 8B 69 B4 2B CB 99 1E AC 72 1B 26 4D 71 1F B1 31 DD FB 51 61 02 53 A6 AA F5 49 2C 05 78 45 A5 2F 89 CE E7 99 E7 FE 8C E2 57 3F 3D C6 92 DC 4A F8 7B 33 E4 79 0A FB F0 75 88 41 9C FF C5 03 51 99 AA D7 6C 9F 93 69 87 65 29 83 85 C2 60 14 C4 C8 C9 3B 14 DA C0 81 F0 1F 0D 74 DE 92 22 AB CA F7 FB 74 7C 27 E6 F7 4A 1B 7F A7 C3 9E 2D AE 8A EA A6 E6 AA 27 16 7D 61 F7 98 71 11 BC E2 50 A1 4B E5 5D FA E5 0E A7 2C 9F AA 65 20 D3 D8 96 E8 C8 7C A5 4E 48 44 FF 19 E2 44 07 92 0B D7 68 84 80 5D 6A 78 64 45 CD 60 46 7E 54 C1 13 7C C5 79 F1 C9 C1 71 02 03 01 00 01
```


```
30 82 01 0A 02 82 01 01 00 A2 63 0B 39 44 B8 BB 23 A7 44 49 BB 0E FF A1 F0 61 0A 53 93 B0 98 DB AD 2C 0F 4A C5 6E FF 86 3C 53 55 0F 15 CE 04 3F 2B FD A9 96 96 D9 BE 61 79 0B 5B C9 4C 86 76 E5 E0 43 4B 22 95 EE C2 2B 43 C1 9F D8 68 B4 8E 40 4F EE 85 38 B9 11 C5 23 F2 64 58 F0 15 32 6F 4E 57 A1 AE 88 A4 02 D7 2A 1E CD 4B E1 DD 63 D5 17 89 32 5B B0 5E 99 5A A8 9D 28 50 0E 17 EE 96 DB 61 3B 45 51 1D CF 12 56 0B 92 47 FC AB AE F6 66 3D 47 AC 70 72 E7 92 E7 5F CD 10 B9 C4 83 64 94 19 BD 25 80 E1 E8 D2 22 A5 D0 BA 02 7A A1 77 93 5B 65 C3 EE 17 74 BC 41 86 2A DC 08 4C 8C 92 8C 91 2D 9E 77 44 1F 68 D6 A8 74 77 DB 0E 5B 32 8B 56 8B 33 BD D9 63 C8 49 9D 3A C5 C5 EA 33 0B D2 F1 A3 1B F4 8B BE D9 B3 57 8B 3B DE 04 A7 7A 22 B2 24 AE 2E C7 70 C5 BE 4E 83 26 08 FB 0B BD A9 4F 99 08 E1 10 28 72 AA CD 02 03 01 00 01
```


```
30 82 01 0A 02 82 01 01 00 B9 47 96 FD A0 94 F5 34 15 C9 B7 5D FB C7 AA 15 AB 34 D6 34 88 D7 D1 CC 6C 8D D4 40 FB F0 6E B9 43 9A DA 0A C3 52 07 F4 2A 1F 7F BE 88 D7 80 A1 5D C4 9B 66 07 6B D0 F1 A2 CC B8 4C 8D 11 64 A7 22 4F 65 21 F4 0F F4 7D 22 CA C7 07 8F B3 52 B4 86 7F 19 8B 74 74 AA 97 69 B8 5F CF B9 F3 67 88 8F 1E DC 60 69 C8 45 1A 2F 2D 5B 60 5D 2A 4C 5C C7 AE FB E3 3C 23 E1 57 F9 E7 BB 27 C1 37 0C 27 33 BD 56 88 E7 55 46 C8 80 13 35 F4 35 4E D4 7A B5 51 5C 28 14 F1 25 98 B5 EB 30 89 6A 64 2C 30 F0 E3 FA B6 01 92 59 F8 A9 D3 E2 4C 35 26 04 76 B3 02 ED 6F 09 54 9E 03 E0 14 DF 0A 4E 31 08 C8 5B DB 66 D2 FA 2C E0 C7 56 77 31 75 81 4D 1D 09 3A 94 50 33 74 E0 B4 EF 3B 84 EC FB 1C F6 B3 7D D1 D3 11 A4 0B C8 F8 1D 34 E2 11 70 19 86 D4 60 67 00 33 6A 5A AD B3 91 FE 08 F1 C1 00 03 66 65 02 03 01 00 01
```


```
30 82 01 0A 02 82 01 01 00 A7 53 FA 0F B2 B5 13 F1 64 CF 84 80 FC AE 80 35 D1 B6 D7 C7 A3 2C AC 1A 2C AC F1 84 AC 3A 35 12 3A 92 91 BA 57 E4 C4 C9 F3 2F A8 48 3C B7 D6 6E DC 97 22 BA 51 79 61 AF 43 2F 0D B7 9B B4 49 31 AE 44 58 3E A4 A1 96 A7 87 4F 23 7E C3 6C 65 24 90 55 3E A1 CA 23 7C C5 42 E9 C4 7A 62 45 9B 7D DE 63 74 CB 9E 63 25 F8 84 9A 9A AD 45 4F AE 7D 1F C8 13 CB 75 9B C9 E1 E1 8A F8 0B 0C 98 F4 CA 3E D0 45 AA 7A 1E A5 58 93 36 34 BE 2B 2E 2B 31 58 66 B4 32 10 9F 9D F0 52 A1 EF E8 3E D3 76 F2 40 5A DC FA 6A 3D 1B 4B AD 76 B0 8C 5C EE 36 BA 83 EA 30 A8 4C DE F1 0B 2A 58 41 88 AE 00 89 AB 03 D1 16 82 20 22 76 EB 5E 54 38 12 62 E1 D2 70 24 DB ED 1F 70 D2 64 09 80 2D E2 B6 9D CE 1F F2 BB 21 F3 6C DB D8 B3 19 7B 8A 50 9F EF EC 36 0A 5C 9A B7 4A D3 08 A0 39 79 FD DD BF 3D 3A 09 25 02 03 01 00 01
```
## Post #65
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-08-07T04:12:42+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from skills4u2envy
>
> I'm fairly new to ripping, and don't have a lot of experience with pak files, but I found these in the .exe
Not sure if they'll help someone or not, I'll post them anyways.

Thank you! I really appreciate you took the time.
The keys are supposed to be 140 bytes, I noticed the ones you found are larger. 
Do you think they could have changed that or...?
## Post #66
- Username: skills4u2envy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 27, 2016 2:17 am
- Post datetime: 2016-08-07T07:52:26+00:00
- Post Title: Re: Evolve (.PAK)

That's what I was thinking but I'm not sure.
Usually the pattern is that it starts with " 30 89" and ends with "02 03 01 00 01" so this is the closest pattern I could find.
## Post #67
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-07T11:33:30+00:00
- Post Title: Re: Evolve (.PAK)

Didn't someone already post a tutorial how to extract the keys earlier? Can't this just be followed?
## Post #68
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-08-07T22:14:15+00:00
- Post Title: Re: Evolve (.PAK)

> Reply from Gh0stBlade
>
> Didn't someone already post a tutorial how to extract the keys earlier? Can't this just be followed?

Nope, not anymore.
## Post #69
- Username: silikone
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 11, 2016 8:15 am
- Post datetime: 2016-08-11T01:47:33+00:00
- Post Title: Re: Evolve (.PAK)

I'm also interested in the Evolve files.
Have all PAKs been altered? Does one just need a new key?
## Post #70
- Username: SporeAltair
- Rank: advanced
- Number of posts: 63
- Joined date: Sun Mar 20, 2016 1:47 am
- Post datetime: 2016-08-13T18:33:48+00:00
- Post Title: Re: Evolve (.PAK)

Now Evolve in Stage 2, who knows how to unpack the pack, I believe with the update files and the new version? It is desirable to find a solution soon, I need the files for the site.
## Post #71
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-08-17T12:13:29+00:00
- Post Title: Re: Evolve (.PAK)

doesn't look like there's much interest for Evolve on Xentax
## Post #72
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-19T07:03:04+00:00
- Post Title: Re: Evolve (.PAK)

I'll second interest in this, or whatever number of people interested we're up to...!
## Post #73
- Username: marviraptor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 21, 2016 8:41 am
- Post datetime: 2016-09-21T00:45:07+00:00
- Post Title: Re: Evolve (.PAK)

Aye, I would love to get my hands on the dialogues files for this game. Unfortunately the instruction does not seem to apply to the F2P build of the game. If any kind folk can help on this matter, it would be most wonderful.
## Post #74
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-09-21T01:08:47+00:00
- Post Title: Re: Evolve (.PAK)

Definitely interested! Would love to play around with the models from this...
## Post #75
- Username: SporeAltair
- Rank: advanced
- Number of posts: 63
- Joined date: Sun Mar 20, 2016 1:47 am
- Post datetime: 2016-10-10T08:15:06+00:00
- Post Title: Re: Evolve (.PAK)

[https://www.dropbox.com/s/9awzg1q1rpm0s ... a.zip?dl=0](https://www.dropbox.com/s/9awzg1q1rpm0sw1/characters_monsters_krakenelder_data.zip?dl=0)

in this archive same .PAK file from the Evolve Stage 2, that I can't open.
## Post #76
- Username: deanimate
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 09, 2018 2:10 am
- Post datetime: 2018-09-08T18:30:07+00:00
- Post Title: Re: Evolve (.PAK)

Did anyone have any luck in the end with extracting any of the pak files? I'm primarily talking about the initial version of Evolve (Evolve Legacy) now that the servers for stage 2 have been shutdown.
## Post #77
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-09-08T22:45:57+00:00
- Post Title: Re: Evolve (.PAK)

Id also love to gain access to the latest paks as well, the keys seem to be working, but they changed the archive structure and nothing can be extracted anymore unless someone comes back to it and fix the initial unpack tool.
## Post #78
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-01T13:51:27+00:00
- Post Title: Re: Evolve (.PAK)

To reactivate my membership with "RidersOfDeadHorses" club  here's the log for the AnimationsCAF_NEW.pak you sent me where I got stuck with:

Size of src file: 0x2161e3e
PK\x05\x06 Signature Hit!
Check it at 0x2161518 
Process central directory record...
pCDRInfo->nCommentLength 0x910
Seek to 0x216152e
pCDR Size 0x6ccf9
pCDRInfo->lCDROffset 0x20f482f, pCDRInfo->lCDRSize 0x6cce9
No zip structure parsing! <<<  (version: 14313)


> Since "CryEngine is open source therefore you can find information regarding it fairly easily."
posting this link should not be against the rules, should it?
[http://atom0s.com/forums/viewtopic.php?f=11&t=223](http://atom0s.com/forums/viewtopic.php?f=11&t=223)

As I've been told the RSA key is not the problem with the new Evolve paks - they changed the zip structure.

(Sadly I'm too busy with my own projects to dig deeper with those paks.)
