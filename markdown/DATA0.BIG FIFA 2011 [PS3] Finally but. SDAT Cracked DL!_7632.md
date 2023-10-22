## Post #1
- Username: IngPereira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2011 8:55 am
- Post datetime: 2011-11-05T02:43:07+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

Hello, first I am happy to have access to this incredible community and i am a developer of the PS3 community.

I've been working with the game FIFA 2011 PS3 and made ​​progress and overcome the limits imposed by EA in this version. 

First the most important data in the fifa game (DATA0.BIG) are not in its original format .big i mean it was compressed in a proprietary format called SDATA of sony (.SDAT) many games should use this format (Big tons) but i have a tool programmed by a friend asmodean that just uncompress the files in sdat to his original format but need to be used on the ps3 itself.

Here is the tool decrsdat 1.0 source code file that need to be compiled with the PS3SDK 3.41 and later you will install the pkg on your cfw on the PS3.
 a gift for you guys and soon i will uploading the compiled version to the people working with the SDAT.

Update Here are the link for the PKG that make the magic of decrypt the SDATA to his original form.


> This program runs on the GameOS and loads the file decrsdat.lst from the path /dev_usb or the installation path pkg / dev_hdd0/game/ASMO00001/USRDIR/decrsdat.lst and reads the first line of This file and the command with the file name of the encrypted SDATA and the name of the output file

Well i just used on FIFA 11 DATA0.BIG.SDAT and now i have the DATA0.BIG but when i use the same tool to extract the content that use the pc modders(FIFAFS, Others scripts in python) on fifa i just have the following errors:

.- In. XML are some strange symbols and letters instead of the required text.

.- The database for example seems to be completely destroyed away as it does not distinguish anything, and even seems to have errors in the header like so many files.

There are errors with the tools and the ps3 .big maybe because the pc tools are for little endian and the big in the ps3 and the 360 are just BIG ENDIAN.

The FIFA in the PS3 console never has been modified and it's a great game that need help to be more great like others and if we have access to the db inside the data0.big is all what we need to make progress.

Details:

The SDATA has been cracked!.
Now we have a beatifull big endian file named DATA0.BIG from FIFA 11.

We need (My team and all the people interested in this) an script for Quickbms to work with this .BIG (Maybe extracting and modify some stuff and repack but right now extracting will be a Big step) that is maybe the last chance to get the this project finished.

Here are the file DATA0.BIG without the SDATA layer like the 360 or the pc but with the arquitecture diference.

Header 
42 49 47 34 "BIG4"



Again i tried with the aluigi fightnight for 360 quickbms script(Great Guy thanks to him for his great scripts) but there are some incompatibility maybe because of the header

With the others tools on pc there are a bunch of errors and wrongs symbols in the extracted files and i think that this is due to the endianness. 

I will be uploading more stuff here and I will thank you guys for your help with the needed quickbms script.

Update2

Like you can read on the rest of the topic (just down, total commander with game unpacker plugin and Open source big editors but the best way is with total commander) is possible to extract the files from the BIG but you cannot make modifications (I just try all the ways) in the archive there are some problems with the only editor i know that can repack the bigs (BIG Editor new version beta) the editor modified some important bytes in the archive but this need more work with that right now we need a real packer for this files maybe some with skills in Bms right now there are other problems:

There is need later to re-done the SDAT file i mean convert again the BIG to BIG.SDAT but if we patch the loader (FIFAZF.SELF, EBOOT.BIN) in the IDA dissasembler to leave the sdat and just look for the big with that we can just make our BIG modified and the game will look for that big instead of the sdat.

Thanks for your help and i will be waiting for your help guys.

Greetings
## Post #2
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2011-11-11T11:11:54+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

it's compressed EA BIG file with big endian byte order. the compression used is the same as in latest CnC series.
Game Unpacker Plug-in for Total Commander is able to open this archives.
Here is all files from your .big file unpacked:
## Post #3
- Username: IngPereira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2011 8:55 am
- Post datetime: 2011-11-11T19:25:51+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

Thanks for your reply, but i take note about that some days before but i never have extracted the files because there are problems with the other explorers or editors of BIG files (Big Editor, etc) but thanks for your help right this is very usefull with the bigs but i have encounteres some more errors with the modifications and the errors are related to the executable file that is more secure and it don't let me modify some bigs like this because the SDAT format need to be re-done in the BIG again after the Modifications but there are no ways to make the SDATA i mean i can make sdatas but debugs with the PS3 SDK but these don't work with fifa 11 right now i am moving my works to FIFA 2012, when i have the game i will continue the investigation, the files on fifa 12 are like the fifa 11 in the PS3, so this need work and i will be working with this and add all the info that we recolect in this forum.

Thanks so much for your help and sorry for errors in the topic related to my lenguage that is not english.

Right now we need a way to make or repack the BIG with the modifications (Right now is possible to extract then) and later gonna see the problem with the SDAT.

Again i will be working with the executable maybe to invalidate the use of SDATA and make that the game look just for the .BIG file instead of sdata first. But in that way there is the need to repack the changes on the BIG so any other help with this will be great.

Greetings
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-12T13:58:36+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

I did the script:
[http://aluigi.org/papers/bms/ea_big4.bms](http://aluigi.org/papers/bms/ea_big4.bms)

the problem is that the Electronic Arts compression is not supported in compress mode (only decompression) so the script can't be used for reimporting (all) the files.
## Post #5
- Username: IngPereira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2011 8:55 am
- Post datetime: 2011-11-13T11:29:27+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

Thanks for your help aluigi you are great with BMS, Is better to have a exact script just for fifa series (11,12) like you did it instead of using other tools (total cmd or big editor) maybe can help that the old latest beta of the Open source BIG Editor 0.58 that can open the big's but have errors in the decompression (Not like your great script) but can compress the BIG file i mean look like it have a great support in compression of the big files (EA Format)

Maybe in the code is any help in the compression but i know that we already can try to make the BIG repacked with os big editor using all the folders extracted from your script and saving in a format a little different that the used in fifa 12 because when i open a big of fifa 11 or 12 it dont have the Folder structure and we cannot extract the files that are in folders but we can extract the files on the root directory (Without directory) maybe is a big step because the files compressed that are maded by the os big editor (.BIG) have some differences in the fifa one.

Bad the SVN of OS Big editor just at [http://www.ppmsite.com](http://www.ppmsite.com) is not working for me there are some sources of that but maybe the website will be some time up. i think that final big can make the .BIG again but like CnC series maybe that work with fifa?

Thanks for your help aluigi and the others...
## Post #6
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-05-28T18:59:14+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

Is it working with .sdat file from heavy rain ?
Thanks
## Post #7
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-06-25T17:40:38+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

How can i repack some file back to sdat ?
## Post #8
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-06-25T22:11:53+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

Pkease
## Post #9
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2012-06-26T03:30:27+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

> Reply from xboxmaniac
>
> Is it working with .sdat file from heavy rain ?
Thanks
did it work with heavy rain?
## Post #10
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-06-26T05:53:03+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

I think is working.
I want repack sdat from driver SF.
## Post #11
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2012-06-26T08:03:41+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

> Reply from xboxmaniac
>
> I think is working.
I want repack sdat from driver SF.
nope it didn't work
## Post #12
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-06-26T13:50:30+00:00
- Post Title: DATA0.BIG FIFA 2011 [PS3] Finally but. SDAT Cracked DL!

So, i cant repack some file back to sdat ? 
It must be some way how repack files.
