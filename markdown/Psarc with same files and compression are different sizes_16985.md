## Post #1
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2017-09-08T13:44:16+00:00
- Post Title: Psarc with same files and compression are different sizes

i replaced the original with the same contents but re-compressed, same compression type etc, i verified both psarcs, and they have the exact same contents with same internal file sizes and compression, yet the re compressed one is 20kb larger, and looks different in hex editor, anyone know why?
this causes resistance 3 to load infinatly

any help would be greatly appreciated 

Original: [https://drive.google.com/open?id=0ByFI1 ... VFzNGoza2s](https://drive.google.com/open?id=0ByFI12GVKGY4R0xuVVFzNGoza2s)

repack: [https://drive.google.com/open?id=0ByFI1 ... EtFNGp4azQ](https://drive.google.com/open?id=0ByFI12GVKGY4bVUwTEtFNGp4azQ)

list of contents fro both original and repack are exactly the same: 
the only change i can find is when i dump the psarc's:

/built/levels/haven_town_center/aa_training_to_diner/instances.lua.trimmed  os=15926 cs=4567 fb=7658
/built/levels/haven_town_center/aa_training_to_diner/instances.lua.trimmed  os=15926 cs=4567 fb=7659

a few of them have different "fb" but i dk what that is or how to fix it

```
/built/levels/haven_town_center/shaders.dat (922887/4174976 22%)
/built/levels/haven_town_center/textures.dat (142470600/207110144 68%)
/built/levels/haven_town_center/cubemaps.dat (646738/1110784 58%)
/built/levels/haven_town_center/ties.dat (14322289/27636864 51%)
/built/levels/haven_town_center/shrubs.dat (47962/100864 47%)
/built/levels/haven_town_center/animsets.dat (9886473/16135040 61%)
etc

```
