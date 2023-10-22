## Post #1
- Username: slawek
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 27, 2021 6:25 pm
- Post datetime: 2021-03-28T19:37:30+00:00
- Post Title: Port Royale 4 wrong unpacking global.res

hi

I have a problem with unpacking the global.res file for the game Port Royale 4 version 1.5 (the latest).It extract file but there is empty global.txt file I use tools from Port Royale 3 that worked in older versions of Port Royale 4: port_royale3_text_export.exe and port_royale3_text_import.exe, . Needed files are in attachments, I also thought about quickbms but there is no batch file .bms ...Please help


 global-new.7z
(188.77 KiB) Downloaded 17 times
## Post #2
- Username: slawek
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 27, 2021 6:25 pm
- Post datetime: 2021-03-28T19:56:18+00:00
- Post Title: Port Royale 4 wrong unpacking global.res

Tools pack/unpack txt for Port Royale 3 - works on older versions of Port Royale 4 (less than 1.5) 

link to tools 
[https://dark0946.tistory.com/m/47?category=537202](https://dark0946.tistory.com/m/47?category=537202)

in the attachment the older version of global.res by Port royale 4 .Please help unpacking globalnew.res 


 global-oldres.7z
(172.32 KiB) Downloaded 16 times
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-02T21:36:57+00:00
- Post Title: Port Royale 4 wrong unpacking global.res

Hello. I have compared both of your samples and there are indeed some differences as you said.
Here you can see my documentation [http://wiki.xentax.com/index.php/Port_Royale_4_RES](http://wiki.xentax.com/index.php/Port_Royale_4_RES)

I have also created a tool which will extract data to TXT file.
You can check it here [https://github.com/bartlomiejduda/Tools ... ES_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Port%20Royale%204/Port_Royale_4_RES_Tool.py)


After extraction you will see something like this [https://i.imgur.com/SQ0mixO.png](https://i.imgur.com/SQ0mixO.png)
## Post #4
- Username: slawek
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 27, 2021 6:25 pm
- Post datetime: 2021-04-03T11:51:36+00:00
- Post Title: Port Royale 4 wrong unpacking global.res

Hello

It works!!  
 You are the master - thank you. Global.res unpacking works.
I have a question: how to pack this txt file back to thearchive global.res
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-03T12:09:42+00:00
- Post Title: Port Royale 4 wrong unpacking global.res

Repacking would require creating custom import tool. Some values are stil unknown in the header section, also there is some new field (checksum?) in the info section which was not present in the 1.4 version of the game.

Theoretically copying unknown values from original global.res as-is to the new one could work, 
but someone would need to do some testing on that.

So until someone will figure it out, you can only export.
