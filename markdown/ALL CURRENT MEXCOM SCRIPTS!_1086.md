## Post #1
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-15T10:46:42+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

Scroll below for the atttached [complete text file](http://multiex.xentax.com/complete_scripts.txt) !

```
==-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-==
MultiEx Commander Binary MultiEx Scripts (BMS)
15-2-2005
--=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=--
Number of formats: 180
--=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=--
+-----------------------------------------------+
Game   : 	Abomination The Nemesis Project 
Archive: 	CLT
+-----------------------------------------------+
IDString 0 AWAD ;
Get FILECNTL Long 0 ;
SavePos FILESTART 0 ;
Set DUMMYL Long 65 ;
Set TAILOFF Long DUMMYL ;
Math TAILOFF *= 4 ;
Do ;
Math FILESTART += 1 ;
GoTo FILESTART 0 ;
Get FILENAME String 0 ;
Math FILESTART += TAILOFF ;
Math FILESTART -= 1 ;
GoTo FILESTART 0 ;
Get FILESIZE Long 0 ;
Get FILEOFF Long 0 ;
SavePos FILESTART 0 ;
Log FILENAME FILEOFF FILESIZE 0 0 ;
Math EXTRCNT += 1 ;
While EXTRCNT <> FILECNTL ;

+-----------------------------------------------+

+-----------------------------------------------+
Game   : 	Abomination The Nemesis Project 
Archive: 	AWF
+-----------------------------------------------+
Get FILECNTL Long 0 ;
SavePos FILESTART 0 ;
Set DUMMYL Long 65 ;
Set TAILOFF Long DUMMYL ;
Math TAILOFF *= 4 ;
Do ;
GoTo FILESTART 0 ;
Get FILEOFF Long 0 ;
SavePos FILESTART 0 ;
Get FILENAME String 0 ;
Math FILESTART += TAILOFF ;
GoTo FILEOFF 0 ;
Get DUMMYL Long 0 ;
Get FILESIZE Long 0 ;
Log FILENAME FILEOFF FILESIZE 0 0 ;
Math EXTRCNT += 1 ;
While EXTRCNT = FILECNTL ;

+-----------------------------------------------+

+-----------------------------------------------+
Game   : 	Actua Soccer 1 audio            
Archive: 	MAD
+-----------------------------------------------+
ImpType Standard ;
SavePos FILESTART 0 ;
GetDString FILENAME 16 0 ;
Get DUMMYL Long 0 ;
GoTo FILESTART 0 ;
Math DUMMYL /= 24 ;
For T = 1 To DUMMYL ;
GetDString FILENAME 16 0 ;
SavePos FOO 0 ;
Get FILEOFF Long 0 ;
SavePos FSO 0 ;
Get FILESIZE Long 0 ;
Log FILENAME FILEOFF FILESIZE FOO FSO ;
Next T ;

+-----------------------------------------------+

+-----------------------------------------------+
Game   : 	Actua Soccer 2 audio            
Archive: 	MAD
+-----------------------------------------------+
ImpType Standard ;
SavePos FILESTART 0 ;
GetDString FILENAME 16 0 ;
Get DUMMYL Long 0 ;
GoTo FILESTART 0 ;
Math DUMMYL /= 24 ;
For T = 1 To DUMMYL ;
GetDString FILENAME 16 0 ;
SavePos FOO 0 ;
Get FILEOFF Long 0 ;
SavePos FSO 0 ;
Get FILESIZE Long 0 ;
Log FILENAME FILEOFF FILESIZE FOO FSO ;
Next T ;

+-----------------------------------------------+

+-----------------------------------------------+
Game   : 	Actua Soccer 3 audio            
Archive: 	MAD
+-----------------------------------------------+
ImpType Standard ;
SavePos FILESTART 0 ;
GetDString FILENAME 16 0 ;
Get DUMMYL Long 0 ;
GoTo FILESTART 0 ;
Math DUMMYL /= 24 ;
For T = 1 To DUMMYL ;
GetDString FILENAME 16 0 ;
SavePos FOO 0 ;
Get FILEOFF Long 0 ;
SavePos FSO 0 ;
Get FILESIZE Long 0 ;
Log FILENAME FILEOFF FILESIZE FOO FSO ;
Next T ;

```


Etc...! 
Get the attached text file to get them all!
[complete_scripts.zip](https://xentaxbackup.github.io/file/133_complete_scripts.zip)
## Post #2
- Username: peter_limited
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-03-05T19:46:19+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

> Reply from Mr.Mouse
>
> 
Get the attached text file to get them all!

what text file
## Post #3
- Username: ilikeicecream
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-03-05T19:47:12+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

> Reply from peter_limited
>
> Mr.Mouse wrote:
Get the attached text file to get them all!

what text file

*flame*
note the link
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-03-06T22:39:42+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

Actually, to download the file, you have to be a registered member of the forum.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-06T23:04:47+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

> Reply from Dinoguy1000
>
> Actually, to download the file, you have to be a registered member of the forum.

Yep, that's right.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-03-06T23:51:19+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

Of course, you could always click through the link and then go to File > Save As...
## Post #7
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-17T13:25:15+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

Here has decided to please you so to say  with this collection of scripts MultiEx Commander supports +76 games  sat the whole week and checked.. All works perfectly   
Supports games :

4x4 Evolution
4x4 Evolution 2
Against Rome
Ajax Club Football 2005
Alien Versus Predator 2
Alpha Black Zero
American McGees Alice
Arena Wars
Armored First 3
Blitzkrieg
Blitzkrieg Burning Horizon
Blitzkrieg Rolling Thunder
BloodRayne 2 Demo
Brothers Pilots 4
C&C Generals Zero Hour
Call of Duty United Offensive
Cellblock Squadrons
Contract J.A.C.K
Counter-Strike Condition Zero
Deadly Dozen 2 Pacific Theater
Delta Force Black Hawk Down
Delta Force Black Hawk Down Team Sabre
Delta Force Extreme
Delta Force Task Force Dagger
Desperados Wanted Dead or Alive
Die Hard Nakatomi Plaza
Doom 2
Doom 3
Duke Nukem Manhatten Project
El Airplane
Empire Earth 2 
Empire Earth 2 Demo
F22 Lighting 3
FIFA 2004
FIFA 2005
Fire Starter
Freedom Fighters
Freedom Force
Freedom Force vs The 3rd Reich
Hard Truck 18 Wheels Of Steel
Heavy Metal F.A.K.K. 2
Hellhog XP
Heroes of Might & Magic 3 Armageddon's Blade
Heroes of Might & Magic 3 Restoration of Erathia
Heroes of Might & Magic 3 The Shadow of Death
Hot Rod American Street Drag
Hunting Unlimited 3
Itch
Jedi Knight 1
Jedi Knight 2 Jedi Academy
Jedi Knight 2 Jedi Outcast
Jedi Knight Mysteries of the Sith
Joint Operations Typhoon Rising
Kohan II Kings of War
Law And Order 3 Justice Is Served
Line of Sight Vietnam
Lionheart
Maximus XV
MDK 2
Medal Of Honor Allied Assault
Medal of Honor Allied Assaut Breakthrough
Medal of Honor Allied Assaut Spearhead
Metal Gear Solid
Microsoft Flight Simulator 2004
MIG 26 Fulcrum
Monte Cristo
Myst 4 Revelation
NBA 2003
Need For Speed 1
Need For Speed 2
Need For Speed 2 SE
Need For Speed 3
Need For Speed 4 High Stakes
Need For Speed 5 Porsche 2000
Neighbours From Hell
Neighbours From Hell 2
NHL 2003
No One Lives Forever 2
Outfront
Packmania 2
Perimeter
Pusher
Richard Burns Rally
Ricochet Lost Worlds Recharged
Ricochet Xtreme
Sabotain
Schizm 2
Serious Sam
Serious Sam The Second Encounter
Shogo Mobile Armor Division
Singles Flirt Up Your Life
Skisprung Wintercup 2005
Soldier Of Fortune 2 Double Helix
Soldiers Of Anarchy
Space Interceptor
Star Wolves
Starlancer
Swat 3 Close Quarters Battle
Team Factor
Terminator 3
Terrorist Takedown
The Fall Last Days Of Gaia
Thief
Tribes 2
Tron 2.0
UEFA Champions League 2004 - 2005
Universal Combat - A World Apart
Uplink
Vampire The Masquerade Redemption
XPand Rally
XS Mark
[MultiEx Commander Scripts Pack.rar](https://xentaxbackup.github.io/file/293_MultiEx Commander Scripts Pack.rar)
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-17T13:56:13+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

Awesome!
## Post #9
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-17T15:57:40+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

You only in a faint do not fall now I prepare for 24 more scripts
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-18T20:22:24+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

Good work at the WIKI!
## Post #11
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-18T23:41:03+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

> Reply from Mr.Mouse
>
>  Good work at the WIKI!
Thx i try
## Post #12
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-21T06:28:56+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

New scripts   
Support 20 games and 2 Utils

Games : 
Battlefield 1942 - FULL VERSION
Battlefield 1942 Vietnam - FULL VERSION
Descent 2
Euro 2000
I The Gangster
Marine Sharpshooter
Marine Sharpshooter 2 Jungle Warfare
NBA 2004
NBA 2005
Need For Speed 6 Hot Persuit 2
NHL 2004
NHL 2005
Paradise Cracked
Sudden Strike 2
Sudden Strike Forever
Sudden Strike Resource War
Thief 3
UEFA Euro 2004
World War 2 Normandy
World War 2 Sniper

Utils : 
Winamp - SKINS
Windows Media Player - SKINS

All works perfectly
[MultiEx Commander Scripts Pack 2.rar](https://xentaxbackup.github.io/file/297_MultiEx Commander Scripts Pack 2.rar)
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-21T06:55:50+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

Haha! And KorNet is BACK. Good work! I already included your previous list (registered users can use the web update function to get them). 

There were some already supported though. And I do not believe Doom 2 has PK3 files? So I did not include them. 

I will credit you in the next release for a lot of additional formats! Perhaps you should join XeNTaX.
## Post #14
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-21T07:39:10+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

I today looked mods for game Doom 2 and have seen archives in format PK3... If I am fair was surprised... Such format is used in Quake 3 Arena, Call Of Duty. By the way I wished to ask for MultiEx Commander 4.1.0 is Mex Binder Plus and Mex Scriptor? And I used that Mex Binder Plus from 4.0.1 and have put in version 4.1.0 as a result MultiEx Commander to swear the beginnings
## Post #15
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-21T08:10:07+00:00
- Post Title: ALL CURRENT MEXCOM SCRIPTS!

Better then scripts from a forum to clean
## Post #16
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-21T08:26:39+00:00
- Post Title: 

Update v1.0.2a   
Support 2 Games :

Bionicle
Joint Operations Typhoon Rising

All works perfectly  
[MultiEx Commander Scripts Pack v1.0.2a.rar](https://xentaxbackup.github.io/file/298_MultiEx Commander Scripts Pack v1.0.2a.rar)
## Post #17
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-21T08:33:24+00:00
- Post Title: 

+ 1 Script 

Doom 3 Resurrection Of Evil  
[Doom 3 Resurrection Of Evil.rar](https://xentaxbackup.github.io/file/299_Doom 3 Resurrection Of Evil.rar)
## Post #18
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-21T08:58:18+00:00
- Post Title: 

+ 1 Script 

Age of Mythology The Titans 

```
Set S Long 12 ;
GoTo S 0 ;
Get FC Long 0 ;
Get FTSize Long 0 ;
SavePos TailOffOff 0 ;
Get TO Long 0 ;
Set FJ Long 4 ;
Math FJ *= FC ;
GoTo TO 0 ;
For TE = 1 To FC ;
Get FE Long 0 ;
Math FE += TO ;
Math FE += FJ ;
SavePos CB 0 ;
GoTo FE 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos TP 0 ;
Math TP += 12 ;
GoTo TP 0 ;
Get FN String 0 ;
Log FN FO FS FOO FSO ;
GoTo CB 0 ;
Next TE ;
```

[Age of Mythology The Titans.rar](https://xentaxbackup.github.io/file/300_Age of Mythology The Titans.rar)
## Post #19
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-21T09:10:02+00:00
- Post Title: 

+1 Script 
Joint Operations Escalation  
[Joint Operations Escalation.rar](https://xentaxbackup.github.io/file/301_Joint Operations Escalation.rar)
## Post #20
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-21T10:22:45+00:00
- Post Title: 

+1 Script .. MultiEx Commander support new game -> Battlefiled 2 Demo ( ONLY )  
[Battlefield 2 Demo.rar](https://xentaxbackup.github.io/file/302_Battlefield 2 Demo.rar)
## Post #21
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-21T16:11:30+00:00
- Post Title: 

+1 Script ... Support Battlefield 2 ( FULL VERSION )  
[Battlefield 2.rar](https://xentaxbackup.github.io/file/304_Battlefield 2.rar)
## Post #22
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-22T15:10:56+00:00
- Post Title: 

+1 Script ... MultiEx Commander Support new game Hoyle Games Demo 2005 ( ONLY )  
[Hoyle Games Demo 2005.rar](https://xentaxbackup.github.io/file/307_Hoyle Games Demo 2005.rar)
## Post #23
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-23T14:21:04+00:00
- Post Title: 

Mr.Mouse you added new sctipts in mc.mrf ?   

Doom 3 Resurrection Of Evil
Age of Mythology The Titans
Battlefiled 2 Demo 
Battlefiled 2
Hoyle Games 2005 Demo
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-23T15:03:58+00:00
- Post Title: 

Not yet, will do when I have the time.
## Post #25
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-23T15:43:29+00:00
- Post Title: 

Here now at present MultiEx Commander supports 358 games + 5 which are written above... Soon for 400 will come and MultiEx Commander it will not be loaded
## Post #26
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-23T16:33:50+00:00
- Post Title: 

Ha, I have fixed that .. it's unlimited.
## Post #27
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-06-23T16:53:04+00:00
- Post Title: 

It in what version 4.1.0 or in future version MultiEx Commander?
## Post #28
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-04T20:46:53+00:00
- Post Title: 

Ok, all the scripts are now available from the webupdate.
## Post #29
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-05T14:43:53+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Ok, all the scripts are now available from the webupdate.
WOW Perfect
## Post #30
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-15T13:10:55+00:00
- Post Title: 

New scripts WAD and PAK   
Support next 19 games :

Action Half-Life
Azure Sheep
FireArms
FrontLine Force
Gangsta Wars
Half-Life Battles of the Millenium
Half-Life Game of the Year Edition
Half-Life Natural Selection
Half-Life Poke646
Half-Life Rally
Half-Life Redemption
Half-Life Retribution
Half-Life Science And Industry
Half-Life Todesangst
Half-Life Uplink
Half-Life Vampire Slayer
Star Gate
They Hunger
They Hunger Trilogy

Half-Life Engine   
All works perfectly  
[MultiEx Commander New Scripts Pack.rar](https://xentaxbackup.github.io/file/357_MultiEx Commander New Scripts Pack.rar)
## Post #31
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-15T13:16:31+00:00
- Post Title: 

+1 Script

Conquest of the New World

[Conquest of the New World.rar](https://xentaxbackup.github.io/file/358_Conquest of the New World.rar)
## Post #32
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-15T13:18:49+00:00
- Post Title: 

+1 Script

Hands Of Fate

[Hands Of Fate.rar](https://xentaxbackup.github.io/file/359_Hands Of Fate.rar)
## Post #33
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-15T13:21:34+00:00
- Post Title: 

+1 Script

Search & Rescue 2
[Search & Rescue 2.rar](https://xentaxbackup.github.io/file/360_Search & Rescue 2.rar)
## Post #34
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-15T13:23:56+00:00
- Post Title: 

+1 Script

Search & Rescue 3

Like more updatings will not be 
[Search & Rescue 3.rar](https://xentaxbackup.github.io/file/361_Search & Rescue 3.rar)
## Post #35
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-18T20:35:37+00:00
- Post Title: 

Thanks!  !


By the way:

[viewtopic.php?p=9985#9985](http://forum.xentax.com/viewtopic.php?p=9985#9985)

Get the MexBinderPlus program there! Especially for registered users that can't wait until the new 4.2.0 version of MexCom.
## Post #36
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-18T23:06:18+00:00
- Post Title: 

```
GoTo EOF 0 ;
SavePos End 0 ;
Set TailSize Long 288 ;
Math End -= TailSize ;
Math End += 1 ;
GoTo End 0 ;
For T = 1 To 32 ;
GetDString B 2 0 ;
String InfoName += B ;
Next T ;
Get HeaderStart Long 0 ;
Get D Long 0 ;
Get HeaderSize Long 0 ;
SavePos CP 0 ;
Math CP += 20 ;
GoTo CP 0 ;
Set InfoName String B ;
For T = 1 To 32 ;
GetDString B 2 0 ;
String InfoName += B ;
Next T ;
Get FilesStart Long 0 ;
Get D Long 0 ;
Get FilesSize Long 0 ;
SavePos CP 0 ;
Math CP += 20 ;
GoTo CP 0 ;
Set InfoName String B ;
For T = 1 To 32 ;
GetDString B 2 0 ;
String InfoName += B ;
Next T ;
Set ResetString String B ;
Get FooterStart Long 0 ;
Get D Long 0 ;
Get FooterSize Long 0 ;
SavePos CP 0 ;
GoTo FooterStart 0 ;
Get FileNum Long 0 ;
Set T Long 1 ;
Do ;
Get NameSize Int 0 ;
Set FN String ResetString ;
For A = 1 To NameSize ;
GetDString B 2 0 ;
String FN += B ;
Next A ;
Get RelOff Long 0 ;
Math RelOff += FilesStart ;
Get D Long 0 ;
Get Size Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Log FN RelOff Size 0 0 ;
Math T += 1 ;
While T <= FileNum ;
```


+Script Axis & Allies Update ... HoT FiX

[Axis & Allies.rar](https://xentaxbackup.github.io/file/368_Axis & Allies.rar)
## Post #37
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-18T23:08:52+00:00
- Post Title: 

Mr. Mouse at game 18 Wheel of Steel Pedal to the Metal expansion of game archive not ZIP and SCS... Change expansion in mc.mrf
[18 Wheel of Steel Pedal to the Metal.rar](https://xentaxbackup.github.io/file/369_18 Wheel of Steel Pedal to the Metal.rar)
## Post #38
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-18T23:11:58+00:00
- Post Title: 

Now that's something like it... When release MexCom 4.2.0?
## Post #39
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-23T08:27:36+00:00
- Post Title: 

Added new formats to the webupdate.
## Post #40
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-26T21:03:39+00:00
- Post Title: 

+20 New Scripts 

Big Kahuna Reef
Black Arrow
Cold Fear
Dino And Aliens
Driver 3
First To Fight
Grand Theft Auto San Andreas
Halo
Halo 2
Mortal Combat Trilogy
Restricted Area
Sacred
Scrapland
Screamer 4x4
Second Sight
Starsy And Huth
Total Club Manager 2005
Vietcong
Wanted Guns
WWII Pacific Heroes

Mr.Mouse add this scripts in mc.mrf
## Post #41
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-26T21:59:34+00:00
- Post Title: 

Thank you!! I've got them!
## Post #42
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-27T00:15:35+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Thank you!! I've got them!
Good using web update ?
## Post #43
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-03T02:12:45+00:00
- Post Title: 

+1 Script

Midnight Outlaw Illegal Street Drag Nitro Edition
[Midnight Outlaw Illegal Street Drag Nitro Edition.rar](https://xentaxbackup.github.io/file/395_Midnight Outlaw Illegal Street Drag Nitro Edition.rar)
## Post #44
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-08-03T02:20:50+00:00
- Post Title: 

With how much he contributes, I'm thinking Kornet needs some special recognition here! Just a thought, you know...
## Post #45
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-03T06:50:25+00:00
- Post Title: 

Oh yes, that's why he's a three star Very Very Important Person (VVIP). 
Also, he will be in the credits of the new version of MultiEx Commander. Don't worry, all will get what they deserve.
## Post #46
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-03T15:21:33+00:00
- Post Title: 

XeNTaX Teamâ„¢    ... Wait new version MultiEx Commander .
## Post #47
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-08-03T16:14:42+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Oh yes, that's why he's a three star Very Very Important Person (VVIP). 
Also, he will be in the credits of the new version of MultiEx Commander. Don't worry, all will get what they deserve.
Ooh, does that mean I get a knuckle sandwich?  (wierd sense of humor)
## Post #48
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-08-04T19:25:38+00:00
- Post Title: 

This is a revised script, as added to the wiki by me a few minutes ago.

It now handles every SRF file I have without error (however, the String append command does not appear to work, but is left in for better documentation of the GRAF)

```
Get FILELNGH Long 0 ;
ReverseLong FILELNGH ;
Get HEADLNGH Long 0 ;
ReverseLong HEADLNGH ;
SavePos FILESTART 0 ;
Do ;
GoTo FILESTART 0 ;
GetDString FILENAME 4 0 ;
Get SUBCOUNT Long 0 ;
ReverseLong SUBCOUNT ;
For T = 1 To SUBCOUNT ;
GetDString SUBNAME 4 0 ;
String FILENAME += SUBNAME ;
Get FILEOFF Long 0 ;
ReverseLong FILEOFF ;
Get FILESIZE Long 0 ;
ReverseLong FILESIZE ;
Log FILENAME FILEOFF FILESIZE 0 0 ;
String FILENAME -= SUBNAME ;
Next T ;
SavePos FILESTART 0 ;
While FILESTART < HEADLNGH ;

```
## Post #49
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-04T23:48:11+00:00
- Post Title: 

What game uses the given format of archive?
## Post #50
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-08-05T18:52:30+00:00
- Post Title: 

It's a list of games really, mainly stuff produced by Berkeley Systems or Sierra using the You Don't Know Jack! Engine

This includes every US release of the game up to 5th Dementia, the UK game, the Japanese game, the French game and the first two German ones at least.

Although I haven't tested them, it should also work on HeadRush and Austin Powers: Operation Trivia.

The files extracted are valid, but I can't find any players for them (some are Apple style IMA ADPCM, and others are an animation format I'm not familiar with).
## Post #51
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-08-28T19:07:15+00:00
- Post Title: 

Very Good
## Post #52
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-07T19:50:34+00:00
- Post Title: 

+1 Script 

Fifa 2006
[FIFA 2006.rar](https://xentaxbackup.github.io/file/424_FIFA 2006.rar)
## Post #53
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-10-14T17:01:41+00:00
- Post Title: 

+1 Script -> Soldiers - Heroes of World War II - PAK

Installiation :
1 - Run MultiEx Commander 4.2.0 
2 - Tools -> Add custom BSM to MRF 
3 - In opened dialog select filter -> MultiEx ZIP and open PAK.zip 
4 - Provide the name enter - Soldiers - Heroes of World War II
5 - Push button OK .. 
6 - Wait for restart MultiEx Commander 
7 - File -> Open ->  Select Soldiers - Heroes of World War II (*.PAK) 

Enjoy  
[Soldiers - Heroes of World War II.zip](https://xentaxbackup.github.io/file/463_Soldiers - Heroes of World War II.zip)
## Post #54
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-10-18T00:13:37+00:00
- Post Title: 

+1 Script -> Serious Sam 2 - GRP

Installiation Script : 
1 - Run MultiEx Commander 4.2.0 
2 - Tools -> Add custom BSM to MRF 
3 - In opened dialog select filter -> MultiEx ZIP and open GRO.zip 
4 - Provide the name enter - Serious Sam 2 
5 - Push button OK .. 
6 - Wait for restart MultiEx Commander 
7 - File -> Open -> Select filter -> Serious Sam 2 (*.GRO) 

Enjoy  
[Serious Sam 2.zip](https://xentaxbackup.github.io/file/465_Serious Sam 2.zip)
## Post #55
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-10-18T07:33:49+00:00
- Post Title: 

Very nice!
## Post #56
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-10-18T20:54:49+00:00
- Post Title: 

Mr.Mouse how working ZIP's files ( Password )
## Post #57
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-10-18T22:24:05+00:00
- Post Title: 

Small FIX For Serious Sam 2 :

Rename GRP.zip in GRO.zip and ADD in mc.mrf ... Enjoy.
## Post #58
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-10-21T11:19:55+00:00
- Post Title: 

+1 Script -> Qauke 4 - PK4 

Installiation Script : 
1 - Run MultiEx Commander 4.2.0 
2 - Tools -> Add custom BSM to MRF 
3 - In opened dialog select filter -> MultiEx ZIP and open PK4.zip 
4 - Provide the name enter - Qauke 4 
5 - Push button OK .. 
6 - Wait for restart MultiEx Commander 
7 - File -> Open -> Select filter -> Qauke 4 (*.PK4) 

Enjoy

P.S - Remember REGISTERING MultiEx Commander 4.2.0 ( $6 )  
[Quake 4.zip](https://xentaxbackup.github.io/file/467_Quake 4.zip)
## Post #59
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-19T20:04:11+00:00
- Post Title: 

+1 Script -> Shadowgrounds - FBZ 

Installiation Script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> MultiEx ZIP and open FBZ.zip
4 - Provide the name enter - Shadowgrounds
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select filter -> Shadowgrounds (*.FBZ) 

Enjoy
[Shadowgrounds.zip](https://xentaxbackup.github.io/file/497_Shadowgrounds.zip)
## Post #60
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-26T04:24:31+00:00
- Post Title: 

+1 Script -> Dirty Little Helper '98 - DLU

Installiation Script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> MultiEx ZIP and open DLU.zip
4 - Provide the name enter - Dirty Little Helper '98
5 - Push button OK ..
6 - Wait for restart MultiEx Commander 
7 - File -> Open -> Select filter -> Dirty Little Helper '98 (*.DLU) 

Enjoy  
[Dirty Little Helper '98.zip](https://xentaxbackup.github.io/file/515_Dirty Little Helper '98.zip)
## Post #61
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-26T08:16:52+00:00
- Post Title: 

Thanks Kornet!!!!
## Post #62
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-26T10:13:00+00:00
- Post Title: 

+1 Script - Backspin Billiards - DAT

Installiation :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open DAT.bms
4 - Provide the name enter - Backspin Billiards
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Backspin Billiards (*.DAT)

```
IDString 0 PXMDY ;
Get RN Long 0 ;
For T = 1 To RN ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
Get NameSize Byte 0 ;
GetDString FileName NameSize 0 ;
Log FileName FO FS FOO FSO ;
Next T ;
```


Big thanks Mr.Mouse  
[Backspin Billiards.zip](https://xentaxbackup.github.io/file/519_Backspin Billiards.zip)
## Post #63
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-26T10:49:18+00:00
- Post Title: 

+1 Script - Mercedes Benz World Racing - SYN

Installiation :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open SYN.bms
4 - Provide the name enter - Mercedes Benz World Racing
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Mercedes Benz World Racing (*.SYN)

```
IDString 0 SYN!v2.0 ;
Get FN Long 0 ;
Set D Long 64 ;
GoTo D 0 ;
For T = 1 To FN ;
GetDString FNAME 48 0 ; 
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos UKO 0 ;
Get UK Long 0 ;
Get UK2 Long 0 ;
Log FNAME FO FS FOO FSO ;
Next T ;
```


Thx Mike  
[Mercedes Benz World Racing.zip](https://xentaxbackup.github.io/file/521_Mercedes Benz World Racing.zip)
## Post #64
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-26T20:44:05+00:00
- Post Title: 

Thanks KorNet and PXR for your excellent work!
## Post #65
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-27T14:34:54+00:00
- Post Title: 

Thanks You for scripts
## Post #66
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-31T16:25:55+00:00
- Post Title: 

+1 Script - NHL 2006 -> VIV/BIG

```
IDString 0 BIGF ;
Get D Long 0 ;
Get FC Long 0 ;
ReverseLong FC ;
Get D Long 0 ;
SavePos FS 0 ;
For T = 1 To FC ;
GoTo FS 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
ReverseLong FO ;
SavePos FSO 0 ;
Get FSI Long 0 ;
ReverseLong FSI ;
Get FN String 0 ;
SavePos FS 0 ;
Log FN FO FSI FOO FSO ;
Next T ;
```

Installiation BIG script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open BIG.bms
4 - Provide the name enter - NHL 2006
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - NHL 2006 (*.BIG)

Installiation VIV script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open VIV.bms
4 - Provide the name enter - NHL 2006
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - NHL 2006 (*.VIV)

Enjoy  
[NHL 2006.ZIP](https://xentaxbackup.github.io/file/528_NHL 2006.ZIP)
## Post #67
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-31T16:50:02+00:00
- Post Title: 

+1 Script - EA Cricket 2005 -> BIG

```
IDString 0 BIGF ;
Get D Long 0 ;
Get FC Long 0 ;
ReverseLong FC ;
Get D Long 0 ;
SavePos FS 0 ;
For T = 1 To FC ;
GoTo FS 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
ReverseLong FO ;
SavePos FSO 0 ;
Get FSI Long 0 ;
ReverseLong FSI ;
Get FN String 0 ;
SavePos FS 0 ;
Log FN FO FSI FOO FSO ;
Next T ;
```


Installiation BIG script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open BIG.bms
4 - Provide the name enter - EA Cricket 2005
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - EA Cricket 2005 (*.BIG)

Enjoy  
[EA Cricket 2005.zip](https://xentaxbackup.github.io/file/529_EA Cricket 2005.zip)
## Post #68
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-31T16:50:47+00:00
- Post Title: 

+1 Script - Harry Potter And The Goblet Of Fire -> BIG

```
IDString 0 BIGF ;
Get D Long 0 ;
Get FC Long 0 ;
ReverseLong FC ;
Get D Long 0 ;
SavePos FS 0 ;
For T = 1 To FC ;
GoTo FS 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
ReverseLong FO ;
SavePos FSO 0 ;
Get FSI Long 0 ;
ReverseLong FSI ;
Get FN String 0 ;
SavePos FS 0 ;
Log FN FO FSI FOO FSO ;
Next T ;
```


Installiation BIG script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open BIG.bms
4 - Provide the name enter - Harry Potter And The Goblet Of Fire
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Harry Potter And The Goblet Of Fire (*.BIG)

Enjoy  
[Harry Potter And The Goblet Of Fire.zip](https://xentaxbackup.github.io/file/530_Harry Potter And The Goblet Of Fire.zip)
## Post #69
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-01T22:12:40+00:00
- Post Title: 

+1 Script by Mr.Mouse - Need For Speed Most Wanted - BIN

```
Get VarType Long 0 ;
Get RemainingSize Long 0 ;
Get U1 Long 0 ;
Get RelOff1 Long 0 ;
SavePos COff 0 ;
Math COff += RelOff1 ;
GoTo COff 0 ;
Get VarType Long 0 ;
Get ResInfoSize Long 0 ;
Get VarType Long 0 ;
Get HeaderSize Long 0 ;
SavePos COff 0 ;
Get U2 Long 0 ;
GetDString BINName 28 0 ;
GetDString OriName 64 0 ;
Set FP String . ;
Get OriSize Long 0 ;
Math COff += HeaderSize ;
GoTo COff 0 ;
Get VarType Long 0 ;
Get TableSize Long 0 ;
SavePos COff 0 ;
Math COff += TableSize ;
GoTo COff 0 ;
Get VarType Long 0 ;
Get ResInfoSize Long 0 ;
Set FileNum Long ResInfoSize ;
Math FileNum /= 24 ;
For T = 1 To FileNum ;
Get VarType Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get UCS Long 0 ;
Get U3 Long 0 ;
Get U4 Long 0 ;
Set Name String OriName ;
String Name += FP ;
String Name += T ;
Log Name FO FS FOO FSO ;
Next T ;
```


Installiation BIN script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open BIN.bms
4 - Provide the name enter - Need For Speed Most Wanted
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Need For Speed Most Wanted (*.BIN)

Enjoy  
[Need For Speed Most Wanted.zip](https://xentaxbackup.github.io/file/533_Need For Speed Most Wanted.zip)
## Post #70
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-01T22:20:34+00:00
- Post Title: 

+Script

Game Name : DarkWatch
Author : Mr.Mouse
File Type : PCK

```
GoTo EOF 0 ;
SavePos END 0 ;
Math END -= 7 ;
GoTo END 0 ;
SavePos TailOffOff 0 ;
Get TailOffSet Long 0 ;
GoTo TailOffSet 0 ;
Get DIREntries Long 0 ;
Get FileNum Long 0 ;
Get U1 Long 0 ;
Get U2 Long 0 ;
SavePos FNOffset 0 ;
Math DIREntries *= 16 ;
Math FNOffset += DIREntries ;
Set C Long 0 ;
Do ;
Get U4 Long 0 ;
Get U5 Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos FP 0 ;
If U5 <> 0 ;
GoTo FNOffset 0 ;
Get U6 Long 0 ;
Get NameSize Long 0 ;
GetDString FName NameSize 0 ;
SavePos FNOffset 0 ;
Math C += 1 ;
Log FName FO FS FOO FSO ;
GoTo FP 0 ;
EndIf ;
While C < FileNum ;
```


Installiation PCK script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open PCK.bms
4 - Provide the name enter - DarkWatch
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - EDarkWatch (*.PCK)

Enjoy 
[DarkWatch.zip](https://xentaxbackup.github.io/file/534_DarkWatch.zip)
## Post #71
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-01T22:24:45+00:00
- Post Title: 

+Script

Game Name : Dead To Right 2 (PS2)
Author : Mr.Mouse
File Type : PAK

```
Get U1 Long 0 ;
Get U2 Long 0 ;
Get U3 Long 0 ;
Get FileNum Long 0 ;
For T = 1 To FileNum ;
GetCT FName String 10 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get U3 Long 0 ;
Log FName FO FS FOO FSO ;
Next T ;
```


Installiation PAK script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open PAK.bms
4 - Provide the name enter - Dead To Right 2 (PS2)
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Dead To Right 2 (PS2) (*.PAK)

Enjoy 
[Dead To Right 2 (PS2).zip](https://xentaxbackup.github.io/file/535_Dead To Right 2 (PS2).zip)
## Post #72
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-01T22:29:24+00:00
- Post Title: 

+Script

Game Name : Backyard Football
Author : Mr.Mouse
File Type : MET

```
Get HeaderSize Long 0 ;
Get DataSize Long 0 ;
SavePos COff 0 ;
Do ;
SavePos FOO 0 ;
Get FO Long 0 ;
If FO <> 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get NSize Long 0 ;
GetDString FName NSize 0 ;
SavePos COff 0 ;
Log FName FO FS FOO FSO ;
Else ;
Set COff Long HeaderSize ;
EndIf ;
While COff < HeaderSize ;
```


Installiation MET script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open MET.bms
4 - Provide the name enter - Backyard Football
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Backyard Football (*.MET)

Enjoy 
[Backyard Football.zip](https://xentaxbackup.github.io/file/536_Backyard Football.zip)
## Post #73
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-01T22:41:14+00:00
- Post Title: 

+1 Script

Game Name : Need For Speed Underground 2
Author : Mr.Mouse
File Type : BIN

```
Get VarType Long 0 ;
Get RemainingSize Long 0 ;
Get U1 Long 0 ;
Get RelOff1 Long 0 ;
SavePos COff 0 ;
Math COff += RelOff1 ;
GoTo COff 0 ;
Get VarType Long 0 ;
Get ResInfoSize Long 0 ;
Get VarType Long 0 ;
Get HeaderSize Long 0 ;
SavePos COff 0 ;
Get U2 Long 0 ;
GetDString BINName 28 0 ;
GetDString OriName 64 0 ;
Set FP String . ;
Get OriSize Long 0 ;
Math COff += HeaderSize ;
GoTo COff 0 ;
Get VarType Long 0 ;
Get TableSize Long 0 ;
SavePos COff 0 ;
Math COff += TableSize ;
GoTo COff 0 ;
Get VarType Long 0 ;
Get ResInfoSize Long 0 ;
Set FileNum Long ResInfoSize ;
Math FileNum /= 24 ;
For T = 1 To FileNum ;
Get VarType Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get UCS Long 0 ;
Get U3 Long 0 ;
Get U4 Long 0 ;
Set Name String OriName ;
String Name += FP ;
String Name += T ;
Log Name FO FS FOO FSO ;
Next T ;
```


Installiation BIN script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open BIN.bms
4 - Provide the name enter - Need For Speed Underground 2
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Need For Speed Underground 2 (*.BIN)

Enjoy  
[Need For Speed Underground 2.zip](https://xentaxbackup.github.io/file/537_Need For Speed Underground 2.zip)
## Post #74
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-02T00:01:37+00:00
- Post Title: 

OMG Excellent, KorNet!  You the man!
## Post #75
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-02T05:01:42+00:00
- Post Title: 

+1 Script Call Of Duty 2 - IWD

Installiation :
1 - Run MultiEx Commander 4.2.0 
2 - Tools -> Add custom BSM to MRF 
3 - In opened dialog select filter -> MultiEx ZIP and open IWD.zip 
4 - Provide the name enter - Call Of Duty 2
5 - Push button OK .. 
6 - Wait for restart MultiEx Commander 
7 - File -> Open ->  Select - Call Of Duty 2 (*.IWD) 

Enjoy  
[Call Of Duty 2.zip](https://xentaxbackup.github.io/file/540_Call Of Duty 2.zip)
## Post #76
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-02T21:32:50+00:00
- Post Title: 

+Script

Game Name : Mechanized Assault And Exploration
Author : Mr.Mouse
File Type : RES

```
ImpType StandardTail ;
SavePos TailOffOff 0 ;
Get TailOff Long 0 ;
Get TailSize Long 0 ;
Set FileNum Long TailSize ;
Math FileNum /= 16 ;
GoTo TailOff 0 ;
For T = 1 To FileNum ;
GetDString Name 8 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log Name FO FS FOO FSO ;
Next T ;
```


Installiation RES script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open RES.bms
4 - Provide the name enter - Mechanized Assault And Exploration
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Mechanized Assault And Exploration (*.RES)

Enjoy 
[Mechanized Assault And Exploration.zip](https://xentaxbackup.github.io/file/542_Mechanized Assault And Exploration.zip)
## Post #77
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-03T20:28:10+00:00
- Post Title: 

+Script

Game Name : Evil Dead Regeneration
Author : Mr.Mouse
File Type : FSB
Thanks : sajad

```
Get FNum Long 0 ;
Get FO Long 0 ;
Math FO += 24 ;
Get DataLen Long 0 ;
Get Dummy1 Long 0 ;
Get DummyNull Long 0 ;
For n = 1 To FNum ;
SavePos Start 0 ;
Get EntryLen Int 0 ;
Math Start += EntryLen ;
SavePos EndFN 0 ;
Math EndFN += 34 ;
Get FN String 0 ;
GoTo EndFN 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
GoTo Start 0 ;
Log FN FO FS 0 FSO ;
Math FO += FS ;
Next n ;
```


Installiation RES script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open FSB.bms
4 - Provide the name enter - Evil Dead Regeneration
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Evil Dead Regeneration (*.FSB)

Enjoy 
[Evil Dead Regeneration.zip](https://xentaxbackup.github.io/file/550_Evil Dead Regeneration.zip)
## Post #78
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-03T21:09:26+00:00
- Post Title: 

+1 Script -> Slave Zero - ZIP

Installiation :
1 - Run MultiEx Commander 4.2.0 
2 - Tools -> Add custom BSM to MRF 
3 - In opened dialog select filter -> MultiEx ZIP and open ZIP.zip 
4 - Provide the name enter - Slave Zero
5 - Push button OK .. 
6 - Wait for restart MultiEx Commander 
7 - File -> Open ->  Select -> Slave Zero (*.ZIP) 

Enjoy  
[Slave Zero.zip](https://xentaxbackup.github.io/file/551_Slave Zero.zip)
## Post #79
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-06T19:47:37+00:00
- Post Title: 

+1 Script

Game Name : Nexus - The Kindom Of THe Winds
Author : PXR
File Type : DAT

```
Get FILENUM Long 0 ;
Math FILENUM -= 1 ;
For F = 1 To FILENUM ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
GetDString FNAME 13 0 ;
SavePos NEXTFILE 0 ;
Get FSIZE Long 0 ;
Math FSIZE -= FOFFSET ;
Log FNAME FOFFSET FSIZE FOFFSETX 0 ;
GoTo NEXTFILE 0 ;
Next F ;
```


Installiation RES script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open DAT.bms
4 - Provide the name enter - Nexus - The Kindom Of THe Winds
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Nexus - The Kindom Of THe Winds (*.DAT)

Enjoy 
[Nexus - The Kindom Of THe Winds.rar](https://xentaxbackup.github.io/file/568_Nexus - The Kindom Of THe Winds.rar)
## Post #80
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-09T21:20:12+00:00
- Post Title: 

+Script

Game Name : Crazy Frog Racer
Author : Mr.Mouse
File Type : FSB

```
Get FNum Long 0 ;
Get FO Long 0 ;
Math FO += 24 ;
Get DataLen Long 0 ;
Get Dummy1 Long 0 ;
Get DummyNull Long 0 ;
For n = 1 To FNum ;
SavePos Start 0 ;
Get EntryLen Int 0 ;
Math Start += EntryLen ;
SavePos EndFN 0 ;
Math EndFN += 34 ;
Get FN String 0 ;
GoTo EndFN 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
GoTo Start 0 ;
Log FN FO FS 0 FSO ;
Math FO += FS ;
Next n ;
```


Installiation RES script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open FSB.bms
4 - Provide the name enter - Crazy Frog Racer
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Crazy Frog Racer (*.FSB)

Enjoy 
[Crazy Frog Racer.zip](https://xentaxbackup.github.io/file/578_Crazy Frog Racer.zip)
## Post #81
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-08T19:16:56+00:00
- Post Title: 

+1 Script -> Call of Juarez - PAK

Installiation :
1 - Run MultiEx Commander 4.2.0 
2 - Tools -> Add custom BSM to MRF 
3 - In opened dialog select filter -> MultiEx ZIP and open PAK.zip 
4 - Provide the name enter - Call of Juarez
5 - Push button OK .. 
6 - Wait for restart MultiEx Commander 
7 - File -> Open ->  Select -> Call of Juarez (*.PAK) 

Enjoy  
[Call of Juarez.zip](https://xentaxbackup.github.io/file/786_Call of Juarez.zip)
## Post #82
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-09T07:53:31+00:00
- Post Title: 

And he's back  

Soon you will be able to enter the script at the Xentax WIKI and it will be immediately available to MexCom users.
## Post #83
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-13T03:20:49+00:00
- Post Title: 

+1 Script -> Switchball - BOD

Author : PXR ( Thank you   )

Installiation :
1 - Run MultiEx Commander 4.2.0 
2 - Tools -> Add custom BSM to MRF 
3 - In opened dialog select filter -> BMS and open BOD.bms
4 - Provide the name enter - Switchball
5 - Push button OK .. 
6 - Wait for restart MultiEx Commander 
7 - File -> Open ->  Select -> Switchball (*.BOD) 

Enjoy  
[Switchball.zip](https://xentaxbackup.github.io/file/789_Switchball.zip)
## Post #84
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-16T18:48:42+00:00
- Post Title: 

+Script

Game Name : Tom Clancy Rainbow Six Lockdown
Author : Mr.Mouse
File Type : FSB

```
Get FNum Long 0 ;
Get FO Long 0 ;
Math FO += 24 ;
Get DataLen Long 0 ;
Get Dummy1 Long 0 ;
Get DummyNull Long 0 ;
For n = 1 To FNum ;
SavePos Start 0 ;
Get EntryLen Int 0 ;
Math Start += EntryLen ;
SavePos EndFN 0 ;
Math EndFN += 34 ;
Get FN String 0 ;
GoTo EndFN 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
GoTo Start 0 ;
Log FN FO FS 0 FSO ;
Math FO += FS ;
Next n ;
```


Installiation script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open FSB.bms
4 - Provide the name enter - Tom Clancy Rainbow Six Lockdown
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Tom Clancy Rainbow Six Lockdown (*.FSB)

Enjoy 
[Tom Clancy Rainbow Six Lockdown.ZIP](https://xentaxbackup.github.io/file/790_Tom Clancy Rainbow Six Lockdown.ZIP)
## Post #85
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T15:20:57+00:00
- Post Title: 

+Script

Game Name : The Da Vinci Code
Author : PXR
File Type : RPE

```
Get TEMP Long 0 ; 
Get FILENUM Long 0 ; 
GoTo 32 0 ; 
For F = 1 To FILENUM ; 
GetDString FNAME 6 0 ; 
SavePos TEMP 0 ; 
Math TEMP += 26 ; 
GoTo TEMP 0 ; 
SavePos FOFFSETX 0 ; 
Get FOFFSET Long 0 ; 
SavePos FSIZEX 0 ; 
Get FSIZE Long 0 ; 
Get TEMP Long 0 ; 
Log FNAME FOFFSET FSIZE FOFFSETX FSIZEX ; 
Next F ;
```


Installiation script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open RPE.bms
4 - Provide the name enter - The Da Vinci Code
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - The Da Vinci Code (*.RPE)

Enjoy 
[The Da Vinci Code.zip](https://xentaxbackup.github.io/file/795_The Da Vinci Code.zip)
## Post #86
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T19:32:05+00:00
- Post Title: 

+Script

Game Name : Moorhuhn Piraten
Author : PXR
File Type : DAT

```
IDString 0 MHP ; 
Set ENDDIRSTRING String **** ; 
GoTo 64 0 ; 
Get DATAX Long 0 ; 
GoTo 80 0 ; 
Do ; 
GetDString FNAME 64 0 ; 
If FNAME = ENDDIRSTRING ; 
CleanExit ; 
EndIf ; 
SavePos FOFFSETX 0 ; 
Get FOFFSET Long 0 ; 
SavePos FSIZEX 0 ; 
Get FSIZE Long 0 ; 
Get TEMP Long 0 ; 
Get TEMP Long 0 ; 
Log FNAME FOFFSET FSIZE FOFFSETX FSIZEX ; 
SavePos CHECK 0 ; 
While CHECK < DATAX ;
```


Installiation script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open DAT.bms
4 - Provide the name enter - Moorhuhn Piraten
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Moorhuhn Piraten (*.DAT)

Enjoy 
[Moorhuhn Piraten.zip](https://xentaxbackup.github.io/file/803_Moorhuhn Piraten.zip)
## Post #87
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T20:11:13+00:00
- Post Title: 

+1 Script -> Expedition Trophy

Installiation :
1 - Run MultiEx Commander 4.2.0 
2 - Tools -> Add custom BSM to MRF 
3 - In opened dialog select filter -> MultiEx ZIP and open PAK.zip 
4 - Provide the name enter - Expedition Trophy
5 - Push button OK .. 
6 - Wait for restart MultiEx Commander 
7 - File -> Open ->  Select -> Expedition Trophy (*.PAK) 

Enjoy  
[Expedition Trophy.zip](https://xentaxbackup.github.io/file/804_Expedition Trophy.zip)
## Post #88
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-19T20:58:56+00:00
- Post Title: 

PXR and Kornet you are the men!
## Post #89
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T21:24:30+00:00
- Post Title: 

Okey go next   

+Script

Game Name : Rugby 2005
Author : Mr.Mouse
File Type : BIG

```
IDString 0 BIGF ;
Get D Long 0 ;
Get FC Long 0 ;
ReverseLong FC ;
Get D Long 0 ;
SavePos FS 0 ;
For T = 1 To FC ;
GoTo FS 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
ReverseLong FO ;
SavePos FSO 0 ;
Get FSI Long 0 ;
ReverseLong FSI ;
Get FN String 0 ;
SavePos FS 0 ;
Log FN FO FSI FOO FSO ;
Next T ;
```


Installiation script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open BIG.bms
4 - Provide the name enter - Rugby 2005
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Rugby 2005 (*.BIG)

Enjoy 
[Rugby 2005.zip](https://xentaxbackup.github.io/file/807_Rugby 2005.zip)
## Post #90
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T21:25:57+00:00
- Post Title: 

+Script

Game Name : Ski Racing 2006
Author : Mr.Mouse
File Type : FSB

```
Get FNum Long 0 ;
Get FO Long 0 ;
Math FO += 24 ;
Get DataLen Long 0 ;
Get Dummy1 Long 0 ;
Get DummyNull Long 0 ;
For n = 1 To FNum ;
SavePos Start 0 ;
Get EntryLen Int 0 ;
Math Start += EntryLen ;
SavePos EndFN 0 ;
Math EndFN += 34 ;
Get FN String 0 ;
GoTo EndFN 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
GoTo Start 0 ;
Log FN FO FS 0 FSO ;
Math FO += FS ;
Next n ;
```


Installiation script :
1 - Run MultiEx Commander 4.2.0
2 - Tools -> Add custom BSM to MRF
3 - In opened dialog select filter -> BMS and open FSB.bms
4 - Provide the name enter - Ski Racing 2006
5 - Push button OK ..
6 - Wait for restart MultiEx Commander
7 - File -> Open -> Select - Ski Racing 2006 (*.FSB)

Enjoy 
[Ski Racing 2006.zip](https://xentaxbackup.github.io/file/808_Ski Racing 2006.zip)
## Post #91
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-08-20T02:17:16+00:00
- Post Title: 

> Reply from KorNet
>
> Author : Mr.Mouse
Suck-up...
## Post #92
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-20T17:56:12+00:00
- Post Title: 

> Reply from Dinoguy1000
>
> KorNet wrote:Author : Mr.Mouse
Suck-up...
lol
## Post #93
- Username: xennex
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Oct 06, 2006 6:00 am
- Post datetime: 2006-12-13T12:25:10+00:00
- Post Title: 

BMS Script for Scrapland.
File extension: *.packed

```
Goto 8 0 ;
Get FNum Long 0 ;
For n = 1 to FNum ;
Get FNLen Long 0 ;
GetDString FN FNLen 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FS FO FSO FOO ;
Next n ;

```
## Post #94
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2008-12-19T20:02:38+00:00
- Post Title: 

Oh! Where is the our almighty KorNet?

He's latest post is Sun Aug 20, 2006 9:56 pm

Many crystal games so need his magic hands' working!
## Post #95
- Username: lyzasrey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 16, 2008 12:00 pm
- Post datetime: 2008-12-20T01:35:38+00:00
- Post Title: 

how about some more games such as Cake Mania 3 ? (I think it a diff quest 4 u but sorry i want its files   )
## Post #96
- Username: lyzasrey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 16, 2008 12:00 pm
- Post datetime: 2008-12-20T01:43:13+00:00
- Post Title: 

how about Cake Mania 3 (Advanced Quest for u but i need its files   )
## Post #97
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-12-20T16:49:27+00:00
- Post Title: 

> Reply from Gocha
>
> Oh! Where is the our almighty KorNet?

He's latest post is Sun Aug 20, 2006 9:56 pm
2006?!  Has it really been so long?
## Post #98
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-12-20T17:26:43+00:00
- Post Title: 

Hmm, where IS this Russian friend of ours. ...
## Post #99
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-12-22T18:10:22+00:00
- Post Title: 

Actually, according to his profile, his last visit was September 5, 2007... Still, he's obviously been MIA for a while now, hasn't he?
## Post #100
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-17T00:29:38+00:00
- Post Title: 

can someone verify quickly the BMS script for "Call to Power 2"?
(I don't have a registered multiex for testing it by myself)

I'm writing a tool which parses and executes the BMS scripts and this particular script for this game (at about line 1580 of complete_scripts.txt) gives some problems when executed in my program because the first files are handled correctly but then there is an error with the TAILSIZEB value which gets an invalid value (TAILOFF - DUMMYL with this one which is bigger).

I have attached one of the ZFS files found in the linux demo.

@mr.mouse
can you update the fields and the commands listed on [http://wiki.xentax.com/index.php/BMS](http://wiki.xentax.com/index.php/BMS) ?
in that document there are no references for GetCT, ComType and ReverseLong and nothing about the special variables like EXTRCNT (used just in the CTP2 script) or about the other datatypes like asize (I guess also PureText, PureNumber, TextOrNumber and FileNumber).
it would be very useful.

then would be good to discuss about other commands to add, I already have some ideas :)
[pat565.zip](https://xentaxbackup.github.io/file/1964_pat565.zip)
## Post #101
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2009-04-17T16:42:47+00:00
- Post Title: 

I'm pretty sure there's another page somewhere on the wiki which talks about the MexScript language in a slightly different manner, describing a different set of functions, but I can't seem to find it at the moment. In any case, the description of the MexScript language does drastically need a facelift/expansion; we've known this for some time now.  Note that you can register an account on the wiki for free, after which you can contribute to that page (and any others) as much as you like.[/cheap recruitment drive]
## Post #102
- Username: deve
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 22, 2009 4:56 pm
- Post datetime: 2009-05-02T19:20:11+00:00
- Post Title: 

thank you
## Post #103
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-02T23:19:18+00:00
- Post Title: 

I have figured the algorithm and file format of Deer Hunter 2005 and I have written a script for [QuickBMS](http://aluigi.org/papers.htm#quickbms) available [here](http://aluigi.org/papers/bms/deer_hunter_2005.bms).

the only bad thing of the script is that it's a bit slow due to the various operations performed on the single bytes but for the rest it works perfectly.

oh, the script work with both the demo and retail SPK archives. the only thing which changes is the initial encryption key. by default I have set the retail one while the demo is simply commented
## Post #104
- Username: deve
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 22, 2009 4:56 pm
- Post datetime: 2009-05-02T23:42:57+00:00
- Post Title: 

for first thx very much but how do you use quickbms  and the script where to put ?
## Post #105
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-02T23:49:25+00:00
- Post Title: 

it's very simple to use, if you are not much practical with the command-line/console I suggest you to copy quickbms.exe, the script and the SPK archive in c:, then create a new folder in c: called output and then type the following string in Start->Run:

```
c:\quickbms.exe c:\deer_hunter_2005.bms c:\data.spk c:\output
```

anyway I suggest you to learn a bit the basis of the windows console because it's very simple

*edit*: quickbms now works also with a minimalistic GUI
## Post #106
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-12T16:00:54+00:00
- Post Title: Re: ALL CURRENT MEXCOM SCRIPTS!

I have a doubt about FindLoc.
what happens if the string is not found?
should the script terminate or what value is assigned to the variable in this case?
## Post #107
- Username: zhelatinobambino
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-16T07:53:12+00:00
- Post Title: Re: ALL CURRENT MEXCOM SCRIPTS!

It terminates.
## Post #108
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2009-10-19T04:07:35+00:00
- Post Title: Re: ALL CURRENT MEXCOM SCRIPTS!

I hope this is the right place for this.  I wanted to learn about QuickBMS scripts and converted an old extractor to QuickBMS.  I left the "print" statements in (commented out for now) for easier debugging if desired.  I noticed other posts include installation instructions.  Unfortunately, I don't have MulitEx Commander (yet).

Game: Robot Alchemic Drive [PS2][SLUS-20445]
File Extension: Various
Magic Bytes: "VFS\0"

Here's the code:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms
#
# Tested against REMOTE.DAN, CONTROL.DY files 
#
# Some filenames contain kanji chars, please adjust your OS as needed to
#  support such chars.  REMOTE.DAN contains duplicate names.

idstring "VFS\x00"
get NUMFOLDERS long
get DUMMY long
get HEADERSIZE long

#print "Number of folders: %NUMFOLDERS%\n"

for i = 0 < NUMFOLDERS
  
  # save position at start of this folders info line
  savepos FOLDER_INFO_LINE_BEGIN
  
  # get folder information
  get RELATIVE_OFFSET_FOLDERNAME long
  get FILES_IN_THIS_FOLDER long
  get FOLDER_HEADER_OFFSET long
  get FOLDER_HEADER_LENGTH long
  
  # goto the location of the folder name
  math RELATIVE_OFFSET_FOLDERNAME += FOLDER_INFO_LINE_BEGIN
  goto RELATIVE_OFFSET_FOLDERNAME
  # print "Folder %i% offset: %RELATIVE_OFFSET_FOLDERNAME%\n"
    
  # get the folder name
  get FOLDERNAME string
  # print "Folder %i% name: %FOLDERNAME%\n"
  
  # print number of files
  #print "Folder %i% has %FILES_IN_THIS_FOLDER% files\n"
  
  # goto the location of the file headers for this folder
  goto FOLDER_HEADER_OFFSET
  
  for j = 0 < FILES_IN_THIS_FOLDER
  
    savepos FILE_INFO_LINE_BEGIN
  
    get FILESIZE long
    get FILEOFFSET long
    get RELATIVE_OFFSET_FILENAME long
  
    # goto the location of the file name
    math RELATIVE_OFFSET_FILENAME += FILE_INFO_LINE_BEGIN
    goto RELATIVE_OFFSET_FILENAME      
    # print "Filename %j% offset: %RELATIVE_OFFSET_FILENAME%\n"

    # get the file name
    get FILENAME string
    # print "Filename %j%: %FILENAME%\n"  
  
    # build the output path
    set FULLNAME string FOLDERNAME
    string FULLNAME += FILENAME 
    # print "Fullname %j%: %FULLNAME%\n"  
  
    # extract the file
    log FULLNAME FILEOFFSET FILESIZE
    # print "Fullname %j%: has been extracted\n"  
  
    # return to the next line in the file information area
    math FILE_INFO_LINE_BEGIN += 0x10
    goto FILE_INFO_LINE_BEGIN
  
  next j
  
  # return to the next line in the folder information area
  math FOLDER_INFO_LINE_BEGIN += 0x10
  goto FOLDER_INFO_LINE_BEGIN
  
next i
```
## Post #109
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-19T10:25:16+00:00
- Post Title: Re: ALL CURRENT MEXCOM SCRIPTS!

very good.
do you have also one of these (small) archives for a quick verification/curiosity?
have you also verified the files extracted with the old extractors with those extracted with the new script?

I have a tool that I use for this job called [dircomp](http://aluigi.org/mytoolz.htm#dircomp) so when I need to make this type of verification I extract the files with the first extractor and then with the other one in two different folders and then I compare their content with:

```
dircomp c:\old c:\new
```
hope it helps :)
## Post #110
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2009-10-19T14:11:10+00:00
- Post Title: Re: ALL CURRENT MEXCOM SCRIPTS!

> Reply from aluigi
>
> very good.
do you have also one of these (small) archives for a quick verification/curiosity?
have you also verified the files extracted with the old extractors with those extracted with the new script?

I have a tool that I use for this job called...

Sorry, but the files are too large to share.  The test samples I worked with were ~150mb and ~210mb.  I'll take another look when I return home for a smaller file.  Hopefully I can find a smaller one, since it's always helpful to have a second opinion on these things.

I compared a few random files using size and CRC32, but I'll also try your tool.

Thanks for the input, and, of course, QuickBMS.
## Post #111
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-27T17:22:46+00:00
- Post Title: Re: ALL CURRENT MEXCOM SCRIPTS!

a note about the scripts in complete_scripts.txt regarding the Battlefield series.
they can't work because many of the files in these RFA archives are compressed with chunks of LZO1x.
I have released a [quickbms script for them](http://aluigi.org/papers/bms/rfa.bms).
## Post #112
- Username: zhelatinobambino
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-11-20T22:01:24+00:00
- Post Title: Re: ALL CURRENT MEXCOM SCRIPTS!

A bit of a dead topic, but here is a new one to be used in MultiEx Commander: 

```
#Extraction mexscript by Mr.Mouse 
Get D1 Long 0 ;
Get D2 Long 0 ;
Get FIOff Long 0 ;
Get FISize Long 0 ;
Get NIOff Long 0 ;
Get NISize Long 0 ;
Get DataOff Long 0 ;
Get DataSize Long 0 ;
Math FIOff += 32 ;
Set ST Long FIOff ;
Math ST += FISize ;
Set CP Long FIOff ;
GoTo FIOff 0 ;
Get D3 Long 0 ;
Get FNum Long 0 ;
SavePos SP 0 ;
For T = 1 To FNum ;
GoTo SP 0 ;
Get FNPOS Long 0 ;
Get OffSet Long 0 ;
Get Size Long 0 ;
Get D4 Long 0 ;
Get D5 Long 0 ;
Get D6 Long 0 ;
SavePos SP 0 ;
Set FNO Long NIOff ;
Math FNO += FNPOS ;
GoTo FNO 0 ;
Get FNAME String 0 ;
Log FNAME OffSet Size 0 0 ;
Next T ;

```
