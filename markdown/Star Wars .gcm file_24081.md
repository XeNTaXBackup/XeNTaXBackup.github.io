## Post #1
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-19T00:59:06+00:00
- Post Title: Star Wars .gcm file

Been trying to figure these out today to help someone and was going through other samples people posted in the past and noticed these kind of structures but have no idea how to deal with the faces, could get the vertices but can't figure out the faces. Vertex/faces stride should be 26. This is from a gamecube star wars game.


 gcm.rar
(154.32 KiB) Downloaded 19 times
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-19T22:18:00+00:00
- Post Title: Star Wars .gcm file

well, you'll need to subtract 32768 from the face indices in case they're "above or equal to" that value.

Plus another trouble which I couldn't fix yet (maybe those >= values to be handled as strip separators as usually 0xFFFF would be?)
so this is only a partial mesh (FVFsize= 12 bytes):
.



cis_inf_cydon_anims-gcm.png (136.34 KiB) Viewed 76 times


(That other FIs' block starting at 0xDC4C doesn't really help.)
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-20T10:18:49+00:00
- Post Title: Star Wars .gcm file

Here's a test script for converting the two main objects in the file "cis_inf_cydon_anims.gcm" to OBJ format:


 fmt_StarWar_gcm.zip
(1.46 KiB) Downloaded 19 times


Result:
[](https://ibb.co/m486hcz)
## Post #4
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-20T20:44:01+00:00
- Post Title: Star Wars .gcm file

> Reply from Bigchillghost ↑Sun Jun 20, 2021 6:18 pm at Sun Jun 20, 2021 6:18 pm
>
> 
Here's a test script for converting the two main objects in the file "cis_inf_cydon_anims.gcm" to OBJ format:
fmt_StarWar_gcm.zip
Result:

Works well for that specific char, however I'm facing this error which appears to be the same for the rest of them (int too large to convert). Was actually interesting to see how you structured the script for Noesis though. 




 CIS_inf_droid.rar
(163.99 KiB) Downloaded 11 times
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-21T02:03:19+00:00
- Post Title: Star Wars .gcm file

> Reply from dimis9138 ↑Mon Jun 21, 2021 4:44 am at Mon Jun 21, 2021 4:44 am
>
> 
Works well for that specific char, however I'm facing this error which appears to be the same for the rest of them (int too large to convert).
Well, that's why it's called a "test" script. It's only for showing how the geometry data should be handled.
