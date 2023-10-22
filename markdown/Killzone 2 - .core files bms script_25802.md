## Post #1
- Username: n1nonly1
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jan 30, 2022 10:40 pm
- Post datetime: 2022-09-13T18:06:45+00:00
- Post Title: Killzone 2 - .core files bms script?

hello,
i have been trying to extract models from killzone 2 for a long time (renderdoc is successful but no uvs) so im turning to a quickbms script.
using these scripts 
```
# script for QuickBMS http://quickbms.aluigi.org

comtype lz4
idstring "\x83\xc1\x10\xcb"
get CHUNK_SIZE long
get SIZE longlong
getdstring DUMMY 0x10

get NAME basename
get EXT extension
string NAME p "%s_unpack.%s" NAME EXT

xmath CHUNKS "SIZE / CHUNK_SIZE"
if SIZE % CHUNK_SIZE
    math CHUNKS + 1
endif

savepos TMP
xmath OFFSET "TMP + (CHUNKS * 4)"

log NAME 0 0
append
for x = 0 < CHUNKS
    get CHUNK_ZSIZE long
    if CHUNK_ZSIZE == 0 # ???
        math CHUNK_ZSIZE = CHUNK_SIZE
    endif
    if CHUNK_ZSIZE >= CHUNK_SIZE
        log NAME OFFSET CHUNK_SIZE  # ???
    else
        clog NAME OFFSET CHUNK_ZSIZE CHUNK_SIZE
    endif
    math OFFSET + CHUNK_ZSIZE
next x
append

```


```
# script for QuickBMS http://quickbms.aluigi.org

get ARCHIVE_NAME basename

get INFO_SIZE long
get DUMMY long
get DUMMY long
get DUMMY long
get ZERO long
get ZERO long

get NAMES_SIZE long
savepos OFFSET
log MEMORY_FILE OFFSET NAMES_SIZE

math OFFSET + NAMES_SIZE
goto OFFSET

get INFO_SIZE long
savepos OFFSET
log MEMORY_FILE2 OFFSET INFO_SIZE

get ENTRIES long MEMORY_FILE2
savepos OFFSET MEMORY_FILE2
set PATH string ""
set NAME string ""
putarray 0 0 0  # nested function
callfunction EXTRACT

startfunction EXTRACT
    savepos BCK_OFF MEMORY_FILE2
    goto OFFSET MEMORY_FILE2
    string PATH + NAME
    string PATH + /
    for CUR_ENTRIES = ENTRIES > 0
        get NAME_OFF long MEMORY_FILE2
        math FLAGS = NAME_OFF
        xmath NAME_OFF "NAME_OFF & ((1 << 23) - 1)"
        goto NAME_OFF MEMORY_FILE
        get NAME string MEMORY_FILE
        get OFFSET long MEMORY_FILE2
        if FLAGS & 0x80000000
            get ENTRIES long MEMORY_FILE2
            callfunction EXTRACT
        else
            callfunction HANDLE_PACK_NUM 1
            get SIZE long MEMORY_FILE2
            string NAME p "%s%s" PATH NAME
            set EXT extension NAME
            if EXT == "core" && ARCHIVE_NAME == "psp"
                goto OFFSET
                get ZERO long   # probably XSIZE64
                get XSIZE long
                reverselong XSIZE
                math OFFSET + 8
                math SIZE   - 8
                clog NAME OFFSET SIZE XSIZE
            else
                log NAME OFFSET SIZE
            endif
        endif
    prev CUR_ENTRIES
    goto BCK_OFF MEMORY_FILE2
endfunction

startfunction HANDLE_PACK_NUM
    xmath PACK_NUM "(FLAGS >> 23) & 0x1f"
    getarray LAST_PACK_NUM 0 0
    if PACK_NUM != LAST_PACK_NUM
        putarray 0 0 PACK_NUM
        get EXT extension
        if PACK_NUM == 0
            string TMP p "%s.%s" ARCHIVE_NAME EXT
        else
            string TMP p "%s%02d.%s" ARCHIVE_NAME PACK_NUM EXT
        endif
        open FDSE TMP
    endif
endfunction

```


however, these 2 scripts have proven unsucessful, so im turning to the community for help. any other way to extract this model? samples are available in this drive [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1_eSSwhZo9uGjfFLC9JulvovGDfUl1xD8?usp=sharing)
please pm me if you have any questions, or reply to this post.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-13T19:27:04+00:00
- Post Title: Killzone 2 - .core files bms script?

Using a point cloud skinner (too lazy to search for suiting face indices):
.



assets_description.vehicles.isa_intruder_baseassets_isa_intruder_baseassets.jpg (120.97 KiB) Viewed 188 times
## Post #3
- Username: n1nonly1
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jan 30, 2022 10:40 pm
- Post datetime: 2022-09-13T21:29:08+00:00
- Post Title: Killzone 2 - .core files bms script?

hello shakotay,
what is the basic usage for this?
thank you for the help
## Post #4
- Username: n1nonly1
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jan 30, 2022 10:40 pm
- Post datetime: 2022-09-13T22:18:50+00:00
- Post Title: Killzone 2 - .core files bms script?

im aware that one particular user (luxox18) manage to extract various models from the game, and im trying to replicate what he did however i just cant find enough information. im guessing this has to do with my experience too (not very experienced)
## Post #5
- Username: n1nonly1
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jan 30, 2022 10:40 pm
- Post datetime: 2022-09-14T15:24:20+00:00
- Post Title: Killzone 2 - .core files bms script?

with renderdoc, after stretching and deleting double vertices, you can get something like this:[https://imgur.com/a/B0eYITP](https://imgur.com/a/B0eYITP)
but the problem is the uv's...[https://imgur.com/a/XseS3Ha](https://imgur.com/a/XseS3Ha)
so thats one of the main problems. however renderdoc does give you the textures (model textures, normal maps, etc)
## Post #6
- Username: n1nonly1
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jan 30, 2022 10:40 pm
- Post datetime: 2022-09-15T15:45:37+00:00
- Post Title: Killzone 2 - .core files bms script?

please do correct me if im wrong, but i think i found the start of vertices [https://imgur.com/a/lWzepOt](https://imgur.com/a/lWzepOt)
and the end of vertices [https://imgur.com/a/olpCdJV](https://imgur.com/a/olpCdJV)

some (a lot of) lines above we have what i assume are face indices (start) [https://imgur.com/a/vKeU2zo](https://imgur.com/a/vKeU2zo)

i will definitely need some help here    so again, please do correct me if im wrong.

edit1: also im unsure if its data type is sequencial or blocked (seperate and structured, respectively)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-15T16:13:47+00:00
- Post Title: Killzone 2 - .core files bms script?

Hi,
you can always use VB, "blocked", "sequential" is obsolete since VB with an FVFsize of 12 (for floats) is the same as sequential. (I left "sequential" in the tutorial because of educational reasons only).

Now for the vertex start, you're pretty close. Problem is that none of the face indices blocks I tested did fit.
Here's some H2O examples (load model file (once), then a H2O file. Press "go1" and adjust vertex count, if required (scroll down in left lower listbox for found vertex count) before pressing the "mesh" button):
-

 assets_description.vehicles.isa_intruder_baseassets_isa_intruder_baseassets_0_to_7.zip
(2.32 KiB) Downloaded 12 times
## Post #8
- Username: n1nonly1
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jan 30, 2022 10:40 pm
- Post datetime: 2022-09-15T17:45:58+00:00
- Post Title: Killzone 2 - .core files bms script?

i have been messing around with the values. so, assuming the vertex data pos. is correct, i need to find the correct face indices and figure out the VB block size?
also im sure that it is big endian (ps3 and xbox 360 use big endian, while next gen consoles and windows use little endian if im correct)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-15T18:18:32+00:00
- Post Title: Killzone 2 - .core files bms script?

> Reply from n1nonly1 ↑Fri Sep 16, 2022 1:45 am at Fri Sep 16, 2022 1:45 am
>
> 
i have been messing around with the values. so, assuming the vertex data pos. is correct, i need to find the correct face indices and figure out the VB block size?Yep. You can toggle "noPtC" to "PtCld", then press "mesh" to check for a decent point cloud.

btw: you can use +/- buttons to change "startaddress of vertices", then press "mesh". Current delta is 0x100.
## Post #10
- Username: n1nonly1
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jan 30, 2022 10:40 pm
- Post datetime: 2022-09-16T18:46:29+00:00
- Post Title: Killzone 2 - .core files bms script?

alright, i still havent gotten a decent point cloud, so i guess its just a matter of time until i get a decent one.
i will be in touch.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-16T21:14:00+00:00
- Post Title: Killzone 2 - .core files bms script?

Sadly I have no idea what the problem could be nor the time to dig deeper (intruder, 3 point clouds added):
.



0xFAD94_0x103864_0x11C2C0.jpg (130.12 KiB) Viewed 115 times
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-17T18:45:12+00:00
- Post Title: Killzone 2 - .core files bms script?

more decent:
.



intruder_c_.jpg (187.05 KiB) Viewed 95 times

I have no idea why those face indices at 0xdc628, 0xe0640 or 0xe4658
DON'T fit. Really hate it. 

0xe8670 comes close, but still weird.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-17T19:19:20+00:00
- Post Title: Killzone 2 - .core files bms script?

Well, finally. One of about 25 sub meshes of "intruder". Not much better than with auto created FIs (see above). Looks like another tri strips algo is required, had to erase dozens of superfluous faces:
.



intruder_10_finally.jpg (144.85 KiB) Viewed 89 times



H2O file (4th ? sub mesh):

0xE8670 8150
Vb1
20 99
0x1BA72 3294
121400
0x0 255

---------------
18th mesh, FVFsize= 14 at 0xBDE69, 2861 vertices
## Post #14
- Username: n1nonly1
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jan 30, 2022 10:40 pm
- Post datetime: 2022-09-17T22:36:26+00:00
- Post Title: Killzone 2 - .core files bms script?

[https://imgur.com/a/VS4yktB](https://imgur.com/a/VS4yktB)
(aerial view, face indice block starting 0xE8670)

from what im seeing here, i guess that each of the face indices groups are tied to different vertex groups, if you get what im saying (correct me if im wrong)
i will try to "match" the correct face indices to the correct vertex groups. Still, i guess its more complicated than that xD
by the way, do you have any idea of the cause of the deformation?
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-18T06:27:59+00:00
- Post Title: Killzone 2 - .core files bms script?

> Reply from n1nonly1 ↑Sun Sep 18, 2022 6:36 am at Sun Sep 18, 2022 6:36 am
>
> 
https://imgur.com/a/VS4yktB
(aerial view, face indice block starting 0xE8670)

from what im seeing here, i guess that each of the face indices groups are tied to different vertex groups, if you get what im saying (correct me if im wrong)Didn't care for vertex group so far. You'll need to be more specific.

> i will try to "match" the correct face indices to the correct vertex groups. Still, i guess its more complicated than that xD
Simply search for 010000000000000000000000000000000000 to give the intruder file a structure. 4th find: 0x1BA5D -> start of vertex block: 0x1BA72
You'll get 25 blocks that way. 
Now find the suiting face indices blocks. That's how I'd do it.

> by the way, do you have any idea of the cause of the deformation?Which "deformation"? The additional (wrong) faces? Similar problem as here, probably:

> Reply from shakotay2 ↑Wed Aug 31, 2022 11:48 pm at Wed Aug 31, 2022 11:48 pm
>
> 

As I wrote, slightly different tri strips algo required,  other than the one I use (but a, b read from data, not preset):

> Reply from shakotay2 ↑Sat Feb 27, 2016 7:12 am at Sat Feb 27, 2016 7:12 am
>
> 

Maybe the one from Noesis could do but the formula is lost in my notes/old PC, whatever.

(If you know python you could try it out for yourself using noesis.RPGEO_TRIANGLE_STRIP.)
nope, problem not solved:
.



TriStrips_prob.jpg (114.35 KiB) Viewed 68 times


Maybe I should remove the lots of doubles (1665) first?
(Or the indices are meant to be used differently, indirect or so?)
## Post #16
- Username: n1nonly1
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jan 30, 2022 10:40 pm
- Post datetime: 2022-10-03T13:27:33+00:00
- Post Title: Re: Killzone 2 - .core files bms script?

hello, been dead for a while, things popped up, so for now consider this post suspended

(other users may continue thread)
