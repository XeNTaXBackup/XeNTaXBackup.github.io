## Post #1
- Username: Tomaszewski1994
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 04, 2019 2:03 am
- Post datetime: 2019-11-03T18:21:53+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

Has anyone tried to extract the 3D data from an old EA Sports game called NASCAR Revolution, SE, or 2000?

Looking at the install directory, there is a sub-directory that seems to contain the 3D data for the cars in the game, in the form of .OBJ files. However, when trying to view them in Notepad++, I would get garbled text as opposed to vertex data, and I can't import them using OBJ importers in Blender, leading me to conclude that Stormfront Studios (the designers of the games) is using a proprietary format.

I have had no luck in getting the 3D models using tools such as 3D Ripper DX, Ninja Ripper, and 3DVia Printscreen. The closest I have been to getting the 3D models was when using 3DVia Printscreen, but then upon previewing the files, the window would be blank, and extracting the 3DXml file will reveal that none of the vertices are recorded, and are instead all zeroes.

Below is a screenshot of the game, cropped to one of the cars shown:



example.bmp (109.39 KiB) Viewed 136 times



The next logical step would be to look into the EXE file itself using hex editors such as FlexHex and Cheat Engine. Having no experience in reverse-engineering EXE files, so I wouldn't know how to find memory addresses. I can look and see where the files themselves are loaded, but it won't do any good unless I know how to actually get the data.

Where would be a good place to start? Thanks in advance.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-04T03:44:11+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

> Reply from Tomaszewski1994 ↑Mon Nov 04, 2019 2:21 am at Mon Nov 04, 2019 2:21 am
>
> Where would be a good place to start?
To upload some samples of these OBJ files of course. It's usually simpler than digging into the exe.
## Post #3
- Username: Tomaszewski1994
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 04, 2019 2:03 am
- Post datetime: 2019-11-04T22:05:00+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

Here's the entire folder containing what I assume are the car models for NASCAR Revolution SE.


 cars - RevSE.rar
Contains the OBJ files used by NASCAR Revolution SE (43.34 KiB) Downloaded 23 times
## Post #4
- Username: Tomaszewski1994
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 04, 2019 2:03 am
- Post datetime: 2019-11-04T22:05:54+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

Car models for NASCAR 2000.


 cars - N2000.rar
(25.93 KiB) Downloaded 17 times
## Post #5
- Username: Tomaszewski1994
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 04, 2019 2:03 am
- Post datetime: 2019-11-04T22:06:44+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

And for sh*ts and giggles, the car models for Andretti Racing (same developers).


 cars - Andretti.rar
(16.1 KiB) Downloaded 18 times
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-05T05:58:15+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

> Reply from Tomaszewski1994 ↑Tue Nov 05, 2019 6:05 am at Tue Nov 05, 2019 6:05 am
>
> 
Here's the entire folder containing what I assume are the car models for NASCAR Revolution SE.
Using AMR on cockpit.obj:



asTris.png (143.95 KiB) Viewed 105 times



The faces seem to be encoded as quads. And the extra data in the face structure might be 8-bit UV coordinates.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-05T07:54:35+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

> Reply from Bigchillghost ↑Tue Nov 05, 2019 1:58 pm at Tue Nov 05, 2019 1:58 pm
>
> The faces seem to be encoded as quads.yeah, but I didn't get a proper mesh using quads:
.



cockpit.png (36.33 KiB) Viewed 99 times


Are they supposed to be:
f 6 7 21 22
f 7 8 22 23
f 8 9 23 24
f 9 10 24 25
f 10 11 25 26
f 11 12 26 27
...
or do I need to review my code?
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-05T08:31:54+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

> Reply from shakotay2 ↑Tue Nov 05, 2019 3:54 pm at Tue Nov 05, 2019 3:54 pm
>
> 
Are they supposed to be:
f 6 7 21 22
...
Should be "f 6 7 22 21".
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-05T08:35:46+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

Here's a Noesis OBJ to obj converter for NASCAR Revolution SE:


 fmt_NASCAR_RevolutionSE_obj.zip
(985 Bytes) Downloaded 22 times
## Post #10
- Username: Tomaszewski1994
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 04, 2019 2:03 am
- Post datetime: 2019-11-05T22:47:33+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

You people are life-savers and I cannot thank you enough!
I used the Noesis plugin and I was able to rip models from Revolution, 2000, and Andretti Racing. Results are attached below.

Top left: Ford Taurus model from NASCAR Revlution SE
Top Right: Pontiac Grand Prix model from NASCAR 2000
Bottom Left: Indy car model from Andretti Racing
Bottom Right: Stock car model from Andretti Racing



result.JPG (17.57 KiB) Viewed 84 times



Again, I cannot thank you enough. I should also consider learning AMR, so I could be a little more self-sufficient and able to help others.

IMHO you should consider uploading to the Models Resource. I'd do it myself, but I am above taking undue credit for others' work.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-11-06T02:18:01+00:00
- Post Title: Has anyone tried extracting 3D models from NASCAR Revolution/SE/2000?

> Reply from Tomaszewski1994 ↑Wed Nov 06, 2019 6:47 am at Wed Nov 06, 2019 6:47 am
>
> 
Again, I cannot thank you enough. I should also consider learning AMR, so I could be a little more self-sufficient and able to help others.
I admire that.  
Yet there's no tutorial on AMR yet but if you're interested in the field, you might check the tut through the 1st link in my signature.

> Reply from Tomaszewski1994 ↑Wed Nov 06, 2019 6:47 am at Wed Nov 06, 2019 6:47 am
>
> 
IMHO you should consider uploading to the Models Resource. I'd do it myself, but I am above taking undue credit for others' work.
No thanks. I'm not interested in model sharing stuff. Feel free to do whatever you want.
