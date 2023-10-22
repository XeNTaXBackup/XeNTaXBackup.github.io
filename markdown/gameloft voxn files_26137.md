## Post #1
- Username: fengye
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 17, 2021 1:49 pm
- Post datetime: 2023-01-02T14:49:40+00:00
- Post Title: gameloft voxn files

Hi and this file should be a compressed file of a music file.If anyone knows about this file, please help me unpack it.Thanks for that.
here a sample file:
[https://drive.google.com/file/d/13-7PGt ... p=drivesdk](https://drive.google.com/file/d/13-7PGt4CprK6jyrAaxzTMrvzF2YW1nJ6/view?usp=drivesdk)
btw,this file has been compressed twice,for the first time, an algorithm called voxarch is used.(The vxon file has been decompressed once)If it is useful, this is the bms script I found on the Internet that can decompress this algorithm.

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "Voxarch"  # Voxarch1 and Voxarch2
getdstring VER 1
get ZERO long
get DUMMY long
get FILES long
get OFFSET3 long
get OFFSET4 long
get OFFSET5 long
get OFFSET6 long
get NAMES_OFF_OFF long
get NAMES_OFF long
get DUMMY long
get DUMMY long
get OFFSET11 long
get OFFSET12 long
get OFFSET13 long
goto NAMES_OFF_OFF
for i = 0 < FILES
    get NAME_OFF long
    savepos TMP
    math NAME_OFF + NAMES_OFF
    goto NAME_OFF
    get NAME string
    goto TMP
    putarray 0 i NAME
next i
goto OFFSET4
for i = 0 < FILES
    get DUMMY longlong
    if VER == "1"
        get SIZE long
        get OFFSET long
    elif VER == "2"
        get ZERO long
        get SIZE long
        get ZERO long
        get OFFSET long
    elif VER == "3"
        get ZERO long
        get SIZE long
        get ZERO long
        get DUMMY long  # -1
        get OFFSET long # 64bit?
        get ZERO long
    else
        print "Error: version %VER% not supported, contact me"
        cleanexit
    endif
    getarray NAME 0 i
    log NAME OFFSET SIZE
next i

```
