## Post #1
- Username: Ripernoob1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 25, 2021 12:24 am
- Post datetime: 2021-08-24T18:23:35+00:00
- Post Title: how extract  3d moldel  From Power Rangeres Samurai 360 kinet

Hello im new in the forum 
> i already download the  ISO game   and extract all with XBOX 360 ISO Extract 
> i was try use the nijaRiper with Xena 360 pc emulator but look  is not compatible 
> i try use the Unreal Engine Viwer umodel_64.exe  dwonload ithe [https://www.gildor.org/](https://www.gildor.org/) but noting 

and all that i look is .BIN files how can i  open and get the 3d  models
also i add the folder that i think that models can be there if someone want to try 


[https://drive.google.com/file/d/1BBrR-X ... sp=sharing](https://drive.google.com/file/d/1BBrR-XZNY-VUxIkAuxnS9IVPkn1-TSv2/view?usp=sharing)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-25T09:32:54+00:00
- Post Title: how extract  3d moldel  From Power Rangeres Samurai 360 kinet

First rule to the beginers: don't ever trust the file extensions or to use any tools that deal with files of the same extensions unless you know what you're doing. And maybe try to reduce the size of your uploaded samples next time to avoid traffic waste and make it easier for anyone who'd like to check them.

The bin files are obviously compressed. Here's a BMS script to unpack them:
[PRSSBinUnpacker.zip](https://xentaxbackup.github.io/file/20686_PRSSBinUnpacker.zip)
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-25T09:39:35+00:00
- Post Title: how extract  3d moldel  From Power Rangeres Samurai 360 kinet

Using AXE on the unpacked aya_dayu.NDXR from "aya_dayu/aya_dayu.BIN":


aya_dayu.NDXR.png (137.48 KiB) Viewed 76 times
## Post #4
- Username: Ripernoob1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 25, 2021 12:24 am
- Post datetime: 2021-08-27T03:14:28+00:00
- Post Title: how extract  3d moldel  From Power Rangeres Samurai 360 kinet

>> OH my thanks a lot Bigchillghost  
 I was losing hope that someone will answer me in this forum or in some other.
> I have more than 4 days looking everywhere I really appreciate it
## Post #5
- Username: Ripernoob1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 25, 2021 12:24 am
- Post datetime: 2021-08-27T22:41:13+00:00
- Post Title: how extract  3d moldel  From Power Rangeres Samurai 360 kinet

> Reply from Bigchillghost ↑Wed Aug 25, 2021 5:39 pm at Wed Aug 25, 2021 5:39 pm
>
> 
Using AXE on the unpacked aya_dayu.NDXR from "aya_dayu/aya_dayu.BIN":aya_dayu.NDXR.png

AH im stuck again 
> i  dowload the quickbms  from this page [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm) s 
   i  select the script that you add in the post then i select  all the files   that say r_yellow [https://i.gyazo.com/6fd9eb3b87cbfc9d6af ... eeeb1d.png](https://i.gyazo.com/6fd9eb3b87cbfc9d6af1ac7268eeeb1d.png)  so i got this  [https://i.gyazo.com/871d6fd8a829ad64f5f ... cc593d.png](https://i.gyazo.com/871d6fd8a829ad64f5f477ae81cc593d.png) 
then  I google the tool  "advancer mesh reaper - xtream edtion" but i dont  found the same tool that you  add inthe picutres 

when i try the file .nfxr o .ntrx dont works 
[https://i.gyazo.com/0b9089102eac79be4c8 ... 8d260e.png](https://i.gyazo.com/0b9089102eac79be4c8dd7eb9e8d260e.png) 

[https://i.gyazo.com/1c61f7f4649f727371d ... 35312a.png](https://i.gyazo.com/1c61f7f4649f727371dce19f4135312a.png)

i add the files 

[https://drive.google.com/file/d/1h1ZMRj ... sp=sharing](https://drive.google.com/file/d/1h1ZMRj8awuRYREQYdkWydsOSexqFJ15R/view?usp=sharing)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-28T05:59:13+00:00
- Post Title: how extract  3d moldel  From Power Rangeres Samurai 360 kinet

> Reply from Ripernoob1 ↑Sat Aug 28, 2021 6:41 am at Sat Aug 28, 2021 6:41 am
>
> 
then  I google the tool  "advancer mesh reaper - xtream edtion" but i dont  found the same tool that you  add inthe picutres
Check the 2nd link in my signature.

> Reply from Ripernoob1 ↑Sat Aug 28, 2021 6:41 am at Sat Aug 28, 2021 6:41 am
>
> 
when i try the file .nfxr o .ntrx dont works
It's not a tool for specific game so you definitely can NOT just open the file without specifying any parameters and expect that it'll work.
There're 5 submeshes in this file but as a quick workaround I just assigned different materials to the polygons:



r_yellow.NDXR.png (121.58 KiB) Viewed 41 times



You can check the tutorials through the 1st link in my signature and read the demonstration on how to use AXE through the link on its release page.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-28T06:15:26+00:00
- Post Title: how extract  3d moldel  From Power Rangeres Samurai 360 kinet

FYI, here's the PLC file for that sample you uploaded:


 r_yellow.NDXR.zip
(1023 Bytes) Downloaded 11 times



Just place it into the same directory where r_yellow.NDXR resides and open it through the "Open" button within the "Parameter List" group box. To preview the mesh you must "Load" the paramters first and check the "From Parameter Sets" check box at the lower right corner. Then you can hit the "Preview" button to preview the mesh or the UV. To export the model just navigate to the menu "File" then select "Export from List".
