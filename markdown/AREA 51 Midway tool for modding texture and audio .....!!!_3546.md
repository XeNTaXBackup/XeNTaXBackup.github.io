## Post #1
- Username: shaska
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 21, 2009 11:05 am
- Post datetime: 2009-06-21T23:39:53+00:00
- Post Title: AREA 51 Midway tool for modding texture and audio .....!!!

Hi guy ...i m new member in this forum  i from italy sorry my english

i search urgent unpak e repack file for modding in HI-RES for free full game AREA51 Midway ..production on 2005 

e game e' become free in the year 2008...in the game as proprietary 

file.000
file.DFS

they are successful to only extract file audio .mp3  .txt  .psb .form with this tool :

[http://www.volny.cz/nova-software/](http://www.volny.cz/nova-software/)

Extractor 2.5 - Freeware

It can extract the sound files, but you won’t have file names
only read file.000 and extraxt in sequenzi audio format .mp3  and .txt et no unpack e repack file for modding texture and more file Skin world map ,skin weapon,skin alien,...ecc ecc

please help me a tool for modding!!!!

down link for free full game and my patch fx for grafic similar verion next gen 



Area 51, developed by Midway Studios Austin (previously known as Inevitable Entertainment) and published by Midway for PC in 2005, PlayStation 2 and Xbox is a first-person shooter (FPS) genre of video game, and is a loose remake on the 1995 light gun video game of the same name. In the gameplay, players control Ethan Cole, a HazMat operative voiced by David Duchovny sent to the infamous base to investigate some manner of viral outbreak.

Area 51 game play has the plot about the U.S. Army has received a distress signal from Area 51 where a viral outbreak has just shut down the research facility and the automated quarantine procedures have locked all scientific and military personnel inside. A small Special Forces unit including Specialist Ethan Cole of the HAZMAT (hazardous materials) Division is sent to investigate

who interested in playing Area 51, Midway has made the PC version of Area 51 available for free download and free playing without cost. Everybody can now download full version of Area 51 game to install on Windows PC for free playing without limitation or restriction

Do anticipate the large download size of 1.93GB for the Area 51 setup installer (midway_area51.exe or midway_area51.zip).

link free full game from Gameshell and Midway release!!!!

[http://www.gamershell.com/download_33790.shtml](http://www.gamershell.com/download_33790.shtml) (gameshell)

[http://gamedaily.newaol.com/pub/midway_area51.exe](http://gamedaily.newaol.com/pub/midway_area51.exe) (Midway ,FAST download)
__________________________
__________________________

i have edit a little mod for game and new dll ,my edit experiment BLOOM + HDR patch added in game

MY MOD FX GRAFIC V2 FOR AREA 51 by shaska

[DOWNLOAD FX PATCH AREA 51 V2](http://uploading.com/files/ZAML39A2/FXPATCH%20AREA51-V2.shaska.rar.html)

bloom
HDR 
bump
specular
riflessi
shadow
60 fps 
enb series .ini

Note : its patch is compatible 100% winxp sp2 sp3 ...
i don not win vista .....i no have vista for test

_______________________________
_______________________________
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-21T20:33:08+00:00
- Post Title: AREA 51 Midway tool for modding texture and audio .....!!!

I'm just bumping this one time as he clearly made an effort to write a lot of pre-info.
## Post #3
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2009-07-29T06:39:44+00:00
- Post Title: AREA 51 Midway tool for modding texture and audio .....!!!

I second that....

The only reason i uninstalled this game was because i spent hours searching all over for an extractor and tried everything that i know of try it and nothing would work. Watto's Game Extractor didn't work and neither did any type of BMS script that i tried.

I'm mainly after the sound files and textures just to even look would be great.

-jenx
## Post #4
- Username: jenx
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-08-01T12:15:06+00:00
- Post Title: AREA 51 Midway tool for modding texture and audio .....!!!

```
GetDString ID 4  1 ;
Set IDS String "SFDX";
If ID = IDS ;
Get Version Long 1 ;
Get U1 Long 1 ;
Get PadSize Long 1 ;
Get U2 Long 1 ;
Get FileNum Long 1 ;
Get U3 Long 1 ;
Get U4 Long 1 ;
Get U5 Long 1 ;
Get U6 Long 1 ;
Get U7 Long 1 ;
Get STOffset Long 1 ;
Get ArchiveSize Long 1 ;
Get ArchiveSizeHigh Long 1 ;
SavePos Info 1 ;
Set Folders Long STOffset ;
Math Folders += 3 ;
GoTo Folders 1 ;
Get Folder String 1 ;
For T = 1 To FileNum ;
GoTo Info 1 ;
Get Prefix_Offset Long 1 ;
Get FNOffset Long 1 ;
Get U8 Long 1 ;
Get ExtOffset Long 1 ;
Get Offset Long 1 ;
Get Size Long 1 ;
SavePos Info 1 ;
Math Prefix_Offset += STOffset ;
GoTo Prefix_Offset 1 ;
Get B Byte 1 ;
If B <> 0 ;
GoTo Prefix_Offset 1 ;
Get Prefix String 1 ;
Else ;
Set Prefix String "" ;
EndIf ;
Math FNOffset += STOffset ;
GoTo FNOffset 1 ;
Get B Byte 1 ;
If B <> 0 ;
GoTo FNOffset 1 ;
Get FName String 1 ;
Else ;
Set FName String "" ;
EndIf ;
Math ExtOffset += STOffset ;
GoTo ExtOffset 1 ;
Get Ext String 1 ;
Set Path String Folder ;
String Path += Prefix ;
String Path += FName ;
String Path += Ext ;
Log Path Offset Size 0 0 ;
Next T ;
EndIf;

```


This is the script for MultiEx Commander to open *.000 files that have a accompanying *.DFS file in the same folder. It will show the correct filenames. 

Here's the BMS file to use in MultiEx Commander. Just go to BMS-->Add BMS to MRF and follow the instructions. Point to the BMS file and name the game.


 000.zip
(539 Bytes) Downloaded 91 times



Here's an example (maplist.txt in preload.000)

```
 { Level:s                }
// ----------------------
   "CAMPAIGN\DREAMLND"   
   "CAMPAIGN\UNDRGRND"   
   "CAMPAIGN\SEARCH"     
   "CAMPAIGN\GETBIG"     
   "CAMPAIGN\LASTSTND"   
   "CAMPAIGN\ONEOFTHM"   
   "CAMPAIGN\MUTATION"   
   "CAMPAIGN\SIDETRCK"   
   "CAMPAIGN\DR_CRAY"    
   "CAMPAIGN\ILLUMIN"    
   "CAMPAIGN\FLYNOBJS"   
   "CAMPAIGN\LIESPAST"   
   "CAMPAIGN\CAVES"      
   "CAMPAIGN\BOARDING"   
   "CAMPAIGN\ASCEND1"    
   "CAMPAIGN\ASCEND2"    
   "CAMPAIGN\ASCEND3"    
   "CAMPAIGN\EXIT"       
   "MP_00\BLOOD"         
   "MP_00\BRIDGE"        
   "MP_00\CLDRN"         
   "MP_00\CORE"          
   "MP_00\CQB"           
   "MP_00\DEATH2"        
   "MP_00\FLOW"          
   "MP_00\GAZEBO"        
   "MP_00\HKING"         
   "MP_00\MDOWN"         
   "MP_00\REACT"         
   "MP_00\SHAFT"         
   "MP_00\STEAM"         
   "MP_00\SPOOKY"        
   "MP_00\TRINTY"        
   "MP_00\2TANGO"        
   "MP_00\WIRED"         
   "CAMPAIGN\HOTZONE"    
   "MP_00\BLAZE"         

```


Oh and a table of contents I let MultiEx Commander save.
[toc_preload_000.zip](https://xentaxbackup.github.io/file/2239_toc_preload_000.zip)
## Post #5
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2009-08-06T16:46:34+00:00
- Post Title: AREA 51 Midway tool for modding texture and audio .....!!!

Thank you Mr.Mouse!! I hope the OP finds many uses for this, as i will   

Now i just need to install this again so i can Poke around and see what interesting bit and pieces i can dig up  

Thanks again
## Post #6
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-12-20T17:27:35+00:00
- Post Title: AREA 51 Midway tool for modding texture and audio .....!!!

Now we just need a way to convert the RIGIDGEOM (meshes) to something useable in a 3d modeler/editor.
## Post #7
- Username: nickru58
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Nov 17, 2011 11:10 am
- Post datetime: 2011-11-17T03:12:37+00:00
- Post Title: AREA 51 Midway tool for modding texture and audio .....!!!

how the hell do u extract the textures im new here but not to modding i cant figure out how to open the .000 files someone plz help
## Post #8
- Username: nickru58
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Nov 17, 2011 11:10 am
- Post datetime: 2011-12-17T02:28:00+00:00
- Post Title: AREA 51 Midway tool for modding texture and audio .....!!!

hey could somebody make a gloves mod patch or something for first person if it's at all possible
