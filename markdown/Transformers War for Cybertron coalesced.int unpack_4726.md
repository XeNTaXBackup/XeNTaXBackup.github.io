## Post #1
- Username: Rapid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 20, 2006 11:32 pm
- Post datetime: 2010-07-07T16:42:36+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

Hi!
Can someone decode the Tranformers: War for Cybertron's localization files? I need a packer/unpacker to translate the texts in it, but non of the existing programs works. 

The file's coding is possibly XOR.
If we have the key, the coalesced.ini will be decodeable too for the modders.

Please, if someone can create the program, I'll mention his/her name in my hungarian translation's installer, in my blog and I think the game translator community will praise his/her name.

I attached the international coalesced file to this post.

Thank you!

Rapid
[Coalesced_int.rar](https://xentaxbackup.github.io/file/3213_Coalesced_int.rar)
## Post #2
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2010-07-07T17:16:40+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

Just figured out:

first 4 bytes = number of blocks

Each block:

4 first bytes = bytes length ahead (always null terminated?)

Good luck with decryption 

Zeeh
## Post #3
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-07-10T18:57:30+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

Well, here is the secret xor password (61 characters long): 'as;dwepo2345098]qw]{}p2039458pseasdfzcvvp;aseiurwefsdcfszdcvn'

I created a simple encoder/decoder. Converts the coalesced.int file to editable text file and vice-versa. Tested on the game, it works!

One important thing:
The line separator in the text file is the \0A character, NOT the usual \0D \0A character-pair!
So don't let your text editor to replace the \0A characters with \0D \0A characters!!!
If you do so, the encoder won't work correctly!!!
Tip: Use the Notepad++ for editing, and set the EOL Conversion to UNIX format!
## Post #4
- Username: Rapid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 20, 2006 11:32 pm
- Post datetime: 2010-07-10T21:56:16+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

> Reply from bacter
>
> Well, here is the secret xor password (61 characters long): 'as;dwepo2345098]qw]{}p2039458pseasdfzcvvp;aseiurwefsdcfszdcvn'

I created a simple encoder/decoder. Converts the coalesced.int file to editable text file and vice-versa. Tested on the game, it works!

One important thing:
The line separator in the text file is the \0A character, NOT the usual \0D \0A character-pair!
So don't let your text editor to replace the \0A characters with \0D \0A characters!!!
If you do so, the encoder won't work correctly!!!
Tip: Use the Notepad++ for editing, and set the EOL Conversion to UNIX format!

I tried it and it works great.  Thank you so much Bacter!
## Post #5
- Username: xtgreyfell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 12, 2010 8:43 am
- Post datetime: 2010-07-13T18:14:48+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

> Reply from bacter
>
> I created a simple encoder/decoder. Converts the coalesced.int file to editable text file and vice-versa. Tested on the game, it works!

Works great for me on Coalesced.ini. Thanks so much. Joined this forum just so I could d/l your decoder, but will be sticking around/lurking if there is info this good elsewhere on the site!
## Post #6
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2010-07-18T19:53:14+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

Strangest thing, I chnaged bsmoothframerate from True to False (have to do this twice) and for whatever reason the game still plays at 30 FPS   .   I really thank you for the program that allows us to edit that file now but I'm not sure why the changes don't take?  I reopened the file just to see whats going on.  The bsmoothframerate still equals False.  So I change the MaxSmoothedFrameRate=250 and still no change in game (still 30 FPS).  So I change bsmoothframerate back to true and still 30 FPS.  I'm not sure what else is involved.  Vysnc is disabled.
## Post #7
- Username: xtgreyfell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 12, 2010 8:43 am
- Post datetime: 2010-07-24T20:06:28+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

> Reply from East
>
> Strangest thing, I chnaged bsmoothframerate from True to False (have to do this twice) and for whatever reason the game still plays at 30 FPS   .   I really thank you for the program that allows us to edit that file now but I'm not sure why the changes don't take?  I reopened the file just to see whats going on.  The bsmoothframerate still equals False.  So I change the MaxSmoothedFrameRate=250 and still no change in game (still 30 FPS).  So I change bsmoothframerate back to true and still 30 FPS.  I'm not sure what else is involved.  Vysnc is disabled.

I've noticed that there are to sets of engine settings in the ini, and you have to change both for the setting to take effect.
## Post #8
- Username: East
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 30, 2010 10:37 am
- Post datetime: 2010-07-31T23:26:10+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

Are you talking about [Engine.GameEngine]?  Yes, there are 2 of them and I changed bSmoothFramerate=False for both of them.  But it doesn't change the 30 FPS cap.
## Post #9
- Username: warning316
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 08, 2010 11:11 am
- Post datetime: 2010-08-08T12:10:27+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

im getting sorry some error occured. anyone kno whats the problem?
## Post #10
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-08-09T04:12:01+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

That's a command line program, you have to give it the correct parameters.
If you want to decode the coalesced.int file, try this, for example:

TWfC_util.exe D coalesced.int decoded.txt
## Post #11
- Username: Nikolai09
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 18, 2010 3:51 am
- Post datetime: 2010-08-20T03:52:29+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

Hey there! Well, I'm trying decode this file, too. But I'm a little noob in this thing of command lines.  

So, could anybody make a tutorial how to decode this file?
## Post #12
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-08T06:31:27+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

O.K. I created a simple graphical interface to my util. I hope you can use it.
## Post #13
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2010-09-09T13:03:50+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

does anybody know in which file there are fonts?

i want to make russian fonts
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-09-21T06:51:28+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

> Reply from Carampucilo
>
> 


uydi otsyuda ...

English or die.
## Post #15
- Username: doctorsullivan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 13, 2010 9:52 am
- Post datetime: 2010-11-03T02:48:27+00:00
- Post Title: Transformers: War for Cybertron coalesced.int unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-11-04T16:19:37+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

I updated my converter, I hope it works. Your attached "Coalesced.ini" and "Coalesced.int" seems O.K. 
But not works with the "Coalesced.FRA", because it contains some kind of unknown block from the 30B62 file position.
## Post #17
- Username: royboy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 13, 2011 7:06 am
- Post datetime: 2011-02-12T23:17:05+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

i am like a complete dummy on this soooo yeahhhh... one of my friends messed with the coalesced file and got his soldier to have cloack warcry nullray and fusion cannon... can som1 explain how i can do that???
## Post #18
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-02-19T18:41:13+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Here's the updated version of my tool. Theoretically it works with the problematic "Coalesced.FRA" and "Coalesced.RUS" files too.
(I don't have the game, so I couldn't try it.)
## Post #19
- Username: royboy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 13, 2011 7:06 am
- Post datetime: 2011-02-21T18:32:21+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

i got it unpacked and i got a bunch of random crap lol guess i have to poke around?

as my description states, ima ultra-n00b lol
## Post #20
- Username: Gishank
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 11, 2011 5:58 pm
- Post datetime: 2011-07-11T10:13:03+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Forgive me for necroing this thread, but I thought it best to do so rather than creating an entirely new thread.

I noticed that the tool that Bacter has posted, has since been removed (judging by the post edits, by himself). I was wondering if anyone else has an appropriate tool? I was doing some googling and came across this site, however it would appear the XOR file encoder/decoder in the Tools section doesn't seem to want to work (at least not with the key posted in this thread).

Any help would be greatly appreciated, as I really wish to experiment with the Singleplayer aspect of Transformers to make it more difficult but at the same time - enjoyable.
## Post #21
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-07-11T15:37:12+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

I cannot see any download link for the tool ? Does it woek also for X360 version ?
## Post #22
- Username: Sweetz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 15, 2011 1:11 pm
- Post datetime: 2011-07-15T05:15:53+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from Gishank
>
> 
I noticed that the tool that Bacter has posted, has since been removed (judging by the post edits, by himself). I was wondering if anyone else has an appropriate tool?
Same question here.  I just started playing the game and I'm having some issues with slow texture streaming despite having a good system (much the same issue as Singularity has).  I wanted to play around with increasing the texture pool size.

If anyone still has the editor I'd really appreciate it.
## Post #23
- Username: luluxiu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 18, 2011 6:41 pm
- Post datetime: 2011-07-19T05:31:33+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

I really appreciate your program, let us now edit the file, but I do not know why not to change? I re-open the file, just to see what's going on. bsmoothframerate still equals false.
[undecided.gif](https://xentaxbackup.github.io/file/4511_undecided.gif)
## Post #24
- Username: Gata
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 24, 2011 11:06 am
- Post datetime: 2011-07-26T00:48:04+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Was working to decrypt the XBOX DLC files, and wondered how exactly you were able to decrypt the coalesced.ini file, as in, what method did you use?
## Post #25
- Username: Belthasar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 20, 2011 8:42 am
- Post datetime: 2011-08-04T12:35:54+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Can someone repost TWfC_util.exe? The Mediafire link is dead
## Post #26
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-19T09:59:49+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

I have created a quickbms script supporting the FRA file too:
[http://aluigi.org/papers/bms/cybertron_coalesced.bms](http://aluigi.org/papers/bms/cybertron_coalesced.bms)

it performs only the decryption so you cannot re-encrypt it.
## Post #27
- Username: polyneutron
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 27, 2012 1:47 pm
- Post datetime: 2012-05-27T06:25:56+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Is anyone there? Can someone just post converted (to editable format) Coalesced.ini file here? Was looking for no-HUD solver  within .ini file - no result... Any help appreciated!
## Post #28
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-05-27T08:20:41+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

wow I might have to crack open this game again, sounds like I might get shockwave on PC after all.
BTW if you want to know how to decrypt your file, take all that text and save it in a .txt file, download quick bms, open quickbms and select the .txt you made then select the .ini, make sure to put the new file in a different output folder. Simple really. Hope that's clear enough im not good at explaining things.
## Post #29
- Username: polyneutron
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 27, 2012 1:47 pm
- Post datetime: 2012-05-27T08:40:03+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Troopermanaic,
thx for advice though it didn't help   Made a new .txt file with all the characters from original Coalesced.ini, put it into one directory. Copied Coalesced.ini file into another one. Ran quickbms.exe, choose .txt first, then .ini, then output dir (the 3rd folder) = got only some 'c_structs: ...' errors and the final one: 'invalid command 'i' or arguments -1 at line 33'
Sadface is so sad...
## Post #30
- Username: polyneutron
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 27, 2012 1:47 pm
- Post datetime: 2012-08-21T14:46:41+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

*bump* Still no luck, can someone just upload that coalesced editor somewhere? Or write a detailed manual how to open it for editing and decrypt after all? I repeat, no hacking willing here, just interest in internal structure of the game (as well as just being curious what settings are applied in that version of engine), plus I'd like to turn off the hud to film/ make some good screenshots and try how the game would feel in that way. Thx for attention! Cheers!
## Post #31
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-08-21T16:03:30+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

I have bacter tool here from 2010.
Some anti-virus detect it as a malware.
I don't know if it's a false positive or no.

If you wanna download it by your own risk, here's the link:
[http://dl.dropbox.com/u/62858477/TWfC_util.exe](http://dl.dropbox.com/u/62858477/TWfC_util.exe)

And here's the Virus Total analysis:
[https://www.virustotal.com/file/c9a1b41 ... 345564712/](https://www.virustotal.com/file/c9a1b417ee4173c66bf541875674136e837e71a3f188c898f4fb4d21412063d2/analysis/1345564712/)
## Post #32
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-21T18:48:19+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

i hope there will be a repacker for this ^_^
## Post #33
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-08-21T19:27:06+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from lllccc
>
> i hope there will be a repacker for this ^_^
Bacter's tool can extract and repack the .ini file.

See usage.
## Post #34
- Username: polyneutron
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 27, 2012 1:47 pm
- Post datetime: 2012-08-22T10:25:48+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Many many many thanks (actually, tons of 'em) Herdell! At first I 've tried the .int file, but couldn't find any familiar lines. Only after unpacking the .ini file, I've got it working! No any HUD on screen, yay!   
This is so awesome, I can't even describe my feelings right now! And again, thank you very much!
## Post #35
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-23T13:21:39+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from Herdell
>
> lllccc wrote:i hope there will be a repacker for this ^_^
Bacter's tool can extract and repack the .ini file.

See usage.
thanks i will give this a try tonight
## Post #36
- Username: static77
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 20, 2012 1:37 pm
- Post datetime: 2012-08-23T16:28:51+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from bacter
>
> Here's the updated version of my tool. Theoretically it works with the problematic "Coalesced.FRA" and "Coalesced.RUS" files too.
(I don't have the game, so I couldn't try it.)
Sorry, but where is updated version or any kind of version? I don't see any attached file?
## Post #37
- Username: polyneutron
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 27, 2012 1:47 pm
- Post datetime: 2012-08-24T13:43:05+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from static77
>
> bacter wrote:Here's the updated version of my tool. Theoretically it works with the problematic "Coalesced.FRA" and "Coalesced.RUS" files too.
(I don't have the game, so I couldn't try it.)
Sorry, but where is updated version or any kind of version? I don't see any attached file?

Look at the top of the page, Herdell have already shared the bacter tool from 2010. If your anti-virus will close the download session (as it does in my case) or do smth else to prevent you from downloading the file, just turn it off for a while. You can be sure it's NOT a virus, and it's safe to use.
## Post #38
- Username: static77
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 20, 2012 1:37 pm
- Post datetime: 2012-08-24T14:08:18+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

I've tried. Look what I got
[](http://fastpic.ru/view/42/2012/0824/2b69c38e00bb58ba48a9ccb4eb5d57c5.jpg.html)
## Post #39
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-24T14:38:31+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from static77
>
> I've tried. Look what I got

this is how you extract and repack your file open up cmd make sure you have all the files in one area ( incuding the gui and 
coalesced.int in the same place i would say put everything on the desktop) once you have the cmd up type cd desktop 
okay when your done  type in TWfC_util d Coalesced.int <what ever you want to nameit.txt> once you are done and you want to repack type TWfC_util e <what ever you want to named it when you unpacked it>.txt Coalesced.int thats what you do


do not type in < >
so
unpack 
TWfC_util d Coalesced.int <what ever you want to nameit.txt>

repack
TWfC_util e <what ever you want to named it when you unpacked it>.txt Coalesced.int
## Post #40
- Username: static77
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 20, 2012 1:37 pm
- Post datetime: 2012-08-24T15:11:17+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

lllccc, sorry, I'm really dumb ass.

> open up cmd 
which command?

> once you have the cmd up type cd desktop


> when your done type in TWfC_util d Coalesced.int <what ever you want to nameit.txt>
I can't type anything in TWfC_util.
## Post #41
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-24T15:20:46+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from static77
>
> lllccc, sorry, I'm really dumb ass.
open up cmd 
which command?
once you have the cmd up type cd desktop

when your done type in TWfC_util d Coalesced.int <what ever you want to nameit.txt>
I can't type anything in TWfC_util.

cmd is command you not typing it in twfc_util  if you on windows xp go to run and type in cmd windows vista/7 use the search bar under all programs  type cmd in there and it will open up and type in the info i gave you (both are in the start menu)

cd desktop 
then the info to extract and repack
## Post #42
- Username: static77
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 20, 2012 1:37 pm
- Post datetime: 2012-08-25T15:06:41+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

lllccc, did I write something wrong?


Could you unpack that .int file and attach .txt file here, please?
[Coalesced.int](http://uploaded.net/file/4wkgas6i)
## Post #43
- Username: polyneutron
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 27, 2012 1:47 pm
- Post datetime: 2012-08-26T10:06:00+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from static77
>
> lllccc, did I write something wrong?


Could you unpack that .int file and attach .txt file here, please?
Coalesced.int
static77 correct me if I'm wrong, but don't you need your TWfC_util.exe to be on your Desktop to launch it through the cmd.exe using those commands that lllccc had provided? And btw, there's no need to put those '<'/ '>' symbols, you should type the following:

TWfc_util.exe D Coalesced.int Decoded.txt

instead of

TWfc_util.exe D <Coalesced.int_file><txt_file>

Because that line was just an example of how you should write a command to unpack the thing. And yeah, 'Decoded.txt' is just a random name for a file that you'll get after the unpack, you can name it whatever you want.

In my case I've made a new folder named 'TWFC' right on my C:\ drive, so the full path was: C:\TWFC\
Then I've opened cmd.exe, typed in

cd C:\TWFC

After that I was able to open the TWfC_util.exe right from the TWFC folder and then perform the unpack operation:

TWfc_util.exe D Coalesced.int Decoded.txt

Done!
Last important thing to note: even though I have the Coalesced.int unpacked, I couldn't find any useful data there, so I was like 'Why is that? Where all the system settings like smoothing fps rate, DynamicDecals=True etc.
I unpacked the Coalesced.ini file, and that was the right choice. So, if you don't find anything useful in Coalesced.int, remember that you can unpack Coalesced.ini file too, and feel free to mod it!
Good luck!

*Sry for such a large post, I was trying to cover everything about these Coalesced-files unpacking
## Post #44
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-26T13:42:38+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from static77
>
> lllccc, did I write something wrong?


Could you unpack that .int file and attach .txt file here, please?
Coalesced.int
yea you did you dont use< > and  then you will have it right
## Post #45
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-26T13:44:46+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from lllccc
>
> static77 wrote:lllccc, did I write something wrong?


Could you unpack that .int file and attach .txt file here, please?
Coalesced.int
yea you did you dont use< > and  then you will have it right and just type in  coalesced.int not coalesced.int_file

so it would look like this
TWFC_util.exe d coalesced.int txt.txt
## Post #46
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2012-09-11T12:01:02+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Hi all coders, where I find fonts and how unpack/pack back? Maybe are encrypted. Thanks for reply or help. 

Bacter, I used your tools, but after clicking occurs APPCRASH, any idea? I using W7 64-bit. Thanks.
## Post #47
- Username: EKlipse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 01, 2012 5:55 pm
- Post datetime: 2013-03-22T03:09:31+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

When trying to decode it seems to be working then after a few minutes it will say TWfC_util encountered a problem and has to close and the command prompt will say this...

Exception EOutOfMemory in module TWfC_util.exe at 00002A88.
Out of memory.

Any idea how to fix this? Tried on another computer and I don't get the out of memory but it still says TWfC_util has encountered a problem and must close after a couple minutes of decoding.

EDIT I just tried the program on a third computer and it also crashes a minute after started to decrypt.
## Post #48
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2015-07-02T09:18:23+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

*REDACTED
## Post #49
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2015-07-02T09:19:48+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Or does the game not check and not care what I put in it so long as it has a correctly encrypted file
## Post #50
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2015-07-02T09:43:52+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from bacter
>
> Well, here is the secret xor password (61 characters long): 'as;dwepo2345098]qw]{}p2039458pseasdfzcvvp;aseiurwefsdcfszdcvn'

I created a simple encoder/decoder. Converts the coalesced.int file to editable text file and vice-versa. Tested on the game, it works!

One important thing:
The line separator in the text file is the \0A character, NOT the usual \0D \0A character-pair!
So don't let your text editor to replace the \0A characters with \0D \0A characters!!!
If you do so, the encoder won't work correctly!!!
Tip: Use the Notepad++ for editing, and set the EOL Conversion to UNIX format!
Would that also be the decryption/encryption code for the 360 version aswell?
## Post #51
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2015-07-11T04:22:47+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from bacter
>
> Well, here is the secret xor password (61 characters long): 'as;dwepo2345098]qw]{}p2039458pseasdfzcvvp;aseiurwefsdcfszdcvn'

I created a simple encoder/decoder. Converts the coalesced.int file to editable text file and vice-versa. Tested on the game, it works!

One important thing:
The line separator in the text file is the \0A character, NOT the usual \0D \0A character-pair!
So don't let your text editor to replace the \0A characters with \0D \0A characters!!!
If you do so, the encoder won't work correctly!!!
Tip: Use the Notepad++ for editing, and set the EOL Conversion to UNIX format!

Is this for xbox or PC?
## Post #52
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2015-07-11T04:28:29+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

I used the unpacker util tool and edited my coalesced.ini just fine. When I encrypted it back, and burn it to a disk. (Verbatum) then installed it to my hard drive. It is able to run in the background. But It says the disk is unreadable even tho its running behind the error message just fine. like wtf? Is this util tool workable for xbox or not?
## Post #53
- Username: BurnPL
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 31, 2015 2:36 am
- Post datetime: 2015-12-30T18:49:48+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

How to pack it after i change something in my file ?
## Post #54
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2016-01-01T06:26:50+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from BurnPL
>
> How to pack it after i change something in my file ?
You encrypt it.
## Post #55
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2016-01-01T06:29:01+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Got these ti work on xbox
## Post #56
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2016-03-07T17:28:24+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

Reposting the thing (TWfC_util.exe) for posterity.
[TWfC_util.zip](https://xentaxbackup.github.io/file/10564_TWfC_util.zip)
## Post #57
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2016-03-07T17:34:22+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

posted a video of moded on xbox on youtube.
## Post #58
- Username: gula
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 14, 2014 8:17 pm
- Post datetime: 2016-03-09T20:57:52+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from KJTR
>
> posted a video of moded coalesced on xbox on youtube. type transformers wfc iso mod
Succeeded written texttool on xbox360?
## Post #59
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2016-03-09T22:11:36+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

> Reply from gula
>
> KJTR wrote:posted a video of moded coalesced on xbox on youtube. type transformers wfc iso mod
Succeeded written texttool on xbox360?
The tool also work on the 360.
## Post #60
- Username: LadiesMan217
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 18, 2016 5:33 am
- Post datetime: 2016-03-19T01:32:56+00:00
- Post Title: Re: Transformers: War for Cybertron coalesced.int unpack

*REDACTED
