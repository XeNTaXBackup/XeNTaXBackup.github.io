## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-11T19:16:50+00:00
- Post Title: PROJECT: CODENAME Eureka

WATTO, any others that wish to participate and me can use this thread to discuss ways to create the support program, codename Eureka, that enables the innocent user of Game Resource Archivers to figure out newly encountered GRAs. 

Stuff that should be discussed:

- strategies of the program to identify whole formats of archives or parts of formats of archives
- routines needed to accomplish subtasks
- methods to ensure easy additions of new format specifications
- known file identity tags to scan for specific file types in an archive
- ways to identify files that don't have readily distuigishable tags
- ways to locate compressed files and if possible recognize the format used
- support excutables or inclusion of decompression/encyption code to be used on matched formats

I think this kind of discussion and research may help us reach a common strategy and approach, before we even have to code a single line!
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-11T20:11:36+00:00
- Post Title: PROJECT: CODENAME Eureka

LOL, thats funny, for my coding site, i just did a forum.  Its a little more, specific than yours though. 

[http://dl748.com/forums/](http://dl748.com/forums/)

[EDIT]I pretty much know the languages that are listed in there[/EDIT]
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-11T20:50:02+00:00
- Post Title: PROJECT: CODENAME Eureka

Make that A LOT more specified   . 

The purpose of the Code Talk forum is to be able to separate the talk about code (MultiEx related) on this forum from the other subjects, and to offer a place were MultiEx related projects can be discussed.
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-11T20:52:36+00:00
- Post Title: PROJECT: CODENAME Eureka

Yeah, I know, I like to talk about a lot of things about coding, including ideas.
## Post #5
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2004-08-12T04:22:41+00:00
- Post Title: PROJECT: CODENAME Eureka

> Reply from Rahly
>
> 
[EDIT]I pretty much know the languages that are listed in there[/EDIT]
Judging by that list, you may like to learn [Python](http://www.python.org). It's a fun language that's easy to pick up, versatile, and powerful.
## Post #6
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-12T09:53:33+00:00
- Post Title: PROJECT: CODENAME Eureka

> Reply from Captain
>
> Rahly wrote:
[EDIT]I pretty much know the languages that are listed in there[/EDIT]
Judging by that list, you may like to learn Python. It's a fun language that's easy to pick up, versatile, and powerful.

I know that already, I said, I know pretty much all the languages there, I didn't say those were the only languages I know.  I also know COBOL and ADA and BrainF*ck, and a bunch more.
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T08:10:00+00:00
- Post Title: PROJECT: CODENAME Eureka

Well, anyway, let's stay on topic in this thread.   

I think one of the key issues in creating Eureka is the define how it should operate. 

The first thing it should do in my opinion is check whether it has encountered an archive format it already knows. Let's call this the Current_Match process. It would be advisable to create the program in such a way that we can feed it additional known format identity tags (FIT). These FITs can be seen as a list of things Eureka has to confirm present in the archive. The format of a FIT may be very easy, all you might need is a list of strings or bytes that have the following structure:

FIT-structure:

[0] : Type - What type of data is Eureka to load from the file? (e.g. string, null-string, word, dword etc.) 
[1] : Offset - Where in the file is Eureka to load this variable?
[2] : Match - The variable of type Type loaded at offset Offset should match this variable

In VB you can easily convert strings to words, to bytes, to dwords etc. if you define a array of strings. Thus, you can easily make some kind of tab-delimited text file in which you put these components. 

For instance, you can start a line with:
1. Archive Format Name (e.g. "Painkiller .PAK format")
2. Archive Format Index (if we create a new list of locations of multiex scripts and plugins)
3. Number of criteria to match (and that follow, that Eureka has to load)
4-XX - The three-string entries for each criteria. 

When all criteria are met Eureka could declare the archive known and try to open it. When a lot, but not all criteria are met, Eureka could declare it "The format resembles XXXX format for NN %". 

If too little criteria are met, Phase 2 should start, identifying patterns, files etc in the archive. But I think it best if we're sure of the principle of Current_Match phase first, before we move on.
## Post #8
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-13T10:03:52+00:00
- Post Title: PROJECT: CODENAME Eureka

I have some idea, but I hesitate to share, only cuz that would get me involved, and it would get me distracted from the plugin manager.   I'd mostly start writing code for it, to test the theory.
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T10:19:18+00:00
- Post Title: PROJECT: CODENAME Eureka

You can always share your views without getting involved. You don't have to start writing code! This thread is usefull for discussion, not code. We can all agree on an approach and then only some will actually code it. Or someone (like WATTO or me) will make the decision, based on the discussion and start to code, limiting further discussion about that particular part.
## Post #10
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-13T11:21:18+00:00
- Post Title: PROJECT: CODENAME Eureka

I know that .  But its just the kind of person I am, though.

Anyway, I'm thinking of a drag and drop method.  Drop large batches of files, like "everything" in the data directory.  And file pattern similiarities between them, like the first 4 bytes in these group of files are all the same, or for these other group of files at position $22 looks like it represents the file size,  or the filesize - $22(Maybe $22 is a header size).  Also have different methods of checking that the user can select.  like "Check all known" "Check for simple patterns" "Thorough check of files list (warning: this option can take a while, especially if the files are large)", "Try raw compression schemes"
## Post #11
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-13T14:38:14+00:00
- Post Title: PROJECT: CODENAME Eureka

OK, these are the things I can think up at the moment, so bear with me 

Filename searches shouldn't be too difficult to do - we should consider something a filename if it contains at least 5 characters in the English character set - this gets around the format types that include 4-byte extension strings or tags (i call them chunk-based archives). We could also confirm the presence of a filename by locating a . character in it, but this is not always the case.

Once we find a filename, we should first try the bytes before it for something which may provide the filename size - this will either be a 1-byte, 2-byte, or a 4-byte value. Failing this, we should then read through until the first null, making sure to check each character as we go, because if a non-english character appears before the null, it probably isn't a file name.

Once we have a file name confirmed, we should find the next filename. This will help us discover an important fundamental of the archives - the entry size for each file. Alternatively, it will also tell us if there is a separate filename directory, usually constructed of all the filenames separated by a single null character - opviously this is the case if the second filename starts directly after the first.

If we can find out the entry size, we should then check by skipping forward those X bytes and check that the beginning of the filename starts at this position - if not then we are probably dealing with a variable-length entry size, usually brought about by allowing filenames of any length.

Anyway, from there we should try to figure out the rest of the fields in each entry. Knowing that most fields are 4-byte fields, we should start with that and see what patterns we can find. We should look for patterns of increasing value first, which would indicate either a File ID field or a File Offset field. Once we determine the File Offset field, the next logical step is to look for a File Size field.

Where we go from here is to be determined. We could go to each offset and look for a known file header, or even any string of 4-bytes that might indicate a header. We could also try to pick out whether the files are compressed by searching in the entries for a field which is always bigger than the File Size. We should also look for a pointer either at the start or the end of the archive which points to the directory, and a numFiles field.


The things to look out for...
1. Archives that are chunk-based (ie archives that do not have a directory, rather they have a format like header-file-header-file-etc. for the entire file, thus the files are stored in chunks.)
2. Variable-length entries will be a pain
3. Long file headers may interfere with the determination of a filename
4. Similarly, if directories are stored in the archive (ie if it contains a nested directory structure) then it will be quite difficult to determine the structure of the archive, and the directory names will interfere with filename detection


Thats all I can think of at this point in time, feel free to critique.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-13T14:55:45+00:00
- Post Title: PROJECT: CODENAME Eureka

Here is a list of the many different fields that I have encountered, ranked approximately by their level of occurrance (with the most common fields at the top). Add some more if you find any I have missed.

Data Offset
Compressed File Size (also includes the File Size field in non-compressed archives)
Number Of Files
Archive Header (usually 4-byte, but sometimes 2, 4, 6, 8, or a really large number)
Archive Version (sometimes as a number, sometimes as a string)
Filename
Filename Fillers (usually 0-3 bytes, to pad the file entries to multiples of 4 bytes)
Filename Offset
Filename Length
File Tag / Extension (a 4-byte String representing the files extension)
Archive Size
Header Size
File Data Size (total size of all file data)
Directory Size / First File Offset (typically the same thing)
Nested Directory Offset
Filename Directory Offset
Uncompressed File Size
Number Of Directories
File Entry Size
Compression Type
Archive Name
Timestamp (as a 4-byte millisecond count from 1/1/1970)
Checksum (usually 8-bytes)
Unicode Filename
Archive Creation Year (as a string eg "2002")


Also, there are quite a few archives that use fixed padding sizes for directory entries, files, and anything else. Common padding sizes I have found are 2048, 512, 128, 64, 32, and 4. The 4 padding is most used in file entries in the directory, used when an arbitary-length filename is allowed, where each filename is padded to a multiple of 4 bytes by adding 0-3 nulls.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T15:01:57+00:00
- Post Title: PROJECT: CODENAME Eureka

Okay, well, we are now talking about Phase 2 of the identification process (skipping phase 1 I talked about: identifying known formats, the Current_Match function).   Do you agree with the approach I came up with for that?

About Phase 2, the identification of filenames I have done in 2000 with Mexscan. Here's a piece of the docs that came with it :

> Reply from mexscan.doc
>
> msSCFILEHEADER
--------------

Example log text:

;**** Header Scan Initiated ****
;17 >> C:\TOOLS\MC\BREAD.EXE >> DELTA 17 >> AL 20 >> F 15
;281 >> C:\TOOLS\MC\EDITOR.MCT >> DELTA 264 >> AL 19 >> F 14
;545 >> C:\TOOLS\MC\FILE.MKD >> DELTA 264 >> AL 21 >> F 5
;809 >> C:\TOOLS\MC\LFE.EXE >> DELTA 264 >> AL 22 >> F 16
;1073 >> C:\TOOLS\MC\MC.BAT >> DELTA 264 >> AL 23 >> F 11
;1337 >> C:\TOOLS\MC\MC.INI >> DELTA 264 >> AL 23 >> F 11
;1601 >> C:\TOOLS\MC\MC.PIF >> DELTA 264 >> AL 23 >> F 5
;1865 >> C:\TOOLS\MC\MCMAIN.EXE >> DELTA 264 >> AL 19 >> F 9
;2129 >> C:\TOOLS\MC\MCVIEW.EXE >> DELTA 264 >> AL 19 >> F 14
;2393 >> C:\TOOLS\MC\MULTIAD.EXE >> DELTA 264 >> AL 18 >> F 9
;2657 >> C:\TOOLS\MC\MULTIEX.EXE >> DELTA 264 >> AL 18 >> F 13
;2921 >> C:\TOOLS\MC\multiex.imp >> DELTA 264 >> AL 18 >> F 4
;3185 >> C:\TOOLS\MC\MULTIEX.INI >> DELTA 264 >> AL 18 >> F 13
;3449 >> C:\TOOLS\MC\multiex.lst >> DELTA 264 >> AL 18 >> F 9
;3713 >> C:\TOOLS\MC\README.1ST >> DELTA 264 >> AL 19 >> F 9
;3977 >> C:\TOOLS\MC\selected.mkd >> DELTA 264 >> AL 17 >> F 8
;4241 >> C:\TOOLS\MC\TREAD.EXE >> DELTA 264 >> AL 20 >> F 15
;!! Possible HEADER at approx. 17, 16 files 264 spacing !!
;Most probable header : offset 374456, at least 48 files.
;=-*** Header Scan Ended ***-=

The log said it initiated the header scan and then reports any 
filename found: this has the following format:

<offset> >>
<text> >>
DELTA <number of bytes distance from previous reported filename> >>
AL <percentage of non-letter character>
F <average frequency of all the different characters in the text>

When MEXSCAN sees that the DELTA is the same it counts this as a
possible header, and counts the number of possible files in the 
datafile, until it finds a possible filename that has a different 
DELTA. It then gives a summary of the previous header:
;!! Possible HEADER at approx. 17, 16 files 264 spacing !!
When the whole file has been scanned it will give the most probable
header(containing filenames) found and ends by saying that the scan 
is done.

What it did was look for strings of Egyptian characters (I think that's the type we use in the Western world languages if I remember correctly from my history lessons) for at least a set amount of length (probably 8 or something) and calculate the percentage of non-Egyptian characters (e.g. /, \, . ). If below a set percentage it would consider it a valid text string, only when the percentage of each different character in the string would also be below a set percentage (to avoid reading strings that are actually just 1 specific character repeated multiple times (think of graphic files and you know what it was trying to avoid!   ). It would remember where the string began and continue the search. It would stumble upon a second valid string and substract the position of the previous string with the new one to get a Delta. It would then search on for the next, and start comparing deltas. If they would be equal it would start to count them as header entries. This would stop whenever it would encounter a string that showed a different delta. Then it would note down the number of possible entries, the spacing, and the offset of the first "filename". Search would continue, so it might note down multiple possible headers. 

The problem with this approach was that pieces of text might be something completely different (game related) but still at regular intervals. The strong thing we should implement would have to be more checking to see if someting is really a filename, and if it is really a header. Perhaps you're right to say it should do this immediately when ever it find such a string. I think thought, that the filenamestring identification code needs to be spot-on first.

[EDIT]Look above for the text in bold.
## Post #14
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-13T15:10:59+00:00
- Post Title: PROJECT: CODENAME Eureka

this is similar to the unix "strings" command.

[http://linux.about.com/library/cmd/blcmdl_strings.htm](http://linux.about.com/library/cmd/blcmdl_strings.htm)
## Post #15
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-13T15:37:38+00:00
- Post Title: PROJECT: CODENAME Eureka

Sorry, I wasn't really going by phases or anything, thats just a lot of random dribble that I thought about when you first mentioned the project to me.

Anyway, I have now read what you posted about phase 1, and I think I see what you are trying to say - you think we should define some kind of standard system for checking files against known types? For example, you would like to develop another mexscript-like system where we check for certain aspects in a file and, if matching, present the probability that the file is of a type we already know. Is that what you mean?

If so, I think that is probably the way to go, or maybe we can simply have 2 buttons for the user so that they can perform the 2 different techniques individually from each other. I can see your phase 1 idea being pretty good because we can keep it updated with the latest formats using a plugin-like interface much like you do now in your MexCom, or like my Game Extractor.

So yes, this is a good idea, and wouldn't be too difficult to implement.

And I agree completely with the filename issue you mentioned, and I can see we will need to think very carefully about the technique we use to verify whether it is a valid filename. Here are some things I can see at the moment...

1. It must be at least 5 characters long, and less than 256 characters long
2. If should preferably contain a dot or a directory slash, this would greatly improve the probability of a filename
3. It must contain some identifier of the filename length, either by a trailing null or a length field before the name. If looking for a null, it must not encounter any non-English characters before it.

We can also look for a drive letter or a directory slash as the first character - some archives store filenames with them included.


Just throwing around ideas.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #16
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-13T16:24:11+00:00
- Post Title: 

This could potentially be a bigger project than Mexcom, as in the future, it will prolly "merge" with mexcom.

Here is a small outline I think it might work.

1) Try all known format (plugin call(IsArchive) or by mexscript)

2) Search Archive for known archive formats (archive in an archive)

3) Attempt to uncompress file if its a known compression type

4) search file for known nonarchive file types (picture files, word processing files, compressed files)

5) attempt to look for pattern recognition

5 shouldn't be used to actually TRY to unarchive, but rather, email us, the developers on what it found in the archive.

back on this "new script", i'm thinking about maybe a specialized RegEx (Regular Expression) language for it.
## Post #17
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-13T16:39:44+00:00
- Post Title: 

Question: What do you do about split archives?  Like in Prince of Persia, they have the index in one file, and binary data in the other file?
## Post #18
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2004-08-13T18:12:27+00:00
- Post Title: 

> Reply from friendsofwatto
>
> OK, these are the things I can think up at the moment, so bear with me 

Filename searches shouldn't be too difficult to do - we should consider something a filename if it contains at least 5 characters in the English character set - this gets around the format types that include 4-byte extension strings or tags (i call them chunk-based archives). We could also confirm the presence of a filename by locating a . character in it, but this is not always the case.

Once we find a filename, we should first try the bytes before it for something which may provide the filename size - this will either be a 1-byte, 2-byte, or a 4-byte value. Failing this, we should then read through until the first null, making sure to check each character as we go, because if a non-english character appears before the null, it probably isn't a file name.

Once we have a file name confirmed, we should find the next filename. This will help us discover an important fundamental of the archives - the entry size for each file. Alternatively, it will also tell us if there is a separate filename directory, usually constructed of all the filenames separated by a single null character - opviously this is the case if the second filename starts directly after the first.

If we can find out the entry size, we should then check by skipping forward those X bytes and check that the beginning of the filename starts at this position - if not then we are probably dealing with a variable-length entry size, usually brought about by allowing filenames of any length.

Anyway, from there we should try to figure out the rest of the fields in each entry. Knowing that most fields are 4-byte fields, we should start with that and see what patterns we can find. We should look for patterns of increasing value first, which would indicate either a File ID field or a File Offset field. Once we determine the File Offset field, the next logical step is to look for a File Size field.

Where we go from here is to be determined. We could go to each offset and look for a known file header, or even any string of 4-bytes that might indicate a header. We could also try to pick out whether the files are compressed by searching in the entries for a field which is always bigger than the File Size. We should also look for a pointer either at the start or the end of the archive which points to the directory, and a numFiles field.


The things to look out for...
1. Archives that are chunk-based (ie archives that do not have a directory, rather they have a format like header-file-header-file-etc. for the entire file, thus the files are stored in chunks.)
2. Variable-length entries will be a pain
3. Long file headers may interfere with the determination of a filename
4. Similarly, if directories are stored in the archive (ie if it contains a nested directory structure) then it will be quite difficult to determine the structure of the archive, and the directory names will interfere with filename detection


Thats all I can think of at this point in time, feel free to critique.

WATTO
watto@watto.org
http://www.watto.org
I agree. This is an approach I would use. It wouldn't be suitable for all archives around, but would fill in some significant blanks in most of them.

It's probably impossible to automate the entire process, so I think the best thing would be to create a semi-automatic hex-editor with some specified controls to easily find patterns, while the user and his superior brain figures out how the general structure works. The user would then use different controls to feed the app that knowledge, and the tool spits out a script.

I would suggest a fault-tolerant interface in which the user can instantly see the result of his actions. By this I mean that whenever the user changes something in the test-structure he's creating, the tool can immediately perform a scan on the file we're researching, and show the result in a results-windows. One window would hold the directory and filename structure, as interpreted by the tool. When clicking on a filename in that structure, if the tool has enough knowledge of the archive type, the tool immediately shows the contents of that file, in hex or whatever format the user chooses. I think that would at least speed up the discovery process an order of magnitude.

For Mr.Mouse's idea I would suggest an object oriented approach where, for each archive type, a specific class is derived from a main ArchiveSignature class, and has specific implementations of methods for detection, analysis, and other stuff. I don't know if this can be done in VB, but if it's possible it would keep things tidy. This way, the tool can just loop through the available classes, and apply them to the archive(s) we're investigating.
## Post #19
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T18:22:01+00:00
- Post Title: 

> Reply from Rahly
>
> this is similar to the unix "strings" command.

http://linux.about.com/library/cmd/blcmdl_strings.htm

Similar but not the same. I don't think the two use the same approach in identifying a valid string.   

@PHASE 1 

Although there may be two buttons for starting phase 1 or phase 2, I don't think it would make much sense to offer it. I think Phase 1 should just precede Phase 2. If an archive is known to the program, I need not start Phase 2, right? Likewise, suppose a user clicks to start Phase 2 - which may have some settings to set, as Rahly sugggests, but the archive format if already known? If Phase 1 would not precede Phase 2, Phase 2 would be initalized, taking quite some time and trying to figure out something Phase 1 could have told it beforehand. 

Yes, I do suggest some kind of very easy script to go through a file, looking for clues that define it as a certain format. It must be able to compare almost anything anywhere in the fiel with what we ask it to compare with. Besides that, it must also be able to perform specific tasks, such as follow a route (go to offset A, read the long there, try to jump to it....SUCCES? Good, next criterium - FAILURE ? - Not the known format).
This jumping around is necessary, because many formats don't use clear identity tags whatsoever, so you must try to follow the rout (e.g. Get resource offset, try to jump to it, Get Resource size, try to virtualy extract it, OOPS! Resource larger than actual Archive? - FAILURE! - Not the known format etc etc). Perhaps something other than a script, but a set of commands that we can easily use to code additional formats. 

[EDIT]@Captain: That would be nice, to do it with classes, yet it would require to create new executables each time you wish to add a new check, would it not? I'm trying to avoid that.
But indeed, it will be a big challenge to get the tool to be userfriendly. We must make sure however, not to create a vastly complicated tool that will put off those I personally would like to see it use: anybody. We may offer an advanced version for those with the superior brains you describe, but a stripped down, but smart version would certainly be a good thing. 
It should not be for coders. Thus, the interface should not be for coders either. And that's not always easy.
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T18:35:42+00:00
- Post Title: 

> Reply from Rahly
>
> back on this "new script", i'm thinking about maybe a specialized RegEx (Regular Expression) language for it.

Enlighten me, please, there's some terminology I haven't heard, don't forget, I'm your basic hobbycoder.   

> Reply from Rahly
>
> This could potentially be a bigger project than Mexcom, as in the future, it will prolly "merge" with mexcom.

Here is a small outline I think it might work.

1) Try all known format (plugin call(IsArchive) or by mexscript)

2) Search Archive for known archive formats (archive in an archive)

3) Attempt to uncompress file if its a known compression type

4) search file for known nonarchive file types (picture files, word processing files, compressed files)

5) attempt to look for pattern recognition

5 shouldn't be used to actually TRY to unarchive, but rather, email us, the developers on what it found in the archive.

I agree with the latter, but it may be an option for the user to try at their own risk (or people who know what they're doing, I'm thinking along the lines of Captain's suggestions, and my own of havind an Advanced mode or version). 
Your roadmap to Total Archive Demystification is one I imagine as well.
## Post #21
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-13T19:52:08+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> That would be nice, to do it with classes, yet it would require to create new executables each time you wish to add a new check, would it not? I'm trying to avoid that.
But indeed, it will be a big challenge to get the tool to be userfriendly. We must make sure however, not to create a vastly complicated tool that will put off those I personally would like to see it use: anybody. We may offer an advanced version for those with the superior brains you describe, but a stripped down, but smart version would certainly be a good thing. 
It should not be for coders. Thus, the interface should not be for coders either. And that's not always easy.

It could be something as simple as making our own classable scripting engine, or use a popular modular one that can be imported in.  That way they just download a "compiled" script and it auto imports it.  Or even better, just download the script itself, and program compiles it as needed.

> Reply from Mr.Mouse
>
> Enlighten me, please, there's some terminology I haven't heard, don't forget, I'm your basic hobbycoder.

Regular Expressions are one liner that let you test for string validity.  It became really popular with perl and a lot of languages use a PCRE(Perl Compatible Regular Expression) or (Perl Compatible RegEx Engine) however you wanna say it, php, python, lots of other languages.  I'll show you some of the ones i've written

/\s*(.*?)\s*\=\s*(.*?)\s*$/

/(".*?"|.*?)(\s+|\Z)/

/^(.*?)(?:\s|\Z)(.*)$/

now i'll give you a few simple ones

string =~ /^:/

This means "does the string begin with a :" (true/false), you may think, oh.. wow.. so what?.. thats easy to write.  But Wait.

string =~ /^H\s+E\s+L.+L\s*O$/

whoa.... whats that?! its basically saying
"does the string begin with a H, followed by one or more spaces, followed by an E, followed by one or more spaces, followed by L, followed by one or more any character, followed by L, followed by Zero or more spaces, followed by O at the end of the line".  Try writing the code to parse that in one line .

H E L L O = True
H E L LO = True
H E LxL O = True
HxE L L O = False

A lot of programming utilities allow regex search expressions.  I'm just saying we could "adapt" one to our standards.  I had started one but it was only ment for * or ? wildcards in filenames.

> Reply from Mr. Mouse
>
> I agree with the latter, but it may be an option for the user to try at their own risk (or people who know what they're doing, I'm thinking along the lines of Captain's suggestions, and my own of havind an Advanced mode or version). 
Your roadmap to Total Archive Demystification is one I imagine as well.

I'm for this, i wrote a visual control for delphi, for hex editing, looks exactly like HexWorkshop (favorite hexeditor), it wouldn't be hard to convert it to an ActiveXControl to import into VB.  Although Its unfinished, as I only ment it for display purposes, i need to add highlighting and "editable".  I can give you screen shots of the control if you want.  Although I still would like a popup "Format Not Found, email data to developers?".
## Post #22
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T21:40:28+00:00
- Post Title: 

Yeah, there must be an option for users to send whatever log the program created after any run. 

Ah, now I understand the RegEx, though the syntax is something I had not seen before, but then again, I haven't looked. Captain's been bugging me for a long time :" Dammit man, you should get off your lazy ass and  learn Python!" and I reply : "Yes, man, you are right", but never get to it. Guess it's just because I have another schedule.   Captain's done a fab job on OpenMex, a project now cancelled, but showing good promise to replace MultiEx Commander. The amount of time to actually do such a thing was just too much to handle for him, and it's true, and that's what puts me off as well: having to rewrite everything in another language. 
Ok, so far for my excuses for not coding in 'better' languages.   

I see however the possibilities of creating or own Regular Expression set. 
The problem is that Eureka would have to perform very specific tasks, like those I mentioned before, before it could succesfully 'tag' an archive.
If you could offer Eureka a script to do that, that would ultimately not be unlike having Eureka compile a script first as it would compile it to tasks set by the commands of the script; ergo it might as well perform them instead of compiling them. Still, the question is in any case: what script to use? I could try an adapt the MexScript and make it perform tasks needed, and return the results. But that would interfere with or rely on 'legacy' code, that may not all be needed, and may not be what we want in a new program. Decisions, decisions..
## Post #23
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-10-01T17:32:24+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> having to rewrite everything in another language. 
Ok, so far for my excuses for not coding in 'better' languages.

Why not use .NET? You can use multiple programming languages in 1 application. Also, you don't need to create your own scripting language for plugins, .NET can import (and run) uncompiled code during runtime!
## Post #24
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-01T21:04:20+00:00
- Post Title: 

> Reply from Anonymous
>
> Mr.Mouse wrote:having to rewrite everything in another language. 
Ok, so far for my excuses for not coding in 'better' languages.  


Why not use .NET? You can use multiple programming languages in 1 application. Also, you don't need to create your own scripting language for plugins, .NET can import (and run) uncompiled code during runtime!

Thats not the same thing, .NET can import uncompiled .NET code, which is a byte code similar to java.  It cannot import readable languages such as pascal, c, c++, basic, etc etc etc etc.  You still need a compiler for that, like Visual Studio.  You've always been able to use multiple languages in one application.  I can compile a pascal unit down and import it into a c program, or vice versa.  The only true advantage for .NET would be its ability to run on multiple platforms.  Since PDAs are limited in memory and mexcom usually works with large files (archives), running on a PDA really isn't feasible.  The only thing would be left is linux, and that still is beta, you still can't run a compiled .NET app from VS on linux with mono.  If we truely wanted to be multiplatformed we would go with java, since its supported on 100x the platforms that .NET is.
## Post #25
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2004-10-02T11:01:22+00:00
- Post Title: 

> Reply from Rahly
>
> Anonymous wrote:Mr.Mouse wrote:having to rewrite everything in another language. 
Ok, so far for my excuses for not coding in 'better' languages.  


Why not use .NET? You can use multiple programming languages in 1 application. Also, you don't need to create your own scripting language for plugins, .NET can import (and run) uncompiled code during runtime!

Thats not the same thing, .NET can import uncompiled .NET code, which is a byte code similar to java.  It cannot import readable languages such as pascal, c, c++, basic, etc etc etc etc.  You still need a compiler for that, like Visual Studio.  You've always been able to use multiple languages in one application.  I can compile a pascal unit down and import it into a c program, or vice versa.  The only true advantage for .NET would be its ability to run on multiple platforms.  Since PDAs are limited in memory and mexcom usually works with large files (archives), running on a PDA really isn't feasible.  The only thing would be left is linux, and that still is beta, you still can't run a compiled .NET app from VS on linux with mono.  If we truely wanted to be multiplatformed we would go with java, since its supported on 100x the platforms that .NET is.
Yes I agree. Java seems like a good choice for this, although I prefer Python for building tools (I have had very good experiences with the Python/wxWindows combo). Java can get overly complex for simple tasks at times, as in, metaphorically speaking, when I want a simple candlestick I don't want to have to build an entire christmas tree, just to support my candle.

And Mr. Mouse doesn't know Java (or OOP in general as far as I know), so we'll have to drag him in kicking and screaming. And let me tell you, that's not an easy thing to do. Furthermore, Mr.Mouse is on his honeymoon now and there's no telling what his priorities will be when he returns as a married man. lol.

Oh and just to finish up this rambling, garbled post, I know regular expressions very well so I can help out when necessary.
