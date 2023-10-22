## Post #1
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-08-29T03:15:03+00:00
- Post Title: Operation 7 and Karma Revo - MMOFPS

i have those games and i want extract it, but file extension is a number ( Karma ) and .cdt .cdo (operation 7) so i don't know what are their engine and how to unpack them 

Sample files:
[http://www.mediafire.com/?dcz81k72ee2m82w](http://www.mediafire.com/?dcz81k72ee2m82w)
[http://www.mediafire.com/?2pcroc2v3l0d81e](http://www.mediafire.com/?2pcroc2v3l0d81e)


Sorry about my bad Eng
## Post #2
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2017-05-17T05:36:41+00:00
- Post Title: Operation 7 and Karma Revo - MMOFPS

*bump*
I've had free time recently so I decided to try hex2obj with this kind of file, followed the tutorial and I got this result:

I think the reason is UVs is FVF , but I don't know how. Can shakotay or Acewell show me how to do it? Thank you so much  

And any moderator can move it to 3d/2d models thread, since this file wasn't an archive. Thank you

Sample file: mediafire.com/?qmc50a7k071iirq
[18379000_1849886735025253_421231688_o.png](https://xentaxbackup.github.io/file/12901_18379000_1849886735025253_421231688_o.png)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-17T06:58:19+00:00
- Post Title: Operation 7 and Karma Revo - MMOFPS

HAND_29.cdm  



HAND_29_cdm.png (49.83 KiB) Viewed 66 times



and this bms script will clean up the dds headers in your *.cdt texture samples  

```
get NAME basename
string NAME + ".dds"
findloc TEXDDS string "DDS"
goto TEXDDS
savepos OFFSET
math SIZE - OFFSET
log NAME OFFSET SIZE
```
## Post #4
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2017-05-17T08:59:33+00:00
- Post Title: Operation 7 and Karma Revo - MMOFPS

> Reply from AceWell
>
> HAND_29.cdm  
HAND_29_cdm.png

and this bms script will clean up the dds headers in your *.cdt texture samples  
Code: Select allget SIZE asize
get NAME basename
string NAME + ".dds"
findloc TEXDDS string "DDS"
goto TEXDDS
savepos OFFSET
math SIZE - OFFSET
log NAME OFFSET SIZE

can you show me how to detect or find out if it was FVFsize  I don't know how to find the values of FVFsize

wow, i can figure the cdt files are texture but I need to use a simple way: open by hex editor and delete headers, can you show me how to make a bms script for these types of file?  I mean other files, which need to be cleaned up their headers as same as .cdt files

And why the address of verticles is 0x14? because when I followed shakotay's tutorial, it gave me the address 0x544C
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-17T13:43:29+00:00
- Post Title: Operation 7 and Karma Revo - MMOFPS

> Reply from onelove1210
>
> can you show me how to detect or find out if it was FVFsize  I don't know how to find the values of FVFsize
well tutorials only use an example, counts and addresses change from one to the next, fvfsize is just the vertex stride.   

> wow, i can figure the cdt files are texture but I need to use a simple way: open by hex editor and delete headers, can you show me how to make a bms script for these types of file?  I mean other files, which need to be cleaned up their headers as same as .cdt files
i already did, that is what the script is for, as long as there is an existing valid dds header you don't need to
use hex editor, the script automates the task, but samples from other games may or may not work, the script
is only for the samples from your first post or if they are similar in structure. 

> And why the address of verticles is 0x14? because when I followed shakotay's tutorial, it gave me the address 0x544C
because thats where the data is. if the tutorial wasn't about this sample specifically then it won't work here, you 
have to figure this stuff out on your own, no one can teach you counts and addresses because they change from
file to file and everybody needs to learn how to identify data to use these tools.
## Post #6
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2017-05-17T14:27:51+00:00
- Post Title: Operation 7 and Karma Revo - MMOFPS

> Reply from AceWell
>
> 
because thats where the data is. if the tutorial wasn't about this sample specifically then it won't work here, you 
have to figure this stuff out on your own, no one can teach you counts and addresses because they change from
file to file and everybody needs to learn how to identify data to use these tools.

I know. At least I can figure that my file is "blocked mode" and I was right    thanks for your help.

P/s: Last question: how to enable "blue UV map" in an UV-obj window?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-17T16:39:34+00:00
- Post Title: Operation 7 and Karma Revo - MMOFPS

> Reply from onelove1210
>
> P/s: Last question: how to enable "blue UV map" in an UV-obj window?
press E key to toggle edge display
press W key to toggle background white or black
press L key to toggle constant shading (especially useful when viewing point clouds to reveal all points)
press P key repeatedly to increase point display size, press shift+P to decrease size
press F to render points/triangles red, not sure what use this has
press Q or Esc key to close 3d or UV window
press spacebar to reset view
press 1 to toggle a clear window
right-click and drag the mouse to zoom in/out
middle-click and drag to pan
left-click and drag to rotate
press ctrl+left or right or middle click and drag to move the light source
press S key to render smooth(?) shading, not entirely sure, the changes are subtle

and thats all i can think of right now
## Post #8
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2017-05-18T02:11:03+00:00
- Post Title: Operation 7 and Karma Revo - MMOFPS

> Reply from AceWell
>
> 

and thats all i can think of right now

Thank you so much
