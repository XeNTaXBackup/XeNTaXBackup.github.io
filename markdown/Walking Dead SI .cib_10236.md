## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-03-19T20:05:41+00:00
- Post Title: Walking Dead SI .cib

hey guys im sorry for opening a second page about this game 

i just wanted to know if anyone can open the .cib files 

[http://www.mediafire.com/download.php?liyt15rq8gxotix](http://www.mediafire.com/download.php?liyt15rq8gxotix)

if someone can please open theses files i would be very thankful
## Post #2
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-03-20T12:12:32+00:00
- Post Title: Walking Dead SI .cib

anyone?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-03-20T13:17:03+00:00
- Post Title: Walking Dead SI .cib

> Reply from lllccc
>
> if someone can please open theses files i would be very thankfulCould you be more precise?

This is the ASCII contents of axe_2h.cib:

physics\weapon\fireman_axe.phys2
skeletal\weapons\fireman_axe.dfm 
weapon\melee\axe_2h.cit ro.cit
weapons\fireman_axe.dfm
standard

 none a

 worldModel weapon\fireman_axe.phys2
 itemName db_Felling_Axe
 motionStyle axe
 soundStyle fireaxe
 equippedIconIndex 6
 inventoryIconIndex 15
 survivalModifier 6
 successModifier 9
 highlightColor eHighlightColor_red
 normalDamage 25
 powerDamage 60
 damageRange 6
 audioImpactRadius 20
 weaponType eWeaponAxe2h
 damageType eDamageBlade
 normalAttackLevel eAttackLevelMedium
 powerAttackLevel eAttackLevelHeavy

 chargeMoveSpeed 0.65
 swingMoveSpeed 0.5
 swingMoveSpeedDuration 1.25

 collisionRadius 0.5
 swingTime 0.01
 powerSwingTime .6

 sortId 0

 itemInfoDescription UI_Weapon_2HAxe
 itemInfoType UI_Inv_Blade
 itemInfoPropertyName1 UI_Title_Damage
 itemInfoPropertyValue1 UI_Inv_Heavy
 itemInfoPropertyName2 UI_Title_Reach
 itemInfoPropertyValue2 UI_Inv_Far
 itemInfoPropertyName3 UI_Title_Swing
 itemInfoPropertyValue3 UI_Inv_Slow
 itemInfoPropertyName4 UI_blank
 itemInfoPropertyValue4 UI_blank
## Post #4
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-03-20T13:43:43+00:00
- Post Title: Walking Dead SI .cib

to make a quickbms script to be able to extract/repack the files with ^_^ i know iv looked in to hxd to file out whats in it
if you can help with that that would be very nice
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-03-20T15:44:22+00:00
- Post Title: Walking Dead SI .cib

> Reply from lllccc
>
> to make a quickbms script to be able to extract/repack the files with ^_^As far as I can see there's nothing to extract in cib files.

> i know iv looked in to hxd to file out whats in it
There are ASCII strings in the cib files, 
and some hex patterns like
FF FF FF FF FF FF FF FF 00 00 00 00 00 00 00 00
for example.

There's no mesh data or something similar.
What do you want to extract?
Model  data (mesh, bone, animation)?
Then you should have a look at dfm or cit files I guess.
## Post #6
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-03-20T16:05:11+00:00
- Post Title: Walking Dead SI .cib

kk thank you i was going to see if there was any txt files since there was dmg for weapons in it
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-03-20T17:34:46+00:00
- Post Title: Walking Dead SI .cib

If you want to change weapon damage you could try to edit
axe_2h.cib for example:

```
00000230   00 04 00 00 00 6E 6F 72  6D 61 6C 44 61 6D 61 67   .....normalDamag
00000240   65 00 32 35 00 00 04 00  00 00 70 6F 77 65 72 44   e.25......powerD
00000250   61 6D 61 67 65 00 36 30  00 00 04 00 00 00 64 61   amage.60......da
```


Changing 0x242 0x32 -> 0x37 should increase normal Damage to 75.
(Don't owe this game so don't know whether this will work.)

But be sure to overwrite bytes only!

(Inserting bytes is not safe as long as the file format is not known properly.)
## Post #8
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-03-20T17:43:02+00:00
- Post Title: Walking Dead SI .cib

yea i tried that way it gives errors that why i was asking ^_^ thank u so much for your help
