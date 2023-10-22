## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-10T20:52:29+00:00
- Post Title: Encrypted/compressed formats

The idea for this thread is having an updated list of games which don't seem to use plain-text or readable data in their packages.

For example we have the packages with the SFFS header used in games like Bet on Soldier which use the Starforce encryption.
Another type of encryption is that used by ActiveMark for the data files of games like 18 Wheels of Stell Convoy (the version available on the Trygames website).

Naturally these are only a couple of examples and probably the worst I could find (DRM) eh eh eh.

Some better but solved examples are the CBF files of Vietcong and the tntfolder files of HoveRace and FireStarter.

So if you have a package file which doesn't contain readable data in it or you want to discuss about an algorithm, come here.
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-11T01:30:28+00:00
- Post Title: Encrypted/compressed formats

Sounds great .

OK well I will begin - There is a game called TrackMania (and the sequal TrackMania Sunrise) that both have one large resource archive, however I have never been able to do anything with them - maybe this would be a nice one to delve into? At least we know there are multiple games using the same format, which means that future (and other) games by the same developer will probably use the same format too.

Hmm I can't think of any others at the moment, but this is a start. Once again, thanks for your assistance  . Oh, and there is no rush on this either.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: AdamTheStudent
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 11, 2005 8:52 am
- Post datetime: 2005-12-11T01:35:42+00:00
- Post Title: Encrypted/compressed formats

Hi. I'm attempting to write a program that can use files archived in *.rfa archive files of the game Battlefield 1942. The wiki information had allowed me to know how to separate the files into the proper directories, but only in compressed form, which is unuseable for me. 

What compression/encryption method is being used on the data files? The sourceforge project, [http://sourceforge.net/projects/r2at](http://sourceforge.net/projects/r2at) , files aren't of much use since I've not been able to determine the correct algorithm to use from them. 

Using a hex editor I have noticed that every compressed file has the following structure: 

Header: 0100 0000 xxxx 0000 xxxx 0000 0000 0000 

Last 3 bytes of file: 1100 00 

The DragonUnpacker can properly extract both the retail and demo version archives, but the author has yet to reply to my email. 

I'd appreciate any assistance in regards to this, please reply here or email me at [adamthestudent@hotmail.com](mailto:adamthestudent@hotmail.com) 

Thank you....
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-11T02:15:15+00:00
- Post Title: Encrypted/compressed formats

Hi mate,

You can download the source code for Dragon Unpacker from SourceForge - that would be your best bet. Thankfully, Delphy is pretty easy to read and understand.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: AdamTheStudent
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 11, 2005 8:52 am
- Post datetime: 2005-12-11T03:41:35+00:00
- Post Title: Encrypted/compressed formats

I had no idea the cose was at sourceforge! I only visited the authors main site and didn't see source listed.

Thank you for the assistance. I'll take a tutorial on Delphi soon I bet 

Regards, Adam.
## Post #6
- Username: AdamTheStudent
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 11, 2005 8:52 am
- Post datetime: 2005-12-11T04:03:10+00:00
- Post Title: Encrypted/compressed formats

I downloaded the source code, but I'm not finding the plugin for *.rfa files. Might you be able to point in me in the right direction or lend a hand in finding the correct *.pas file? thanks.
## Post #7
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-12-11T04:56:39+00:00
- Post Title: Encrypted/compressed formats

Need For Speed: Most Wanted .bin files.
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-11T11:35:44+00:00
- Post Title: Encrypted/compressed formats

> Reply from AdamTheStudent
>
> I downloaded the source code, but I'm not finding the plugin for *.rfa files. Might you be able to point in me in the right direction or lend a hand in finding the correct *.pas file? thanks.

I took a brief look at the source - I think I found it in file plugins/drivers/default/drv_default.dpr at about line 7756. This is just a normal text file, so just open it using Textpad or something. The method is called RFA_Decomp(), and appears to do the main decompression work. There is also another method further down on line 8098 called DecompressRFA() which I think is just an entry point into the RFA_Decomp() method.

Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: AdamTheStudent
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 11, 2005 8:52 am
- Post datetime: 2005-12-11T15:26:29+00:00
- Post Title: Encrypted/compressed formats

> Reply from friendsofwatto
>
> AdamTheStudent wrote:I downloaded the source code, but I'm not finding the plugin for *.rfa files. Might you be able to point in me in the right direction or lend a hand in finding the correct *.pas file? thanks.

I took a brief look at the source - I think I found it in file plugins/drivers/default/drv_default.dpr at about line 7756. This is just a normal text file, so just open it using Textpad or something. The method is called RFA_Decomp(), and appears to do the main decompression work. There is also another method further down on line 8098 called DecompressRFA() which I think is just an entry point into the RFA_Decomp() method.

Good luck.

WATTO
watto@watto.org
http://www.watto.org

What wonderful news to be greeted with today. I will go and take a look!  Thank you very much for your assisting me.

Regards, Adam.
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-11T19:02:31+00:00
- Post Title: Encrypted/compressed formats

> Reply from friendsofwatto
>
> 
There is a game called TrackMania (and the sequal TrackMania Sunrise) that both have one large resource archive,

Sunrise uses SFFS (remember the other thread?) and Trackmania seems to use something similar with the only difference that there is no SFFS header.
Anyway I'll investigate for sure

Oh I think that the game "Metal Heart Replicants Rampage" discussed in a previous thread is a candidate for this thread too since seems to use encryption as showed by headrift.
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-11T20:58:13+00:00
- Post Title: Encrypted/compressed formats

Okay, another one. What type of compression is used in the balance.pak file in this thread? [viewtopic.php?t=1612](http://forum.xentax.com/viewtopic.php?t=1612) I've written MultiEx Commander support, but it will only extract the resources still compressed.
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-11T21:43:22+00:00
- Post Title: Encrypted/compressed formats

> Reply from Mr.Mouse
>
> 
Okay, another one. What type of compression is used in the balance.pak file in this thread?

I already checked Ski Alpine/Racing 2005 some hours ago so I have a partial answer for you 8-)
Almost all the files contained in the packages used by these 2 games have the data in plain-text format, except some types of files like .txt.
So your script works perfectly with all the most important files (wave for example), don't worry.
Now the only question is: are we so curious to find what compression is used by the balance file?
Ok I will check it quickly just for curiosity.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-11T21:48:00+00:00
- Post Title: Encrypted/compressed formats

Hehe...yes, we ARE so curious, because it is annoying when even just one file out of many does not "compute"  

Thanks by the way on the update that the script works with other .pak files. I just tried the balance.pak file, didn't have time to get the game or a demo somewhere.
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-11T22:41:52+00:00
- Post Title: Encrypted/compressed formats

The good news is that I'm able to uncompress the data.
The less good news is that I still don't know what is the original algorithm.
So how we can implement the decompression in your program?
It requires at least an external dll containing the ripped code.
If for you is too much problematic I can write a stand-alone extractor.
## Post #15
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-12T00:00:07+00:00
- Post Title: Encrypted/compressed formats

Hey, you are doing absolute wonders 

In regards to TrackMania and Sunrise - I guess we can't really do much more with those at the moment.

In regards to the post above, you may be able to write a MexCom plugin for the Rahly Plugin Manager - I think its just a "template" that MexCom can understand, but plugins that implement Rahly do all the actual work - you would need to discuss this more with Mr Mouse.

Now for another game  . Maybe a year ago I had tried to read a game called Heart Of Darkness, and someone else actually requested that I add support for the game, but I didn't really get anywhere. Maybe you could grab a look at this game - I don't know if there is a demo, so if you need some files or the executables or whatever then let me know and I will see how I can get them to you. Once again, no rush.

Thanks for all your help, you are an absolute champ!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-12T08:28:15+00:00
- Post Title: 

> Reply from Bugtest
>
> The good news is that I'm able to uncompress the data.
The less good news is that I still don't know what is the original algorithm.
So how we can implement the decompression in your program?
It requires at least an external dll containing the ripped code.
If for you is too much problematic I can write a stand-alone extractor.

Yes, I think you are a wonderful addition to our team! Together, we can bring in a lot of knowledge into our project. 

Watto's suggestion is right. I have enabled plugins to be created for MexCom, these are either ActiveX DLLs (see thread here: [viewtopic.php?t=1388](http://forum.xentax.com/viewtopic.php?t=1388))

or, better still, DLL's that work with Rahly's Plugin Manager for MexCom. Rahly is the one that can help you about the functions the DLL must provide to be able to communicate to the manager. You can read all about the process here. [viewtopic.php?t=852](http://forum.xentax.com/viewtopic.php?t=852)

Rahly and I still have to check wether the latest manager works ok with the lates MexCom, and then I will do a release of MexCom with Rahly's new mananger. After that, anyone could create Rahly's Plugins to talk to MexCom.
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-12T11:26:04+00:00
- Post Title: 

Well, for the moment I have created the stand-alone unpacker and have updated the thread.
Anyway this format is used by ALL the games developed by 49Games: [http://www.49games.de](http://www.49games.de) so I think we must update the wiki too, let me know.
Sorry for the dll but I have preferred the fastest way for me eh eh eh (I'm a lazy boy!)
## Post #18
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2005-12-12T11:51:10+00:00
- Post Title: 

[quote="Mr.Mouse
Yes, I think you are a wonderful addition to our team! Together, we can bring in a lot of knowledge into our project. [/quote]

no doubt!!
if only i had so much knowledges 


@Bugtest:I'm amazed all the work,toolz done on your site!!
## Post #19
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-20T22:56:54+00:00
- Post Title: 

Just posting an update re: games that use Starforce protection. These are the games I have found thus far, but I havn't looked at all the archives from these games yet to see whether the archives are themselves protected.

```

Arc Protect?	Game Name
=========================================================
Yes		Bet On Soldier
Unknown		Cold War
Unknown		Ricky Ponting International Cricket 2005
Probably	TrackMania
Probably	TrackMania Sunrise
Probably	TrackMania Sunrise Extreme
Unknown		UFO Aftershock
```


That is all so far.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #20
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-20T23:02:14+00:00
- Post Title: 

Also, while I am here, I am going to suggest another game that uses compression, for which I know there are many people wanting support. The games are the Madden NRL series (mostly 2004/2005). The structure of the archive is easy enough - you can find that on the wiki - the problem just lies in the compression of the files. If anyone could help out with this game, I know it would be benificial - I am constantly recieving emails from people wanting support for these games 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #21
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2005-12-20T23:09:40+00:00
- Post Title: 

Prince of persia : the two thrones is another starforce game.
## Post #22
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-21T00:31:23+00:00
- Post Title: 

OK Excellent 

I have set up a page on the Wiki that lists all the compression/encryption archives - check it out at [http://wiki.xentax.com/index.php/List_O ... ssed_Games](http://wiki.xentax.com/index.php/List_Of_Compressed_Games) . It is a bit easier than trying to keep an updated list on the forums, and makes it easy to see which games have unknown compression types (for those people who want something to do )

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #23
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-21T06:08:43+00:00
- Post Title: 

Cool!
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-26T16:46:46+00:00
- Post Title: 

I would also like to add 

Mercedes Benz World Racing 
Mercedes Benz Truck Racing 

SYN files to the list. The resources are compressed. 

See for examples: 

[viewtopic.php?t=1637](http://forum.xentax.com/viewtopic.php?t=1637)
## Post #25
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-26T22:07:21+00:00
- Post Title: 

I have seen the new section in the wiki and it is really excellent 8-)
Having all the "strange" compression/encryption algorithms collected and documented in one page is really useful.

I have found only one problem while I wanted to add the .tntfolder and some other formats to the page, in short after having hitted the "Login" button it has reached the 412 Precondition Failed page... now I don't know if is a casuality but this error happens with any other wiki page.
Sorry if I have not surfed too much the forum lately but I was a bit busy.

About the Mercedes Benz files, have you understood what type of compression is used?
## Post #26
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-26T22:32:40+00:00
- Post Title: 

No, I haven't. So I added it here, to be investigated.  Hopefully we can figure out this method. 

Offtopic: Did you have a good Christmas? I had!
## Post #27
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2005-12-27T09:40:16+00:00
- Post Title: 

> Reply from Bugtest
>
> About the Mercedes Benz files, have you understood what type of compression is used?

Have you guys noticed this:
FF "TRUEVISI"
FF "ON-XFILE"

Seems similar to KOF pak files (where FF indicates next 8 bytes are to be copied etc..) ..no?
## Post #28
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-27T10:11:47+00:00
- Post Title: 

Yeah I noticed that - and I agree that it is probably some kind of RLE-based data compression algorithm - they are pretty common in games because they are pretty simple, don't need much memory, and can be customised well depending on the type of data that is being compressed.

A good example of this type of algorithm is used for The Sims 2 and Simcity 4 - these games store 20 different languages for each item used in the game, but often they aren't translated into all the different languages. Therefore, there are multiple duplicates of the English translation, which can be shrunk down to practically nothing by an RLE-like method that points to the first english translation and tell it to copy the whole thing.

I am not sure exactly how the method for this game works, but I imagine it would be something similar. Thanks for helping.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #29
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-27T12:05:09+00:00
- Post Title: 

Thanks guys I knew that you me you will help  

Watto , Mike
## Post #30
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-12-29T00:35:42+00:00
- Post Title: 

I'm just throwing an idea out here, perhaps we should add a 'Compression/Encryption' section to the individual format pages, to be used for specific methods if applicable...? It would be more work, but would make the Wiki that much more complete and useful.
## Post #31
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-29T07:00:03+00:00
- Post Title: 

Yeah sure, if you want - it will make it a big more structured. Feel free to do so if you are interested 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
