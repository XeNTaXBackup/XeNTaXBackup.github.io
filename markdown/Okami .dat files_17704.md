## Post #1
- Username: bug
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 10, 2018 9:51 am
- Post datetime: 2018-02-14T23:35:57+00:00
- Post Title: Okami .dat files

Hey folks, real new at this sort of stuff so might come off as a bit of a dunce here.

I'm trying to find all the possible .dat files in the Okami HD PC data that I can convert into .dds files, mainly things like the maps and other 2D images. Problem is I honestly have no clue how I'm supposed to do this. 

So far I've decrypted everything stored in \Okami\data_pc with quickbms and been trying to view files with Noesis, which like I said before only lets me view certain files. 

Thanks and sorry if this is in the wrong section
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-15T16:44:52+00:00
- Post Title: Okami .dat files

How are others supposed to help if you don't upload any samples?
## Post #3
- Username: bug
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 10, 2018 9:51 am
- Post datetime: 2018-02-15T21:58:20+00:00
- Post Title: Okami .dat files

> Reply from Bigchillghost
>
> How are others supposed to help if you don't upload any samples?

oh sorry!

[https://mega.nz/#!cu5SnBYS!GYfOap2rIq5B ... xyR7utR0S0](https://mega.nz/#!cu5SnBYS!GYfOap2rIq5BzUYfPW2on1RPRvOe4nBonxyR7utR0S0)

this first one is what ive already been able to extract as i mentioned in the original post

[https://mega.nz/#!Ji4SFQII!KgFrNEoOBDqO ... K5lBci_Hb8](https://mega.nz/#!Ji4SFQII!KgFrNEoOBDqOvlBoojWGE1tE2LZWpbLvqK5lBci_Hb8)

and this is an example of decrypted .dat files that im triyng to convert to .dds
## Post #4
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-02-16T07:53:57+00:00
- Post Title: Okami .dat files

What's the problem? I mean, all the files are properly handled by my tools I've posted in this thread: [viewtopic.php?f=21&t=17404&start=30#p137061](http://forum.xentax.com/viewtopic.php?f=21&t=17404&start=30#p137061)

see this [map_r10e_0.png](http://photouploads.com/images/dad7d4.png)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-16T09:33:07+00:00
- Post Title: Okami .dat files

> Reply from ffgriever
>
> all the files are properly handled by my tools I've posted in this thread
Not sure whether he has seen that or not.

> Reply from bug
>
> this is an example of decrypted .dat files that im triyng to convert to .dds
Anyway here's a BMS script that can dump the images from the dat files you uploaded.


 DDSExtractor.rar
(605 Bytes) Downloaded 91 times
## Post #6
- Username: bug
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 10, 2018 9:51 am
- Post datetime: 2018-02-16T21:55:56+00:00
- Post Title: Okami .dat files

> Reply from Bigchillghost
>
> ffgriever wrote:all the files are properly handled by my tools I've posted in this thread
Not sure whether he has seen that or not.
bug wrote:this is an example of decrypted .dat files that im triyng to convert to .dds
Anyway here's a BMS script that can dump the images from the dat files you uploaded.
DDSExtractor.rar

thanks so much, you're an absolute lifesaver
## Post #7
- Username: bug
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 10, 2018 9:51 am
- Post datetime: 2018-02-16T23:10:13+00:00
- Post Title: Okami .dat files

> Reply from ffgriever
>
> What's the problem? I mean, all the files are properly handled by my tools I've posted in this thread: viewtopic.php?f=21&t=17404&start=30#p137061

see this map_r10e_0.png

i could be doing something wrong, but ive tried those and unfortunately they don't seem to work for me (they close almost immediately after i open them), im not sure if its because im on windows 10 or if im missing something else?
## Post #8
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-02-17T12:39:07+00:00
- Post Title: Okami .dat files

These are command line tools. It's just much easier and faster to type things than click through them. Not to mention how much easier these are to use in batch mode (with a simple for-do batch  loop). Making GUIs is just too much hassle, comparing the value they add (or detract) to the application.

```
okami-pack -u input_file output_dir
```


But that may be a matter of age.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-20T07:21:54+00:00
- Post Title: Okami .dat files

> Reply from Bigchillghost
>
> Anyway here's a BMS script that can dump the images from the dat files you uploaded.
DDSExtractor.rar
 man you went all out, nice detective work!   
this is a generic ripper script that can do the same  

```

findloc OFFSET binary "\x44\x44\x53\x20"
do
    goto OFFSET
    goto -0x14 0 seek_cur
    get NAME string
    string NAME p "OkamiHD_PC\%s.dds" NAME
    goto OFFSET
    goto 0x14 0 seek_cur
    get SIZE long
    log NAME OFFSET SIZE
    findloc OFFSET binary "\x44\x44\x53\x20" 0 "" -1
while OFFSET != ""

```
## Post #10
- Username: kyojindesu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 17, 2020 6:49 pm
- Post datetime: 2020-05-17T11:32:36+00:00
- Post Title: Okami .dat files

Hi. I let myself refresh the topic, because I'm trying to extract some images from the Okami dat files, but neither method seems to be working. I tried using the BMS script and okami-pack, but I'm getting errors. It may be that a given dat file doesn't contain an image, but I tried several different files, and it never worked.
