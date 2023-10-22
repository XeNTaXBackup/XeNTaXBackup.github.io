## Post #1
- Username: raykingnihong
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-10T15:07:37+00:00
- Post Title: Knights Contract

Here are the 2 bms scripts needed to extract the files from this game.
Run this one first

```
open FDDE IDX 1

get BPK long 1
get asize long 1
get version long 1
get files long 1
goto 0x40 1
for i = 0 < files
get offset long 1
get null1 long 1
get size long 1
get null2 long 1
get null3 long 1
get null4 long 1
get null5 long 1
get null6 long 1
set name i
string name + .unk
log name offset size
next i

```


Then run this on the resulting files

```
endian big
goto 0x80
get baseoff long
comtype deflate
math baseoff + 0x88
get files long
for i = 0 < files
set offset baseoff
math offset + 0x80
get size long
get type long

if type == -2077433207
set type 2pc

else if type == -2077433207
set type 2pt

else if type == 48062435
set type abc

else if type == 1600766189
set type ans

else if type == 1605305327
set type apd

else if type == 700709536
set type arc

else if type == 115627141
set type bmr

else if type == 2027142469
set type bsf

else if type == -1464889846
set type bxf

else if type == 1694218024
set type cgb

else if type == -1955723919
set type cog

else if type == -679944956
set type csr

else if type == -1982659432
set type ddm

else if type == -1162246804
set type dds

else if type == 1624721550
set type dmv

else if type == -1349155670
set type dnw

else if type == 1837987305
set type drr

else if type == -1339352920
set type dsp

else if type == -908241797
set type dsr

else if type == 1349996278
set type dvc

else if type == -1637551090
set type ecc

else if type == 56343547
set type eeb

else if type == 1332200963
set type esm

else if type == -1365447186
set type fvc

else if type == 2050114035
set type gfco

else if type == -1574744784
set type gxe

else if type == 1574775495
set type hcf

else if type == -1920368724
set type hcs

else if type == -1744819546
set type hsc

else if type == -606102844
set type hxt

else if type == 1333876174
set type joc

else if type == 1868120587
set type kap

else if type == -1403670365
set type kib

else if type == -544546096
set type kie

else if type == -1665395071
set type kif

else if type == -1920470747
set type kpm

else if type == -696812936
set type lir

else if type == 907843691
set type lpt

else if type == 1561005259
set type mgb

else if type == 372040259
set type nfa

else if type == 1338361581
set type nft

else if type == 616330692
set type ngb

else if type == 1781641826
set type otb

else if type == 926030501
set type pac

else if type == -1426408101
set type pcw

else if type == -1495804707
set type phc

else if type == 1580651307
set type ps3m

else if type == 1647761907
set type ps3v

else if type == 1652157221
set type rcp

else if type == -464469195
set type rpb

else if type == -408136338
set type S_PACK

else if type == -388107492
set type S_PACK

else if type == -576126889
set type sls

else if type == -2037049364
set type sme

else if type == 2115006688
set type tdi

else if type == 1897062215
set type tmc

else if type == -908055351
set type ttr

else if type == -1621944739
set type vbin

else if type == -990788177
set type vgb

else if type == -575906572
set type vlp

else if type == -1237740716
set type wns

else if type == 693148865
set type ssr

else if type == -1844831858
set type wcc

else if type == 1907876278
set type xet

else 

endif

get null long
get null long
getdstring name 0x100
string name + .
string name + type
get zsize long
math baseoff + zsize
math zsize - 0x80
get size2 long
get comp long
get null long
clog name offset zsize size
next i

```
## Post #2
- Username: ultima
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 08, 2009 12:37 pm
- Post datetime: 2014-07-02T22:27:01+00:00
- Post Title: Knights Contract

currently there a script to extract multiple files at the same time? There are still many files ^^'
with a bat file for example?

Thx in advance 

(sorry for my english >_<)
