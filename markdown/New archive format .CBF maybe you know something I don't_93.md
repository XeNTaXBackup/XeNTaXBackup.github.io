## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-01-18T04:48:03+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

I have an archive file in .CBF format. I am trying to extract files from this archive, but it is not supported in any extractors that I have found.  I think it would be a good addition to the MultiEX Commander.  

This archive came with the new Vietcong demo, in one archive there are 5326 files.  If opened in a hex editor, there is a list of all the files in the archive and they are listed in the same order that they are in the archive.

ex:

DEV\VERSION\GOD.JPG.[.......!....#KC....lk..................
DEV\VERSION\GOD.TGA._7......!...".TC.....P..................
DEV\VERSION\GOD_B.TGA.S<......!...0.[C.....|......."..........
DEV\VERSION\ILLUSION.TGA.C_......!.....`C.....]..................
DEV\VERSION\ILLUSION_B.TGA..c......!.....lC........................
DEV\VERSION\IS.JPG..T......!...ZIqC....LF.......-..........
DEV\VERSION\NVIDIA.TGA.........!.....zC.....4..................
DEV\VERSION\NVIDIA_B.TGA.........!...v..C....d.......&...........
DEV\VERSION\ORDERNOW.TGA.........!....G.C....8d..................

The codes after the file extension of each file are all the same length.  The actual files in the archive are divided by this "[..]" 

example of a .JPG file:

[..]....,@......H. ...A .......#J.H.....3j...... C..I....(S.\.....0c..I....8s.......@...J....H.*]
.....P.J.J....X.j......`...K....h..].....p...K..
..x............L......+^......#K.L.....3k.......
C..M.....S.^......c..M.....s.....o...R.R...$S.<q
....$L...........JFIF.....H.H.....vPhotoshop3.0.
8BIM.........H.......H......8BIM...........x8BIM
................8BIM..........8BIM'.............
//

//
................................................
................................................
................................................
................................................
................................................
................................................
.....[..]

On each file there is what, I guess to be a type of header, that varies in length for each file.  As in the example above, even though it starts out with "....,@......H. ...A" the actual jpeg file starts at "....JFIF". 

I wondered if maybe anybody recognized this fomat or the layout of the archive. I also wondered if the directory code pointed to the file in the archive.  If you have any ideas let me know.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-18T17:11:49+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

Okay, it seems at first glance a reasonable format that shoudl not be too difficult to write a formats script for MultiEx Commander for. I will see if there's a demo verison of Vietcong around so I can have a look-see in the .CBF files. I will let you know here what I found.
## Post #3
- Username: Bama
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 18, 2003 12:12 pm
- Post datetime: 2003-01-18T22:50:40+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

Huh, I wonder why it put me down as Guest, I am the one who posted this.  Anyway, that would be great, I've been able to rip out some of the files with a hex editor, but others are just a pain.   
I have found 28 different file fomats in the archive: .FNT, .PK, .ANM, .WAV, .SHM, .IFL, .LDT, .TX3, .XST, .XDT, 
.STD, .JPG, .BMP, .DAT, .STG, .STO, .BES, .DDS, .TGA, .EQP, .MANM, .SCR, .INI, .TXT, .CTR, .OCT, .SCO, .OGG.  
I recognize a few, but others are new to me.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-19T09:51:53+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

OK you can try this Mex3Script (open Mex3Scriptor from the tools menu, paste it into the main window, save it as cbf.bms, and choose the "Use Custom BMS On..." option from the tools menu) and open a CBF file. 
This will let you extract some, but a lot of resources in there are packed, zipped so to speak, and cannot be extracted (yet). I will have to know what zip method is used, and judging from the format I will also have to adapt MultiEx3 to be able to process it correctly. 

Here's the Mex3Script :

ImpType StandardTail ;
IDString 0 BIGF ;
Set D Long 16 ;
GoTo D 0 ;
Get FC Long 0 ;
SavePos TailOffOff 0 ;
Get TP Long 0 ;
Get D Long 0 ;
Get TS Long 0 ;
GoTo TP 0 ;
For T = 1 to FC ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos J 0 ;
Math J += 16 ;
GoTo J 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos J 0 ;
Math J += 16 ;
GoTo J 0 ;
Get FN String 0 ;
Log FN FO FS FOO FSO ;
Next T ;
## Post #5
- Username: Bama
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 18, 2003 12:12 pm
- Post datetime: 2003-01-19T23:13:10+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

I seem to be getting an error when trying to open the .CBF "run-time error 63: bad record number"
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-20T09:11:08+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

That's interesting, but which program gives the error? MultiEx3Scriptor or MultiEX Commander?
## Post #7
- Username: Bama
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 18, 2003 12:12 pm
- Post datetime: 2003-01-20T23:04:11+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

In MultiExCommander, I selected "Run Custom BMS On..." and loaded the BMS.  When I tried to load the .CBF afterwards is when the error occured.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-20T23:49:48+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

Ok, take this BMS file and try again

[http://www.xs4all.nl/~michael/temp/cbf.bms](http://www.xs4all.nl/~michael/temp/cbf.bms)

1. Choose the BMS File
2. Choose the game archive

Note : it may be that this only works on the demo version and NOT on the retail version. If all goes well you should be able to extract some WAV files with this BMS.
## Post #9
- Username: Bama
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 18, 2003 12:12 pm
- Post datetime: 2003-01-21T05:12:18+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

Great, I was able to extract .OGG, but not .WAV.  It did however list all the files, starting point, and length. Better than nothing.
## Post #10
- Username: Zagash
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-03-16T20:06:41+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

Yeah! 

Sooo great, if the MultiEx will supports this beautiful game...
## Post #11
- Username: [TKC]Mullah Omar
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-03-26T18:52:27+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

I get corrupted file info on most files.

Vietcong Demo is on [http://www.vietcong-game.com](http://www.vietcong-game.com)
## Post #12
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-03-28T03:06:02+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

the file format changed in the final version.
in the demo it was able to list & listen to audio files but in final it dont even list the files in the .cbf
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-03-28T09:10:53+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

ah I see, that's too bad. 
Pehaps I'll fix this in the next release.
## Post #14
- Username: Zagash
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-04-17T00:51:13+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

Great!

Is there any information about the release date of that new version of MultiEx
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-04-17T07:24:02+00:00
- Post Title: New archive format .CBF maybe you know something I don't?

Not yet. Currently writing my PhD-thesis takes up most of my time.   But there will be a new version in the future.
## Post #16
- Username: lumper
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-04-19T21:08:00+00:00
- Post Title: 

what about viewing the setup.cbf and config.cbf etc.. there in text and i believe just the games config where the movements, video selection m, etc... are stored, when i open them without an editor they look like this
"ƒ<
## Post #17
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-05-08T21:18:30+00:00
- Post Title: 

Hello!

Is there any Update about the Vietcong's CBF format?
## Post #18
- Username: Zagash
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-05-08T21:19:03+00:00
- Post Title: 

Khm,

Is there any Update about the Vietcong's CBF format?
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-05-08T21:50:45+00:00
- Post Title: 

Hmm, writing a PhD-thesis is not an easy job, it takes time. Besides, I will need to have a look-see in the CBF files of the retail version to update it. As I said in a previous thread, I can't go around buying all games just to support them in MultiEx Commander!   That would make me seriously broke!
## Post #20
- Username: newb
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-05-08T23:20:08+00:00
- Post Title: 

Mr.Mouse. If you need the cbf files I would be more than willing to send them to you. 
Also, what major is your phd thesis for?
## Post #21
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-05-09T06:31:37+00:00
- Post Title: 

I think sending them would be a problem right? I reckon these files are huge, so standard mailboxes won't accept them? Perhaps you can upload one or two (small ones) somwhere so I can download them?

I'm a moleculair biologist by trade, and I graduated in neurophysiology and medical physiology 4 years ago as a student of Biology. The last four years I have been working on elucidating a tiny part of the immune system of the brain as part of my PhD-project. I don't know what "major" that would be. Suffice it to say my thesis will make me PhD as a Moleculair and Genetics Neuroimmunologist. Because that's what I do.
## Post #22
- Username: newb
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-05-10T03:34:27+00:00
- Post Title: 

all i have to say is... damn your smart.. i remember biology in high school.... photosynthesis and stuff like that.. that was hard enough.
with the files, i could zip them for you and open a share on my hard drive and let you get them off my machine.. get ahold of me on AIM: jpp3773 and ill give you the address and share name from which you can get them.. i am a huge vietcong fan and would love to start modding the game.. i am willing to do anything i can to help. i am a computer engineer major, so if you would like to explain the extraction process to me i could try and help you develope extraction scripts for new games.. peace
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-05-12T14:41:05+00:00
- Post Title: 

Are you also to be found at ICQ/MSN?
## Post #24
- Username: newb
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-05-14T05:11:44+00:00
- Post Title: 

ok i just set up my msn account i think.  my id is [jpp3773@yahoo.com](mailto:jpp3773@yahoo.com)
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-05-14T08:28:11+00:00
- Post Title: 

Ok. Added.
## Post #26
- Username: Chevket
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-06-11T14:44:43+00:00
- Post Title: 

Hello !

Does the support of newb make you find some solution during your free time ?

It would be great if we can extract files from the cbf files !

Thanks for all your work !
## Post #27
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-11-26T14:34:30+00:00
- Post Title: 

its not working on full version, any ideas?
## Post #28
- Username: An American
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-12-28T09:36:27+00:00
- Post Title: 

I came here looking for info on the vc game cbf files. Its nice that you share your very own software.  

[link removed]

You may be smarter than a turd but your political views are as skewed as one just stepped on.  You are obviously too busy to actually read much or  understand what is going on now in the world or the history of the world.

 I assume you are Dutch?  I hope you recognize that those perfectly good Native American "Indian" Symbols that were taken and used by Hitler you installed in our flag show how little you appreciate what America did for you during WWII.   I do appreciate the support NL did give the US in the current conflicts.  Perhaps your site is only a satire but it doesn't look that way. Frankly it is offensive even if funny, if that is how you really think of the US.

I suggest you climb down from your "ivory tower" and remove the stick it has impaled in a unmentionable area that is effecting your impression of the USA and its people including those whom may not have voted for our current leaders.  It is our country not yours.  If you don't like it  I suggest you go live in a cave and wrap a towel around your head.  Would you like me to create a site showing your countries  gay political leader that was assassinated with those same symbols on your country's flag?  If you want to be part of the blame America crowd you would fit right in with some of our local liberals. But I suggest you should see it and its people for yourself  with an open mind and leave your  preconceptions behind. 

 Do you recognize that the US has  been fighting this war for years with the backing of the  United Nations supporting the containment of Saddam Hussein while the UN officials were all the while sucking in millions of $$ from a corrupt oil for food program.   Who do you think has been supplying weapons systems too these rouge states?  Do you think the youth of IRAN really want to support their Billionaire Mullahs? Or our youth want to support our leaders?  


Do you think we really like being there having our young men and older national guard in harms way?  I may not agree with many things the US has been involved in either. However please realize if it wasn't for the USA  your national language may have ended up being dictated to be either Deutsch or Russian.


 Please reconsider your website design it is offensive to Americans. And  looks like a beginning student of html created it.   

"This 
  page is a strong verbal protest against American agression on the sovereign 
  countries 
  of the world. Their Neo-Imperialism and theft of other countries' resources 
  is an insult to humanity. "

Yes there is oil there as well as in the kingdom of SAUD where much money was made selling the USA oil and donation to madrassas where plenty of young boys are being taught to hate the US and all Westerners including you and that we should be irradicated.   And perhaps the US should not support Israel or the Saudi Arabian Kingdom.  Just where did you get lost on this? Israel became a reality due to what happened in Europe.  History and News are effected by who writes it.  Did you know that in Japan they are taught that the US attacked them and nothing about Pearl Harbor in school history.

 Do you think the Arabs pushing the black Africans out of the Sudan is a respectable action either?  Do you think we can stop everything in the world? Bill Clinton did nothing about Rwanda and sometimes there is little one can do, even a country must pick its battles.

No one is perfect, i.e. Bosnian town of Srebrenica.

( The report by the Netherlands' Institute for War Documentation accused political leaders of carrying out an "ill-conceived plan" to boost Dutch international prestige. Unprepared troops were sent on a "mission impossible" to defend about 30,000 refugees who fled Serb forces in the surrounding hills, it said.  Some 200 lightly armed Dutch peacekeepers stood by as Mladic ordered Muslim men and women in Srebrenica separated. The women were deported and the men and boys were executed. 

Last week's report said Dutch troops were hampered by orders not to fire unless fired upon, and the military command had not provided the mandate needed to respond to 1,500 Serb attackers. The United Nations had declared Srebrenica a "safe zone" for Muslim refugees without defining what that meant, the report said.

Dutch leaders failed to prevent the 1995 massacre of Muslims in the Bosnian town of Srebrenica.

Army Chief of Staff Lt. Gen. Ad van Baal stepped down after meetings with Defense Minister Frank de Grave, taking responsibility for mistakes made by military commanders that led to the massacre of 7,500 Muslim men and boys by Serb troops.  )

I wish we could just all get along but when there foreign ppl that want to kill me I expect my government to do something about it. Incidentally the 19  9/11 highjackers were allowed to travel through IRAN with border guards receiving specific instructions "not" to have their passports stamped from higher Iranian authorities.  I think we have a definate problem with Iraq's large neighbor's government.  I would imagine that we should not have supported the Shah or many other worlds dictators and  if had not it may not be in the state of government it is in today.  But this support was related directly back to what happened in Europe in WWII and after.

However in this Iraq conflict
I repeat there were no inspectors there anymore and the corrupt UN that does nothing much but suck in money throught corruption only makes "resolutions" like paper Indian treaties that meant nothing while the USA actually enforced the no fly zone the last 10 years before this action.

You think we are there only for the oil then well you haven't learned much about the US or the World in all of that schooling.  You think the biotech industry your in is clean and free of problems?  Really please climb down from that Ivory Tower and remove that stick.
## Post #29
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-12-28T10:28:32+00:00
- Post Title: 

This is not the place for political comments, "An American". 

This site has nothing to do with the one you linked to. As such, refrain from further comments here. 

The link has been removed. If you wish to discuss politics, I'm sure there are other fora that would suit your needs in a better way.
## Post #30
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-07T06:26:53+00:00
- Post Title: 

Sorry to necro-post but I just wrote a script for those files, at least for the uncompressed *.cbf versions of Vietcong:

```

IDSTRING "BIGF"
goto 0x4
get COM byte
if COM == 1
	cleanexit
else
	goto 0x10
	get FILES long
	get FILEINFO long
	goto FILEINFO

	for i = 1 <= FILES
		get OFFSET long
		get ZERO long
		get UNK1 long
		get UNK2 long
		get UNK3 long
		get SIZE long
		get ZERO long
		get UNK5 long
		get UNK6 long
		get UNK7 long
		get NAME string
		log NAME OFFSET SIZE
	
	next i
endif
```
## Post #31
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-10-07T08:05:13+00:00
- Post Title: Re: New archive format .CBF maybe you know something I don't

only the multiplayer demo of the first Vietcong used that unusual type of CBF archive, but that script is not enough.

anyway the idea was good because I have seen that my cbfext tool didn't support it (ok I know that it's useless to support an archive used only in a jurassike demo but why not?) so I have updated it:
[http://aluigi.org/papers/cbfext.zip](http://aluigi.org/papers/cbfext.zip)
