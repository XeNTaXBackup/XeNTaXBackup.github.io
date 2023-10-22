## Post #1
- Username: mclarenf
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 14, 2006 2:22 am
- Post datetime: 2006-04-13T18:32:21+00:00
- Post Title: A Question

Hi,
I Have a question...
Can I make a plugin for Multiex Commander to Extract A Program Archive ? ( Not a Game Archive )
If I can , please tell me how.
Thank's for your attention.
REGARDS.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-13T19:30:20+00:00
- Post Title: A Question

Well, of course you can make a plugin for any archive you wish, sure. What kind of archive do you wish to create a plugin for?
## Post #3
- Username: mclarenf
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 14, 2006 2:22 am
- Post datetime: 2006-04-14T04:41:21+00:00
- Post Title: A Question

Hi Mr.Mouse,
Very Good ...
I want to make a plugin for a DAT extension that when I use MultiEx Commander to Open It , In some Cases program ready for view contact of this file but in progress, my system hang and CPU Usage Go to %100 ...
This DAT Extension isn't a Game File and it has a different structure ...
I Research and found that it has 2 Primary Sections , First section is for Program Boot Process, and All Datas is in Section 2 ...
I Use the Article whit name: 
"Definitive_Guide_To_Exploring_File_Formats"
I Use HexWorkshop and found the Offset that All Data Begins From there ( in Section 2 of file ), But Now I want to make a plugin for MultiEx Commander to view all content of section 2 of this file ...
I Read Your Article about make Plugin ... But I can't make it and I need more Guide ...
Can you Guide me more about this ?
Thank's for your attention.
REGARDS.
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-16T07:28:53+00:00
- Post Title: A Question

Now im getting curious....what is the program file you are
trying to extract? what program? =o

could you post the .dat file here? if its not too large.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-16T07:32:19+00:00
- Post Title: A Question

> Reply from mclarenf
>
> Hi Mr.Mouse,
Very Good ...
I want to make a plugin for a DAT extension that when I use MultiEx Commander to Open It , In some Cases program ready for view contact of this file but in progress, my system hang and CPU Usage Go to %100 ...
This DAT Extension isn't a Game File and it has a different structure ...
I Research and found that it has 2 Primary Sections , First section is for Program Boot Process, and All Datas is in Section 2 ...
I Use the Article whit name: 
"Definitive_Guide_To_Exploring_File_Formats"
I Use HexWorkshop and found the Offset that All Data Begins From there ( in Section 2 of file ), But Now I want to make a plugin for MultiEx Commander to view all content of section 2 of this file ...
I Read Your Article about make Plugin ... But I can't make it and I need more Guide ...
Can you Guide me more about this ?
Thank's for your attention.
REGARDS.

Yes, please tell usmore on this. Also please ask what you need to know so I can help you!
## Post #6
- Username: mclarenf
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 14, 2006 2:22 am
- Post datetime: 2006-04-24T04:35:09+00:00
- Post Title: A Question

Hi Mr.Mouse and Mr.Strobe ,
Thanks for your attention.
My File is 26 Mb and I can't Upload it ...
Can you Tell Me How Can I write A Script For it ( For MultiEx Commander ) ?
Please Guide me more about this ...
Please tell me that ... I must do this work like write a script for a game file or another way to wrute script.
and How can I do this work ??? Is your guide to write a script enough ? or for softwares files like this , I must change somthings ???
Please tell Me more about write a BMS script in Notepad for a data file ... and use it in MultiEx Commander ...
Thanks For Your Attention ...
REGARDS.
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-24T06:40:21+00:00
- Post Title: A Question

I dont know if the file you are talking about is an archive of some sort
or not. this makes it difficult for me. if you could upload the file somewhere
i could have a look at it, but at the moment i cannot tell you what to do. :/

Even if the file is not an real archive you could still extract files
from it (if the datafile contains files), but without an archiveindex
i dont think BMS could do it, but i might be wrong.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-04-24T20:34:49+00:00
- Post Title: A Question

Actually, MexCom BMS can handle formats without an archive directory (I assume that's what you're referencing), as an example, there's a thread floating around here somewhere concerning the Carnivores *.CAR file format. It's in the Game requests forum, BTW.

@ mclarenf: You can find the current BMS writing tutorial on the WIKI, at [http://wiki.xentax.com/index.php/BMS](http://wiki.xentax.com/index.php/BMS). Regrettably, it doesn't have any examples, but if you can find a simple script elsewhere on the WIKI and follow along, you could learn somewhat of it.
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-24T20:52:52+00:00
- Post Title: A Question

Yes, BMS can handle non-directory stuff as well, as long as there's some way of finding an offset or size of files. 

I should really update the stuff at the WIKI with more info, but I'm waiting until the next release, when the script has changed somewhat (added on to). 

But you can start MexBinder++/Scriptor in the MultiEx Commander directory and then view the help files. There's also an old 16-bit MultiEx help text I believe, that has a simple example of the way it works. That script is not used anymore, but the help file might still point out a few things.

And any questions you may have, just post them here!
