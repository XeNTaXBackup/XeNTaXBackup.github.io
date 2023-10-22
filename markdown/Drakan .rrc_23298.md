## Post #1
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2021-01-12T16:20:50+00:00
- Post Title: Drakan .rrc

Hi, i would like to write a simple c# program to edit some strings in the game Drakan (i.e. item names etc). So i know, that all strings are in the dragon.rrc file, wich i uploaded here: [https://www.mediafire.com/file/lxsmggi5 ... C.zip/file](https://www.mediafire.com/file/lxsmggi5nzqubpa/DragonRRC.zip/file)

There must be some words inside the file like "Runenklinge" or "Energiebogen". I have the german version of it.
The problem is, that i cant read the file with a binary reader and output them, because the strings are encrypted for some reason.
I got this information here: 
[https://github.com/Zalasus/opendrakan/issues/9](https://github.com/Zalasus/opendrakan/issues/9) and [https://gist.github.com/UCyborg/e16d39f ... c1b5d4c69e](https://gist.github.com/UCyborg/e16d39f716e397869655d6c1b5d4c69e)

I would like to fix some translation problems in the game for all, but i need to read/resave the .rrc file correctly in c#. My know-how about c++ isnt good enough for that. 

Can anyone help me please?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-12T20:25:50+00:00
- Post Title: Drakan .rrc

There is a quickbms script which may help you unpack this file [https://aluigi.altervista.org/bms/drakan.bms](https://aluigi.altervista.org/bms/drakan.bms)
[https://i.imgur.com/t3qHZ6n.png](https://i.imgur.com/t3qHZ6n.png)

Also here you have full implementation of the class that you have linked
[https://github.com/Zalasus/opendrakan/b ... anager.cpp](https://github.com/Zalasus/opendrakan/blob/446c15a2d194779742d83b0e3958407efdbd83a7/src/gui/GuiManager.cpp)

You can always build this project and try to debug it and understand its code
Here you have the instructions
[https://github.com/Zalasus/opendrakan](https://github.com/Zalasus/opendrakan)


If you will have any issues with debugging, you can always check the tutorials section for some info
[viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)



Edit: Ceck also these files:
odCore\SrscFile.h
odCore\SrscFile.cpp
odCore\FilePath.h
odCore\DataStream.h
odCore\SrscRecordTypes.h
It may help you understand what's going on.


Edit2: Oh, and definitely check this documentation file 
doc\riot_database_format.txt


Edit3: Here is also some information on our wiki
[http://wiki.xentax.com/index.php/Surrea ... re_Archive](http://wiki.xentax.com/index.php/Surreal_Software_Archive)


(Sorry for too many edits :p)
## Post #3
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2021-01-12T22:39:29+00:00
- Post Title: Drakan .rrc

Thank you, i will give it a try. 
Well yes, i tried with the bms script, but it extract only some .dat files, wich isnt really usefull or readable. 

I also know about this project "openDrakan" and was looking at the sourcecode, but i dont understand it - thats why iam asking here. I spend a lot of time to read the rrc... maybe someone understand c++ and can help me, i think thats the main problem. I dont need the other functionality of the project. I will one more check on the sourcecode there, but... it would be very very usefull, if someone understand how to open the rrc correctly for the strings...
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-12T23:17:51+00:00
- Post Title: Drakan .rrc

Basically everything you need is in "riot_database_format.txt" document:

Full file format ---> Lines 89-112   
String info --> Lines 561-567
Decryption method --> Lines 704-714


So to extract readable strings you need to write a tool
which is able to:
1. Read all files in archive 
2. Recognize string signature (0x0400 and 0x0401)
3. Decrypt strings
4. Save them to separate files.

in this order.


I don't know C# very well, so I can't help you with coding, but
you can check some of my examples in Python here
[https://github.com/bartlomiejduda/Tools ... EW%20Tools](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools)
## Post #5
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2021-01-13T00:35:18+00:00
- Post Title: Drakan .rrc

Thanks, wow nice work!    I dont know much about python   

```
=================
    Strings in 0x402 records can be decrypted using the following alogrithm:

        uint32_t key = 0x5FDD390D;

        for(size_t i = 0; i < len; ++i)
        {
            str[i] ^= key & 0xFF;
            key = (key<<3) | (key>>(32-3));
        }
```


This i dont understand. size_t should be a uInt in c#... but i really dont know what does the for loop. If i try to convert it in c#, vs get an error in this line: 
```
str[i] ^= key & 0xFF;
```
 on left side i have a string array, on the right is a uint   

In the game you have i.e. an item name called "<0x810f>Lava Rune". The "0x810f" is the ID for the string in dragon.rrc. I extracted the rrc file with the bms script and got a lot of .dat files (attached). I dont know, if they contained strings in it (maybe still encrypted?)

I also would be happy, if there is a way in python to read the rrc file..
[dat.zip](https://xentaxbackup.github.io/file/19297_dat.zip)
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-14T18:31:27+00:00
- Post Title: Drakan .rrc

Here is my implementation of extraction and decryption methods.
You have also C++ decryptor in the same directory for comparsion and file format documentation for reference
[https://github.com/bartlomiejduda/Tools ... ols/Drakan](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Drakan)

I have added "_DECRYPTED" string for you to the filename, so you should be able to recognize
which one was encrypted and which one was plain text
[https://i.imgur.com/DlIbCgy.png](https://i.imgur.com/DlIbCgy.png)

I have also updated the wiki
[http://wiki.xentax.com/index.php/Surrea ... ot_Engine)](http://wiki.xentax.com/index.php/Surreal_Software_Archive_%28Riot_Engine%29)
