## Post #1
- Username: Ekarissor
- Rank: VIP member
- Number of posts: 11
- Joined date: Sun Jun 12, 2005 3:48 am
- Post datetime: 2005-06-11T20:00:19+00:00
- Post Title: Survival project

First hello to all   

I tried for long now to explore a pak file from my favorite game wich is : survival project online.

I tried dragon unpacker first, but no result, and after i tried game extractor wich i register an no result...after multiex wich i gave a donation, but still not had the register number.

I hope u can help me to solve this problem and help me with this pak file.

I used filecutter and so ad now the header and the tail....u can find them at : [http://www.chadim.be/sp/pak](http://www.chadim.be/sp/pak)

For more info of the game u can go to : [http://www.survival.com.my](http://www.survival.com.my)

Thanks for the help,

Benito
## Post #2
- Username: Ekarissor
- Rank: VIP member
- Number of posts: 11
- Joined date: Sun Jun 12, 2005 3:48 am
- Post datetime: 2005-06-13T12:01:04+00:00
- Post Title: Survival project

Hello,

I know, it's only my second post here, but have someone an idea ?

A little answer would be really appriciate,

Benito
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-06-13T14:02:35+00:00
- Post Title: Survival project

Hi there,

I downloaded the file you posted, but it does not look like an archive. If it is an archive, it might be encrypted or something ?? I don't think we will have any luck with this format.

Are you sure it is an archive? If so, is there a small file in the same directory with the same name. For example, if the archive is called "Archive.pak", are there any files called "Archive.xxx" which are quite small (<100kbs). If there are, could you post it for us.

Thanks.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Ekarissor
- Rank: VIP member
- Number of posts: 11
- Joined date: Sun Jun 12, 2005 3:48 am
- Post datetime: 2005-06-13T15:04:14+00:00
- Post Title: Survival project

Hello,

Well, the main archive is image.pak who is about 200 mo    so i used fillecutter to take the first and the last part, maybe i should just upload the file into my serveur and made a link for u.

Anyway, tks a lot for havinf taking the time to have a look,

Benito
## Post #5
- Username: Ekarissor
- Rank: VIP member
- Number of posts: 11
- Joined date: Sun Jun 12, 2005 3:48 am
- Post datetime: 2005-06-13T15:49:41+00:00
- Post Title: Survival project

I found this file in the image folder, maybe it can help  
[image1.zip](https://xentaxbackup.github.io/file/282_image1.zip)
## Post #6
- Username: Ekarissor
- Rank: VIP member
- Number of posts: 11
- Joined date: Sun Jun 12, 2005 3:48 am
- Post datetime: 2005-06-13T17:16:55+00:00
- Post Title: Survival project

I just upload the complete pack file :  ttp://[www.www.chadim.be/image.zip](http://www.www.chadim.be/image.zip)

This is the main archive, the other, see previous message is the idx file.

Ty,

Benito
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-13T18:05:35+00:00
- Post Title: Survival project

Well, that certainly is helpful. .idx might be .index eh? There are 6220 files listed in there. All images. But not saved there. 

The header is the same as the big file and resources start at 38.

Size and offset info are saved in the .idx file. 

Some of the images are in Progressive Graphics Format (.PGF). 

[http://www.xeraina.ch/pgf/pgf_facts.pdf](http://www.xeraina.ch/pgf/pgf_facts.pdf)

However, their headers have been stripped. You should reconstruct them in some way. I have not found any free viewers/editors for pgf files.
## Post #8
- Username: Ekarissor
- Rank: VIP member
- Number of posts: 11
- Joined date: Sun Jun 12, 2005 3:48 am
- Post datetime: 2005-06-13T18:30:34+00:00
- Post Title: Survival project

Hello again 

Many many thanks for the lastest information (which honestly i don't understand a lot    ), but u are right when u say that they used pgf files.

I used to open all the file and see what they contained, and saw that most were pgf files and others sprites...wich interrest me the most   

If u could find a way to extract the files within the pak file, i will take in charge to read them.

Ty,

Benito
## Post #9
- Username: Ekarissor
- Rank: VIP member
- Number of posts: 11
- Joined date: Sun Jun 12, 2005 3:48 am
- Post datetime: 2005-06-14T19:51:07+00:00
- Post Title: Survival project

Any new's from someone ? 

Help would be nice   

Benito
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-14T22:12:46+00:00
- Post Title: Survival project

Just in crunch mode at work for a deadline. Get back to you soon.
## Post #11
- Username: Ekarissor
- Rank: VIP member
- Number of posts: 11
- Joined date: Sun Jun 12, 2005 3:48 am
- Post datetime: 2005-06-15T09:12:47+00:00
- Post Title: Survival project

Ah great    just keep me intoutch and good luck for ur deadline !!
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-15T20:43:55+00:00
- Post Title: Survival project

Here's a plugin for MultiEx COmmander...

Unzip in the data/plugins directory. (You should get an IDX folder in there). 

Make sure you open a .IDX file when a .PAK file that belongs to it has the same name. So :

image.idx
image.pak 

should be in the same folder. 

You can now extract the contents.  Choose Survival .IDX files 
[idx.zip](https://xentaxbackup.github.io/file/285_idx.zip)
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-16T07:46:59+00:00
- Post Title: Survival project

Hmm, it's slightly off with the filenames. I will update the plugin soon. 

Meanwhile, you can view the format discovered up to now at the WIKI. 

[http://wiki.xentax.com/index.php/Survival_Project](http://wiki.xentax.com/index.php/Survival_Project)
## Post #14
- Username: Ekarissor
- Rank: VIP member
- Number of posts: 11
- Joined date: Sun Jun 12, 2005 3:48 am
- Post datetime: 2005-06-16T13:27:30+00:00
- Post Title: Survival project

Hello !!!

What a great job u did !!!!     Thanks u so much, i couldn't believe it when i saw the answer   

Well, i have extracted all now   must now find some viewer for the spg file and others sprites !

Thanks again,

Benito
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-16T20:34:40+00:00
- Post Title: Survival project

Here's the updated plugin. 

Should fix the incomplete filenames issue.

Enjoy! 
[idx.zip](https://xentaxbackup.github.io/file/289_idx.zip)
## Post #16
- Username: HepapatitiS
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 29, 2005 8:04 pm
- Post datetime: 2005-09-29T12:12:09+00:00
- Post Title: 

Does anyone already get the PGF Viewer?
## Post #17
- Username: MANIC
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 27, 2006 2:49 am
- Post datetime: 2006-01-26T19:43:45+00:00
- Post Title: 

Lol I couldn't figure out how to view/open those .pgf files. I tried XnView but it couldn't do it either. The company still hasn't released a plug-in for Windows. I guess we have to play the waiting game.
Keep in mind that it is a new image format, not widely used.
## Post #18
- Username: NightBlade
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 12, 2006 8:09 pm
- Post datetime: 2006-09-12T22:07:25+00:00
- Post Title: 

OMG after 2 hours of searching I finally found something! Btw what's your name on SP? I just came back to play it   and...hi I'm new!
