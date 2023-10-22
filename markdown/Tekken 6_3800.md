## Post #1
- Username: ESR
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 19, 2009 3:10 am
- Post datetime: 2009-10-22T22:33:10+00:00
- Post Title: Tekken 6

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-11-07T16:02:30+00:00
- Post Title: Tekken 6

I'm also interested.
## Post #3
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2009-12-17T15:33:31+00:00
- Post Title: Tekken 6

Hm... And what is it?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-20T17:47:27+00:00
- Post Title: Tekken 6

xbdecompress.exe can extract tekken 6 files perfectly.
## Post #5
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2009-12-21T20:02:47+00:00
- Post Title: Tekken 6

> Reply from chrrox
>
> xbdecompress.exe can extract tekken 6 files perfectly.

It's because you are the man Chrrox
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-01-22T15:57:14+00:00
- Post Title: Tekken 6

> Reply from UberBlack
>
> chrrox wrote:xbdecompress.exe can extract tekken 6 files perfectly.

It's because you are the man Chrrox
How to use this program? And how is it possible to export the models?
## Post #7
- Username: alvincx
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Nov 24, 2009 7:15 pm
- Post datetime: 2010-02-01T04:48:21+00:00
- Post Title: Tekken 6

> Reply from UberBlack
>
> chrrox wrote:xbdecompress.exe can extract tekken 6 files perfectly.

It's because you are the man Chrrox

i tried, it doesn't work
how do we extract the .bin file??
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-02T14:12:30+00:00
- Post Title: Tekken 6

the success (or not) of xbdecompress is related to its version.
in this case probably you need to use xbdecompress 6534 and not 7645
## Post #9
- Username: alvincx
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Nov 24, 2009 7:15 pm
- Post datetime: 2010-02-02T23:39:27+00:00
- Post Title: Tekken 6

thanks for the info, but where can i find that version?? i've searched it but unfortunately i can't find it anywhere   
does it really extract the files inside the .bin??
if it becomes successful would we able to get the .spd files??
## Post #10
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-02-03T13:38:29+00:00
- Post Title: Tekken 6

xb(de)compress doesn't extract / inject files... it just compresses or decompreses them....
you'll still have to parse the bigfile yourself or hope that someone does it for you
## Post #11
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-03-17T10:21:33+00:00
- Post Title: Tekken 6

this is  kazuya.

I guess maybe people no more interest in tekken 6 ripping.

I had success to get decompress bin files. but dont know how to get spd files.
[1.jpg](https://xentaxbackup.github.io/file/2870_1.jpg)
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-03-17T13:49:08+00:00
- Post Title: Tekken 6

> Reply from epopoe
>
> this is  kazuya.

I guess maybe people no more interest in tekken 6 ripping.

I had success to get decompress bin files. but dont know how to get spd files.
It is very interesting for me! how did you do? And there are the bones?
## Post #13
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-03-19T14:26:47+00:00
- Post Title: Tekken 6

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: rev
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 06, 2010 2:43 am
- Post datetime: 2010-04-05T19:17:15+00:00
- Post Title: Tekken 6

So... is there any progress on this? I'd love to get Tekken characters 3d models, but I have no idea how to get them. I'd be willing to learn too, if nobody had done it
## Post #15
- Username: fxfx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 16, 2007 5:04 am
- Post datetime: 2010-04-27T14:41:10+00:00
- Post Title: Tekken 6

The sample file uploaded by ESR (DATA301.bin) appears to be related to Campaign mode, although it might be mix of everything else from the game thrown together.

After decompression, there is no easy way to extract all the files out of it so my findings are based on quickly glancing over the data in a hex editor

XML-style .GYA files are littered all over in plain ascii format, for example:

> <!-- //nbgi/dfs/team/tekken/tk65data/game/x360/prop/latest/cr01.gya -->
>
> <gya>
>
> 
>
> <version>0.9</version>
>
> 
>
> <maya_3_01_scene_name>V:/tekken/tk65data/orig/ps3/prop/model/scenes/cr01.mb</maya_3_01_scene_name>
>
> <maya_3_01_animation_name>./cr01_render_08100120.anim</maya_3_01_animation_name>
>
> <template_name>//nbgi/dfs/team/tekken/tk65data/game/x360/prop/latest/cr01.mtmp</template_name>
>
> <date>2009/08/10 01:20:45</date>
>
> <update>2009/08/10 01:20:45</update>
>
> 
>
> <template_id>01</template_id>
>
> <element_nb>87</element_nb>
>
> <frame_nb>01</frame_nb>
>
> 
>
> <element_list>
>
>     <def_element>_O_OBJ__O_HIR_AllBody PROP_cr01 trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_AllBody PROP_cr01 rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_AllBody PROP_cr01 scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FL_TIRE_ALL _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FL_TIRE_ALL _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FL_TIRE_ALL _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_FL_TIRE _O_OBJ__O_HIR_FL_TIRE_ALL trans_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_FL_TIRE _O_OBJ__O_HIR_FL_TIRE_ALL rot_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_FL_TIRE _O_OBJ__O_HIR_FL_TIRE_ALL scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FR_TIRE_ALL _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FR_TIRE_ALL _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FR_TIRE_ALL _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_FR_TIRE _O_OBJ__O_HIR_FR_TIRE_ALL trans_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_FR_TIRE _O_OBJ__O_HIR_FR_TIRE_ALL rot_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_FR_TIRE _O_OBJ__O_HIR_FR_TIRE_ALL scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RL_TIRE_ALL _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RL_TIRE_ALL _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RL_TIRE_ALL _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_RL_TIRE _O_OBJ__O_HIR_RL_TIRE_ALL trans_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_RL_TIRE _O_OBJ__O_HIR_RL_TIRE_ALL rot_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_RL_TIRE _O_OBJ__O_HIR_RL_TIRE_ALL scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RR_TIRE_ALL _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RR_TIRE_ALL _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RR_TIRE_ALL _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_RR_TIRE _O_OBJ__O_HIR_RR_TIRE_ALL trans_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_RR_TIRE _O_OBJ__O_HIR_RR_TIRE_ALL rot_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_RR_TIRE _O_OBJ__O_HIR_RR_TIRE_ALL scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FR_DOOR _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FR_DOOR _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FR_DOOR _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_SORTBIASm1200__O_OBJ__O_HIR__O_AUTOSKELID_FRin_MoveWindow _O_OBJ__O_HIR_FR_DOOR trans_xyz</def_element>
>
>     <def_element>_O_SORTBIASm1200__O_OBJ__O_HIR__O_AUTOSKELID_FRin_MoveWindow _O_OBJ__O_HIR_FR_DOOR rot_xyz</def_element>
>
>     <def_element>_O_SORTBIASm1200__O_OBJ__O_HIR__O_AUTOSKELID_FRin_MoveWindow _O_OBJ__O_HIR_FR_DOOR scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FRInnerKnob _O_OBJ__O_HIR_FR_DOOR trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FRInnerKnob _O_OBJ__O_HIR_FR_DOOR rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FRInnerKnob _O_OBJ__O_HIR_FR_DOOR scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FRoutKnob _O_OBJ__O_HIR_FR_DOOR trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FRoutKnob _O_OBJ__O_HIR_FR_DOOR rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FRoutKnob _O_OBJ__O_HIR_FR_DOOR scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RL_DOOR _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RL_DOOR _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RL_DOOR _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RLoutKnob _O_OBJ__O_HIR_RL_DOOR trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RLoutKnob _O_OBJ__O_HIR_RL_DOOR rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RLoutKnob _O_OBJ__O_HIR_RL_DOOR scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RR_DOOR _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RR_DOOR _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_RR_DOOR _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FL_DOOR _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FL_DOOR _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FL_DOOR _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_SORTBIASm1200__O_OBJ__O_HIR__O_AUTOSKELID_FLin_MoveWindow _O_OBJ__O_HIR_FL_DOOR trans_xyz</def_element>
>
>     <def_element>_O_SORTBIASm1200__O_OBJ__O_HIR__O_AUTOSKELID_FLin_MoveWindow _O_OBJ__O_HIR_FL_DOOR rot_xyz</def_element>
>
>     <def_element>_O_SORTBIASm1200__O_OBJ__O_HIR__O_AUTOSKELID_FLin_MoveWindow _O_OBJ__O_HIR_FL_DOOR scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FLInnerKnob _O_OBJ__O_HIR_FL_DOOR trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FLInnerKnob _O_OBJ__O_HIR_FL_DOOR rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FLInnerKnob _O_OBJ__O_HIR_FL_DOOR scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FLoutKnob _O_OBJ__O_HIR_FL_DOOR trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FLoutKnob _O_OBJ__O_HIR_FL_DOOR rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_FLoutKnob _O_OBJ__O_HIR_FL_DOOR scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_ATshiftlever _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_ATshiftlever _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_ATshiftlever _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_Handle _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_Handle _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ__O_HIR_Handle _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_LightCover _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_LightCover _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_LightCover _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Backlamp_on _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Backlamp_on _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Backlamp_on _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Brake_on _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Brake_on _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Brake_on _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Light_on1 _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Light_on1 _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Light_on1 _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Light_on2 _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Light_on2 _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_OBJ_O_HIR_Light_on2 _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_SORTBIAS70__O_OBJ__O_AUTOSKELID__O_HIR_Phone_on _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_SORTBIAS70__O_OBJ__O_AUTOSKELID__O_HIR_Phone_on _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_SORTBIAS70__O_OBJ__O_AUTOSKELID__O_HIR_Phone_on _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
>     <def_element>_O_SORTBIAS100__O_OBJ__O_AUTOSKELID__O_HIR_Phone_call _O_OBJ__O_HIR_AllBody trans_xyz</def_element>
>
>     <def_element>_O_SORTBIAS100__O_OBJ__O_AUTOSKELID__O_HIR_Phone_call _O_OBJ__O_HIR_AllBody rot_xyz</def_element>
>
>     <def_element>_O_SORTBIAS100__O_OBJ__O_AUTOSKELID__O_HIR_Phone_call _O_OBJ__O_HIR_AllBody scale_xyz</def_element>
>
> </element_list>
>
> 
>
> <frame_list>
>
>     <frame frame="0">
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>         <element>0.000000 0.000000 0.000000</element>
>
>         <element>0.000000 -0.000000 0.000000</element>
>
>         <element>1.000000 1.000000 1.000000</element>
>
>     </frame>
>
> </frame_list>
>
> 
>
> 
>
> </gya>
These are probably cutscene events where objects get animated at a higher level.

I also spotted "MODEL_" strings and "BONE" strings, but I haven't seen any vertex geometry yet.
I will look at nattakorn's sample later
## Post #16
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-04-27T20:09:57+00:00
- Post Title: Re: Tekken 6

Thank you so much fxfx for this progress.
All the file from the dise are start from DATA301.BIN, DATA302.BIN, DATA303.BIN to DATA320.BIN
I only upload DATA312.BIN because it is the smallest file.

Please let us know how you go with DATA312.BIN.
And please let me know if you want me to upload any more file, I am happy to upload it for you fxfx.

Thank you
## Post #17
- Username: fxfx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 16, 2007 5:04 am
- Post datetime: 2010-04-27T22:01:11+00:00
- Post Title: Re: Tekken 6

I had a look over DATA312 and it appears to contain information on Customisation parts

There was a nice long list of ascii strings containing names ("Kint Cap", "Metal Headband", "Cowboy Hat"...) and also what appear to be directory heirarchies ("lar1/sunglass_04", "cmn1/tfm_cmnglow000", "cmn1/tfm_rageglow002", "cmn1/katana"...) in a different place

The name strings are listed in different languages (English, French, German and Russian) and do not contain any other information pointing to associated data.

But generally, the structure of the entire BIN file is still chaotic and not easy to extract without knowing whether the offsets are relative to their containers or some other arbitary point.

Both these BIN files contain similar data chunks:
"NDXR"
"NTXR"
"GID"
"BONE"

The "BONE" ones are the most intriguing because we would expect geometry information to be nearby.

The "NDXR" chunks appear to be the primary data-containers though, and it may be possible to extract them by a brute-force approach through a simple script.

Don't bother uploading anymore samples, these two BIN files should be more than enough
## Post #18
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-05-10T19:38:38+00:00
- Post Title: Re: Tekken 6

> Reply from fxfx
>
> I had a look over DATA312 and it appears to contain information on Customisation parts

There was a nice long list of ascii strings containing names ("Kint Cap", "Metal Headband", "Cowboy Hat"...) and also what appear to be directory heirarchies ("lar1/sunglass_04", "cmn1/tfm_cmnglow000", "cmn1/tfm_rageglow002", "cmn1/katana"...) in a different place

The name strings are listed in different languages (English, French, German and Russian) and do not contain any other information pointing to associated data.

But generally, the structure of the entire BIN file is still chaotic and not easy to extract without knowing whether the offsets are relative to their containers or some other arbitary point.

Both these BIN files contain similar data chunks:
"NDXR"
"NTXR"
"GID"
"BONE"

The "BONE" ones are the most intriguing because we would expect geometry information to be nearby.

The "NDXR" chunks appear to be the primary data-containers though, and it may be possible to extract them by a brute-force approach through a simple script.

Don't bother uploading anymore samples, these two BIN files should be more than enough
"NDXR" = geomerty (vertex,uvs, indices etc...)
"NTXR" = texture main chunk
"GID" = texture data
"BONE" = do i need to precise ?
## Post #19
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-26T23:58:00+00:00
- Post Title: Re: Tekken 6

Okay I had some time to look at the files:
To the best of my knowledge no 3d models are in the decompressed Data312 file, but there are models in the Data301 file.
I found 3 different types of models, one type had the following format:
Vertex(x,y,z) NormalMapping(x,y,z)

Another type had this:
Vertex(x,y,z) NormalMapping(x,y,z) Float, Float, Float,Float

The last type looked vaguely familiar to models (but are nowhere near the same)  in the PS2 version of Tekken Tag Tournament:
Vertex(x,y,x) 4byte
Normal(x,y,z) 4byte
Texture(u,v) 4byte 4byte

All of the the three different types have some kind of "rogue" Face List, that I can not seem to decipher, that has many "FF FF" bytes scattered inside.
Also there is usually a xml file right before the models that says what the model is.
Here is a picture of the vertexes from some kind of motorcycle or car:
## Post #20
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-27T00:16:56+00:00
- Post Title: Re: Tekken 6

> Reply from FurryFan
>
> Okay I had some time to look at the files:
To the best of my knowledge no 3d models are in the decompressed Data312 file, but there are models in the Data301 file.
I found 3 different types of models, one type had the following format:
Vertex(x,y,z) NormalMapping(x,y,z)

Another type had this:
Vertex(x,y,z) NormalMapping(x,y,z) Float, Float, Float,Float

The last type looked vaguely familiar to models (but are nowhere near the same)  in the PS2 version of Tekken Tag Tournament:
Vertex(x,y,x) 4byte
Normal(x,y,z) 4byte
Texture(u,v) 4byte 4byte

All of the the three different types have some kind of "rogue" Face List, that I can not seem to decipher, that has many "FF FF" bytes scattered inside.
Also there is usually a xml file right before the models that says what the model is.
Here is a picture of the vertexes from some kind of motorcycle or car:

Oh, grate work man, I'll stay tune!
## Post #21
- Username: FurryFan
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-27T01:01:46+00:00
- Post Title: Re: Tekken 6

the faces use that as a reset for the strip.
just reset the tri-strip when you read that.
## Post #22
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-27T06:51:40+00:00
- Post Title: Re: Tekken 6

It's actually almost exactly the same as the Soul Calibur 4 format:

[http://img31.imageshack.us/i/tekkenguy.jpg/](http://img31.imageshack.us/i/tekkenguy.jpg/)

I'm as clueless as anyone else as far as knowing how to actually get data out of the decompressed bin intelligently, though. Guessing the file tables somewhere in the xex. The guy above is located at offset 253394944 (0xF1A8000) of the decompressed data301.bin.

Some of the files are actually the exact same format as SC4, but one of the reserved values in the NDXR header that is always 0 in SC4 now contains non-0 values to indicate version changes presumably, and non-0 version files have a couple differences in their vertex formats.

As far as I can tell, when version > 0, the UV+color array becomes only a UV array, so it has a 4 byte stride instead of 8, and the color values are removed from vertex types 6 and 7 as well, reducing their sizes to 24 and 40 (from 28, 44), respectively.

The other version > 0 change is that the index for the diffuse texture seems to be located 18 bytes into the texture data instead of 34 bytes. But I don't know how to intelligently parse that data. If I did, I might not have to worry about those hardcoded offsets.

Edit: I was completely wrong about the version flag. The existence of the color components depends on the low bits of the vertex type value. There are actually a few of these colorless components in SC4 models too, but I hadn't noticed them, because they're mostly tiny out of the way bits (and they didn't show up on any unweighted surfaces, apparently, which prevented the vertex stride from ever being wrong).
## Post #23
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-27T11:42:10+00:00
- Post Title: Re: Tekken 6

MrAdults, that is a good observation. The format for Tekken Tag Tournament is also very similar to Soul Caliber 3.
## Post #24
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-27T12:57:19+00:00
- Post Title: Re: Tekken 6

I endeavored to find out a bit more about the material command lists (or whatever the hell they really are) to get Tekken 6's textures all mapped out correctly:

[http://img80.imageshack.us/i/t6textures.jpg/](http://img80.imageshack.us/i/t6textures.jpg/)

Soul Calibur 4 uses the "type 8" chunks to define a texture index directly, where Tekken 6 seems to use type 16 and type 20 chunks to actually reference a texture by its global index (as defined by the GIDX chunk in front of the texture data). Here's some code for stumbling through the command lists:

```
{
	BYTE *orig = cmdBuf;
	while (1)
	{
		if (cmdBuf[0] == 8)
		{ //direct texture index
			return GetBigWordRaw(cmdBuf+34);
			//cmdBuf += 56;
		}
		else if (cmdBuf[0] == 18)
		{
			cmdBuf += 32;
		}
		else if (cmdBuf[0] == 16 || cmdBuf[0] == 20)
		{
			int gidx = GetBigWordRaw(cmdBuf+2);
			for (int i = 0; i < textures.Num(); i++)
			{
				noesisTex_t *tex = textures[i];
				if (tex->globalIdx == gidx)
				{
					return i;
				}
			}
			cmdBuf += 24;
		}
		else if (cmdBuf[0] == 0)
		{
			cmdBuf += 4;
		}
		else if (cmdBuf[0] == 63)
		{
			cmdBuf += 4;
		}
		else if (cmdBuf[0] == 65 || cmdBuf[0] == 255)
		{ //seems to indicate the end
			//cmdBuf += 16;
			break;
		}
		else
		{
			break;
		}
	}
	return 0;
}

```


Does anyone know if these values correspond to any kind of GPU opcodes, or if it's just Namco's own crazy proprietary stuff?
## Post #25
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2010-05-28T00:37:36+00:00
- Post Title: Re: Tekken 6

there are a few jets and helicopter in tekken 6 could i get them out with that program
## Post #26
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-05-28T09:05:06+00:00
- Post Title: Re: Tekken 6

> Reply from MrAdults
>
> I'm as clueless as anyone else as far as knowing how to actually get data out of the decompressed bin intelligently, though. Guessing the file tables somewhere in the xex.

As far as i can tell, the file tables are in the IDX files.  8 byte entries.  If the file size is invalid (usually 0xFFFFFFFF), skip that entry as it should repeat the offset again.

```
uint32 dataSize;

```


Sector size is 0x8000, so the start offset is sectorOffset * 0x8000.  i am guessing the BIN files starting with 0x0FF512ED determine whether a file is compressed or not.
## Post #27
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-28T10:20:43+00:00
- Post Title: Re: Tekken 6

Thanks for that revelation. I don't have a fully extracted disc image, so I wasn't aware of the existence of index files.  I do happen to own (and love) Tekken 6 for the 360, though, so I'll be extracting a full image to play with in the near future.

And here's some code to handle the new BONE chunk. Everything else short of the material change I've mentioned is 100% identical to Soul Calibur 4.

```
{
	BYTE			id[4];
	int				unknownA;
	int				unknownB; //A&B maybe version?

	WORD			unknownC;
	WORD			unknownD;

	int				numBones;
	float			unknownE;

	int				hieOfs;
	int				transOfs;
	int				rotOfs;
	int				ofs3;
	int				ofs4;
	int				nameOfs;
	int				ofs5;

	int				pad[3];
} tkBoneHdr_t;

//transform a bone
static void Model_SC4_TransformBone(CArrayList<nmdBone_t> &nmdBones, nmdBone_t &bone)
{
	if (bone.didTrans)
	{
		return;
	}
	bone.didTrans = true;
	if (bone.parentIdx >= 0)
	{
		Model_SC4_TransformBone(nmdBones, bone);
	}

	if (bone.parentIdx >= 0)
	{
		Math_MatrixMultiply(&nmdBones[bone.parentIdx].postTransMat, &bone.boneMat, &bone.postTransMat);
	}
	else
	{
		bone.postTransMat = bone.boneMat;
	}
}

//load BONE (used in tekken, also little endian even for 360)
static void Model_SC4_LoadBONE(BYTE *data, CArrayList<nmdBone_t> &nmdBones)
{
	tkBoneHdr_t *hdr = (tkBoneHdr_t *)data;
	for (int i = 0; i < hdr->numBones; i++)
	{
		int *hieData = (int *)(data + hdr->hieOfs);
		nmdBone_t nb;
		memset(&nb, 0, sizeof(nb));
		nb.objName = (char *)(data + hdr->nameOfs + i*32);
		nb.decDat = NULL;
		nb.parentIdx = hieData[i];
		float *pos = (float *)(data + hdr->transOfs + i*12);
		float *ang = (float *)(data + hdr->rotOfs + i*12);
		fourxMatrix_t fm = g_identityMatrix4x4;
		Math_TranslateMatrix4x4(&fm, pos);
		Math_RotateMatrix4x4(&fm, ang[2]*57.295779514f, 0.0f, 0.0f, 1.0f);
		Math_RotateMatrix4x4(&fm, -ang[1]*57.295779514f, 0.0f, 1.0f, 0.0f);
		Math_RotateMatrix4x4(&fm, ang[0]*57.295779514f, 1.0f, 0.0f, 0.0f);
		Math_4x4ToModelMat(&fm, &nb.boneMat);
		nmdBones.Append(nb);
	}

	//transform all of the bones after loading
	for (int i = 0; i < nmdBones.Num(); i++)
	{
		Model_SC4_TransformBone(nmdBones, nmdBones[i]);
	}
}

```

(contrast this to Soul Calibuer 4, where the bones are matrices in the NMD chunk, and in post-transform space but inverted)
## Post #28
- Username: alvincx
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-30T00:49:46+00:00
- Post Title: Re: Tekken 6

Attached is a stupid and blunt tool to extract the idx+bin files, but it requires the bin to be decompressed (if applicable) before-hand. It will name everything with a .raw extension, except files which it can find model data in which will be named with a .nmd extension. (probably not appropriate, but it's the extension I started using for this format due to SC4)

I've still only looked through the 301 bin to any extent so far, but I've found that most of the characters' parts and crap are not in the same files:
[http://img36.imageshack.us/i/alisay.jpg/](http://img36.imageshack.us/i/alisay.jpg/)
My model loader handles infinite layers of data for the stacked containers (most of the files are stacked), but that doesn't reveal a lot. Most commonly it just produces some extra texture sets (they like to store head textures in separate chunks for some reason).

I'm curious if there are some more complete "decked out" character models, maybe for cinematics or other canned purposes, in the other .bin files. Otherwise putting them together could be a real pain, unless someone finds the data that links all of that stuff together.

Edit: Got around to checking out the other bins, turns out almost all of the default costumes are in single packages in some of the later bins.
[](http://img156.imageshack.us/i/jini.jpg/)
And [http://img525.imageshack.us/img525/3109/t6chars.jpg](http://img525.imageshack.us/img525/3109/t6chars.jpg)
[poopypants.zip](https://xentaxbackup.github.io/file/3084_poopypants.zip)
## Post #29
- Username: ALYX
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Apr 08, 2010 2:33 am
- Post datetime: 2010-05-31T15:57:35+00:00
- Post Title: Re: Tekken 6

What kind of tool can open *nmd file ?
## Post #30
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-06-05T03:16:51+00:00
- Post Title: Re: Tekken 6

Wow, finally tekken 6 is extracted able 
I am Thank MrAdulte for the BIN extractor.

I am just wondering on something after reading through the post.
If the format is identical to Soul Calibur 4, would we be getting .SPD files after BIN extraction and if it is this process would be easy to make the extraction with the SPD_EX tool?
## Post #31
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-06-05T03:31:36+00:00
- Post Title: Re: Tekken 6

[http://pastebin.com/vWER3Ubg](http://pastebin.com/vWER3Ubg)
## Post #32
- Username: alvincx
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Nov 24, 2009 7:15 pm
- Post datetime: 2010-06-06T02:14:32+00:00
- Post Title: Re: Tekken 6

i'm kind of confused.. what are the codes for? how do i use them?
## Post #33
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-06-06T13:36:24+00:00
- Post Title: Re: Tekken 6

> Reply from epopoe
>
> http://pastebin.com/vWER3Ubg
I am confused too, I look through the code and it seem that it have talk about texture info, bone info and some model data. I first though that it is a MAX Script, but dose't seem to work.

so i am wondering what the code for and how to use it thank.
## Post #34
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-06T14:02:48+00:00
- Post Title: Re: Tekken 6

> Reply from epopoe
>
> http://pastebin.com/vWER3Ubg
It's source code for soul calibur, i think.
## Post #35
- Username: alvincx
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Nov 24, 2009 7:15 pm
- Post datetime: 2010-06-07T06:57:54+00:00
- Post Title: Re: Tekken 6

thanks MrAdults for the BIN extractor, so i did manage to extract a bin file and get NMDs, what's the next step to view the models??
## Post #36
- Username: 3djungle
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 30, 2010 11:45 pm
- Post datetime: 2010-06-08T13:39:57+00:00
- Post Title: Re: Tekken 6

hello. What tool can open .nmd file
## Post #37
- Username: Tosyk
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-06-09T05:34:28+00:00
- Post Title: Re: Tekken 6

This handles nmd files.

[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)
## Post #38
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-09T06:34:58+00:00
- Post Title: Re: Tekken 6

> Reply from MrAdults
>
> This handles nmd files.

http://oasis.xentax.com/index.php?content=downloads
OMG  , It's great news. You're like Moses who parted the waters 

p.s.: But, ninja gaiden 2 models still without weight data
## Post #39
- Username: ALYX
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Apr 08, 2010 2:33 am
- Post datetime: 2010-06-09T08:55:00+00:00
- Post Title: Re: Tekken 6

> This handles nmd files.
>
> http://oasis.xentax.com/index.php?content=downloads
A big Thanks to you.
## Post #40
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-09T10:06:37+00:00
- Post Title: Re: Tekken 6

The contents of this post was deleted because of possible forum rules violation.
## Post #41
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-06-09T10:14:32+00:00
- Post Title: Re: Tekken 6

Haha, that's a little disturbing. Well, not all of the models have those expected chunks to reference a global texture index, and they will just default to "texture 0" if the data can't be found in either a global or local reference chunk. There are probably still other chunks to parse that data out, as that material chunk data is still fairly unknown. Or maybe some of them have external material reference maps or something? No idea really.
## Post #42
- Username: alvincx
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Nov 24, 2009 7:15 pm
- Post datetime: 2010-06-10T06:45:45+00:00
- Post Title: Re: Tekken 6

it's kinda annoying when i try to move a bone, the mesh just gets deformed, i'm using 3ds max 2010 by the way..i'm new in this kind of thing anyway

thanks for the tools! you're a hero MrAdults, cheers
## Post #43
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-06-10T08:13:33+00:00
- Post Title: Re: Tekken 6

MrAdults , It's an amazing tool.

Could you addon obj + mtl export? (It's only obj without mtl, yet)or  Could you ur source code in purblic?

It´s no doubt about Great tool.   but I have some problem with inconvenience UI. 

ex. I was used it export to fate unlimited models, and I had each order to convert tga, every tm2 files one by one. I feel in heavy labor.

until now my work reporting with appreciation to you, allow use it.

ps.  Your tool  have like a bug, make (./) invisible folders in process creat folder.

Again, thank you.
## Post #44
- Username: epopoe
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-06-10T22:17:57+00:00
- Post Title: Re: Tekken 6

> Reply from alvincx
>
> it's kinda annoying when i try to move a bone, the mesh just gets deformed, i'm using 3ds max 2010 by the way..i'm new in this kind of thing anywayThat's just the way the data is - many bones are flattened in the hierarchy. This results in faster transforms at runtime, and animation matrices are adjusted to compensate for it. It makes perfect sense to flatten your skeleton when you aren't doing any kind of runtime IK-type solutions on the bone hierarchy, as it represents only a performance win. The data for the original unflattened skeleton is likely lost in Namco's own export process and only they have the source data. This is the case with lots of games these days, so it's a good thing for you to be aware of for future reference.

> Reply from epopoe
>
> Could you addon obj + mtl export? (It's only obj without mtl, yet)or Could you ur source code in purblic?Why not just use COLLADA/SMD/etc? obj export is mostly an afterthought. 

> Reply from epopoe
>
> ex. I was used it export to fate unlimited models, and I had each order to convert tga, every tm2 files one by one. I feel in heavy labor.That's because there is no native support for Fate's texture containers, as has been discussed in the Fate thread.

> Reply from epopoe
>
> ps. Your tool have like a bug, make (./) invisible folders in process creat folder../ or .\ in a Windows path simply means "this directory", and it's 100% benign in a path string. It's impossible for a folder named ./ to exist.  (unless you're using some WINE variant and its path implementation is broken, but I've never heard of that happening)

Also, please put posts like this, that are more oriented toward the tool than the game (Tekken 6 in this case), in the tool thread, instead of cluttering game-specific threads with not-really-pertinent stuff.
## Post #45
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-06-11T01:59:14+00:00
- Post Title: Re: Tekken 6

Hi everyone and thank you MrAdults.

I have just one Question, I try to Extract .bin model from data313 to data320 but its dosn't seem to work.

However, the data301 to data312 is working OK for me and I can view the model.

with data313 to data320, when I try using xbdecompress on it, xbdecompress said that there is not been compress.
and when I using MrAdults tool to Extract, I only get 5 or 6 raw files, no model file. 
I am wondering that is this normal for those Bin files. because I am missing another half of the characters

Thank you
## Post #46
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-06-11T02:31:29+00:00
- Post Title: Re: Tekken 6

data313 to data320  are not model files, I think.

maybe movies or something.
## Post #47
- Username: Anonymous77
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 11, 2010 12:29 pm
- Post datetime: 2010-06-11T20:36:39+00:00
- Post Title: Re: Tekken 6

Hi there 

I'm new here, can I have some help please  

I was trying to use xbdecompress (r 6534 I guess) (On Windows Seven, x64) with the (data301).Bin, but nothing happened....

When I open the .Bin file with xbdecompress.exe, I have that message on the command prompt :
"Overwrite DATA301.BIN ? (Yes/No/All): 
If I say Yes or All, the bin file dissapear, and nothing new appear instead of that (?) 
If I say "No", then nothing occur...

I'm clueless on how to decompress that file, any idea ?

Thanks in advance for your help.

Bye
## Post #48
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-06-12T06:46:56+00:00
- Post Title: Re: Tekken 6

> Reply from Anonymous77
>
> Hi there 

I'm new here, can I have some help please  

I was trying to use xbdecompress (r 6534 I guess) (On Windows Seven, x64) with the (data301).Bin, but nothing happened....

When I open the .Bin file with xbdecompress.exe, I have that message on the command prompt :
"Overwrite DATA301.BIN ? (Yes/No/All): 
If I say Yes or All, the bin file dissapear, and nothing new appear instead of that (?) 
If I say "No", then nothing occur...

I'm clueless on how to decompress that file, any idea ?

Thanks in advance for your help.

Bye
I have the same Thing when using xbdecompress.exe on 64 bit window too
but when I try xbdecompress on 32 bit window, its seen to work OK.
I don't know what or If there are other version of xbdecompress that will work for the 64 bit so I think you would be save to use its with 32 bit window.
## Post #49
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-12T07:04:17+00:00
- Post Title: Re: Tekken 6

I use Win7 x64 and everything work fine.

Just put you .bin and .idx files, xbdecompress.exe, xbcompress.exe and xbdm.dll in the same directory, run CMD, find you xbdecompress.exe and type:

```
xbdecompress [options] source_file destination_file
```

OPTIONS:

```
/R           Recursive processing
/S           Search in subdirectories
/H           Include hidden files
/Q           Suppress file list output
/Y           Don't prompt to overwrite
/C           Display the duration of the actual file decompression time
/D           Overwrite files only if newer
/E           Don't copy empty directories
/T           Create destination directory if it does not exist
/F           Force overwrite of read-only files
/M           Decompress to a target xbox only if it has been secured
/?           Display this message
```

for example:

```
xbdecompress DATA302.BIN DATA302_DECOMPRESS.BIN
```

And the program will not ask you about overwriting.
## Post #50
- Username: Anonymous77
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 11, 2010 12:29 pm
- Post datetime: 2010-06-12T10:02:23+00:00
- Post Title: Re: Tekken 6

Hi =)


Okay, Thanks alot, i've tried from CMD and now it's working perfectly =)

Although I've stopped Tekken 6 Data Extractor (poopypants) after 280 Go took by these .raw files   
I was able to see a 3D sword (from the customization) on noesis v125 but nothing else now (based on the Decompressed Data 312.bin ).
But this should be normal, i'll try later, when I'll have more space on my HDD   

(I wasn't able to try on a x86 windows version because my computer was given with only a x64 Windows edition :p)

By the way, sorry to ask that question but how to get those .bin files from the Disc ? 
They are hidden when I put the XBox 360 disc on the computer 
There must be a Disc Explorer/ Extractor or something (?).


Bye bye and have a nice day 

And thanks alot for giving us tools for being able to extract Tekken 6 3D data, it's really kind for TRUE Tekken fans =)
## Post #51
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-12T11:05:42+00:00
- Post Title: Re: Tekken 6

> Reply from Anonymous77
>
> By the way, sorry to ask that question but how to get those .bin files from the Disc ? 
They are hidden when I put the XBox 360 disc on the computer 
There must be a Disc Explorer/ Extractor or something (?).
Use Xbox Backup Creator.
## Post #52
- Username: Anonymous77
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 11, 2010 12:29 pm
- Post datetime: 2010-06-12T13:10:51+00:00
- Post Title: Re: Tekken 6

Thanks alot Tosyk 

Now I'm able to extract Bin and Idx (I understand now what was missing for a proper data extraction :p)

Bye and have a nice day
## Post #53
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-06-14T19:42:25+00:00
- Post Title: Re: Tekken 6

Hi everyone, I been looking for "Paul" and his clothing and his Item pack, but I don't know where it is.
The only thing that I can find is Paul's body without hair and without clothing in Data301.
Their are also other character that I can not locate them, for example; King, anna, Yoshimitsu, Hwoarang and Law.
Same thing with those character, I can only find their body without their clothing or Item pack.

Dose anyone know which Data file is Paul's clothings and Items pack are in?
Or King, anna, Yoshimitsu, Hwoarang and Law clothings and Items pack.
I hope it's not inside those Data file that I can not extract the model files.

Thank
## Post #54
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-06-25T00:36:22+00:00
- Post Title: Re: Tekken 6

Spent some time looking through the Tekken NMD files. 

Here's a list I made of what's inside the archives:

data301 - base models
data302 - misc junk
data303 - misc junk
data304 - misc thugs, a few characters from story mode, art
data305 - Paul, Law, Lei, King, Yoshimitsu,
data306 - Nina, Hwoarang, Xiaoyu, Christie, Jin
data307 - Julia, Kuma, Bryan, Heihachi, Kazuya
data308 - Lee, Steve, Craig, Mokujin, Eddy, Jack6
data309 - Roger, Anna, Wang, Ganryu, Asuka, Bruce
data310 - Baek, Devil Jin, Raven, Feng, Armor King, Lili
data311 - Sergei, Bob, Zafina, Miguel, Leo
data312 - Azazel, Lars, Alisa, NANCY
data313 - ???
data314 - PAC file
data315-320 - Windows Media Video

Characters files will be in the same order as in this list. So, for example, if you start cycling through the NMDs of data310, the first 200 files or so will be parts of Baek, then, another ~200 files of Devil Jin. An so on.

The files that you'll encounter in data305 -> data312 can be divided in the following categories:
- body parts with no diffuse textures (green bump maps are displayed by Noesis instead)
- each body part is immediately followed by 1-3 files that contain a set of diffuse textures for that part
- junk files with data that Noesis doesn't understand (a single gray triangle is displayed)
- miscellaneous hairstyles (usually with no textures - some shared texture is used for those, I guess)
- a full character in a t-pose usually finalizes the set of files for that character

Half of the characters are not present in a form of a single model - so you'll have to assemble those from parts.
## Post #55
- Username: rev
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 06, 2010 2:43 am
- Post datetime: 2010-06-25T02:54:24+00:00
- Post Title: Re: Tekken 6

So how about us who only have the PS3 version of the game? Is there anyway we can get the 3d models?
## Post #56
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2010-06-30T16:20:09+00:00
- Post Title: Re: Tekken 6

anyone know the files of some of the jets helicopters and tanks?
## Post #57
- Username: jordanpower6
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 28, 2010 8:27 pm
- Post datetime: 2010-07-18T18:54:13+00:00
- Post Title: Re: Tekken 6

Is it possible to mod the textures etc by doing this?
## Post #58
- Username: jordanpower6
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 28, 2010 8:27 pm
- Post datetime: 2010-07-26T13:38:05+00:00
- Post Title: Re: Tekken 6

Is there any way to get the other files that come out as raw with poopypants?
## Post #59
- Username: segafan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 06, 2006 3:58 pm
- Post datetime: 2010-07-31T13:51:09+00:00
- Post Title: Re: Tekken 6

Hi,
where can i download application for extracting NMD files from DATA301.BIN - DATA320.BIN? I can find any extractor for these BIN files.
## Post #60
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-07-31T20:00:34+00:00
- Post Title: Re: Tekken 6

> Reply from segafan
>
> Hi,
where can i download application for extracting NMD files from DATA301.BIN - DATA320.BIN? I can find any extractor for these BIN files.
[here](http://www.mediafire.com/?mpy3tz3zbc8mt9j)
## Post #61
- Username: Lonewolf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 30, 2010 11:21 am
- Post datetime: 2010-08-06T02:43:49+00:00
- Post Title: Re: Tekken 6

Well, when I extract the .bin files, only appear .raw files, how can I obtain the .nmd files?

What am I doing wrong? I would appreciate if someone explain the procedure to extract the files

Thanks in advance.
## Post #62
- Username: jinakanishi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Aug 10, 2010 4:20 am
- Post datetime: 2010-08-09T20:38:04+00:00
- Post Title: Re: Tekken 6

im either noob at this or screwing something up i extracted my tekken 6 game to my pc,when i get to the bin files no matter what program says it can extract or open bin files they will not open them i get this isnt a cd image or cant find file or some error about acessing the file,i would appericiate any help on how to extract and open bin files.
## Post #63
- Username: skittles
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 10, 2010 1:25 pm
- Post datetime: 2010-08-11T06:13:06+00:00
- Post Title: Re: Tekken 6

Hello, I wanted my first post to be on this thread for a number of reasons...first and foremost to say thanks to all who made this happen, because as a 3d modeller(of sorts), I have wanted to see how the namco fellas did their models for YEARS, and finally I get to! After reading the thread, I tried everything as instructed and it worked perfectly. I now have nina imported into 3dsmax complete with textures(although I too noticed the textures needed a little tweaking in the V&W but that's not a big deal at all, and certainly not a complaint  ). I'm currently converting her as a model replacement for my left4dead2 game (lol!) so she can kick zombie butt as well hehehe. At any rate, as an attempt to contribute just a little tiny bit, I thought I would run through my method, etc (since it's still fresh in my mind) for those having trouble. A noob trying to help out the other noobs you might say...so here goes...
I have a folder called tekken6 and in this folder i have noesis, xbcompressiontools, and poopypants.exe (best name ever!).
So that folder is where my tools live and where I will put the bin and idx files and the raws and nmds later.
so first things first...I insert my tekken 6 disc into the drive and load up xbox backup creator...of course I have a special drive with a hacked firmware which allows me to read these discs(i guess this really goes without saying but anyhoo)...
so I go to image tools then image browser....
now scroll to the file I want(nina!!) so that's data306..
I highlight the bin right click and choose extract then do the same for the idx...i put them in my tekken6 folder...
Now I open a command prompt and go to the tekken6 folder and run xbdecompress /H /E /D data306.bin (yes to overwrite)
it runs for a bit then finishes...
then i run poopypants data306.bin and that extracts all the raw and nmd files
del the raws cause i don't need them
load noesis and go through the nmd files (the largest are my focus cause they're most likely to have what I want-full character)
once I find nina I go to file/export and choose smd/tga options and let it do its thing.
voila...i can now load the smd file into 3dsmax and fix all the textures that need it(not all do).
so I repeated this exact process, as instructed in the thread, for christie, xiaou, and jin(who required a little more putting together but no biggie) and it works like a charm.
so anyways, I hope that can help someone having troubles...
I'm using win7 ultimate 32bit btw & xbdecompress6534(as instructed)
you can mod the textures(once you get them out)after doing this and I suppose you could find the vehicles too if you looked hard enough...there is a post in here with a general overview of what's in some of the bin files...that's how i knew which one had nina...so i would start by reading that...at the very least it will tell you which files they're not in
hope this helped someone...somewhere....lol
## Post #64
- Username: jinakanishi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Aug 10, 2010 4:20 am
- Post datetime: 2010-08-11T17:51:44+00:00
- Post Title: Re: Tekken 6

i have extracted the bin file but i havent tried running it in command prompt ill try that cause i have used every software that swears to god and its money it can extract files from a bin and they all fail.
## Post #65
- Username: jinakanishi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Aug 10, 2010 4:20 am
- Post datetime: 2010-08-12T05:25:19+00:00
- Post Title: Re: Tekken 6

either my tekken 6 copy is coruupt on my pc or im doing something wrong,everybin file i have extracted using xbox backup image browser everybin extraction ive tried using xbdecompress or using the stuffit bin extractor all say unkown format or the file maybe corrupted
## Post #66
- Username: skittles
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 10, 2010 1:25 pm
- Post datetime: 2010-08-14T22:50:59+00:00
- Post Title: Re: Tekken 6

> Reply from jinakanishi
>
> either my tekken 6 copy is coruupt on my pc or im doing something wrong,everybin file i have extracted using xbox backup image browser everybin extraction ive tried using xbdecompress or using the stuffit bin extractor all say unkown format or the file maybe corrupted

If you're doing everything as I did and using the same tools then, by default, it must be your files. Like the program says, they must be corrupt or something. Are you using the original disc or an image of it? I'm using the original disc. Also, you're certain you have the right drive to read them? Your drive can make working backups? xbdecompress should do its job assuming the file is good...i dunno about stuffit as i never tried using it for this.
## Post #67
- Username: jinakanishi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Aug 10, 2010 4:20 am
- Post datetime: 2010-08-15T01:30:47+00:00
- Post Title: Re: Tekken 6

> Reply from skittles
>
> jinakanishi wrote:either my tekken 6 copy is coruupt on my pc or im doing something wrong,everybin file i have extracted using xbox backup image browser everybin extraction ive tried using xbdecompress or using the stuffit bin extractor all say unkown format or the file maybe corrupted

If you're doing everything as I did and using the same tools then, by default, it must be your files. Like the program says, they must be corrupt or something. Are you using the original disc or an image of it? I'm using the original disc. Also, you're certain you have the right drive to read them? Your drive can make working backups? xbdecompress should do its job assuming the file is good...i dunno about stuffit as i never tried using it for this.i have a image i downloaded because my disc drive cant read my tekken 6 copy
## Post #68
- Username: skittles
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 10, 2010 1:25 pm
- Post datetime: 2010-08-16T21:35:49+00:00
- Post Title: Re: Tekken 6

The contents of this post was deleted because of possible forum rules violation.
## Post #69
- Username: jinakanishi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Aug 10, 2010 4:20 am
- Post datetime: 2010-08-17T23:06:08+00:00
- Post Title: Re: Tekken 6

yeah i tried that file of yours  and i cant extract it,it always gives me the error unkown format,even though its reconised as a bin file.
## Post #70
- Username: Lonewolf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 30, 2010 11:21 am
- Post datetime: 2010-08-19T01:21:31+00:00
- Post Title: Re: Tekken 6

I extracted the .bin files, the .raw files still appear, but now each .raw file weighs 1GB approximately, I delete all they begin to appear, because otherwise I would fill the hard disk. This is my question: I have to wait to stop appearing the .raw files to obtain the .nmd files?
## Post #71
- Username: rtgoins69
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 12, 2010 10:42 am
- Post datetime: 2010-08-23T21:13:12+00:00
- Post Title: Re: Tekken 6

Hello could someone tell me what I'm doing wrong...?

usage:
  xbdecompress [options] srcfile ... destfile

        /X:target  IP address or name of target console
        /R         Recursive processing
        /S         Search in subdirectories
        /H         Include hidden files
        /Q         Suppress file list output
        /Y         Don't prompt to overwrite
        /C         Display the duration of the actual file decompression time
        /D         Overwrite files only if newer
        /E         Don't copy empty directories
        /T         Create destination directory if it does not exist
        /F         Force overwrite of read-only files
        /M         Decompress to a target xbox only if it has been secured

        /?         Display this message

Specify Xbox files as xE:\..., xD:\..., etc.

G:\>G:\Downloads\Tekken6\xbdecompress y DATA301.BIN DATA301_DECOMPRESS.BIN
xbdecompress: error: DATA301_DECOMPRESS.BIN does not exist

I am using the xbdecompress version 7645... I read somewhere in this post that I need ver. 6534....is that true? If not, then am I wording it wrong in CMD? 

Thanks for any help!
## Post #72
- Username: skittles
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 10, 2010 1:25 pm
- Post datetime: 2010-08-23T21:26:51+00:00
- Post Title: Re: Tekken 6

Well, yes, I would try to use the other version...i've never tried the version you are using so can't say if it works or not for sure, but have read that it does not work, so better safe than sorry. I believe if you search through this thread there is a link to the proper version.
try this as your command: xbdecompress data301.bin
when it asks to overwrite just select yes and let it run
hope that helps 


> Reply from rtgoins69
>
> Hello could someone tell me what I'm doing wrong...?

usage:
  xbdecompress [options] srcfile ... destfile

        /X:target  IP address or name of target console
        /R         Recursive processing
        /S         Search in subdirectories
        /H         Include hidden files
        /Q         Suppress file list output
        /Y         Don't prompt to overwrite
        /C         Display the duration of the actual file decompression time
        /D         Overwrite files only if newer
        /E         Don't copy empty directories
        /T         Create destination directory if it does not exist
        /F         Force overwrite of read-only files
        /M         Decompress to a target xbox only if it has been secured

        /?         Display this message

Specify Xbox files as xE:\..., xD:\..., etc.

G:\>G:\Downloads\Tekken6\xbdecompress y DATA301.BIN DATA301_DECOMPRESS.BIN
xbdecompress: error: DATA301_DECOMPRESS.BIN does not exist

I am using the xbdecompress version 7645... I read somewhere in this post that I need ver. 6534....is that true? If not, then am I wording it wrong in CMD? 

Thanks for any help!
## Post #73
- Username: skittles
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 10, 2010 1:25 pm
- Post datetime: 2010-08-23T21:29:43+00:00
- Post Title: Re: Tekken 6

hrmmm... that is odd....sorry but I'm out of ideas on that one 0_o


> Reply from jinakanishi
>
> yeah i tried that file of yours  and i cant extract it,it always gives me the error unkown format,even though its reconised as a bin file.
## Post #74
- Username: rev
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 06, 2010 2:43 am
- Post datetime: 2010-09-04T01:49:35+00:00
- Post Title: Re: Tekken 6

Can somebody here post the extracted models, or is it against the rules? I only have the PS3 version and I don't have a bluray drive on my pc
## Post #75
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2010-09-22T11:14:39+00:00
- Post Title: Re: Tekken 6

> Reply from rev
>
> Can somebody here post the extracted models, or is it against the rules? I only have the PS3 version and I don't have a bluray drive on my pc
+1000
## Post #76
- Username: Armor King
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Sep 17, 2010 11:32 pm
- Post datetime: 2010-09-22T13:48:26+00:00
- Post Title: Re: Tekken 6

How do you use this poopypants anyway?
## Post #77
- Username: Armor King
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Sep 17, 2010 11:32 pm
- Post datetime: 2010-09-25T15:11:02+00:00
- Post Title: Re: Tekken 6

What code should I use write using poopypants? I tried to run it through cmd promt but it said the system cannot execute the program. I tried to decompress it but it didnt give the nmd files. The file that I decompress just got bigger. I NEED HELP PLEASE.
## Post #78
- Username: rev
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 06, 2010 2:43 am
- Post datetime: 2010-09-29T15:13:33+00:00
- Post Title: Re: Tekken 6

> Reply from sprayer
>
> rev wrote:Can somebody here post the extracted models, or is it against the rules? I only have the PS3 version and I don't have a bluray drive on my pc 
+1000
Anybody? Please
## Post #79
- Username: jordanpower6
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 28, 2010 8:27 pm
- Post datetime: 2010-10-11T15:05:45+00:00
- Post Title: Re: Tekken 6

> Reply from MrAdults
>
> Attached is a stupid and blunt tool to extract the idx+bin files, but it requires the bin to be decompressed (if applicable) before-hand. It will name everything with a .raw extension, except files which it can find model data in which will be named with a .nmd extension. (probably not appropriate, but it's the extension I started using for this format due to SC4)

I've still only looked through the 301 bin to any extent so far, but I've found that most of the characters' parts and crap are not in the same files:
http://img36.imageshack.us/i/alisay.jpg/
My model loader handles infinite layers of data for the stacked containers (most of the files are stacked), but that doesn't reveal a lot. Most commonly it just produces some extra texture sets (they like to store head textures in separate chunks for some reason).

I'm curious if there are some more complete "decked out" character models, maybe for cinematics or other canned purposes, in the other .bin files. Otherwise putting them together could be a real pain, unless someone finds the data that links all of that stuff together.

Edit: Got around to checking out the other bins, turns out almost all of the default costumes are in single packages in some of the later bins.

And http://img525.imageshack.us/img525/3109/t6chars.jpg

What bins contain the default costumes?
## Post #80
- Username: Armor King
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Sep 17, 2010 11:32 pm
- Post datetime: 2010-10-12T18:00:22+00:00
- Post Title: Re: Tekken 6

Here is Armor King 


ArmorKingRender.jpg (36.19 KiB) Viewed 641 times

 I dont know why his eyes are light green and blue.
## Post #81
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2010-11-23T20:27:44+00:00
- Post Title: Re: Tekken 6

I have the tools and files you use most do not know please help me = (
## Post #82
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2011-01-11T14:32:17+00:00
- Post Title: Re: Tekken 6

Wow, you guys are amazing. I didn't know this kind of stuff was possible. Looking into it right now as there are non-art assets I'm interested in. I do have questions about how you coders wrote the program though (I'd really like to learn how to do that) that extracts data to that file format. That reverse engineering is mind blowing to me, if someone could link me to a tutorial on it or something I'd really appreciate it.
## Post #83
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-04-18T06:56:29+00:00
- Post Title: Re: Tekken 6

nina's face model looks the worst in tekken 6, I wonder if the file format is the same in tekken 5 dark resurrection so I can just do the same steps and extract her TDR model.
## Post #84
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-04-24T02:50:45+00:00
- Post Title: Re: Tekken 6

data302 and 303 (mainly 303) contain the map (stages) models.

After exporting the clothes I realized that the textures were stored separately from the clothing themselves (didn't play tekken 6, but I'm guessing you could change clothes and clothing color) and that each file that contained textures had a whole bunch of textures.

Anyone know if all the textures for the maps there as well? I extracted some images but it seems pretty hard to match them up. At least with clothes you knew they appeared somewhere near the clothing meshes themselves.
## Post #85
- Username: Cocobollz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 12, 2011 2:49 am
- Post datetime: 2011-04-24T07:02:50+00:00
- Post Title: Re: Tekken 6

Can anyone here upload the DATA301.IDX file? I need it to run poopypants  So please, anyone?
## Post #86
- Username: Davik1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 11, 2011 3:30 am
- Post datetime: 2011-06-14T01:53:40+00:00
- Post Title: Re: Tekken 6

Could anyone post the uvs for Lars and Alisa.
## Post #87
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-06-14T03:02:53+00:00
- Post Title: Re: Tekken 6

I am looking for this CFA-44 model that makes a cameo in g service security level in campaign. It is an ace combat 6 easter egg and since we cannot rip from any ace combat game this would help the ace combat community. also my friend is working on a supreme commander mod and he needs a CFA-44 reference. If someone could help or at lest tell me what archive it is in>
## Post #88
- Username: Cocobollz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 12, 2011 2:49 am
- Post datetime: 2011-06-15T06:20:27+00:00
- Post Title: Re: Tekken 6

What is CFA-44? Isn't that Lili in the picture? Her body sure looks like Lili and looking at the small picture in the top left corner, it is surely is Lili . I think it is Lili with different hair set. If Lili is what you're looking for, then according to firsak, she's in DATA310.BIN.

> Reply from firsak
>
> Spent some time looking through the Tekken NMD files. 

Here's a list I made of what's inside the archives:
data301 - characters' base models (no hair, no clothing)
data302 - misc junk
data303 - misc junk
data304 - misc thugs, a few characters from story mode, art
data305 - Paul, Law, Lei, King, Yoshimitsu,
data306 - Nina, Hwoarang, Xiaoyu, Christie, Jin
data307 - Julia, Kuma, Bryan, Heihachi, Kazuya
data308 - Lee, Steve, Craig, Mokujin, Eddy, Jack6
data309 - Roger, Anna, Wang, Ganryu, Asuka, Bruce
data310 - Baek, Devil Jin, Raven, Feng, Armor King, Lili
data311 - Sergei, Bob, Zafina, Miguel, Leo
data312 - Azazel, Lars, Alisa, NANCY

Characters files will be in the same order as in this list. So, for example, if you start cycling through the NMDs of data310, the first 200 files or so will be parts of Baek, then, another ~200 files of Devil Jin. An so on. 

The files that you'll encounter in data305 -> data312 can be divided in the following categories:
- body parts with no diffuse textures (green bump maps are displayed by Noesis instead)
- each body part is immediately followed by 1-3 files that contain sets of diffuse textures for that part
- junk files with data that Noesis probably doesn't understand (a single gray triangle is displayed)
- miscellaneous hairstyles (usually with no textures - some shared texture is used for those, I guess)
- a full character in a t-pose usually finalizes the set of files for that character

Half of the characters are not present in a form of a single model - so you'll have to assemble them from parts. 
For instance, there isn't a full default t-pose model of Lars Alexandersson (just a few goofy ones with a half-moon over Lars' head). But at the same time there is a full default 1p model of Alisa Boskonovitch.

If you only need the model but can't extract her from the BIN, there's a guy at tombraiderforums.com (Matty-Croft) who share the extracted Lili model in xnalara format.
## Post #89
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2011-06-15T12:23:33+00:00
- Post Title: Re: Tekken 6

He meant aircraft models.
## Post #90
- Username: Oinky
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 20, 2011 1:18 pm
- Post datetime: 2011-06-20T05:21:04+00:00
- Post Title: Re: Tekken 6

what is the data for animation, and what model viewer should i use to see the model AND the animation? ALso i try noesis, but some data somewhat strange i cannot see it very clear, some of the data even worst like the face and other things...
## Post #91
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-06-26T03:58:55+00:00
- Post Title: Re: Tekken 6

can someone send me the bins containing the nmd files? like data309 and the others?
## Post #92
- Username: Marduk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 21, 2011 1:32 am
- Post datetime: 2011-06-29T01:43:42+00:00
- Post Title: Re: Tekken 6

Hello I am having two problems, any suggestions would be welcome.
1.a I extract the bin and idx files with xbox back up creator, but when I try to demcompress with xbdecompress. I get Xbdecompress Warning: failed to decompress DATA302.BIN to DATA302_DECOMPRESS.BIN
b I have tried xbdecompress 6534, 7645, 9328, and 11164.3 all same result
C. Ive reinjected the bin and Idx files into iso and was able to boot in 360 with no issues

2. I figured for some reason maybe my copy of tekken didnt have its bin compressed, so I used poopypants the bin files. All I got was thousands of raw files and nothing else. 

Please help
## Post #93
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2011-06-29T20:08:07+00:00
- Post Title: Re: Tekken 6

> Reply from Marduk
>
> Please help
Read the thread.
## Post #94
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-07-01T15:36:42+00:00
- Post Title: Re: Tekken 6

Anyone know where the default costumes are located? or their other alternates?
## Post #95
- Username: ParadiseHell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 17, 2011 11:38 am
- Post datetime: 2011-08-18T11:22:57+00:00
- Post Title: Re: Tekken 6

Hi everybody   , sorry for my bad english. Can anybody help extract video from Tekken 6 if it's possible? I think that it in DATA314.bin - DATA320.bin. I try to decompress with xbdompress6534 but it says that it's not compressed and i decided unpack DATA314.bin with poopypants and have 2 files DATA314_FILE0000.raw (720 mb) and DATA314_FILE0001.raw (8 kb) So the question is - how unpack this raw containers?
## Post #96
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2011-08-18T12:21:31+00:00
- Post Title: Re: Tekken 6

> Reply from ParadiseHell
>
> I think that it in DATA314.bin - DATA320.bin. I try to decompress with xbdompress6534 but it says that it's not compressed

Video is in data315-320. Files are not compressed. Use poopypants on them. Rename the extracted files to *.wmv.
## Post #97
- Username: ParadiseHell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 17, 2011 11:38 am
- Post datetime: 2011-08-18T17:31:26+00:00
- Post Title: Re: Tekken 6

Wooow it's works haaahaha) many many thanks firsak) you are a Russian like me? that's great)
Спасибо)
## Post #98
- Username: anime87
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 01, 2011 10:45 am
- Post datetime: 2011-10-01T11:01:53+00:00
- Post Title: Re: Tekken 6

First of all, great tutorial. Got some characters already extracted. Is there a way to repackage an obj with all its dds files back to a nmd file? If its allowed, I can pm for those who wish characters that I have been able to obtain.
## Post #99
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2011-11-24T20:46:49+00:00
- Post Title: Re: Tekken 6

Is there anybody so nice who can tell me step by step how to extract models from Tekken 6 into Noesis? I saw that tutorial on forum...
## Post #100
- Username: DeathBillZhao
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 28, 2011 4:11 pm
- Post datetime: 2012-01-20T09:30:16+00:00
- Post Title: Re: Tekken 6

Anybody know how to rip the animations from the XB360 Tekken 6? It seems very hard...
## Post #101
- Username: BlueEngine
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 07, 2012 9:18 pm
- Post datetime: 2012-05-07T19:09:50+00:00
- Post Title: Re: Tekken 6

★☆~ How to extract Tekken 6 3D models ~ Ultimate Guide 1.0 ~☆★ 


Prerequisites
★ Xbox Backup Creator [Indication: Google is a good friend]
★ Xbdecompress [Indication: Google is a good friend]
★ [Poopypants](http://forum.xentax.com/download/file.php?id=3084) [Thanks to MrAdults, page 2 from this thread]
★ [Noesis](http://oasis.xentax.com/index.php?content=downloads)


Guide
1 ☆ Run Xbox Backup Creator
 NB: If you're on Windows Seven, use the Compatibility Mode (to Windows XP) in order to avoid issues. 

2 ☆ in Xbox Backup Creator, go to Image Tool → Image Browser → File → Open Image → Tekken 6.iso

3 ☆ Extract .BIN and .IDX files from any wanted Data (example: DATA307.BIN and DATA307.IDX)

4 ☆ Place all those file in the same directory : 
→ Poopypants.exe
→ xbcompress.exe
→ Xbdecompress.exe
→ xbdm.dll
→ Data3??.BIN (Replace "??" with the Data of your choice)
→ Data3??.IDX (Replace "??" with the Data of your choice)

5 ☆ Open the Windows Command prompt and use Xbdecompress to decompress the Data.BIN, using the following syntax (we still take data307 as an example) :
xbdecompress DATA307.BIN DATA307D.BIN

6 ☆ Use poopypants to extract NMD 3D files from Data, using the following syntax: 
 poopypants Data307.idx Data307D.Bin

6 ☆ start Noesis 3D model viewer in order to view the models and convert them.



Do not hesitate to ask if you have any question.
## Post #102
- Username: Oinky
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 20, 2011 1:18 pm
- Post datetime: 2012-06-14T18:02:39+00:00
- Post Title: Re: Tekken 6

I always having trouble when applying a texture to the models of this game, the normal model always messed with strange texture and something like that....
## Post #103
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-08-02T15:47:06+00:00
- Post Title: Re: Tekken 6

great stuff on that tutorial! followed it and ended up withthis
## Post #104
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-04-17T06:28:48+00:00
- Post Title: Re: Tekken 6

Is the xbdecompress.exe file available anywhere?
## Post #105
- Username: meganmi
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jul 25, 2015 10:31 pm
- Post datetime: 2016-06-11T06:17:47+00:00
- Post Title: Re: Tekken 6

Is there anyone able to extract stage textures? Seems like it doesn't for me.
## Post #106
- Username: fuhuan416
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 22, 2015 6:16 pm
- Post datetime: 2016-06-15T19:45:09+00:00
- Post Title: Re: Tekken 6

> Reply from meganmi
>
> Is there anyone able to extract stage textures? Seems like it doesn't for me.

Me too, no stages textures, also no many UI and effects textures.
## Post #107
- Username: blackops786187
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 24, 2022 5:48 pm
- Post datetime: 2022-05-24T09:50:24+00:00
- Post Title: Re: Tekken 6

Hi,

Bumping an old thread, Do any of the BIN files include images for text like "ROUND 1", "ROUND 2" Etc? If so which BIN contains it?
## Post #108
- Username: mohsen5asim
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 18, 2018 9:50 am
- Post datetime: 2022-10-09T21:41:22+00:00
- Post Title: Re: Tekken 6

i'd say search in the first 5 , 6 bins.theres stage data there which i know for sure.tag 2 had those textures, t6 probably has them too.there in there mate
