## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-01T12:39:49+00:00
- Post Title: obj2hex, simple mesh injector

----------------------------------------------- (thank you for the 'j'  )
obj to hex converter, simple injector
-----------------------------------------------

// This is not intended to be a proper solution.
// It's just a showcase with limitations.
// Covers vertex floats and WORD FIs only
// Tested with a static mesh of one format only!

Due to limited append size you need to get the complete hex2obj (3 zip files) from here:
"Extracting simple Models" thread, post as of Sun Mar 07, 2021 3:29 pm
Download and unpack the zips into a "H2O_or_your_name" folder in case you haven't done so already.

Then copy Hex2obj_inj.exe into that folder.
-------------------------------------------------
load a binary 3D file ("destination")
insert parameters (addresses, counts)
(or load an H2O file)
display (sub) mesh (for parameter validation only)

provide/load a new.obj (renamed test.obj for example):

structure
----------------------
v 51.811073 20.041969 102.817566
v 51.811073 21.317305 102.817566
v 52.684921 20.041969 102.817085
v 52.684921 20.041969 102.817085
...
f 1 2 3 
f 4 5 6 
f 7 8 9 
...
----------------------

So no normals, no uvs.
There's poor checking only. So probably everything will crash if you don't follow the rules.

If there's more vertices and/or more face indices than in the destination file then there's a cut (upps, not implemented, sorry).
As simple as that.

Press "modify" in menu "Misc". ("Help" see next Menu point. Displays this file.)

If the counts of vertices and face indices need an update they are emitted to a log file.
It's your task to locate the original values of those counts and overwrite them in the destination, then.
Of course this is not required in case the counts don't change.

--------------
   example
--------------
(See instruction list at top of file.)

Start Hex2obj_inj.exe (remember to get the 3 hex2obj zips before from the "Extracting simple Models" thread, post as of Sun Mar 07, 2021 3:29 pm).

From the example folder
load MonsterTruck_B.dat (File\Open) and MonsterTruck_B_1.h2o (File\Open H2O).
(.dat file exceeded zip file size above 250 kB. Find it in the 2nd post of the injector thread on Xentax.)

Select Misc\modify to load
test_bdae_6008FIs.obj (it's a copy of "test_uleq_ucp-bdae.obj" with FIs reduced)

Nothing seemed to happen?
It did (on my side at least): (m)_MonsterTruck_B.dat had been created in the example folder.

--------------------------------------------
Load that file into the injector, File\Open.

Press the go1 button. You'll find the updated vertex count (2369) at the bottom of the left lower listbox.
Scrolling down required.

Change 2385 to the new count.

Press the 'mesh' button. (If it's grayed out read from the beginning).

You should see a "car interior" (which is the contents of above mentioned obj file).

If you're somewhat knowledgeable you may have noticed that I didn't adjust the face index count.
6039 should be changed to 6008 (or 6006, see m_log.txt in example folder)
before pressing go1 (see above).

In this case it didn't matter. We just get 10 superfluous vertices.

If you want to use the modified binary 3D file without any hassle
you'll need to locate and adjust vertex and FI count in there (see end of next post).

shak-otay, July 2023
.
[Mesh_Injection.zip](https://xentaxbackup.github.io/file/24002_Mesh_Injection.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-01T12:50:43+00:00
- Post Title: obj2hex, simple mesh injector

The example binary 3D file ("destination") exceeded the allowed 250 kB append size of the previous zip. Thus it's here:
.


 MonsterTruck_B.zip
(45.88 KiB) Downloaded 20 times


.
btw, to get some deeper insight you may compare the injected obj file with the test.obj created from the modified binary:
...
g submesh_4
f 1898 1899 1893 
f 1893 1865 1898 
#-------------------------------
f 2359 2356 2352 
f 2360 2359 2354 
f 2358 2356 2359 
f 2361 2362 2363 
f 2363 2362 2364 
f 2362 2365 2364 
f 2364 2365 2366 
f 2367 2363 2364 
f 2364 2366 2367 
f 2369 2363 2367 
f 2367 2366 2368 

There's 11 additional face lines which belong to the monstertruck mesh which "address" 11 old vertices.
Thus it's required to adjust the counts in the modified binary 3D file for proper use.

MonsterTruck_B.dat, unmodified
v count (i.e. block size 98 DF 00 00) at offset 0x5b1C
FI count (97 17 00 00) at 0x13AB8 in the original .dat file.

blocksize 57216 (dec.) = 24 x 2384, where 24 is the FVFsize.

(Offsets of counts don't change in the modified .dat file.)
## Post #3
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-07-01T17:30:27+00:00
- Post Title: obj2hex, simple mesh injector

Thanks
