## Post #1
- Username: RageX
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 25, 2015 2:15 am
- Post datetime: 2015-11-05T21:45:57+00:00
- Post Title: Call of Duty: Black Ops III (.xpak) pls

Hi, I tried to open these xpak files using hex-editor, at some positions I could see offsets of files inside like this :-

```
¯öaÈY,..°.......width: 256.height: 128.levels: 7.manual: 0.format: BC7.semantic: normalMap.initial: none.name: i_c_zom_zod_zombie_fem_head_2_n.type: image.initial: none.offset0: 0.size0: 43728áñÉ)P...¥.......width: 64.height: 128.levels: 7.manual: 0.format: BC4.semantic: glossMap.initial: none.name: i_c_nrc_supp_kneepads_g.type: image.initial: none.offset0: 0.size0: 5480œv†t....®.
```


Is there any way someone could write a dumper/extractor which will be able to unpack xpak files with offsets ?

Here are the sample files :-

```
http://www.solidfiles.com/d/1281623965/
```
## Post #2
- Username: myasa
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 23, 2015 4:56 pm
- Post datetime: 2015-11-17T12:44:10+00:00
- Post Title: Call of Duty: Black Ops III (.xpak) pls

> Reply from RageX
>
> Hi, I tried to open these xpak files using hex-editor, at some positions I could see offsets of files inside like this :-
Code: Select all¯öaÈY,..°.......width: 256.height: 128.levels: 7.manual: 0.format: BC7.semantic: normalMap.initial: none.name: i_c_zom_zod_zombie_fem_head_2_n.type: image.initial: none.offset0: 0.size0: 43728áñÉ)P...¥.......width: 64.height: 128.levels: 7.manual: 0.format: BC4.semantic: glossMap.initial: none.name: i_c_nrc_supp_kneepads_g.type: image.initial: none.offset0: 0.size0: 5480œv†t....®.

Is there any way someone could write a dumper/extractor which will be able to unpack xpak files with offsets ?

Here are the sample files :-
Code: Select allhttp://www.solidfiles.com/d/1281623965/
 you can use this:
[http://aluigi.altervista.org/bms/cod_kapi.bms](http://aluigi.altervista.org/bms/cod_kapi.bms)
