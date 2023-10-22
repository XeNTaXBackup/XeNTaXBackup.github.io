## Post #1
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2009-06-27T14:50:12+00:00
- Post Title: Cryo .BIG archive [from ZeroZone]

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-27T15:22:49+00:00
- Post Title: Cryo .BIG archive [from ZeroZone]

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "BigFile 1.00\0\0\0\0"
get FILES long
get FILES_SIZE long
get FILES_OFF long
get DUMMY long

for i = 0 < FILES
    get NAMESZ long
    get DUMMY long
    get SIZE long
    get SIZE2 long
    get SIZE3 long
    get DUMMY long
    get OFFSET long
    get DUMMY long
    getdstring NAME NAMESZ

    math OFFSET += FILES_OFF

    log NAME OFFSET SIZE
next i
```
I don't know why are necessary 3 SIZE fields in this format, first because there are no compressed files and then because if was used compression (not in the file you provided) 2 SIZE fields were enough... mah
## Post #3
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2009-06-27T18:48:55+00:00
- Post Title: Cryo .BIG archive [from ZeroZone]

Dude... Are you superman? Or in any way related to superman?

That entire procedure - right from downloading the file, to posting the unpack-script - took you less time than what it took me to cook a dinner (a very late/early dinner - it's 2am here ). And what's more; it worked without a flaw. 

I tried it on the x2 .big files in zerozone, and 4 .big files from a different cryo game. All went fine except for quite a few "the file 'bla.bla' already exists do you want to overwrite it (y/N/all)?" messages in the 4 .big files from the 2nd game. I doubt it's a problem with your script.
Though, is it normal to have two (or more) files with the same filename inside of the same folder in an archive? I've never seen it occur before.

Anyways, best be off to bed, before I pass out.

Thanks HEAPS for your help once again, Luigi. Good stuff.
Keep it real
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-28T04:12:12+00:00
- Post Title: Cryo .BIG archive [from ZeroZone]

in general in the archives of some games happens to have files with the same names moreover if they have been stored as resources instead of files, so it's all enough normal :)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-28T08:52:10+00:00
- Post Title: Cryo .BIG archive [from ZeroZone]

```
SavePos S 0 ;
Math S += 4 ;
GoTo S 0 ;
Get FileNum Long 0 ;
Get DataSize Long 0 ;
Get DataStartL Long 0 ;
Get DataStartH Long 0 ;
For T = 1 to FileNum ;
Get StringSize Long 0 ;
Get U1 Long 0 ;
Get Size1 Long 0 ;
Get Size2 Long 0 ;
Get Size3 Long 0 ;
Get R1 Long 0 ;
Get ROff Long 0 ;
Get U2 Long 0 ;
GetDString FN StringSize 0 ;
Math ROff += DataStartL ;
Log FN ROff Size1 0 0 ;
Next T ;

```


This is the Mexscript (BMS) for MultiEx Commander. 

Here's also the .bms file you can add to MultiEx Commander:


 big.zip
(331 Bytes) Downloaded 32 times


Here's how to add the bms to the standard supported formats in MultiEx Commander. It's real easy.

Select the option from the BMS menu:



select.jpg (47.86 KiB) Viewed 247 times



Fill in the dialogue: point to the location of the .bms file to add, and type in the name of the game.



fill_in_details.jpg (49.49 KiB) Viewed 245 times



You will be asked to make a backup or not and then DONE. Now you can open any big file from Zero Zone just like any other. 



done.jpg (45.73 KiB) Viewed 245 times



Here are some details from the archive:



COCKTAIL.jpg (85.78 KiB) Viewed 244 times





LOGOZZ.jpg (93.63 KiB) Viewed 245 times





RIDLEY.jpg (111.07 KiB) Viewed 244 times



Check the table of contents saved with MultiEx Commander:


 zerozone_big_contents.zip
(12.29 KiB) Downloaded 42 times
## Post #6
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2009-06-28T09:25:24+00:00
- Post Title: Cryo .BIG archive [from ZeroZone]

Mr.Mouse is in da house.

Hi Five!     [um.., lack of more appropriate smilie :S]
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-28T12:53:09+00:00
- Post Title: Cryo .BIG archive [from ZeroZone]

uhmmm but if in multiex the compiled binary scripts are called bms and have the bms extension how are called the textual scripts? ms?
I thought their name was bms (and that's why I called my tool quickbms)... confused :)
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-28T17:13:46+00:00
- Post Title: Cryo .BIG archive [from ZeroZone]

The script is called MexScript (from MultiEx Script) and the compiled versions are Binary MultiEx Script (BMS).  In the past I tried to make sure people understood the difference, but they used the two interchangeably, even [http://wiki.xentax.com/index.php/BMS](http://wiki.xentax.com/index.php/BMS) is technically incorrect. So I just gave up. BMS, MexScript, as long as we understand what it's about, I guess.
