## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-04-05T15:47:14+00:00
- Post Title: Trials in the Sky Chap 2 & 3 .mcc map files

Hey Guys,

I've taken a look at the .mcc files from the MAP directory in Trials in the Sky Chapter 2 and 3 and can see they're archives, they appear to be lightly compressed too, but I'm pretty confident they contain 3D Models and texture files, much like the itp files in the later games from the series.

The company uses Metaseqoia for all their 3D models and .tga files for their textures (according to the rest of the Kiseki series at least), so I'm certain there will be some .msq files in here somewhere (sure thats the right extension).

I've uploaded a link to a map from each of the 2 games here:

[https://dl.dropboxusercontent.com/u/779 ... d3maps.rar](https://dl.dropboxusercontent.com/u/7797280/TrailsintheskyChapt2and3maps.rar)

It'd be great if someone could take a look at this, I've not much experience so I can't say if it'd be complex to extract or not.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-04-07T20:10:29+00:00
- Post Title: Trials in the Sky Chap 2 & 3 .mcc map files

Alright, just to help people out, here's a MexScript for these files to get to the ITC files. 

See also the real-time analysis of these .MCC files, that resulted in this script below here.
[http://youtu.be/Tcmt_zlFuns](http://youtu.be/Tcmt_zlFuns) 

```
#Trials in the Sky .mcc
Get FileNum Long 0 ;
SavePos Jump 0 ;
Math Jump += 12 ;
For T = 1 To FileNum ;
GoTo Jump 0 ;
GetDString Name 16 0 ;
SavePos OffOff 0 ;
Get Offset Long 0 ;
SavePos SizeOff 0 ;
Get Size Long 0 ;
SavePos Jump 0 ;
Math Jump += 8 ;
Log Name Offset Size OffOff SizeOff ;
Next T ;

```


Finally, here's a few .ITC files to check out for further analysis: 

 exztracted.7z
(259.69 KiB) Downloaded 18 times
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-04-07T20:55:31+00:00
- Post Title: Trials in the Sky Chap 2 & 3 .mcc map files

Ah damn.

Mr Mouse I'm so sorry, I logged in here just now to share this script that someone else made for QuickBMS

```
#
# Written by puggsoy
# script for QuickBMS http://quickbms.aluigi.org

get EXT extension

if EXT == "mcc"
   callfunction MCCEXTRACT
elif EXT == "itc"
   callfunction ITCEXTRACT
endif

startfunction MCCEXTRACT
   get FILES long
   goto 0x10
   
   for i = 0 < FILES
      getdstring NAME 0x10
      get OFFSET long
      get SIZE long
      get DUMMY long
      get DUMMY long
      
      log NAME OFFSET SIZE
   next i
endfunction

startfunction ITCEXTRACT
   idstring "V102"
   
   savepos POS
   get CHECK long
   
   for CHECK = CHECK != 0
      goto POS
      get OFFSET long
      get SIZE long
      
      log "" OFFSET SIZE
      
      savepos POS
      get CHECK long
   next i
endfunction

```


That script works for the .itc files too, after that theres just .dat files, loads of them, and they're 1kb each too, either something went wrong or those are really compressed to hell.

You made a video of it too, thats awesome! I'm loving this video series of yours, I'm slow and I've little time but I'm learning how to extract things as I follow along.
