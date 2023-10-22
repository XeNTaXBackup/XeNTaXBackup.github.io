## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-02-15T11:26:24+00:00
- Post Title: Otomedius G pak container.

Hi
I'd like to extract *.pak file from Otomedius G.
Could anyone look into these formats please?
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-15T12:52:14+00:00
- Post Title: Otomedius G pak container.

the script is the following but I have not understood why the files you uploaded have extension "unpacked" and not "pak":

```
# script for QuickBMS http://quickbms.aluigi.org

get PATH basename
get FULLSIZE asize
do
    getdstring SIGN 4
    if SIGN == "TXGP"
        get DUMMY long
        get FILES long
        savepos BASE_OFF
        for i = 0 < FILES
            get OFFSET long
            putarray 0 i OFFSET
        next i
        for i = 0 < FILES
            get SIZE long
            putarray 1 i SIZE
        next i

        for i = 0 < FILES
            getarray OFFSET 0 i
            getarray SIZE 1 i
            math OFFSET += BASE_OFF
            goto OFFSET
            get NAME string
            padding 4
            callfunction DUMPA 1
        next i
    elif SIGN == "MESH"
        get SIZE long
        get DUMMY long
        get NAMESZ long
        get XSIZE long
        getdstring NAME NAMESZ
        math SIZE -= NAMESZ
        callfunction DUMPA 1
    elif SIGN == "CONF"
        get SIZE long
        set NAME string "conf.ini"
        callfunction DUMPA 1
    else
        print "unsupported type %SIGN% at offset %OFFSET|x%"
        cleanexit
    endif
while OFFSET < FULLSIZE

startfunction DUMPA
    savepos OFFSET
    if NAME == ""
        set FNAME string ""
    else
        set FNAME string PATH
        string FNAME += /
        string FNAME += NAME
    endif
    log FNAME OFFSET SIZE
    math OFFSET += SIZE
    goto OFFSET
endfunction
```
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-02-15T17:23:25+00:00
- Post Title: Otomedius G pak container.

Thanks aluigi!!!!!!!
## Post #4
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2012-12-22T08:57:16+00:00
- Post Title: Otomedius G pak container.

Sorry to bump an old topic.

[](http://i38.photobucket.com/albums/e125/nigoli/oto.png)

I've been having trouble with the DLC .pak files. Here's around a 1MB [sample](http://www.mediafire.com/?u09yfthf97dfp0s) of one of the pak files. Thanks.
