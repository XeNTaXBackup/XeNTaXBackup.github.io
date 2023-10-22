## Post #1
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-03T18:59:45+00:00
- Post Title: Return to Zork PRJ File

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-04T03:14:41+00:00
- Post Title: Return to Zork PRJ File

This seems to be a recursive archive from what I can tell and is not easy to support in quickbms.
I think I can write an extractor that will skip over some folders and get the files with names.
ill post my progress here soon.

```
#locate first header
#goto 0x8f3950 #un comment this to get bye the 1 bad file
findloc RES_START string "DATA"
goto RES_START
savepos RES_START
math FILES += 2439

for i = 0 < FILES
getdstring DATA 0x5
endian BIG
get SIZE short
endian small
getdstring HARD 0x17
getdstring FOLDER 0x10
getdstring FILE 0x10
string FOLDER += \
string FOLDER += FILE
set NAME string FOLDER
savepos OFFSET
log NAME OFFSET SIZE
findloc RES_START string "DATA"
goto RES_START

next i

```

This is the best I could do.
## Post #3
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-04T14:08:27+00:00
- Post Title: Return to Zork PRJ File

Thanks very much. I don't know much about programming. How do I compile a program out of what you posted?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-04T19:15:59+00:00
- Post Title: Return to Zork PRJ File

Just save what I put in the code tags as a new text document and change the extension to .bms
then just run this program and follow the instructions.
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
after you run it once it will get stuck on a folder called p\ something just delete the first # where it says to un comment and run the script again.
## Post #5
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-04T22:45:53+00:00
- Post Title: Return to Zork PRJ File

Thank you very much for that. The program worked for as long as it could. 

Did you have an error at hex
008f3943?

The program errored there for some reason when going through the file and will not continue past that point. Otherwise it worked great up until then.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-04T22:47:12+00:00
- Post Title: Return to Zork PRJ File

Yes it has an error there because one of the files contains the word DATA
just un comment this line
#goto 0x8f3950 #un comment this to get bye the 1 bad file
so it looks like
goto 0x8f3950 #un comment this to get bye the 1 bad file
and it will get the rest of the files.
## Post #7
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2009-06-05T10:48:22+00:00
- Post Title: Return to Zork PRJ File

Return to Zork uses the MADE engine and is supported by ScummVM:
[http://scummvm.svn.sourceforge.net/view ... ines/made/](http://scummvm.svn.sourceforge.net/viewvc/scummvm/scummvm/trunk/engines/made/)
There's probably some code to read *.prj files in there

-Darkstar
## Post #8
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-05T23:25:56+00:00
- Post Title: Return to Zork PRJ File

Thanks.

There appears to be some code here.

[http://scummvm.svn.sourceforge.net/view ... ines/made/](http://scummvm.svn.sourceforge.net/viewvc/scummvm/scummvm/trunk/engines/made/)

But, there's not a viewer or anything outside of the scummvm program. I really am clueless about programming -- anyone easily made something out of that for reading the FLE or ANM files?

Thanks
Andy
## Post #9
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-07T07:23:07+00:00
- Post Title: Return to Zork PRJ File

I talked to someone who worked with the SCUMM program. They didn't have time to make anything, but said that this should be the code for the images:

[http://scummvm.svn.sourceforge.net/view ... iew=markup](http://scummvm.svn.sourceforge.net/viewvc/scummvm/scummvm/trunk/engines/made/graphics.cpp?revision=40867&view=markup)

(see previous link... graphics.h might be needed to)
## Post #10
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-20T06:11:57+00:00
- Post Title: Return to Zork PRJ File

chrrox, I think there's an error in this program.

Some files give out only 0 bytes of data, while others are clipped at the end.

Here are some examples.
I included both the raw hex from the archive, as well as how the program errorenously outputs these files. I only noticed this from the text output, but it might effect the non-text files as well.  (I am not sure if the 2E00 at the end of the files is part of that file, or belongs to the next one)



For the Inn one, it gives a completely blank file when it should give something.
Hellhounds, it cuts off the end of the file, this seems to be a very common problem.
Then with FOLLY, this adds to the file parts from the next file, thus nullifying the file that follows.
[sample.rar](https://xentaxbackup.github.io/file/2145_sample.rar)
## Post #11
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-12-05T01:11:39+00:00
- Post Title: Return to Zork PRJ File

I managed to figure out what was wrong with the BMS code and I have presented the revised code here (this actually properly works as compared to the previously released code) 

```
#goto 0x8f3950 #un comment this to get bye the 1 bad file (DISC VER)
findloc RES_START string "DATA"
goto RES_START
savepos RES_START
math FILES += 10000

for i = 0 < FILES

getdstring DATA 0x4
get SIZE long
math SIZE -= 54
getdstring HARD 0x16
getdstring FOLDER 0x10
getdstring FILE 0x10
string FOLDER += -
string FOLDER += FILE
set NAME string FOLDER
savepos OFFSET
log NAME OFFSET SIZE
findloc RES_START string "DATA"
goto RES_START

next i
```
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-12-05T01:49:24+00:00
- Post Title: Return to Zork PRJ File

just do math SIZE -= 36
## Post #13
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-12-05T15:39:11+00:00
- Post Title: Return to Zork PRJ File

Thanks for that. I have edited my code in my post above and that code seems to work perfectly now on the .prj files from the following versions of Return to Zork:

Dos-Floppy, Dos-Disc, Dos-Demo, Mac and Playstation.
I imagine it also works for other games that use the made engine.

The only thing is for the Dos-Floppy version ONLY, after running the program the first one, one must use the "goto" function and run it again a second time for the remainder of the file.
