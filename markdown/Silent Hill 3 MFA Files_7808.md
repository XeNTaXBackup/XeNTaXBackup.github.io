## Post #1
- Username: Henderson
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 10, 2011 8:01 pm
- Post datetime: 2011-12-04T20:31:12+00:00
- Post Title: Silent Hill 3 MFA Files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2011-12-31T04:36:55+00:00
- Post Title: Silent Hill 3 MFA Files

Extraction script:

```

#start of header

GET filename FILENAME
IF filename & "0.mfa"
    GOTO 0xD8
ELSE
    GOTO 0xB8
ENDIF

MATH header_size = 2048
GET real_size ASIZE
CALLFUNCTION Extract 1
MATH temp_size = block_size

FOR block = 1
    IF temp_size < real_size   # if the current total extracted size is smaller than the MFA archive size, continue extracting
        PRINT "Addtional block number %block% at offset %temp_size|h%"
        CALLFUNCTION Additional 1
    ELSE
        CLEANEXIT
    ENDIF
NEXT block

STARTFUNCTION Additional
    MATH extra = 1
    MATH offset = temp_size
    MATH offset += 8
    GOTO offset
    CALLFUNCTION Extract 1
    MATH temp_size += block_size
ENDFUNCTION

STARTFUNCTION Extract
    GET number_of_files LONG
    PRINT "Files: %number_of_files%"
    GET file_section_size LONG
    MATH block_size = file_section_size
    MATH block_size += header_size
    SAVEPOS offset

    FOR i = 0 < number_of_files
    # read file name
        GET name_offset LONG
        IF extra = 1
            MATH name_offset += temp_size
        ENDIF
        GOTO name_offset
        GET filename STRING
    #read file offset
        MATH offset += 4
        GOTO offset
        GET file_offset LONG
        MATH file_offset += header_size
        IF extra = 1
            MATH file_offset += temp_size
        ENDIF
    # this unknown attribute seems to be related to Korean files
        MATH offset += 4
        GOTO offset
        GET korean  LONG
        IF korean == 0x000081A4
            STRING filename += "[K]"
        ENDIF
    # read file size
        GET filesize LONG
    # save the file to disk
        LOG filename file_offset filesize
        SAVEPOS offset
    NEXT i  
ENDFUNCTION

```
## Post #3
- Username: Henderson
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Nov 10, 2011 8:01 pm
- Post datetime: 2011-12-31T11:43:28+00:00
- Post Title: Silent Hill 3 MFA Files

The script is perfect *--*

Thank you very much!!!
## Post #4
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2013-09-28T22:15:56+00:00
- Post Title: Silent Hill 3 MFA Files

Sorry to bump an old thread. Wasn't sure if i should make a new one. Can someone make a script that can do the opposite of this? Make it import files instead of export.
## Post #5
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-03-04T17:46:02+00:00
- Post Title: Silent Hill 3 MFA Files

> Reply from peronmls
>
> Sorry to bump an old thread. Wasn't sure if i should make a new one. Can someone make a script that can do the opposite of this? Make it import files instead of export.

```
3) Reimport the extracted files
===============================


As already said QuickBMS is primarly an extraction tool, anyway from
version 0.4.9 it supports also the -r option that transforms the tool
in a simple reimporter/reinjector and so could be useful in some cases
for who wants to mod or translate a game.

The idea consists in being able to reimport ("injecting back") the
modified files in the majority archives without touching a single line
of the script, yeah just reusing the same bms scripts that already
exist!
```


from QuickBMS readme
[http://pastebin.com/sGGiVDUk](http://pastebin.com/sGGiVDUk)
## Post #6
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2020-11-26T03:15:33+00:00
- Post Title: Silent Hill 3 MFA Files

This script is amazing, I extracted MFA archive with it successfully

Now if only a way to convert those models and textures into regular formats existed, besides ninja ripper walkthroughs, SH Level viewer character dumps
found only this topic: [http://silenthillcommunity.com/viewtopi ... 9&t=438420](http://silenthillcommunity.com/viewtopic.php?f=3319&t=438420)
So basically no way to directly extract in-game models from files is found yet
