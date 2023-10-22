## Post #1
- Username: vertusd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 02, 2010 4:45 am
- Post datetime: 2011-12-25T12:48:03+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

Sry for my english, 
I have met  a problem to repack  Tales of graces F's cpk file,
Tales of graces WII using 2.00.00 to build cpk, when Tales of graces F(PS3) using (CPKMC2.15 DLL2.75)

Currently, there are three tools aviliable to the public:
QuickBms(using a scrpit ), can only unpacking
utf_tab    can only unpacking
CRI PACK FILE MAKER 1.3 can not opening cpks of TOGF,but can repack files from QuickBms, but in game causing infinite loading.
cpk_replace 0.3 can repacking, causing infinite loading too. and the file size is wrong.


but,i tested TOG(Wii), it  works(using cpk_replace to rebuild),which has a lower cpk version, 

Is there any other tools can repack newer cpks?
thx in advance.
## Post #2
- Username: iamatmylimit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 30, 2011 3:35 pm
- Post datetime: 2011-12-26T01:16:08+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

i am in the same position as you are.....i am looking for a cpk extracter and repacker for newer versions as well
## Post #3
- Username: vertusd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 02, 2010 4:45 am
- Post datetime: 2011-12-26T01:36:53+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

why people always not writing repacking tools when there are lots of  unpacking tools?
is it hard to write repacking code?
i may trying to writing the repacking tool myself, when new version of utf_tab/quickBms seems can  extract newer cpks.
## Post #4
- Username: iamatmylimit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 30, 2011 3:35 pm
- Post datetime: 2011-12-26T17:37:24+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

i sent you a reply in pm.....there is a new version of utf tab that is modified....and i came across a newer version of  cpk tools as well dated december 25 2011......

for the utf tab google search for utf_tab07b7_special.zip


i found what appears to be a new cpk tool but i have not tested.

[http://en.sourceforge.jp/projects/sfnet ... fulllist=1](http://en.sourceforge.jp/projects/sfnet_alphateam/releases/?fulllist=1)


and as for the repacking tools.....i notice this also and wish it were different but yes it is harder to repack than to unpack...it like a christmas gift..how easy is it to tear apart the wrapping and open your gift?now how difficult is it to piece it back together to look exactly as it did before or rather to fit exactly as it did before?this is why repacking is more difficult...you are basically putting together the wrapping to a xmas gift and each perfect fold that you just bent you have to make perfect again and im sure youve tried to repackage things in the past and noticed its not perfect but it will do...with programming the it will do part doesnt really work...you know just one number/byte being off will make a program not work....also if you take an apple out of a box and you modified it like made it fat...would it be able to fit back inside the "same" box?you would have to modify the box now....this is pretty much repacking....it is more complicated but this is as easy an explanantion that you will get....it bugs me too man that theres so many extracters and i cant repack stuff....but ya this is the situation....
## Post #5
- Username: vertusd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 02, 2010 4:45 am
- Post datetime: 2011-12-27T03:37:08+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

Thx for your seaching ，the first tools is wrote by a member of the translation group i am in, it's a GUI frontend of cpkmakec.exe(free version of CPK FILE MAKER 1.3), so it's same as cpk file maker 1.3, and it can not handle the newer version cpks of TOGF.
May be it's hard to repacking cpks, we may trying to do a memery patch to modify game files, in this case, repacking is not necessary。we are trying a homebrew named r3volution which mainly wrote by Aaron ,who is the head coder of TOV English translation group .
## Post #6
- Username: vertusd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 02, 2010 4:45 am
- Post datetime: 2011-12-27T04:00:17+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

By the way , if you using cpkmakec.exe(or gui front named cpk_tools) to repack cpks, the final cpks version will be different to the original cpk version number ,coz you repacking it by the old cpkmakec.exe, the game may not Recognize this version of cpk, but some game like Cathrine(PS3)
it works fine.
## Post #7
- Username: vertusd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 02, 2010 4:45 am
- Post datetime: 2011-12-27T04:50:19+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

and i tried to calling the apis in the CpkMaker.DLL of cpk file maker 1.3. it works, i called  compress() to compress some data,
maybe reverse-engineer is possible here, but i did not try it.
## Post #8
- Username: vertusd
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 02, 2010 4:45 am
- Post datetime: 2011-12-27T10:05:12+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

I  read the code of cpk_replace this noon, it seems using the utf_tab04, bug utf_tab04 can not handle some new cpks, so if we change that part of code ,it may works, i am looking into this.
## Post #9
- Username: iamatmylimit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 30, 2011 3:35 pm
- Post datetime: 2011-12-27T21:07:42+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

let me know what you find out....im gonna look to see if theres an alternative
## Post #10
- Username: Wioneul
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 15, 2012 6:00 pm
- Post datetime: 2013-08-17T21:42:35+00:00
- Post Title: CPK (CRI)  repacking ?( version :CPKMC2.15 DLL2.75)

somebody found the answer?
