## Post #1
- Username: Gõndola
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 26, 2018 2:44 am
- Post datetime: 2018-10-27T19:23:14+00:00
- Post Title: Space Channel 5 Part 2 Animation/Model Files, Help Needed

Going off of what has been said in these threads: 
[https://forum.xentax.com/viewtopic.php?f=16&t=14805](https://forum.xentax.com/viewtopic.php?f=16&t=14805)
[viewtopic.php?f=16&t=16513](http://forum.xentax.com/viewtopic.php?f=16&t=16513)
The file formats of the first and second game are almost identical and so they should behave in a similar manner, which they might do, unfortunately the discussion ended more than a year ago, with the only good thing coming from them being the Noesis support for SC5s original animation/model format(which was already going to happen)
I'm kind of sure that the RBPs function remains the same, skeletal data containing animation can be loaded onto another RBP or CDR file containing hundreds of submeshes(the character models of the game) while the individual model/skeleton combos are also stored in cdball.afs where they're contained as cd1 files that can be edited into pvm texture archives and nj model files with hex edit.

Currently, i'm completely lost, the rbp files can't load into noesis and Part 2's animations remain locked away as I have no python experience and would make a custom import plugin if I could, so I seek the help of these forums.

[http://www.mediafire.com/file/dd141odkp ... round1.cdr](http://www.mediafire.com/file/dd141odkpdchj5d/round1.cdr) - potential submesh holder
[http://www.mediafire.com/file/8769dqz52 ... title0.rbp](http://www.mediafire.com/file/8769dqz52mgb5l9/title0.rbp) - potential animation holder

[http://www.mediafire.com/file/u56an8twr9tj62w/DMDM.7z](http://www.mediafire.com/file/u56an8twr9tj62w/DMDM.7z) - example of how SC5 files interact with noesis successfully, opening r11 will request that a file like r10 be opened, when compatible submesh is selected an entire animation set plays
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-28T10:39:05+00:00
- Post Title: Space Channel 5 Part 2 Animation/Model Files, Help Needed

> Reply from Gõndola
>
> Currently, i'm completely lost, the rbp files can't load into noesis and Part 2's animations remain locked away as I have no python experience and would make a custom import plugin if I could, so I seek the help of these forums.playspython experience wouldn't help that much. Noesis uses internal code for that format, afair:
[viewtopic.php?f=16&t=16513&p=132070&hil ... ly#p132070](http://forum.xentax.com/viewtopic.php?f=16&t=16513&p=132070&hilit=+internally#p132070)

btw: since you seem to have taken your 7z upload from that thread it would have made sense to link to it, why not?
## Post #3
- Username: Gõndola
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 26, 2018 2:44 am
- Post datetime: 2018-10-28T15:06:03+00:00
- Post Title: Space Channel 5 Part 2 Animation/Model Files, Help Needed

> Reply from shakotay2
>
> 
btw: since you seem to have taken your 7z upload from that thread it would have made sense to link to it, why not?
I linked to both of the threads at the top of my post, unless there's a third thread I don't know about
I also have the steam version of part 2 and the dreamcast version of part 1 so using those already uploaded files was just a matter of convenience, I can upload any file from them if needed
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-28T22:10:15+00:00
- Post Title: Space Channel 5 Part 2 Animation/Model Files, Help Needed

> Reply from Gõndola
>
> I linked to both of the threads at the top of my post, unless there's a third thread I don't know aboutYeah, see. Should have read more carefully, sry.

In R10.rb there are 136 NJCM, whatever it may stand for.
In title0.rbp there's 11 of them.

One idea would be to understand the structure of R10.rb, then try to transform the contents of title0.rbp following that structure.

But understanding R10.RB will be a tedious task (floats should represent position and quaternion rotation, something like that):

```
   0. CC 00 26 00   0.493959 -1.967435 -0.654830 -0.099689 -0.970021 0.221632 
   1. 00 00 80 80   1.327319 -1.156080 -0.266835 0.055326 -0.476436 0.877467 
   2. 01 00 CC CC   1.482171 -1.760480 -0.602575 0.229110 -0.930084 0.287146 
   3. 02 00 CC CC   -0.161871 -1.043072 -1.368448 -0.264789 -0.333865 -0.904667 
   4. 03 00 80 80   0.465418 -1.678956 -1.272669 -0.150074 -0.654259 -0.741231 
   5. 04 00 80 80   1.152860 -0.239550 -1.222695 0.063712 0.076247 -0.995051 
   6. 05 00 CC CC   1.362650 -1.310050 -1.291290 0.190012 -0.389371 -0.901269 
   7. 06 00 CC CC   -1.042825 -0.417126 -0.302321 -0.624160 0.540653 0.564020 
   8. 07 00 99 99   -0.602690 -1.911482 -0.494726 0.045959 -0.989289 0.138544 
   9. 08 00 4D 4D   -0.601126 -1.663647 -1.071296 0.283213 -0.704340 -0.650920 
  10. 09 00 33 33   -0.921695 -0.156902 -0.926844 -0.460778 0.797339 -0.389787 
  11. 0A 00 4D 4D   -1.006539 -1.169633 -0.129755 -0.186643 -0.051436 0.981080 
  12. 0B 00 80 80   -1.042825 -0.412209 0.308988 -0.624160 0.531510 -0.572645 
  13. 0C 00 99 99   -0.602691 -1.903276 0.525408 0.045959 -0.991390 -0.122613 
  14. 0D 00 4D 4D   -0.601126 -1.646199 1.097916 0.283212 -0.693778 0.662166 
  15. 0E 00 33 33   -0.921696 -0.141972 0.929245 -0.460779 0.803506 0.376909 
  16. 0F 00 4D 4D   -1.006539 -1.167394 0.148550 -0.186642 -0.067211 -0.980126 
  17. 10 00 80 80   0.493958 -1.956647 0.686393 -0.099689 -0.973461 -0.206000 
  18. 11 00 80 80   1.327319 -1.151639 0.285398 0.055326 -0.490489 -0.869690 
  19. 12 00 CC CC   1.482171 -1.750559 0.630818 0.229110 -0.934583 -0.272147 
  20. 13 00 CC CC   -0.161872 -1.020924 1.385048 -0.264790 -0.319269 0.909919 
  21. 14 00 80 80   0.465418 -1.658267 1.299512 -0.150074 -0.642251 0.751659 
  22. 15 00 80 80   1.152859 -0.219851 1.226391 0.063712 0.092243 0.993696 
  23. 16 00 CC CC   1.362649 -1.289109 1.312198 0.190012 -0.374823 0.907416 
  24. 17 00 CC CC   0.728625 -1.184086 1.024547 0.318069 -0.599669 0.734323 
  25. 18 00 80 80   0.465126 -0.609735 1.457465 0.159320 -0.106982 0.981413 
  26. 19 00 80 80   0.465127 -0.633100 -1.447469 0.159321 -0.122755 -0.979565 
  27. 1A 00 80 80   -0.919217 -0.124970 0.109238 -0.858680 0.481159 0.176504 
  28. 1B 00 80 80   0.654223 -1.664162 0.462998 0.355579 -0.888827 0.289052 
  29. 1C 00 99 99   0.654223 -1.671394 -0.436168 0.355579 -0.893361 -0.274716 
  30. 1D 00 99 99   -0.061633 0.545886 0.125135 -0.507966 0.860383 0.041372 
  31. 1E 00 B3 B3   0.728625 -1.200413 -1.005366 0.318069 -0.611403 -0.724581 
  32. 1F 00 80 80   -0.259362 -1.919350 -0.060541 -0.196061 -0.978715 0.060644 
  33. 20 00 99 99   0.621028 0.802051 -0.967404 -0.120347 0.784876 -0.607854 
  34. 21 00 80 80   -0.259362 -1.918128 0.091406 -0.196061 -0.979564 -0.044893 
  35. 22 00 99 99   0.621027 0.817509 0.954377 -0.120347 0.794552 0.595150 
  36. 23 00 80 80   -0.061633 0.543803 -0.133901 -0.507966 0.859606 -0.055208 
  37. 24 00 B3 B3   -0.919217 -0.126711 -0.107217 -0.858680 0.478258 -0.184222 
  38. 25 00 80 80   FF000000 04200000  B0070000

0x7C8
   0. 29 80 25 00  10 00 06 00   0.465053 0.043106 1.284526 0.008914 0.075737 0.997088 
      0.335507 0.825986 0.750679 0.056378 0.864003 0.500320 
      0.429287 -1.088961 0.621877 0.086216 -0.879536 0.467956 
      0.335507 0.825986 -0.750679 0.056381 0.864002 -0.500321 
      0.429287 -1.088961 -0.621877 0.086491 -0.879476 -0.468018 
      0.465054 0.043106 -1.284526 0.008916 0.075739 -0.997088 
   1. 2C 80 2B 00  

0x864: 
   0. A8 00 06 00   1.805973 -1.001204 0.676549 -0.043568 -0.921450 0.386047 
   1. 00 00 80 80   1.458535 -0.214874 -1.292314 -0.106169 -0.171271 -0.979487 
   2. 01 00 80 80   1.805974 -1.001204 -0.672872 -0.042624 -0.922061 -0.384690 
   3. 02 00 80 80   1.207489 0.953650 0.800348 -0.177718 0.833312 0.523457 
   4. 03 00 80 80   1.458535 -0.214874 1.292316 -0.106413 -0.170425 0.979608 
   5. 04 00 80 80   1.207489 0.953649 -0.800335 -0.177718 0.833315 -0.523452 
   6. 05 00 80 80   FF000000 04200000 4C090000
```
