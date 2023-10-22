## Post #1
- Username: prn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 02, 2003 6:19 am
- Post datetime: 2003-08-01T22:30:51+00:00
- Post Title: Error Running on WinXP

hi there

i got an error message when i try to run program on my computer  

my system running winxp sp1, cpu and athlon xp 1800+

error message:

Run-time error '-2147023782 (8007045a)':

Automation error
A dynamic link library (DLL) initialization routine failed.

what can i do? i had exactly these error on my other system that
running winxp (without service pack), but whit same hardware configuration. i think this error must be for VB5 runtime?!

plz help me, best regards, pRn
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-02T06:18:54+00:00
- Post Title: Error Running on WinXP

Strange , it works on my XP installs. 

Has anyone else got a clue? Post it here!
## Post #3
- Username: prn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 02, 2003 6:19 am
- Post datetime: 2003-08-02T21:43:10+00:00
- Post Title: Error Running on WinXP

hi again!

i have two computers with same configuration, one of them
has winxp corporate without SP1

and the other with winxp pro SP1 corporate edition, and the program
failes to run on bouth of them! with same prompt (see it at previous post)

i forgot to say i try to install MultiEX Commander on my win98se as well, but the program failes to run with prompt other than previous post.
(i forgot what it says!!)

plz help me as soon as possible                            thanx for your help
                                                                                          bye
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-03T08:03:00+00:00
- Post Title: Error Running on WinXP

Well, you can try this config file, perhaps it will let you run now. 

[http://www.xentax.com/downloads/multiex/source/user.cfg](http://www.xentax.com/downloads/multiex/source/user.cfg)

Overwrite the user.cfg file in the Multiex/Data/Config directory and run again. 

Secondly, please examine the MultiEx/Data/Config directory:
Do you see dl.tmp, web.mrf or webversion.mvn in thtat directory?
You MUST see mc3238.mex, mc.mrf and user.cfg. 

Thirdly, is there a web.log in the MultiEx/Data directory? Please show it here. (Open it with notepad)

Finally, create a shortcut to mc32.exe (in the multiex directory) and add to the commandline " -debug" 
(so you run it like "mc32.exe -debug") This will create a debug.log file in the MultiEx/Data directory. Please also show that one here. 

Greetz, 
Michael
## Post #5
- Username: prn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 02, 2003 6:19 am
- Post datetime: 2003-08-03T22:45:55+00:00
- Post Title: Error Running on WinXP

hi and thanx for your help Mr.Mouse! (dear Michael)

first: i copied user.cfg in program config dir (but not overwrite
because there was no file with this name, there is one file that
is: mc.mrf 

second: just mc.mrf is present!   and the others are absent!!

third: no, the file that you said (web.log)  is not in data directory! ????

and finaly i do a shortcut with cmd line -debug and nothing happened!
just an old prompt i wrote in previous post

i have downloaded your program 2 times, and installed it 4 times
but nothing changed, what can i do?

at last exkuz me 4 my bad english!            i'll be wait for your help, bye
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-04T08:28:05+00:00
- Post Title: Error Running on WinXP

I have heard the error you have may also be due to the version of MDAC on your computers. look it up on [http://www.microsoft.com](http://www.microsoft.com) 

Are you connected to the internet when you start the program?
If not, please do it it one time. Connect to the internet, then start the program. See if it helps. If it does, go to options and disable the "Get formats from web" option. 

You can also try it on your w98 machine, and use the WORKAROUNF FOR WINDOWS 98 option look esewhere on this forum to do that)

With the debug option, there is no debug.log file ? Please look for it. If it is not there, then the program has a problem running very very early in the startup process.
## Post #7
- Username: prn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 02, 2003 6:19 am
- Post datetime: 2003-08-05T05:50:06+00:00
- Post Title: Error Running on WinXP

hi
trying to run program when i'm online... work in progress!!
please wait... shit, just an old prompt!

no! debug.log no found. i think my problem is very serious
i can do nothing, but, if anyone can send the installed program from
his computer to me   maybe it can solve problem

there is one more thing, and it's: i installed proggy on my win98se
but the files you said on previus post was not created on win98se installs?!
please help me, i need your program (multiex commander) seriously!
i'm a mod creator (graphic designer) with a little of software exprience
please mail me as soon as you find out! 
                                                                           best regards, pRn
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-05T07:22:38+00:00
- Post Title: Error Running on WinXP

You can try to install the vbruntime dll's, 
[@microsoft](http://support.microsoft.com/default.aspx?scid=http://support.microsoft.com:80/support/kb/articles/q192/4/61.asp&NoWebContent=1)
but they should have been installed by MultiEx Commander. 
I'm running out of options here. Installing someone else's install will not do the trick. The problem is much more fundamental than that, and besides, you will miss the dll's installed in the windows/sys32 directory. 
I would like to help you out, but as I do not have the possibility to work on your machines, I don't know how to help. 

When it installs (setup.exe),does it say anything? Like it wants to overwrite system files or something? And if so, do you select yes?

If you have security software or anti-virus software running, try to temporarily disable it and run MC again.
## Post #9
- Username: prn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 02, 2003 6:19 am
- Post datetime: 2003-08-06T22:16:28+00:00
- Post Title: Error Running on WinXP

hi and thanx 4 your friendly support   
because of my work, i'm very busy at now, i'm try your steps before
any posts, plz excuz me 4 the way i'm LAZY!!
kuz of my bad english, i can't say very very big "THANK YOU!"
just exkuz me.
i forgot to say, i used dr. web 4.29c on my machine, disabling
this may solve problem, finaly, please check my topic if you have time
to help me!
by the way, in MC installation, the program show's no prompt 4
overwriting or such! and everything sounds OK, but the prog
failes to start with prompt that i've said in previous post.
i hope this topic can help you for better MultiEX Commander.
                                                                       sincerely yours, bye
                                                                                  parviz (pRn)
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-06T23:33:20+00:00
- Post Title: Error Running on WinXP

Nope, I installed your Dr.Web and my MultiEx Commander is still working on XP. I can't help you out.
## Post #11
- Username: prn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 02, 2003 6:19 am
- Post datetime: 2003-08-16T22:39:09+00:00
- Post Title: Error Running on WinXP

yeeeeeeeeeeha

finaly i got it, the error accures when i install MultiEX on VB installed
winxp!    

i don't know why it's! but when i destroy my windows and installed new one, and then install multiEX, everything runs OK!

thanx a lot for your helps, i have tried to import some resources to
DFBHD and program works NICE! very GOOOOOD!!

have a good time, bye with best and best regards
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-08-17T09:32:23+00:00
- Post Title: Error Running on WinXP

Excellent!   

"And another satisfied customer leaves the building" 

Ok, if other people have the same problem, this is what worked :
Install it on a clean Windows, with no VB installed. Yes, that is quite a surprise. It worked for PRN!

By the way, I have new XP setup version in this thread:
[viewtopic.php?p=2423#2423](http://forum.xentax.com/viewtopic.php?p=2423#2423)

Perhaps that will remove any compatibility issues. 

Thanks prn, for posting again!
## Post #13
- Username: alcatelgod
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Dec 17, 2003 1:30 am
- Post datetime: 2004-05-01T08:33:12+00:00
- Post Title: Error Running on WinXP

SHIT!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

Don't RUN!!! Out of Memory!!!!!    200MB   free!!!!!!!!


PLEASE HELP!!!!
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-01T08:53:25+00:00
- Post Title: Error Running on WinXP

alcatelgod, you are impossible to work with. 

What does not work? The version that is offered in this thread? 
Naturally, it is an old one and you should get the latest version. 
Stop posting in old threads. 

Also, you're giving again way too little information on the error you encounter. I cannot do anything with such a posting.

As a consequence I will close this thread.
