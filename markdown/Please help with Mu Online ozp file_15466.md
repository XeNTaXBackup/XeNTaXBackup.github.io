## Post #1
- Username: Deneky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 08, 2016 1:38 pm
- Post datetime: 2016-11-08T05:45:08+00:00
- Post Title: Please help with Mu Online ozp file

I already searched on google and found some answer how to edit ozp files, they just say to remove first 4 bytes (using hex editor) and save it .png, the img will save .png but I can't see the img, is empry.

I want to convert this file in png one so I can change it [http://www.mediafire.com/file/lqmio444k ... notice.OZP](http://www.mediafire.com/file/lqmio444kpbbbac/Eventnotice.OZP) or maybe if someone tell me how to convert a png file in .ozp

Please someone if know, tell me because I've searched and no results found
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-08T23:02:50+00:00
- Post Title: Please help with Mu Online ozp file

steps.png (95.85 KiB) Viewed 69 times
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-08T23:31:10+00:00
- Post Title: Please help with Mu Online ozp file

here is a bms script to automate this process  

```
get NAME basename
string NAME + ".png"
math OFFSET = 0x4
get SIZE asize
math SIZE - OFFSET
log NAME OFFSET SIZE
```
## Post #4
- Username: Deneky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 08, 2016 1:38 pm
- Post datetime: 2016-11-09T03:15:50+00:00
- Post Title: Please help with Mu Online ozp file

Wow this was so simple herbert, you just save my life. 
Omg I just can't belive honestly  thank you so much bro.

Btw if you have some more free time sometime to answer on this last thing.

Now I plan to edit that png img and if I want to add back in that file how I can add ?
## Post #5
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-09T20:45:48+00:00
- Post Title: Please help with Mu Online ozp file

> Reply from Deneky
>
> Now I plan to edit that png img and if I want to add back in that file how I can add ?Dude, you only have to reverse the steps. I give you a hint: instead of deleting 4 bytes you'll have to add 4 bytes.
You can do it, I believe in you!
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-10T00:25:49+00:00
- Post Title: Please help with Mu Online ozp file

and here is a bms script to change png back to ozp  

```
get NAME basename
string NAME + ".ozp"
set MEMORY_FILE binary "\x89PNG"
log NAME 0 0x4 MEMORY_FILE
append
get SIZE asize
math OFFSET = 0x0
log NAME OFFSET SIZE
```
## Post #7
- Username: Deneky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 08, 2016 1:38 pm
- Post datetime: 2016-11-10T04:32:45+00:00
- Post Title: Please help with Mu Online ozp file

I changed those codes but the file is still .png even if I add .ozp extension 
Check this [http://i.imgur.com/gnDqQfn.png](http://i.imgur.com/gnDqQfn.png) maybe I do something wrong, btw I must tell you that I am new with this software...
Please if you give me few more details how to change the png back to ozp, it really helps me a lot.
## Post #8
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-11T22:31:18+00:00
- Post Title: Please help with Mu Online ozp file

Ok, this is what you have to do in the hex editor:
Open the PNG
Select the first 4 bytes (89 50 4E 47)
CTRL + C
Place the cursor before the first byte (left from 89)
CTRL + V
Save file as *.OZP

If you don't want to edit the files manually, you can let AceWell's bms scripts do the work for you.

First download QuickBMS and extract it somewhere on your PC
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Create a new txt file (you could name it "OZP to PNG.txt")
Copy the first bms script into the txt and save it.

Create another txt file ("PNG to OZP.txt")
Copy AceWell's second bms script.

Now double-click quickbms.exe,
select the script,
select the output folder,
click the Save button
## Post #9
- Username: Deneky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 08, 2016 1:38 pm
- Post datetime: 2016-11-12T04:35:41+00:00
- Post Title: Please help with Mu Online ozp file

Thank you so much bro, I edited it manually like you said. 
The problem that I couldn't save the file .ozp was because I need to add first * before .OZP then delete * and save .OZP

I don't need a software to edit it because I don't work with those things anymore so now the problem is solved
