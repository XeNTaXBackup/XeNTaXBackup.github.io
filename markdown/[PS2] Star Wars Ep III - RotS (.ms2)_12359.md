## Post #1
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-12-09T20:18:19+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

I have what i think are model files from this game and i'm hoping someone could write an import script or at least walk me through one example with Hex2Obj. I could probably take it from there. Any help is appreciated, thanks!   


 Samples.zip
(82.84 KiB) Downloaded 51 times
## Post #2
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2014-12-10T01:43:12+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

I really wish people cared more about star wars games 3d models i mean we got these here and the TFU1 and 2 animations that no one ever fixed the noesis script for or the TFU2 dlc no ones ever cared to go back and edited the bms script for or the .smf format that can only be used with hex2obj from kinect star wars that holds a ton more models.

But i guess no one has a want to care for star wars games that knows how to do any of this stuff... but when star wars battlefront by dice comes out everyone will jump on it cause it's on the frostbite 3 and until about this year people couldn't get stuff from it's files and they'll wanna see how it's changed.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-14T16:04:51+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

these are the patterns which give the .ms2 files some structure:

30 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  
00 0x C0

30 00 00 80 47 00 00 80 47 00 00 80 47 00 00 00
 00 0x C0

30 00 00 00 45 00 00 00 45 00 00 00 00 00 00 00 
 00 0x C0


30 00 00 80 46 00 00 80 46 00 00 80 46 00 00 00
 00 0x C0


since my search for point clouds didn't reveal anything of relevance
I guess the patterns might mark frames for example

then my 15 minutes were eaten by the mighty god of hex reversing
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-09-12T07:36:19+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

I have some sample model files from the Xbox version that may be easier to figure out.    These samples have what i think are a few submeshes and i can spot the face index with H2O but i can't for the life of me figure anything out beyond that relating to UV and vertices which produces positive results.  

*Problem solved samples removed*
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-12T08:11:24+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

looks promissing but you'll need to fiddle around with the submeshes:



hordesuperbattledroid.JPG (86.64 KiB) Viewed 436 times



Maybe another submesh:
0x9921 71
Vb1
44 16
0x9013 52
021000
0x0 255
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-12T12:24:01+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

all 12 submeshes of superbattledroid and (normal) battledroid:



hordesuperbattleDroid_.JPG (32.9 KiB) Viewed 423 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-13T17:37:17+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

here's a Make_H2O.exe to autocreate H2O files from XBOX-msh (tested with three files only)

Using hex2obj's multimesh feature you can create obj files from the H2O parameter files.


 Make_H2O_StarWarsEp3-XBOX.zip
(67.74 KiB) Downloaded 53 times


edit:
For Win7 and higher you'll need libgcc_s_dw2-1.dll (to be copied to the .exe directory).
(Use forum search to get it from some newer Make_H2O zip I released for other formats.)
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-09-13T23:17:03+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

Awesome thanks!   
That's really cool how you have this set up for automation.   

I didn't have a lot of samples because i had to pull them from the *.pak archives by hand.
I'll try more later in the week, hopefully the main characters.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-09-18T04:52:19+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

Okay i had some time to dig out and convert more characters and i'm seeing many are incomplete.
Have a look at the new msh samples for ones that are incomplete when converted. I started digging through them to see if any submeshes were being skipped and i can see some have a FVF of 36 instead of 44 and are not being converted. I'm also having trouble fine tuning these submesh values in H2O to come out right. The nembrut obj file included in the samples was my best attempt at converting these skipped submeshes. Is it possible to include scanning of more than one type with Make_H2O.exe?

*Problem solved samples removed*
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-18T16:04:56+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

thx. (Btw I was missing nembrut.msh?)

> Reply from AceWell
>
> Is it possible to include scanning of more than one type with Make_H2O.exe?that's no problem.

But it's not too easy to gain all the submeshes. For yoda.msh for example there's a special type I didn't handle:
0xCC5B 870
Vb1
16 99
0xB7B7 327
021000
0x0 255

Use the updated exe together with the dll from the previous zip:


 Make_H2O_.zip
(29.72 KiB) Downloaded 48 times


For yoda hex2obj will create .objx files from some H2O files.
Means these meshes might be uncomplete - just rename them to .obj.

There's additional H2O's created (having a number offset of 300) to fix this.
Yoda's left foot is lost, though. (dunno why - maybe Darth Vader cut it off to replace his missing hand, uurps)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-18T18:06:29+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

yoda'sMissingFoot.JPG (141.74 KiB) Viewed 340 times
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-09-18T23:30:20+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

Thanks shakotay you're awesome!    Its time for one of these   
The cool art in this game has been locked up for a decade but is now set free.   

> Reply from shakotay2
>
> (Btw I was missing nembrut.msh?)
oops sorry, i think i accidentally removed it while trying to meet the 250kb max upload requirement.
It looks fixed anyway.  
It turns out i had the wrong start address for the face indices.   

I've no idea why Yoda's foot would be missing but we can just mirror the other one to fix it.  



anakin_duel.png (206.18 KiB) Viewed 326 times
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-23T16:25:44+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

update for chars:


 Make_H2O-StarW_EP3-chars-test.zip
(65.48 KiB) Downloaded 23 times



(In case of troubles use exe from zip some posts above.)

For creation of multiple obj files from .H2O files use File/SaveAs Mmesh from hex2obj.
Rename *.objx (if any) to *.obj.

For getting all of yoda's submeshes more than 2 runs/loops are required;
I would have to rewrite (more or less) working code after 5 years - I simply hate this, so probably won't do.
(see manual corrected FIcnt in the _readme.txt file in the appended zip file)

Multi obj blender import (adjust drive letter and the path to your msh files!):

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
path_to_obj_dir = os.path.join('D:\\', 'test\\msh')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-24T14:21:58+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.ms2)

Yoda_annakin.png (165.89 KiB) Viewed 117 times
