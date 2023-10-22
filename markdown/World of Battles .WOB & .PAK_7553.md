## Post #1
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-10-23T07:56:45+00:00
- Post Title: World of Battles *.WOB & *.PAK

World of Battles. MMORTS.
Here are screen of units:
   

All data of models and textures in the WOB archives (solid not packed data) and PAK (indexes and names for files in WOB). Simple format to extract.

Here models of units [http://www.multiupload.com/01UQHZ2VW5](http://www.multiupload.com/01UQHZ2VW5) (34Mb). I think it is all units from game and if anybody could write importer it will be wonderful.
Here textures for werewolves [http://www.multiupload.com/JNF1RAAL76](http://www.multiupload.com/JNF1RAAL76) (7.5Mb) for example.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-26T21:44:03+00:00
- Post Title: World of Battles *.WOB & *.PAK

> Reply from Nazaroff
>
> 

All data of models and textures in the WOB archives (solid not packed data) and PAK (indexes and names for files in WOB). Simple format to extract.

you posted in the archive research, not 3d section so if you want something in return, give something back. like the extraction script.    

too late now

```
Open FDDE WOB 1

get DUMMY char
GET DUMMY long
get FILES long
get PACKSIZE long

for f = 0 < FILES
  get OFFSET long
  get SIZE long
  get FNLEN long
  getdstring FNAME FNLEN

  if SIZE == 0xFFFFFFFF
    # directory
  else
    log FNAME OFFSET SIZE 1
  endif

next f

```
## Post #3
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-11-07T19:34:45+00:00
- Post Title: World of Battles *.WOB & *.PAK

> Reply from WRS
>
> 
you posted in the archive research, not 3d section so if you want something in return, give something back. like the extraction script.
Thanks for script, WRS. Again  (sorry for late reply)
I don't need post this in 3D section because it is known 3D Ogre format.
