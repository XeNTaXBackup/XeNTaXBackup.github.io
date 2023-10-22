## Post #1
- Username: Cyber200
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 01, 2023 4:11 pm
- Post datetime: 2023-04-01T08:37:01+00:00
- Post Title: Resident Evil Outbreak Script Noesis

Hello Is it possible to make a Noesis script

please as i would like to read resident evil outbreak game models and animations i am giving samples

The P00_00.nbd file
is the model

[https://www.mediafire.com/file/sxgzkmhz ... l.rar/file](https://www.mediafire.com/file/sxgzkmhzzlzf5a4/Model.rar/file)

The pl00_pc_000.bin file
And the animation If it is made possible I will be very happy because this game really interests me thank you very much

The textures are also in the P00_00.nbd files

I would also like to be able to play the animation on the model

I also send a Batch if you want the extract in FBX
to get the textures

Obtool RE Oubreak

[https://www.mediafire.com/file/o6rj8j0j ... k.rar/file](https://www.mediafire.com/file/o6rj8j0jcn1zx5x/Obtool_RE_Oubreak.rar/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-01T09:09:58+00:00
- Post Title: Resident Evil Outbreak Script Noesis

> Reply from Cyber200 ↑Sat Apr 01, 2023 4:37 pm at Sat Apr 01, 2023 4:37 pm
>
> 
Hello Is it possible to make a Noesis scriptHello, it's usually if not always possible to create a Noesis script. Question is: who will?   

I have the strange feeling that you're "one of these guys" who don't search forums, are you?  

If so, you would have found this post (of mine, in this case):

> Reply from shakotay2 ↑Sat Jul 14, 2018 12:09 am at Sat Jul 14, 2018 12:09 am
>
> 
A little bit complicated, but worked, afair. Feel free to improve it.

IMPORTANT: it was for rooms, afair, so may not fit for characters.

Another remark:

> Reply from shakotay2 ↑Mon Jan 21, 2019 2:57 am at Mon Jan 21, 2019 2:57 am
>
> 

Since I've wasted myriads of time on this and no one seemed to care here's only a small contribution to your request:
.



P00_00.png (12.83 KiB) Viewed 179 times
## Post #3
- Username: Cyber200
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 01, 2023 4:11 pm
- Post datetime: 2023-04-01T09:33:23+00:00
- Post Title: Resident Evil Outbreak Script Noesis

> Reply from shakotay2 ↑Sat Apr 01, 2023 5:09 pm at Sat Apr 01, 2023 5:09 pm
>
> 
Cyber200 wrote: ↑Sat Apr 01, 2023 4:37 pm
Hello Is it possible to make a Noesis script
Hello, it's usually if not always possible to create a Noesis script. Question is: who will?   

I have the strange feeling that you're "one of these guys" who don't search forums, are you?  

If so, you would have found this thread (of mine, in this case):
shakotay2 wrote: ↑Sat Jul 14, 2018 12:09 am
A little bit complicated, but worked, afair. Feel free to improve it.

IMPORTANT: it was for rooms, afair, so may not fit for characters.

Another remark:
shakotay2 wrote: ↑Mon Jan 21, 2019 2:57 am

Since I've wasted myriads of time on this and no one seemed to care here's only a small contribution to your request:
.
P00_00.png

Amazing I should have done more research I've always worked on this game But only on FBX photo models Can't play NBD files In Noesis or even play animations I don't know who could do a script but it would be appreciate a lot   

If there was also the possibility to export the models with the animations


> Reply from shakotay2 ↑Sat Jul 14, 2018 12:09 am at Sat Jul 14, 2018 12:09 am
>
> 
Years later (as a designated member of the riders-of-dead-horses-club)  I feel obliged to contribute some room correction feature; it may be a little bit confusing, but works (for room r0150100.AMO at least), better than copying 115 positions by hand, imho:


PS2 Resident Evil Outbreak
--------------------------

- extract .AMO and .AHI from NBD archive:
http://forum.xentax.com/viewtopic.php?f ... eak#p81422

- extract 3ds from .AMO
http://forum.xentax.com/viewtopic.php?f ... bms#p82047

- create smd from .AHI with The Dude's Noesis script from the starting post here:
http://forum.xentax.com/viewtopic.php?f=16&t=18333

- drag 'n drop smd to chg_bin.exe, you'll get three txt files.

- The positions have to be copied (overwrite mode) to the position arrays
  in the script move_0150100.py

  I'll show the steps for vertOffs_x_out.txt:
  cut 0.000000, 0.000000, 0.000000, from the beginning, (delete the last comma) 
  and paste it to the end behind last value, -126.010063,

  Select the whole line and overwrite the contents of the brackets of
  xpos = [...]
  in the script move_0150100.py

  Repeat this for vertOffs_y_out.txt, ypos = [...]
  and for vertOffs_z_out.txt, zpos = [...]

  ### VERY important: before you can use the following mentioned script
  you have to adapt the path to your 3ds files in it:  
  models_path = os.path.join('C:\\', 'REO\\r0150100')

- Open load_several_3ds_blender2.69.py in a blender text window
  and press Alt-p -> meshes are being imported (clumped)

- delete the script (ctrl-A, delete-key) then
  copy contents of modified move_0150100.py into that window

  Alt-p -> room should be displayed correctly

chg_bin.zip

You may view the result here:
http://forum.xentax.com/viewtopic.php?f ... on#p142219

I saw that on this forum you have already helped someone about this Very nice of you Hoping someone can make a Noesis script  
[Kevin.png](https://xentaxbackup.github.io/file/23621_Kevin.png)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-01T16:13:25+00:00
- Post Title: Resident Evil Outbreak Script Noesis

Haha, this guy Kevin looks like young  John Travolta...
## Post #5
- Username: Cyber200
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 01, 2023 4:11 pm
- Post datetime: 2023-04-01T16:20:06+00:00
- Post Title: Resident Evil Outbreak Script Noesis

> Reply from shakotay2 ↑Sun Apr 02, 2023 12:13 am at Sun Apr 02, 2023 12:13 am
>
> 
Haha, this guy Kevin looks like young  John Travolta...

Yeah it's true I always liked this character and this game
## Post #6
- Username: victorhgamesx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 09, 2021 4:32 am
- Post datetime: 2023-04-15T20:50:13+00:00
- Post Title: Resident Evil Outbreak Script Noesis

Ola meu nome é victor e eu estou desenvolvendo um remake fã de Resident evil outbreak
mas estou precisando extrair animação dos porsonagens monstros etc mas nao acho nada na internet sera que tem alguel por aqui que saiba fazer isso ou esta afin de contribuir para que o game va para frente?
