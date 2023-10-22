## Post #1
- Username: rodrigo2397
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 21, 2019 1:00 pm
- Post datetime: 2019-02-20T08:33:13+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

hello i am looking for help on a export of mesh with the hex2obj model i have done my first extraction based on this older thread (i did not wanted to open an older thread) " [https://forum.xentax.com/viewtopic.php? ... ES#p119663](https://forum.xentax.com/viewtopic.php?f=16&t=14483&hilit=SPINTIRES#p119663) " i cant seem to be able to find the uv pos and fbf size everything else based on the faces and vertices ive been able to acomplish, here is the link to the vehicle as the one in the old thread has been removed, [http://s2.modsup.com/cgi-bin/dl.cgi/72x ... 10_mod.rar](http://s2.modsup.com/cgi-bin/dl.cgi/72xqrnxtdbhp3g3i3ozu5vdvhjuaazfijb6qfzneop7tyqfytfxvk5a/82_Chevy_K10_mod.rar) would really appreciate, ( yes i have read all of the tutorial also )
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-20T10:42:51+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

> Reply from rodrigo2397 ↑Wed Feb 20, 2019 4:33 pm at Wed Feb 20, 2019 4:33 pm
>
> ( yes i have read all of the tutorial also )hello, that's nice, but the link to the sample you've provided has expired.
## Post #3
- Username: rodrigo2397
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 21, 2019 1:00 pm
- Post datetime: 2019-02-20T19:54:18+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

i have 2 different files, the first one is the one i have been able to extract buy only the wheels for the second its the same only wheels i haven't been able to get the right UV for the trucks which based on the way the wheel extraction went they all used the same UV pos and fvf size so i would think they might share the same values, again in advance would appreciate the help on this files, quick note the files come without a format but i have modify them with notepad++ to convert them to hex to work with them
## Post #4
- Username: rodrigo2397
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 21, 2019 1:00 pm
- Post datetime: 2019-02-20T19:54:52+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

[https://www.mediafire.com/file/ov1m1t7l ... d.rar/file](https://www.mediafire.com/file/ov1m1t7lsu2s174/82_Chevy_K10_mod.rar/file)

[https://www.mediafire.com/file/dgyf9m0e ... 5.zip/file](https://www.mediafire.com/file/dgyf9m0exjnxqrs/Jeep_Kaiser_M715.zip/file)

forgot to add the links
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-20T23:32:48+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

this is a part of the truck; I don't see where the problem should be with just floats?
(Getting all the subeshes would be a little bit tedious but I'm too busy to include it into the Make_obj project.)



trucks_7oqkolj.png (168.3 KiB) Viewed 142 times



H2O file for lower mesh in above picture (FVFsize= 36):

0x27C7B1 127467
Vb1
36 12
0x120ABD 39573
020000
0x0 255
## Post #6
- Username: rodrigo2397
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 21, 2019 1:00 pm
- Post datetime: 2019-02-21T03:48:05+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

i need more practicing i have been able to extract every single tire but any object in trucks file im not being allowed, the obj tester just opens and closes and im sure its because my face count is wrong i keep getting number close to 65,000 and everytime a number like that pops up it fails
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-21T07:52:09+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

> Reply from rodrigo2397 ↑Thu Feb 21, 2019 11:48 am at Thu Feb 21, 2019 11:48 am
>
> but any object in trucks file im not being allowed, the obj tester just opens and closesThere's a rather simple solution for this: open test.obj for that model in notepad, scroll down to first "ugly line", place cursor, then Edit/Go to..., a line number is being displayed, subtract 1, use this number as vertex count for viewing a point cloud (toggle noPtC button to PtCld, press mesh button).

example for an ugly line:
v 4210678562816000.000000 4281047843864576.000000 4210679099686912.000000

or search for QNAN (not a number)
## Post #8
- Username: rodrigo2397
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 21, 2019 1:00 pm
- Post datetime: 2019-02-21T19:38:26+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

okay ill try that, i still havent quite get the way you got the fvf size, since the tutorial version its not sequential i am confused or does the equation in the tutorial works for both ways? thank you very very much for your help!!
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-21T20:13:52+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

> Reply from rodrigo2397 ↑Fri Feb 22, 2019 3:38 am at Fri Feb 22, 2019 3:38 am
>
> 
okay ill try that, i still havent quite get the way you got the fvf size,It's no rocket science: you look at the data for patterns and in most cases they're easy to find:



FVF = 36 bytes.png (24.88 KiB) Viewed 113 times

(another pattern here is 00010000)

> since the tutorial version its not sequentialhere it's not sequential, too!?

> or does the equation in the tutorial works for both ways?which equation?
## Post #10
- Username: rodrigo2397
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 21, 2019 1:00 pm
- Post datetime: 2019-02-21T20:53:12+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

i got confused with the uv position equation i see thats not for the fvf size i see the patterns now i am working on an extraction now ill try and be right back if it works ill put the screenshot
## Post #11
- Username: rodrigo2397
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 21, 2019 1:00 pm
- Post datetime: 2019-02-21T20:59:31+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

i think i got it
[test hex2obj.png](https://xentaxbackup.github.io/file/15767_test hex2obj.png)
## Post #12
- Username: rodrigo2397
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 21, 2019 1:00 pm
- Post datetime: 2019-02-22T00:18:05+00:00
- Post Title: looking for help on HEX2OBJ just one more thread about the subject

thank you so much i still get some errors here and there but practice should get me going alright
[TEST 2.png](https://xentaxbackup.github.io/file/15768_TEST 2.png)
