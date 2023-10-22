## Post #1
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-06-10T16:55:32+00:00
- Post Title: kh2_file_dumper.exe not dumping files in the nametable....

OK before anyone says anything obvious like, use KH2FM, this happens with BOTH KH2 and KH2FM, in the nametbl.txt (attached), that came with the dumping program i am using it lists the Space Paranoids, Halloween Town etc... models for the weapons ingame (keyblades etc...) but the dumper doesnt dump them and when i type the command "obj/W_EX010_10_TR.mdlx" it says "File not found" now these files are definatley inside the KH2.IMG file because they are used ingame.

so my question is, has anybody actually been able to dump these models and can they instruct me on how i might do so aswell.

I have noticed that im not extracting from the bath with the nametbl.txt file, so ill give that ago but im still not sure if itll ripp the files because of what happens when i type the command i mentioned above....
[nametbl.zip](https://xentaxbackup.github.io/file/5490_nametbl.zip)
## Post #2
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-06-10T21:52:48+00:00
- Post Title: kh2_file_dumper.exe not dumping files in the nametable....

ok so changing the path to where the nametbl.txt is and copying the correct .IMG file to that folder and using Falo's special KH2.IDX ripped the models from KH2FM but now im wondering if its possible to do what falo did with KH2FM,s KH2.IDX file with KH2's KH2.IDX, as id love to compare the fine detail changes that were made from KH2 in KH2FM.

If anyone knows how falo did it please help me out ok/
## Post #3
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-06-10T22:55:02+00:00
- Post Title: kh2_file_dumper.exe not dumping files in the nametable....

KH2.IDX is only the "root" filetable, there are 19 other tables:

```
000al.idx, 000bb.idx, 000ca.idx, 000dc.idx, 000di.idx, 000eh.idx, 000es.idx, 000hb.idx, 000he.idx, 000lk.idx, 000lm.idx, 000mu.idx, 000nm.idx, 000po.idx, 000tr.idx, 000tt.idx, 000wi.idx, 000wm.idx, 000gumi.idx
```
To make a "full" filetable, u need to dump these 19 tables and then merge all into 1 (use a hex editor)

idx Format:
4 Byte = numEntrys, 
16 Byte * numEntrys = Entrys
## Post #4
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-06-11T00:02:51+00:00
- Post Title: kh2_file_dumper.exe not dumping files in the nametable....

> Reply from Falo
>
> KH2.IDX is only the "root" filetable, there are 19 other tables:
Code: Select all000al.idx, 000bb.idx, 000ca.idx, 000dc.idx, 000di.idx, 000eh.idx, 000es.idx, 000hb.idx, 000he.idx, 000lk.idx, 000lm.idx, 000mu.idx, 000nm.idx, 000po.idx, 000tr.idx, 000tt.idx, 000wi.idx, 000wm.idx, 000gumi.idxTo make a "full" filetable, u need to dump these 19 tables and then merge all into 1 (use a hex editor)

idx Format:
4 Byte = numEntrys, 
16 Byte * numEntrys = Entrys

if im reading this right, then all i do is open up KH2's KH2.idx, then at the end paste all the data from inside these 19 files in order from 000al.idx to 000wm.idx? (listed in the order they are dumped in)

BTW Falo, thx for the quick response
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-11T17:47:16+00:00
- Post Title: kh2_file_dumper.exe not dumping files in the nametable....

Just hardcode them into an array and iterate over them, opening/parsing/dumping as you go.
## Post #6
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-06-11T21:54:41+00:00
- Post Title: kh2_file_dumper.exe not dumping files in the nametable....

> Reply from finale00
>
> Just hardcode them into an array and iterate over them, opening/parsing/dumping as you go.

Pardon? (sorry not the best at hex editing) could you explain that in a little more detail for me?
## Post #7
- Username: BrucieK
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 25, 2012 3:10 am
- Post datetime: 2012-06-24T20:01:17+00:00
- Post Title: kh2_file_dumper.exe not dumping files in the nametable....

Does anyone know how to contact with Falo?
