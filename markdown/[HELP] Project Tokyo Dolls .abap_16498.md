## Post #1
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-07-05T15:08:11+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

This game using the Unity engine, but the file has been compressed as .abap. Someone can help me decompile this format? Thank you guy.
Sample file [Mega](https://mega.nz/#!6IxUFIBD!R72R_XQCuZaTn3CLB1O4JDD0ihOzjReJWrG8i_LtTuk)
Playstore: [プロジェクト東京ドールズ](https://play.google.com/store/apps/details?id=com.square_enix.android_googleplay.PTD&ls=1&referrer=azreferrer%3Dadzcorea1016dca-0c87-4bd9-bf2a-cde6e5aedbc8adzcore)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-12T02:05:49+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

The first 0x400 of each file is encrypted.
I am not sure how its encrypted.
once you get the real file start the files are normal compressed unity3d files that work in all tools.
## Post #3
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-12-15T03:41:39+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

still looking for method to unpack em
## Post #4
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2019-08-21T05:11:06+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

> Reply from wansf ↑Sat Dec 15, 2018 11:41 am at Sat Dec 15, 2018 11:41 am
>
> 
still looking for method to unpack em

did you do it?
## Post #5
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-10-10T04:13:42+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

sorry, apparently a necro post, but estertion seems to have found a clue to decryption.

[https://estertion.win/2019/03/project-t ... %E5%85%B3/](https://estertion.win/2019/03/project-tokyo-dolls-%E6%8B%86%E8%A7%A3%E7%9B%B8%E5%85%B3/)

*not work...

```
get SIZE asize
log "test.dat" 0 SIZE
```


I have no knowledge of quickbms, but I tried to decrypt it but it didn't work. I hope someone who understands can solve it.
Thanks!
## Post #6
- Username: einherjar007
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-10T11:13:13+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

According to his post 

> PHP
>
> $dat = file_get_contents('cr0026_c005_0.abip');
>
> 
>
> $key = implode('', array_reverse(str_split(base64_decode('Y2VJOCQpWSNZcyRyNVJGNVd8NFctXzE7Kkw7KVZVenc='), 1)));
>
> $iv  = implode('', array_reverse(str_split(base64_decode('ZTBnJDJuUnAmIWRBUVJXP2pxeCxXPn1FI2ZKRzFEKkw='), 1)));
>
> 
>
> $head = substr($dat, 0, 0x400);
>
> $body = substr($dat, 0x400);
>
> 
>
> $headdec = mcrypt_decrypt(MCRYPT_RIJNDAEL_256, $key, $head, MCRYPT_MODE_CBC, $iv);
>
> 
>
> file_put_contents('cr0026_c005_0-dec.abip', $headdec.$body);
 is the decrypt code
## Post #7
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-10-10T12:35:44+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

> Reply from chrrox ↑Thu Oct 10, 2019 7:13 pm at Thu Oct 10, 2019 7:13 pm
>
> 
According to his post 
PHP
$dat = file_get_contents('cr0026_c005_0.abip');

$key = implode('', array_reverse(str_split(base64_decode('Y2VJOCQpWSNZcyRyNVJGNVd8NFctXzE7Kkw7KVZVenc='), 1)));
$iv  = implode('', array_reverse(str_split(base64_decode('ZTBnJDJuUnAmIWRBUVJXP2pxeCxXPn1FI2ZKRzFEKkw='), 1)));

$head = substr($dat, 0, 0x400);
$body = substr($dat, 0x400);

$headdec = mcrypt_decrypt(MCRYPT_RIJNDAEL_256, $key, $head, MCRYPT_MODE_CBC, $iv);

file_put_contents('cr0026_c005_0-dec.abip', $headdec.$body);
 is the decrypt code

Thanks, apparently I overlooked it.
I had to reverse the string with array_reverse.
777a5 ~ and 4c2a44 ~ are valid keys.

I was able to decrypt those keys using an online tool.
quickbms document has an mcrypt(mcrypt rijndael-256), but doesn't it really work? I don't have a PHP execution environment,
so I would like to decrypt with quickbms if possible.

----
*Edit

Sorry, I finally found it. 
encryption mcrypt_rijndael-256_cbc mode worked!
## Post #8
- Username: einherjar007
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-10T21:07:22+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

```
#Decrypt by chrrox
set MYKEY binary "\x77\x7A\x55\x56\x29\x3B\x4C\x2A\x3B\x31\x5F\x2D\x57\x34\x7C\x57\x35\x46\x52\x35\x72\x24\x73\x59\x23\x59\x29\x24\x38\x49\x65\x63"
set MYIV  binary "\x4C\x2A\x44\x31\x47\x4A\x66\x23\x45\x7D\x3E\x57\x2C\x78\x71\x6A\x3F\x57\x52\x51\x41\x64\x21\x26\x70\x52\x6E\x32\x24\x67\x30\x65"


idstring "\x70\x70\x69\x72"
get TBLOFF  long
get NBASE   long
get BASEOFF long
set FILES NBASE
math FILES - TBLOFF
math FILES / 0x10
append
for i = 0 < FILES
    set MEMORY_FILE binary ""
    goto TBLOFF
    get NSTART long
    get NSIZE  long
    get OFFSET long
    get SIZE   long
    math NSTART + NBASE
    math OFFSET + BASEOFF
    savepos TBLOFF
    goto NSTART
    getdstring NAME NSIZE
    string NAME + .unity3d
    encryption mcrypt_rijndael-256_cbc MYKEY MYIV
    if SIZE > 0x400
        log MEMORY_FILE OFFSET 0x400
        encryption "" ""
        math OFFSET + 0x400
        math SIZE - 0x400
        log MEMORY_FILE OFFSET SIZE
        math SIZE + 0x400
    else
        log MEMORY_FILE OFFSET SIZE
        encryption "" ""
    endif
    log NAME 0 SIZE MEMORY_FILE
next i

```
## Post #9
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2019-10-13T05:06:56+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

> Reply from chrrox ↑Fri Oct 11, 2019 5:07 am at Fri Oct 11, 2019 5:07 am
>
> 
Code: Select all#Project Tokyo Dolls
#Decrypt by chrrox
set MYKEY binary "\x77\x7A\x55\x56\x29\x3B\x4C\x2A\x3B\x31\x5F\x2D\x57\x34\x7C\x57\x35\x46\x52\x35\x72\x24\x73\x59\x23\x59\x29\x24\x38\x49\x65\x63"
set MYIV  binary "\x4C\x2A\x44\x31\x47\x4A\x66\x23\x45\x7D\x3E\x57\x2C\x78\x71\x6A\x3F\x57\x52\x51\x41\x64\x21\x26\x70\x52\x6E\x32\x24\x67\x30\x65"


idstring "\x70\x70\x69\x72"
get TBLOFF  long
get NBASE   long
get BASEOFF long
set FILES NBASE
math FILES - TBLOFF
math FILES / 0x10
append
for i = 0 < FILES
    set MEMORY_FILE binary ""
    goto TBLOFF
    get NSTART long
    get NSIZE  long
    get OFFSET long
    get SIZE   long
    math NSTART + NBASE
    math OFFSET + BASEOFF
    savepos TBLOFF
    goto NSTART
    getdstring NAME NSIZE
    string NAME + .unity3d
    encryption mcrypt_rijndael-256_cbc MYKEY MYIV
    if SIZE > 0x400
        log MEMORY_FILE OFFSET 0x400
        encryption "" ""
        math OFFSET + 0x400
        math SIZE - 0x400
        log MEMORY_FILE OFFSET SIZE
        math SIZE + 0x400
    else
        log MEMORY_FILE OFFSET SIZE
        encryption "" ""
    endif
    log NAME 0 SIZE MEMORY_FILE
next i

Thanks so much!
Although I have a question, does this only work on the card image files? I can't seem to get any other files such as models. Unless I'm just not finding the right files.
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-13T12:28:51+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

```
#Decrypt by chrrox
set MYKEY binary "\x6A\x36\x47\x57\x43\x56\x4B\x39\x55\x4D\x4B\x4B\x64\x33\x70\x6E\x4E\x44\x74\x78\x59\x46\x53\x5A\x34\x7A\x48\x69\x51\x39\x78\x44"
set MYIV  binary "\x64\x51\x41\x54\x5A\x34\x51\x59\x37\x67\x61\x68\x51\x61\x54\x35"

idstring "\x61\x6E\x68"
get FILES short
for i = 0 < FILES
    get NSIZE BYTE
    getdstring NAME NSIZE
    string NAME + .gz
    getdstring HASH 0x10
    get SIZE long
    savepos OFFSET
    encryption mcrypt_rijndael-128_cbc MYKEY MYIV
    log NAME OFFSET SIZE
    encryption "" "" 
    math OFFSET + SIZE
    goto OFFSET
next i

```
## Post #11
- Username: fdtggf
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 07, 2016 3:12 am
- Post datetime: 2019-10-18T17:28:13+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

> Reply from chrrox ↑Fri Oct 11, 2019 5:07 am at Fri Oct 11, 2019 5:07 am
>
> 
Code: Select all#Project Tokyo Dolls
#Decrypt by chrrox
set MYKEY binary "\x77\x7A\x55\x56\x29\x3B\x4C\x2A\x3B\x31\x5F\x2D\x57\x34\x7C\x57\x35\x46\x52\x35\x72\x24\x73\x59\x23\x59\x29\x24\x38\x49\x65\x63"
set MYIV  binary "\x4C\x2A\x44\x31\x47\x4A\x66\x23\x45\x7D\x3E\x57\x2C\x78\x71\x6A\x3F\x57\x52\x51\x41\x64\x21\x26\x70\x52\x6E\x32\x24\x67\x30\x65"


idstring "\x70\x70\x69\x72"
get TBLOFF  long
get NBASE   long
get BASEOFF long
set FILES NBASE
math FILES - TBLOFF
math FILES / 0x10
append
for i = 0 < FILES
    set MEMORY_FILE binary ""
    goto TBLOFF
    get NSTART long
    get NSIZE  long
    get OFFSET long
    get SIZE   long
    math NSTART + NBASE
    math OFFSET + BASEOFF
    savepos TBLOFF
    goto NSTART
    getdstring NAME NSIZE
    string NAME + .unity3d
    encryption mcrypt_rijndael-256_cbc MYKEY MYIV
    if SIZE > 0x400
        log MEMORY_FILE OFFSET 0x400
        encryption "" ""
        math OFFSET + 0x400
        math SIZE - 0x400
        log MEMORY_FILE OFFSET SIZE
        math SIZE + 0x400
    else
        log MEMORY_FILE OFFSET SIZE
        encryption "" ""
    endif
    log NAME 0 SIZE MEMORY_FILE
next i

How to use this?
I use this bms script to extract .abap but doesn't work.
## Post #12
- Username: Moonstone1024
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 16, 2020 6:41 pm
- Post datetime: 2020-06-21T16:43:20+00:00
- Post Title: [HELP] Project Tokyo Dolls .abap

@DKDave from the Discord server found the issue: the original QuickBMS code was expecting an .abip file, which is an archive of multiple .abap files. Since I don't see any .abip archives in the Android version a much simpler code can be used instead for individual .abap files. 

This code should work for all assets in Android: I have been able to dump not only card graphics, but also audio assets (including a song that is unreleased in any streaming site as of this message's writing) and some 3D assets. 

```
# Original thread:  https://forum.xentax.com/viewtopic.php?t=16498


set MYKEY binary "\x77\x7A\x55\x56\x29\x3B\x4C\x2A\x3B\x31\x5F\x2D\x57\x34\x7C\x57\x35\x46\x52\x35\x72\x24\x73\x59\x23\x59\x29\x24\x38\x49\x65\x63"
set MYIV  binary "\x4C\x2A\x44\x31\x47\x4A\x66\x23\x45\x7D\x3E\x57\x2C\x78\x71\x6A\x3F\x57\x52\x51\x41\x64\x21\x26\x70\x52\x6E\x32\x24\x67\x30\x65"

Get SIZE asize
Math SIZE - 0x400
Get OUTPUT_NAME basename
String OUTPUT_NAME + "_decode"

encryption mcrypt_rijndael-256_cbc MYKEY MYIV

Log OUTPUT_NAME 0 0x400

encryption "" ""

Append
Log OUTPUT_NAME 0x400 SIZE
Append

```
