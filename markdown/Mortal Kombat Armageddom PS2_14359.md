## Post #1
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-05-17T22:13:39+00:00
- Post Title: Mortal Kombat Armageddom PS2

How to extract this game? mkda.pak. Script for this? mkda.pak, script for this format?
[imagem.png](https://xentaxbackup.github.io/file/10945_imagem.png)
## Post #2
- Username: Hyder61112
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 04, 2016 4:37 am
- Post datetime: 2016-08-26T08:14:26+00:00
- Post Title: Mortal Kombat Armageddom PS2

> Reply from dswd2015
>
> How to extract this game? mkda.pak. Script for this? mkda.pak, script for this format?

of course. this is the quick bms script

```
# script for QuickBMS http://quickbms.aluigi.org

math XTYPE = 0
get BASE_SIZE asize
callfunction SEC_EXTRACT

startfunction SEC_EXTRACT
    savepos BASE_OFF
    idstring " CES"
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get FILES long
    endian guess FILES
    get SSF_SIZE long
    if XTYPE == 0
        if SSF_SIZE != BASE_SIZE
            math XTYPE = 1
        endif
    endif
    if XTYPE != 0
        get SSF_SIZE long
    endif

    for i = 0 < FILES
        #http://ps23dformat.wikispaces.com/Mortal+Kombat+Armageddon
        #00 00 00 01- Identification File
        #00 00 00 02-Type 1 Texture File
        #00 00 00 03-Type 2 Texture File
        #00 00 00 04-Mesh File
        #00 00 00 05-Ragdoll Mesh File Animations??
        #00 00 00 06-Nested SEC File
        #00 00 00 07-Animation information for Camera?? Also appears to be using Big-Endian
        #00 00 00 08-Nested SEC File
        #00 00 00 0A-Mesh Weight File

        get TYPE long
        get OFFSET long
        get SIZE long
        if XTYPE != 0
            get DUMMY long
        endif

        if OFFSET != 0
            if TYPE == 6
                math TYPE = 1
            endif
            if TYPE == 8
                math TYPE = 1
            endif

            math OFFSET += BASE_OFF
            savepos TMP
            goto OFFSET
            get SIGN long
            if SIGN == 0x20434553   # " CES"
                math TYPE = 1
            elif SIGN == 0x53454320 # "SEC "
                math TYPE = 1
            else
                math TYPE = 0
            endif
            goto TMP

            if TYPE == 1
                savepos TMP
                goto OFFSET
                math BASE_SIZE = SIZE
                callfunction SEC_EXTRACT
                goto TMP
            else
                log "" OFFSET SIZE
            endif
        endif
    next i
endfunction
```
## Post #3
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-11-21T01:42:55+00:00
- Post Title: Mortal Kombat Armageddom PS2

> Reply from Hyder61112
>
> dswd2015 wrote:How to extract this game? mkda.pak. Script for this? mkda.pak, script for this format?

of course. this is the quick bms script
Code: Select all# Mortal Kombat Armageddon "ssf" (script 0.1.1)
# script for QuickBMS http://quickbms.aluigi.org

math XTYPE = 0
get BASE_SIZE asize
callfunction SEC_EXTRACT

startfunction SEC_EXTRACT
    savepos BASE_OFF
    idstring " CES"
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get FILES long
    endian guess FILES
    get SSF_SIZE long
    if XTYPE == 0
        if SSF_SIZE != BASE_SIZE
            math XTYPE = 1
        endif
    endif
    if XTYPE != 0
        get SSF_SIZE long
    endif

    for i = 0 < FILES
        #http://ps23dformat.wikispaces.com/Mortal+Kombat+Armageddon
        #00 00 00 01- Identification File
        #00 00 00 02-Type 1 Texture File
        #00 00 00 03-Type 2 Texture File
        #00 00 00 04-Mesh File
        #00 00 00 05-Ragdoll Mesh File Animations??
        #00 00 00 06-Nested SEC File
        #00 00 00 07-Animation information for Camera?? Also appears to be using Big-Endian
        #00 00 00 08-Nested SEC File
        #00 00 00 0A-Mesh Weight File

        get TYPE long
        get OFFSET long
        get SIZE long
        if XTYPE != 0
            get DUMMY long
        endif

        if OFFSET != 0
            if TYPE == 6
                math TYPE = 1
            endif
            if TYPE == 8
                math TYPE = 1
            endif

            math OFFSET += BASE_OFF
            savepos TMP
            goto OFFSET
            get SIGN long
            if SIGN == 0x20434553   # " CES"
                math TYPE = 1
            elif SIGN == 0x53454320 # "SEC "
                math TYPE = 1
            else
                math TYPE = 0
            endif
            goto TMP

            if TYPE == 1
                savepos TMP
                goto OFFSET
                math BASE_SIZE = SIZE
                callfunction SEC_EXTRACT
                goto TMP
            else
                log "" OFFSET SIZE
            endif
        endif
    next i
endfunction

Thanks for help me.
