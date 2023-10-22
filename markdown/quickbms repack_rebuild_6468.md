## Post #1
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-04-20T16:41:07+00:00
- Post Title: quickbms repack\rebuild

hello everybody first time poster here.

i have a question about .xxx files for mk9 (ps3)

i already extracted  them with quickbms and the Mortal Kombat 9 2011 (*.xxx) script.
that all work fine.(i think gives no error)

but i want repack\rebuild the .xxx file with files swapped(files i want to swap are not bigger) and then its giving me an error \something like: error in src\quickbms.c line 1413: myfopen()

i use cmd.exe in windows and i used the readme of the quickbms

followed this order:quickbms [options] <script.BMS> <input_archive/folder> <output_folder>

and then in options -w -r ....

cant figure it out 
searched the web for a few days but no dice.

if someone has knowledge of this please help.
because im a total noob at this sort of things.

tia

ps:sorry for my bad english!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T17:55:30+00:00
- Post Title: quickbms repack\rebuild

for a generic step-by-step for reimporting files back in an archive take a look here:
[viewtopic.php?p=52546#p52546](http://forum.xentax.com/viewtopic.php?p=52546#p52546)

unfortunately the method used by MK9 doesn't allow to reimport the files because it uses compressed chunks.
so you can't use the quickbms solution.
## Post #3
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-04-20T18:09:03+00:00
- Post Title: quickbms repack\rebuild

> Reply from aluigi
>
> for a generic step-by-step for reimporting files back in an archive take a look here:
viewtopic.php?p=52546#p52546

unfortunately the method used by MK9 doesn't allow to reimport the files because it uses compressed chunks.
so you can't use the quickbms solution.

thanks for the quick reply.

yes i already read that thread and tried it .
but now atleast i know i did it correct and that the .xxx files don't reimport with quickbms because it uses compressed chunks(don't even know what that means :S)

is there an other program that can handle that??or doesnt it work like that?

greets
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T19:41:54+00:00
- Post Title: quickbms repack\rebuild

compressed chunks mean that the file is not compressed directly but it's divided in various pieces and each piece gets compressed separately.

I don't have other solutions, you need someone who wants to write a repacker... a boring job so you need to find someone really motivated.
## Post #5
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-04-23T08:01:08+00:00
- Post Title: quickbms repack\rebuild

thanks for explaining of the compressed stuff

you mean by boring a shitload of work??
well i know there are alot of mortal kombat(coding?) fans are out there ,i will try asking in a new topic. 

greetings
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-23T10:25:22+00:00
- Post Title: quickbms repack\rebuild

usually a repacker is a boring job for various reasons included the fact that it takes time.

for example I can write an extracting script for quickbms in some seconds but if I should create a repacker for the same format it could take me hours.
that's why I don't make repackers.
## Post #7
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-04-23T13:48:21+00:00
- Post Title: quickbms repack\rebuild

well maybe its a few hours for you,but for me i don't even know where to start
 took me a few hours to figure out how cmd works   ,took me an hour how umodel works  
but that doesnt matter its fun learning new things  when you finally get resultst.
