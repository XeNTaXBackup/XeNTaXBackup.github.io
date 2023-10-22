## Post #1
- Username: alcatelgod
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Dec 17, 2003 1:30 am
- Post datetime: 2003-12-16T17:37:02+00:00
- Post Title: BloodRayne English.POD extractor/inserts help me! please

Hungarian Language(I' am sorry):

Ki tud betömörítő modult a BloodRayne-hez PLEASE HELP ME!!!!!!!
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-16T23:37:58+00:00
- Post Title: BloodRayne English.POD extractor/inserts help me! please

POD huh? Hmm, I guess we can look into it in due time. Sorry , no hungarian. I speak Dutch, German, a little French, my regional dialect and English, but Hungarian,  that's the one language I don't speak.
## Post #3
- Username: alcatelgod
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Dec 17, 2003 1:30 am
- Post datetime: 2003-12-17T17:49:02+00:00
- Post Title: BloodRayne English.POD extractor/inserts help me! please

Been Insert module vagy or plugin  the get sotware???? Please healp


SORRY  the Hungarian language
## Post #4
- Username: alcatelgod
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Dec 17, 2003 1:30 am
- Post datetime: 2003-12-17T17:52:08+00:00
- Post Title: BloodRayne English.POD extractor/inserts help me! please

*.POD extractor and Insert sotware or plugin for multi ex commander PLEASE HELP  


HEHE nem tudtok magyarúl:)))) faszszopó köcsögök:))) Na de ne humorizáljunk:)))
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-17T23:45:00+00:00
- Post Title: BloodRayne English.POD extractor/inserts help me! please

Yes, yes, I am helping you. I will finish a MultiEx Commander script for you to use.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-18T00:36:44+00:00
- Post Title: BloodRayne English.POD extractor/inserts help me! please

As a matter of fact. here it is:

You can compile this script in MexScriptor, which comes with MultiEx Commander. You must then start up MultiEx Commander and use it on a *.POD file with the "Use Custom BSM on..." option. Follow the instructions. 

Alternatively, just download this updated [mc.mrf](http://www.xentax.com/downloads/multiex/mc.MRF) file and overwrite the one in this path ..\MultiEx Commander\data\config\mc.mrf . You can then select "BloodRayne *.POD" files from within MultiEx Commander. Guess what, you can replace stuff too (Import function)!   

> Reply from The script
>
> 
ImpType StandardTail ;
IDString 0 POD3 ;
Set D Long 88 ;
GoTo D 0 ;
Get FNU Long 0 ;
Set D Long 264 ;
GoTo D 0 ;
Get TP Long 0 ;
Set DE Long FNU ;
Math DE *= 20 ;
Math DE += TP ;
For T = 1 to FNU ;
GoTo TP 0 ;
Get CO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos TP 0 ;
Math TP += 8 ;
Set DZ Long DE ;
Math DZ += CO ;
GoTo DZ 0 ;
Get FN String 0 ;
Log FN FO FS FOO FSO ;
Next T ;
## Post #7
- Username: alcatelgod
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Dec 17, 2003 1:30 am
- Post datetime: 2003-12-18T17:24:48+00:00
- Post Title: BloodRayne English.POD extractor/inserts help me! please

thank ye  
Thank ye the help        





 THANK YOU
## Post #8
- Username: Madeline
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 09, 2006 12:01 pm
- Post datetime: 2006-11-10T01:59:50+00:00
- Post Title: BloodRayne English.POD extractor/inserts help me! please

I replaced the original file with that file and now the program won't open at all. I was hoping it would fix this problem with the invalid string for bloodrayne 2 files.
