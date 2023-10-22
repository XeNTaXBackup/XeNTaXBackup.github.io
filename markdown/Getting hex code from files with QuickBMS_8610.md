## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-03-22T11:39:03+00:00
- Post Title: Getting hex code from files with QuickBMS?

Hey there,

I'm new to QuickBMS so please go easy on me.
I'm writing a script to extract [the Rayman 3 and Rayman Arena for GC audio files](http://forum.xentax.com/viewtopic.php?f=10&t=7937) at the moment. This script will also extract Rayman 3 HD (that came out yesterday) and Rayman 3 for PS2's audio files if I make some small modifications.  I have analyzed the files as you can see in the topic I linked to and it seems to be a very complex file system. To sum it up:
A HXG file is divided in blocks with different identification strings.
Blocks starting with the identification string "CGCWaveFileIdObj" contain the audio (or reference to external file) and a temporary name (8 bytes) for that audio
Blocks starting with "CGCWavResData" contain either one, or multiple references to multiple audio files' temporary names, and each block contains one number, the counter. If there are multiple temporary names, there is always a string before the temporary name indicating the language of the audio. The files are always the same, only in a different language.
Blocks starting with "CEventResData" contain the counter and the real name of the audio file. For a counter, there isn't always a CEventResData block. For some of the CEventResData, you actually have to look inside another file which has the same basename but the BNH extension.

The problem is that I can't store and search for temporary names correctly. This would all be easier if I could store 8 bytes of hex code somehow and look for those same 8 bytes later. I tried longlongs, doubles and 8-byte strings (which don't work because the temporary names are made of special characters), but none of those work, so does anyone have a suggestion?

I attached my script so far, if you want to take a look at it. It's huge, but then again, the format is also huge. If you have an idea to make it shorter/better or to make it work, please don't hesitate to post it. 
To test it, use the example BNH and HXG files below:
Example bnh file (Knaar_60.bnh): [http://www.box.com/s/uajda81un694j6ltk9bo](http://www.box.com/s/uajda81un694j6ltk9bo)
Example hxg file (Knaar_60.hxg): [http://www.box.com/s/v0nbnfnpolenb4tome4m](http://www.box.com/s/v0nbnfnpolenb4tome4m)

Thanks,
Droolie.

```
# script by Droolie for QuickBMS http://quickbms.aluigi.org
debug
endian big
get LAST_OFF long

for
    FindLoc OFFSET STRING "CGCWaveFileIdObj" 0 ""
    math OFFSET -= 4
    if OFFSET < LAST_OFF
        goto OFFSET 0
        get IDSZ long 0
        getdstring IDENT IDSZ 0
        get TMPNAME longlong 0
        get DUMMY long 0
        get DUMMY long 0
        get DUMMY long 0
        get EXT long 0
        set NAME ""
        set LANG ""
        if EXT == 1
            get EXTSZ long 0
            getdstring EXTF EXTSZ 0
            set NAME "[EXT] "
        endif
        savepos OFFSET 0
        get RIFF long 0
        get RSIZE long 0
        math SIZE = RSIZE
        math SIZE += 8
        goto 0 0
        FindLoc OTHEROFF longlong TMPNAME 0 ""
        goto OTHEROFF 0
        get TMPNAME longlong 0
        getdstring LANGBIT 2 0
        if LANGBIT != ""
            set LANG "_"
            string LANG += LANGBIT
        endif
        for
            goto OTHEROFF 0
            getdstring CHECKSTRING 13 0
            if CHECKSTRING ^ "CGCWavResData"
                break
            else
                math OTHEROFF -= 1
            endif
        next
        savepos ISTHISCOUNT 0
        get COUNT double 0
        goto 0
        FindLoc COUNTOFF double COUNT 0 ""
        if COUNTOFF == ISTHISCOUNT
            goto ISTHISCOUNT 0
            get CUUID1 long 0
            get CUUID2 long 0
            set LOOK CUUID2
            String LOOK += " )"
            open FDDE BNH 1
            goto 0 1
            FindLoc LOOKOFF String LOOK 1 ""
            goto LOOKOFF
            FindLoc LOOKOFF String "file " 1 ""
            math LOOKOFF += 5
            goto LOOKOFF
            FindLoc NAMESZ String " " 1 ""
            math NAMESZ -= LOOKOFF
            getdstring ADDNAME NAMESZ 1
        else
            for
                goto COUNTOFF 0
                getdstring CHECKSTRING 13 0
                if CHECKSTRING ^ "CEventResData"
                    break
                else
                    math COUNTOFF -= 1
                endif
            next
            get CUUID longlong 0
            get DUMMY long 0
            get NAMESZ long 0
            getdstring ADDNAME NAMESZ 0
        endif
        goto OFFSET 0
        String NAME += ADDNAME
        String NAME += LANG
        log NAME OFFSET SIZE 0
    else
        break
    endif
next
```
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-22T15:55:56+00:00
- Post Title: Getting hex code from files with QuickBMS?

you can use the -V option at command-line or you can have the same effect but specific for a portion of code by adding "debug 1" when you want to enable and disable the verbose mode.

example:

```
...
  debug 1
  get NAME_SIZE long
  getdstring NAME NAME_SIZE
  debug 1
...
next
```
## Post #3
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-03-22T18:31:18+00:00
- Post Title: Getting hex code from files with QuickBMS?

Thanks, but I already knew that. I have "debug" in the beginnning of my script so it shows the collected information too, along with a lot of other information.

The problem is that I can't get the TMPNAME variable in my script correctly. For example, the very first TMPNAME in my script, which is in hexadecimal code "56356000312D23FB", can't be saved as a string correcty, nor as a longlong or a double. Because of this, FindLoc finds a way earlier offset in the file when I look for the saved TMPNAME so the script doesn't do what it's meant to do at all.
This would all be fixed if getdstring would get the hexadecimal code instead of ASCII/unicode and FindLoc would look for that hexadecimal code directly. Or is there a workaround?
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-03-24T00:49:23+00:00
- Post Title: Getting hex code from files with QuickBMS?

Use get instead of getDstring and transform to string of hex representation (string VAR p= "%08x" VAR).
I'm not sure if you can search for the content of VAR though (i.e. the string itself). Test it and tell me if it works.
## Post #5
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-03-24T17:49:22+00:00
- Post Title: Getting hex code from files with QuickBMS?

> Reply from AlphaTwentyThree
>
> Use get instead of getDstring and transform to string of hex representation (string VAR p= "%08x" VAR).
I'm not sure if you can search for the content of VAR though (i.e. the string itself). Test it and tell me if it works.
Thanks for the reply, though I tried it out and it still doesn't work - "get" gets strings till any "00" byte and the strings I'm looking for usually contain such bytes. I also can't get "string VAR p= "%08x" VAR" to work. And for converting strings to hex representation, wouldn't "string VAR b= VAR" work better?

Anyway, I just tried this method:

```
        set TMPNAME ""
        for i = 0 < 8
            getdstring TMPB 1 0
            string TMPB b= TMPB
            string TMPNAME += HEXBIT
            string TMPNAME += TMPB
        next i
```


It's supposed to be a workaround which converts every single byte to a hexadecimal string and puts "\x" in it so it's like "\x56\x35\x60\x00\x31\x2d\x23\xfb". ( Will this allow me to search for it correctly?  )
I used the "string VAR b= VAR" method as described above, but it somehow messes up. I think I found a bug here...



In the above method, I was storing every byte in a separate variable (as in TMPONE, TMPTWO, etc), so it still looked a bit clean. "23" is the output I'm supposed to get. But watch this:



This is what happened when I used a for loop on every byte and used the same variable (TMPB) for every byte.
I don't really know why this happens. If it's a bug, hopefully it'll be fixed soon! 

In the meantime, does anybody have an idea for a workaround that doesn't involve hex code?
## Post #6
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-04-02T19:02:07+00:00
- Post Title: Getting hex code from files with QuickBMS?

Okay, so I just managed to get past my previous problem by doing this.

```
            set TMPB ""
            set TMPH "00"
            getdstring TMPB 1 0
            string TMPH b= TMPB
            string TMPH -= -2
            string TMPNAME += HEXBIT
            string TMPNAME += TMPH
        next i
```


Now, even with "\x56\x35\x60\x0\x31\x2D\xFB" as search string, FindLoc doesn't find it at all, even though the hex data "56356000312D23FB" is definitely in the file (check the example HXG file in the first post). Is there any way at all to get data like this correctly from the file and use it later? It's starting to drive me insane... :/
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-09T16:17:38+00:00
- Post Title: Getting hex code from files with QuickBMS?

sincerely I don't understand what's the purpose of all this chaos with scripts that do senseless operations...

while for Findloc I have created a file from scratch, added those bytes you told me in it and then used the following script:

```
print "OFFSET %OFFSET|x%"
```
everything worked perfectly as expected
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-09T22:56:04+00:00
- Post Title: Getting hex code from files with QuickBMS?

If I understood him correctly, he needs something like a custom search:

```
FindLoc FOUNDSTRING string SEARCHSTRING
```

The variable FOUNDSTRING will always be "", even if the string is contained in the file.
## Post #9
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-04-09T23:20:03+00:00
- Post Title: Getting hex code from files with QuickBMS?

I'm sorry if my previous posts didn't make sense to both of you. :/
Let me try to explain.

As QuickBMS saves strings as ASCII or Unicode strings, it's not 100% accurate, it also skips some bytes directly.
Here is the proof for that, right from QuickBMS's debug output:

Here it gets an 8-byte string (with hex representation "\x56\x35\x60\x0\x31\x2D\x23\xFB") from the [example HXG file](http://www.box.com/s/v0nbnfnpolenb4tome4m):

Here it looks for the string inside the example HXG file but it doesn't find anything at all.

If you look for "\x56\x35\x60\x0\x31\x2D\x23\xFB" though, which is the hex representation of the same string, QuickBMS finds it correctly like aluigi said.

So I want to be more accurate, and choose to read and use the strings in their hex representation. The problem is, there is no command to read a string from a file in its hex representation at all. That's why I wrote my own function now, based on the script I had written before.

```
    set HEXBIT = "\x"
    set HEXNAME ""
    for i = 0 < GETHEX_ARG1
        set TMPB ""
        set TMPH "00"
        getdstring TMPB 1 0
        string TMPH b= TMPB
        string TMPH -= -2
        string HEXNAME += HEXBIT
        string HEXNAME += TMPH
    next i
endfunction
```

This perfectly converts the string to its hex representation, as you can see from the picture below.


But FindLoc still shows the same error.

Aluigi's script works nicely though. I presume that this is because our strings are stored as different types of strings. It's a shame I can't use the script like that as it is supposed to look for a hex string read from the file itself, not from my manual input as that would take ages.

Since FindLoc can't look for my hex representation of the string, I have to use this horribly slow workaround to find the offset:

```
            callfunction gethex 1 8
            if HEXNAME ^ TMPNAME
                break
            else
                math OTHEROFF += 1
                goto OTHEROFF 0
            endif
        next
```

This will help me get around the problem I had, but it's still very slow. So I don't need help with this anymore, but adding a separate type for hex strings with no delimiters (not even null bytes like what you have for strings now) that you can use with get and FindLoc would be a much appreciated feature for QuickBMS as it would have prevented this whole problem.

Does it make sense now?
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-09T23:46:23+00:00
- Post Title: Getting hex code from files with QuickBMS?

Isn't that exactly what I was saying?
All the offsets below are empty when you run the script on your file.

```
set SEARCHSTRING2 "\x56\x35\x60\x00\x31\x2D\x23\xFB"
set SEARCHSTRING3 0x56356000312D23FB
FindLoc OFFSET1 string SEARCHSTRING1 0 ""
FindLoc OFFSET2 string SEARCHSTRING2 0 ""
FindLoc OFFSET3 string SEARCHSTRING3 0 ""
```

Would be good to know how to define SEARCHSTRING in order for QuickBMS to find it.
Sorry to bother you with this Luigi, but I had the same question in mind for some time now.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-10T07:15:18+00:00
- Post Title: Getting hex code from files with QuickBMS?

the binary strings like "\x01\x02" are converted in bytes when the script gets read, it works only for constant strings.

findloc should be used only rarely (imho almost never) and with fixed patterns because quickbms is a file format parser and not a "grep" or a ripper.
## Post #12
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-04-10T11:29:08+00:00
- Post Title: Getting hex code from files with QuickBMS?

> Reply from AlphaTwentyThree
>
> Isn't that exactly what I was saying?
Yep, haha, I misunderstood your post for some reason. Sorry for that. xD

> Reply from aluigi
>
> findloc should be used only rarely (imho almost never) and with fixed patterns because quickbms is a file format parser and not a "grep" or a ripper.
I agree, but in some cases (like this one) it is necessary to use functions like FindLoc with changeable search strings to parse the file. This is already possible for normal strings but not for strings with "\x0" bytes in them (as that's the normal string delimiter).

EDIT -> As for the actual script, I seem to have finished it, but it works extremely slow as it uses way too many workarounds.

```
# script by Droolie for QuickBMS http://quickbms.aluigi.org
endian big
get LAST_OFF long

for
    FindLoc OFFSET STRING "CGCWaveFileIdObj" 0 ""
    math OFFSET -= 4
    if OFFSET < LAST_OFF
        goto OFFSET 0
        get IDSZ long 0
        getdstring IDENT IDSZ 0
        callfunction gethex 1 8
        set TMPNAME HEXNAME
        get DUMMY long 0
        get DUMMY long 0
        get DUMMY long 0
        get EXT long 0
        set NAME ""
        set LANG ""
        if EXT == 1
            get EXTSZ long 0
            getdstring EXTF EXTSZ 0
            set NAME "[EXT] "
        endif
        savepos OFFSET 0
        get RIFF long 0
        get RSIZE long 0
        math SIZE = RSIZE
        math SIZE += 8
        goto 0 0
        savepos OTHEROFF 0
        for
            callfunction gethex 1 8
            if HEXNAME ^ TMPNAME
                break
            else
                math OTHEROFF += 1
                goto OTHEROFF 0
            endif
        next
        getdstring LANGBIT 2 0

        if LANGBIT != ""
            set LANG "_"
            string LANG += LANGBIT
        endif
        for
            goto OTHEROFF 0
            getdstring CHECKSTRING 13 0
            if CHECKSTRING ^ "CGCWavResData"
                break
            else
                math OTHEROFF -= 1
            endif
        next
        savepos ISTHISCOUNT 0
        callfunction gethex 1 8
        set COUNT HEXNAME
        goto 0 0

        savepos COUNTOFF 0
        math STOPVAR = 0
        math REALSTOPVAR = 0
        for REALSTOPVAR = REALSTOPVAR != 1
            if COUNTOFF >= ISTHISCOUNT
                break
            endif
            getdstring CHECKSTRING 13 0
            if CHECKSTRING ^ "CProgramResDa"
                math STOPVAR = 1
            elif CHECKSTRING ^ "CEventResData"
                math STOPVAR = 0
                savepos THISISCOUNT 0
            endif
            if STOPVAR == 0
                goto COUNTOFF 0
                callfunction gethex 1 8
                if HEXNAME ^ COUNT
                    math REALSTOPVAR = 1
                else
                    math COUNTOFF += 1
                    goto COUNTOFF 0
                endif
            else
                math COUNTOFF += 1
                goto COUNTOFF 0
            endif
        next
        if COUNTOFF == ISTHISCOUNT
            goto ISTHISCOUNT 0
            callfunction gethex 1 4
            set CUUID1 HEXNAME
            callfunction gethex 1 4
            set CUUID2 HEXNAME
            open FDDE BNH 1
            goto 0 1
            for
                FindLoc LOOKOFF String "\x63\x75\x75\x69\x64\x28\x20" 1
                math LOOKOFF += 9
                goto LOOKOFF 1
                callfunction gethstring 1 4
                if HEXNAME ^ CUUID1
                    math LOOKOFF += 12
                    goto LOOKOFF 1
                endif
                callfunction gethstring 1 4
                if HEXNAME ^ CUUID2
                    break
                endif
            next
            FindLoc LOOKOFF String "file " 1 ""
            math LOOKOFF += 5
            goto LOOKOFF 1
            FindLoc NAMESZ String "\x0A" 1 ""
            math NAMESZ -= LOOKOFF
            getdstring ADDNAME NAMESZ 1
        else
            goto THISISCOUNT 0
            get CUUID longlong 0
            get DUMMY long 0
            get NAMESZ long 0
            getdstring ADDNAME NAMESZ 0
        endif
        goto OFFSET 0
        String NAME += ADDNAME
        String NAME += LANG
        log NAME OFFSET SIZE 0
    else
        break
    endif
next

startfunction gethex
    set HEXBIT = "\x"
    set HEXNAME ""
    for i = 0 < GETHEX_ARG1
        set TMPB ""
        set TMPH "00"
        getdstring TMPB 1 0
        string TMPH b= TMPB
        string TMPH -= -2
        string HEXNAME += HEXBIT
        string HEXNAME += TMPH
    next i
endfunction

startfunction gethstring
    set HEXBIT = "\x"
    set HEXNAME ""
    for i = 0 < GETHSTRING_ARG1
        set TMPB ""
        set TMPS ""
        set TMPH "00"
        getdstring TMPB 2 1
        string TMPS h= TMPB
        string TMPH b= TMPS
        string TMPH -= -2
        string HEXNAME += HEXBIT
        string HEXNAME += TMPH
    next i
endfunction
```
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-10T17:41:58+00:00
- Post Title: Getting hex code from files with QuickBMS?

Okey dokey, thanks for clearing that up.
