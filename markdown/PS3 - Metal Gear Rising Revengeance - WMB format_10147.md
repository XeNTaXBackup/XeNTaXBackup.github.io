## Post #1
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2013-02-18T11:52:38+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

Hi all.
I used the script "dataunpack.bms" of aluigi to try to extract "Metal Gear Rising Revengeance" 3d models
because this game and "Bayonetta" seems to use the same compression system.

```
------------------------------
00001000 1476400    ba00d5.wmb
  0016a000 272        ba00d5.wta
  0016b000 61392      ba00d5.eff
  0017a000 5840       ba00d5_col.hkx
  0017b6d0 93         ba00d5_param.bxm
  0017b730 389        CutInfo.bxm
  0017b8c0 233207     ba00d5.bnk
  001b47c0 272        ba00d5_0000.mot
  001b48d0 360        ba00d5_0000_0_seq.bxm
  001b4a40 272        ba00d5_0001.mot
  001b4b50 272        ba00d5_0002.mot
  001b4c60 272        ba00d5_0003.mot
  001b4d70 272        ba00d5_0004.mot
  001b4e80 272        ba00d5_0005.mot

- 14 files found in 1 seconds
```


And then, the extracting a .dat file of "Bayonetta"

```
------------------------------
00000980 382112     pl0031.wmb
  0005de80 886348     pl0031.wtb
  00136500 22348      pl0031texA.wtb
  0013bc80 22348      pl0031texB.wtb
  00141400 22348      pl0031texC.wtb
  00146b80 360        pl0031_0_4.clp
  00146cf0 172        pl0031_0_4.clw
  00146da0 172        pl0031_1_4.clw
  00146e50 116        pl0031_2_4.clw
  00146ed0 228        pl0031_3_4.clw
  00146fc0 116        pl0031_4_4.clw
  00147040 116        pl0031_5_4.clw
  001470c0 116        pl0031_8_4.clw
  etc....

- 86 files found in 5 seconds
```

Well, using  wmb_exporter.exe with the .wmb of "Bayonetta", the conversion to. obj is simple but impossible to convert the
.wmb of "MGRR" .Using a hex editor the header is different, and it might be due to what the user "loridaz" says [in this post](http://forum.xentax.com/viewtopic.php?f=16&t=4059&p=48047&hilit=wmb#p48047).
The problem is I'm not coder and I can not prove it.





If someone has the solution, please do not hesitate to expose.
Thank you.

If you need more "information", you may request.

Note; 
The textures are in the .dtt files ( .etf & wtp) that are actually gtf files. You can use gtf2dds.exe. 
Many times these files contain multiple  gtf files. You can identify the header:
## Post #2
- Username: ratanegra
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-02-19T01:02:37+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

Can you send me a few model samples?
## Post #3
- Username: siro1987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 13, 2010 7:02 am
- Post datetime: 2013-02-23T05:18:55+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

So... no one is interested in this game?
and this's the sample I extracted from 360 image
[http://www.sendspace.com/file/l9vm27](http://www.sendspace.com/file/l9vm27)
## Post #4
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2013-02-25T21:05:02+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

I actually registered here because of this!
I'd LOVE to have these models.
I'm quite good at 3d modelling but I hardly know anything of "hacking" a game.

Is there any way I could help ?
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-02-26T01:37:53+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

Mariokart wrote a model script for xbox already and I got a texture extractor for the ps3. Texture quality on xbox is much better, ps3 version got shafted.
## Post #6
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-02-26T05:13:22+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from howfie
>
> Mariokart wrote a model script for xbox already and I got a texture extractor for the ps3. Texture quality on xbox is much better, ps3 version got shafted.

Can you share or pm me the texture extractor for PS3
i was attempting to make a .bms script for it
but after reading this and there is already something for it
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-02-26T06:00:53+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

I would wait for codeman to update his bayo tools. Very similar format... In one file there a list of offsets and at the bottom a list of 52-byte items where 2nd to last value determines texture dimensions. 940x940 xbox 512x512 ps3. Ps3 got shafted lol.
## Post #8
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2013-02-26T07:59:56+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

So now we just got to wait for a new toolset and then we can extract the models ?
## Post #9
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2013-02-26T16:30:44+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

By the way, was someone ever succesfull in extracting the models for metal gear solid 4 ?
## Post #10
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-02-26T20:42:05+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from howfie
>
> I would wait for codeman to update his bayo tools. Very similar format... In one file there a list of offsets and at the bottom a list of 52-byte items where 2nd to last value determines texture dimensions. 940x940 xbox 512x512 ps3. Ps3 got shafted lol.

what file are you refering too?
im only interested in the textures for PS3 ,dont have xbox lol
i can extract them manually with an hex editor but that just takes ages going to all those .dtt files
making a .bms script failed for me

i know the header of the .gtf contains the size(@ 0x20 from start of header 4 bytes long) of the .gtf + 0x80 bytes for the header so it would be easy for it to be implemented in a bms script
im just not that skilled in making them lol

so sharing/pming the extractor for textures is my best shot lol
## Post #11
- Username: rensole
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Feb 26, 2013 4:34 am
- Post datetime: 2013-02-27T06:19:15+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from darksoul
>
> howfie wrote:I would wait for codeman to update his bayo tools. Very similar format... In one file there a list of offsets and at the bottom a list of 52-byte items where 2nd to last value determines texture dimensions. 940x940 xbox 512x512 ps3. Ps3 got shafted lol.

what file are you refering too?
im only interested in the textures for PS3 ,dont have xbox lol
i can extract them manually with an hex editor but that just takes ages going to all those .dtt files
making a .bms script failed for me

i know the header of the .gtf contains the size(@ 0x20 from start of header 4 bytes long) of the .gtf + 0x80 bytes for the header so it would be easy for it to be implemented in a bms script
im just not that skilled in making them lol

so sharing/pming the extractor for textures is my best shot lol

And how could we extract the models ? (I'm kindof new to this so sorry).
Would I need special tools?
## Post #12
- Username: siro1987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 13, 2010 7:02 am
- Post datetime: 2013-03-10T01:46:44+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

Still no progress?
## Post #13
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-03-10T19:18:06+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

I was going to explore modding the game, but fell lazy of solving the rest of the structures.

credit goes to chrrox as to helping me discover the face info

Overview:
Files are archived in CRIware's CPK Container. I Used Luigi's BMS script to unpack the files -> [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Once files are unpacked you'll be seeing two common file extensions (*.DAT,*.DTT)

DAT is a general resource container and DTT from what I can tell is just a texture dump file. 
The xbox360 DTT has no headers, however the PS3 DTT has GTF headers. 
GTF is a PS3 format, there file structure is documented in the PS3 SDK literature.
I cannot post the structs from the SDK doc {illegal?}, but I'll be sharing the struct I had prior to finding the structs in the SDK

As for files within the DAT once unpacked, there is ALOT. I'll document only two; (WMB,WPA)
WMB is there model binary format, WTA, is an offset table that relates to the DTT file.

> Format for Xbox360: Data is Big Endian and all integers in are unsigned unless otherwise noted

DAT Format
Description:
you collect the count and the offsets, then jump to each table.
the tables hold basic info like file offset, file size, filename, file extension, etc..

you can then parse the DAT file and dump the containing files. 

> dat_header { // all offsets relative to begining of DAT header
>
> LONG file_count
>
> LONG offset_file_table
>
> LONG offset_extension_table
>
> LONG offset_name_table
>
> LONG offset_size_table
>
> LONG offset_unknown_data
>
> LONG null
>
> }
>
> 
>
> file_table { // n = file_count
>
> LONG[n] offset
>
> }
>
> 
>
> extension_table { // string length fixed at 4
>
> STRING file_ext // Example: "wmb", "wta", "bxm", "mot", "eff"
>
> }
>
> 
>
> name_table {
>
> LONG string_length
>
> }
>
> 
>
> name_table_entries { // n = string_length
>
> STRING name[n]
>
> }
>
> 
>
> size_table { // n = file_count
>
> LONG[n] size
>
> }
WMB Format ("WMB4" Only) "WonderfulModelBinary4"??
Description:
Gah O_o it would take alot of paragraphs to explain this so yeah PM me if you need specifics

Just bare in mind I didn't document all the tables, cause franky they'd just be a bunch of unknowns.. 
so still alot of work ahead for whom ever wants to continue it --vertex def is also incomplete

> wmb_header { // all offsets relative to begining of WMB header
>
> LONG magic "WMB4"
>
> LONG version // ? always -1
>
> SHORT vertex_stride // ? vertex stride 0x00 = 24 | 0x01 = 32
>
> SHORT ukn02
>
> SHORT primitive_type // 0x00=trilist | 0x01= trilist
>
> SHORT ukn03
>
> LONG ukn04
>
> LONG ukn05
>
> LONG ukn06
>
> LONG ukn07
>
> LONG ukn08
>
> LONG ukn09
>
> LONG buffer_table_offset // offset to vertex buffer header offset? lol
>
> LONG buffer_count
>
> LONG element_table_offset // offset to unknown data, after faces buffer
>
> LONG element_count
>
> LONG material_table_offset
>
> LONG bone_table_offset
>
> LONG bone_count
>
> LONG ukn17_offset
>
> LONG ukn17_count
>
> LONG ukn18_offset
>
> LONG ukn18_count
>
> LONG ukn19_offset // material related?
>
> LONG ukn19_count
>
> LONG ukn20_offset
>
> LONG ukn20_count
>
> LONG mesh_table_offset
>
> LONG mesh_count
>
> LONG ukn21_offset // offsets to another table, that then offsets to mesh names
>
> LONG ukn22 //always 0?
>
> LONG ukn23 //always 0?
>
> LONG ukn24 //always 0?
>
> LONG ukn25 //always 0?
>
> }
>
> 
>
> buffer_table {
>
> LONG vert_offset // offset to vertex buffer
>
> LONG ukn33 // offset to vertex colour buffer?
>
> LONG ukn34 // always 0?
>
> LONG ukn35 // always 0?
>
> LONG num_verts
>
> LONG face_offset
>
> LONG num_faces
>
> }
>
> 
>
> element_table {
>
> LONG buffer_index
>
> LONG vert_start
>
> LONG face_start
>
> LONG vert_count
>
> LONG face_count
>
> }
>
> 
>
> material_table {
>
> LONG ukn31_table_offset
>
> LONG count
>
> LONG ukn33
>
> LONG ukn34
>
> LONG ukn35
>
> LONG ukn36
>
> LONG ukn37
>
> LONG ukn38
>
> }
>
> 
>
> ukn31_table {
>
> LONG index
>
> LONG name_index
>
> SHORT ukn40
>
> SHORT ukn41
>
> LONG ukn42
>
> }

> vertex_def { // stride either 24 or 32, based off flag from WMB4 header? unconfirmed
>
> FLOAT32 pos_x
>
> FLOAT32 pos_x
>
> FLOAT32 pos_x
>
> FLOAT16 tex_u
>
> FLOAT16 tex_v
>
> }

WTA Format  "WonderfulTextureAddresses"??
Description:
I only document the header not the tables after, sorry.. but the tables are nearly self-explainitory

> wta_header { // all offsets relative to begining of WTA header
>
> LONG magic // "WTB"
>
> LONG version // ?
>
> LONG count
>
> LONG offset_texture_offsets
>
> LONG offset_texture_sizes
>
> LONG offset_flag_data
>
> LONG offset_file_hashes
>
> LONG offset_XPR2_headers
>
> }
Luigi's CPK BMS

```
#   derived from cpk_unpack of hcs (http://hcs64.com/vgm_ripping.html)
# script for QuickBMS http://quickbms.aluigi.org

quickbmsver 0.3.12
endian big
comtype cpk

idstring "CPK "

set query->offset long 0
set query->index long 0
set query->name string "TocOffset"
callfunction query_utf 1
set toc_offset long UTF_VALUE

set query->offset long 0
set query->index long 0
set query->name string "ContentOffset"
callfunction query_utf 1
set content_offset long UTF_VALUE

set query->offset long 0
set query->index long 0
set query->name string "Files"
callfunction query_utf 1
set CpkHeader_count long UTF_VALUE

goto toc_offset
getdstring signature 4
if signature != "TOC "
    print "TOC signature not found"
    cleanexit
endif

set query->offset long toc_offset
set query->index long 0
set query->name string ""
callfunction query_utf 1
set CpkHeader_count long UTF_VALUE
set toc_entries long table_info.rows    # it remains saved after the call

if content_offset < 0           # "if" can't be unsigned
    set add_offset long toc_offset
elif toc_offset < 0
    set add_offset long content_offset
elif content_offset < toc_offset
    set add_offset long content_offset
else
    set add_offset long toc_offset
endif

for mytoc = 0 < toc_entries
    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "DirName"
    callfunction query_utf 1
    set file_name string UTF_VALUE

    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "FileName"
    callfunction query_utf 1
    set file_name2 string UTF_VALUE

    string file_name += /
    string file_name += file_name2

    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "FileSize"
    callfunction query_utf 1
    set file_size long UTF_VALUE

    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "ExtractSize"
    callfunction query_utf 1
    set extract_size long UTF_VALUE

    set query->offset long toc_offset
    set query->index long mytoc
    set query->name string "FileOffset"
    callfunction query_utf 1
    set file_offset long UTF_VALUE

    math file_offset += add_offset
    if extract_size > file_size
        clog file_name file_offset file_size extract_size
    else
        log file_name file_offset file_size
    endif
next mytoc



startfunction query_utf
    set COLUMN_STORAGE_MASK        long 0xf0
    set COLUMN_STORAGE_PERROW      long 0x50
    set COLUMN_STORAGE_CONSTANT    long 0x30
    set COLUMN_STORAGE_ZERO        long 0x10
    set COLUMN_TYPE_MASK           long 0x0f
    set COLUMN_TYPE_DATA           long 0x0b
    set COLUMN_TYPE_STRING         long 0x0a
    set COLUMN_TYPE_FLOAT          long 0x08
    set COLUMN_TYPE_8BYTE2         long 0x07
    set COLUMN_TYPE_8BYTE          long 0x06
    set COLUMN_TYPE_4BYTE2         long 0x05
    set COLUMN_TYPE_4BYTE          long 0x04
    set COLUMN_TYPE_2BYTE2         long 0x03
    set COLUMN_TYPE_2BYTE          long 0x02
    set COLUMN_TYPE_1BYTE2         long 0x01
    set COLUMN_TYPE_1BYTE          long 0x00

    set UTF_VALUE string ""
    math offset = query->offset
    math offset += 0x10     # needed by the tool
    goto offset

    set table_info.table_offset long offset
    getdstring UTF_signature 4
    if UTF_signature != "@UTF"
        print "not a @UTF table at %offset%"
        cleanexit
    endif
    get table_info.table_size long
    set table_info.schema_offset long 0x20
    get table_info.rows_offset long
    get table_info.string_table_offset long
    get table_info.data_offset long
    get table_name_string long
    get table_info.columns short
    get table_info.row_width short
    get table_info.rows long

    for i = 0 < table_info.columns
        get schema.type byte
        get schema.column_name long
        putarray 0 i schema.type
        putarray 1 i schema.column_name
        putarray 2 i -1     # schema.constant_offset

        math TMP = schema.type
        math TMP &= COLUMN_STORAGE_MASK
        if TMP == COLUMN_STORAGE_CONSTANT
            savepos schema.constant_offset
            putarray 2 i schema.constant_offset

            math TMP = schema.type
            math TMP &= COLUMN_TYPE_MASK
            if TMP == COLUMN_TYPE_STRING
                getdstring DUMMY 4
            elif TMP == COLUMN_TYPE_DATA
                getdstring DUMMY 8
            elif TMP == COLUMN_TYPE_FLOAT
                getdstring DUMMY 4
            elif TMP == COLUMN_TYPE_8BYTE2
                getdstring DUMMY 8
            elif TMP == COLUMN_TYPE_8BYTE
                getdstring DUMMY 8
            elif TMP == COLUMN_TYPE_4BYTE2
                getdstring DUMMY 4
            elif TMP == COLUMN_TYPE_4BYTE
                getdstring DUMMY 4
            elif TMP == COLUMN_TYPE_2BYTE2
                getdstring DUMMY 2
            elif TMP == COLUMN_TYPE_2BYTE
                getdstring DUMMY 2
            elif TMP == COLUMN_TYPE_1BYTE2
                getdstring DUMMY 1
            elif TMP == COLUMN_TYPE_1BYTE
                getdstring DUMMY 1
            else
                print "unknown type for constant"
                cleanexit
            endif
        endif
    next i

    math TMP = table_info.string_table_offset
    math TMP += 8
    math TMP += offset
    math string_table_size = table_info.data_offset
    math string_table_size -= table_info.string_table_offset
    log MEMORY_FILE TMP string_table_size

    for i = query->index < table_info.rows
        math TMP = i
        math TMP *= table_info.row_width
        math row_offset = table_info.table_offset
        math row_offset += 8
        math row_offset += table_info.rows_offset
        math row_offset += TMP

        for j = 0 < table_info.columns
            getarray type 0 j
            getarray column_name 1 j
            getarray constant_offset 2 j

            if constant_offset >= 0
                math data_offset = constant_offset
            else
                math data_offset = row_offset
            endif

            math TMP = type
            math TMP &= COLUMN_STORAGE_MASK
            if TMP == COLUMN_STORAGE_ZERO
                set value long 0
            else
                goto data_offset
                math TMP = type
                math TMP &= COLUMN_TYPE_MASK
                if TMP == COLUMN_TYPE_STRING
                    get string_offset long
                    goto string_offset MEMORY_FILE
                    get value string MEMORY_FILE
                elif TMP == COLUMN_TYPE_DATA
                    get vardata_offset long
                    get vardata_size long
                    goto vardata_offset MEMORY_FILE
                    getdstring value vardata_size MEMORY_FILE
                elif TMP == COLUMN_TYPE_FLOAT
                    get value long
                elif TMP == COLUMN_TYPE_8BYTE2
                    get DUMMY long  # no 64 bit support!
                    get value long
                elif TMP == COLUMN_TYPE_8BYTE
                    get DUMMY long  # no 64 bit support!
                    get value long
                elif TMP == COLUMN_TYPE_4BYTE2
                    get value long
                elif TMP == COLUMN_TYPE_4BYTE
                    get value long
                elif TMP == COLUMN_TYPE_2BYTE2
                    get value short
                elif TMP == COLUMN_TYPE_2BYTE
                    get value short
                elif TMP == COLUMN_TYPE_1BYTE2
                    get value byte
                elif TMP == COLUMN_TYPE_1BYTE
                    get value byte
                else
                    print "unknown normal type"
                    cleanexit
                endif

                if constant_offset < 0
                    savepos row_offset  # row_offset += bytes_read
                endif
            endif

            goto column_name MEMORY_FILE
            get column_name string MEMORY_FILE
            if column_name == query->name
                set UTF_VALUE string value  # result.value.value (qthis)
                math i = table_info.rows    # break
                math j = table_info.columns # break
            endif
        next j
    next i
endfunction

```

My MaxScript

```
caption:"Select a File" \
types: "All files (*.*)|*.dat|"

delete $*

tristrip = false


fn readBElong fstream = (bit.swapBytes (bit.swapBytes (readlong fstream #unsigned) 1 4) 2 3)
fn readBEshort fstream = (bit.swapBytes (readshort fstream #unsigned) 1 2)
fn readBEtriplet fstream = (((readbyte f #unsigned)*0x00010000)+((readbyte f #unsigned)*0x00000100)+((readbyte f #unsigned)*0x00000001))
fn ReadBEfloat fstream = (
bit.intAsFloat (bit.swapBytes (bit.swapBytes (readlong fstream #unsigned) 1 4) 2 3)
)
fn readBEHalfFloat fstream = (
hf=bit.swapBytes (readshort fstream #unsigned) 1 2
sign = bit.get hf 16
exponent = (bit.shift (bit.and hf (bit.hexasint "7C00")) -10) as integer - 16
fraction = bit.and hf (bit.hexasint "03FF")
if sign==true then sign = 1 else sign = 0
exponentF = exponent + 127
outputAsFloat = bit.or (bit.or (bit.shift fraction 13) \
(bit.shift exponentF 23)) (bit.shift sign 31)
return bit.intasfloat outputasfloat*2)
fn readFixedString bstream fixedLen = (
local str = ""
for i = 1 to fixedLen do (
str += bit.intAsChar (ReadByte bstream #unsigned))
str
)
fn writeBElong fstream num = (
writelong fstream (bit.swapBytes (bit.swapBytes (num) 1 4) 2 3) #unsigned)
fn paddstring len instring = (
instring=instring as string
local str="";if instring.count <=len then(
for i = 1 to (len-instring.count) do(str+="0")
str = (str+instring))else(
for i = 1 to len do(str+="0";str[i]=instring[i]));str
)
fn uppercase instring = (
local upper, lower, outstring
upper="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
lower="abcdefghijklmnopqrstuvwxyz"
outstring=copy instring
for i=1 to outstring.count do (
j=findString lower outstring[i]
if (j != undefined) do outstring[i]=upper[j])
outstring)
fn printblockpos bname badr = (
str=((bit.intAsHex badr)as string)
if str[str.count]=="L" do(str = substring str 1 (str.count-1))
format "% @ 0xDD%\n" bname (paddstring 6 (uppercase str))
)
fn printblockpos bname badr = (
str=((bit.intAsHex badr)as string)
if str[str.count]=="L" do(str = substring str 1 (str.count-1))
format "% @ 0x%\n" bname (paddstring 8 (uppercase str))
)
fn writeDDSheader fstream texW texH texM texC = (
texP=0
writelong fstream 0x20534444 #unsigned -- File ID
writelong fstream 0x7C #unsigned -- Header Size
case of( -- dwFlags
(texC==#DXT1): (writelong fstream 0x00081007 #unsigned;texP=((texW*texH)/0x02))
(texC==#DXT3): (writelong fstream 0x00081007 #unsigned;texP=(texW*texH))
(texC==#DXT5): (writelong fstream 0x00081007 #unsigned;texP=(texW*texH))
(texC==#ATI1): (writelong fstream 0x000A1007 #unsigned;texP=((texW*texH)/0x20))
(texC==#ATI2): (writelong fstream 0x000A1007 #unsigned;texP=(texW*texH))
(texC==#P8): (writelong fstream 0x000A1007 #unsigned;texP=((texW*texH)/0x02))
(texC==#ARGB16): (writelong fstream 0x00081007 #unsigned;texP=(((texW*texH)/0x8)*0x10))
(texC==#ARBG32): (writelong fstream 0x00081007 #unsigned;texP=(((texW*texH)/0x4)*0x10)))
writelong fstream texW #unsigned -- Texture Width
writelong fstream texH #unsigned -- Texture Height
writelong fstream texP #unsigned -- Pitch (#of bytes in a single row across the texture)
writelong fstream 0x00 #unsigned -- Image Depth? Not Used, for Image Volume
writelong fstream texM #unsigned -- Texture MIP Count
for i = 1 to 11 do writelong fstream 0x00 #unsigned -- Reserved Space
writelong fstream 0x20 #unsigned -- Size of PIXEL_FORMAT info, always 32bytes;
case of(
(texC==#DXT1): (writelong fstream 0x04;writelong fstream 0x31545844 #unsigned
writelong s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writelong fstream 0x00001000 #unsigned)
(texC==#DXT3): (writelong fstream 0x04;writelong fstream 0x33545844 #unsigned
writelong s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00001000 #unsigned)
(texC==#DXT5): (writelong fstream 0x04;writelong fstream 0x35545844 #unsigned
writelong fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00001000 #unsigned)
(texC==#ATI1): (writelong fstream 0x04;writelong fstream 0x31495441 #unsigned
writelong fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00401008 #unsigned)
(texC==#ATI2): (writelong fstream 0x04;writelong fstream 0x32495441 #unsigned
writelong fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00401008 #unsigned)
(texC==#P8): (writelong fstream 0x20;writelong fstream 0x20203850 #unsigned
writelong fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00401008 #unsigned)
(texC==#ARGB16): (writelong fstream 0x41;writelong fstream 0x00000000 #unsigned
writelong fstream 0x10;writebyte fstream 0x00;writebyte fstream 0x0F;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0xF0;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x0F;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0xF0;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00001000 #unsigned)
(texC==#ARBG32): (writelong fstream 0x41;writelong fstream 0x00000000 #unsigned
writelong fstream 0x20;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0xFF
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0xFF;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0xFF;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0xFF;writelong fstream 0x00001000 #unsigned))
for i = 1 to 4 do writelong fstream 0x00 #unsigned -- Reserved Space for CAPS
)
fn Get_PS3FORMAT id = (
case id of ( -- replaced a few from offical ones, for backwards compatiblity
0x86: #DXT1
0x88: #DXT5
default: #UNKNOWN
)
)

if (fsource!=undefined) then (
fpath=getFilenamePath fsource
fname=getFilenameFile fsource
fsize=getFileSize fsource
fext=getFilenameType fsource
if ((doesFileExist fsource)==true) then (
clearlistener ()
f = fopen fsource "rb"



struct package_resource (offset,type,name,size,data)
struct model_binary_4 (header,buffer,element,skeleton,ukn10,ukn11,material,ukn12,mesh)
struct model_binary_4_header (magic,ukn01,ukn02,ukn03,ukn04,ukn05,info,ukn06,ukn07,ukn08,ukn09)
struct offset_and_count (offset,count)
datArray = (package_resource \
	offset:#() \
	type:#() \
	name:#() \
	size:#() \
	data:#())

case (readFixedString f 4) of (
"DAT":(
dat_offsets = #()

dat_01 = readBElong f -- count: files
dat_02 = readBElong f -- offset: offset table
dat_03 = readBElong f -- offset: extension table
dat_04 = readBElong f -- offset: name table
dat_05 = readBElong f -- offset: size table
dat_06 = readBElong f -- offset: ?? unknown data
dat_07 = readBElong f -- Blank? Reserved?

fseek f dat_02 #seek_set
for i = 1 to dat_01 do (datArray.offset[i] = readBElong f)
fseek f dat_03 #seek_set
for i = 1 to dat_01 do (datArray.type[i] = uppercase (readFixedString f 4))
fseek f dat_04 #seek_set;str_len = readBElong f
for i = 1 to dat_01 do (datArray.name[i] = readFixedString f str_len)
fseek f dat_05 #seek_set
for i = 1 to dat_01 do (datArray.size[i] = readBElong f)
for i = 1 to dat_01 do (datArray.data[i] = #())
for d = 1 to dat_01 do (
fseek f datArray.offset[d] #seek_set
case datArray.type[d] of (
"WTA":(
ukn00 = readBElong f -- "WTB"
ukn01 = readBElong f -- version?
ukn02 = readBElong f -- count
ukn03 = (readBElong f)+datArray.offset[d] -- offset to texture offsets
ukn04 = (readBElong f)+datArray.offset[d] -- offset to texture sizes
ukn05 = (readBElong f)+datArray.offset[d] -- offset to flag data?
ukn06 = (readBElong f)+datArray.offset[d] -- offset to file hashes?
ukn07 = (readBElong f)+datArray.offset[d] -- offset to XPR2 headers


fn stringtobytes str fstream= (
str = str as string
for t = 1 to 24 do (
if t<=str.count then (
writebyte fstream (bit.charAsInt str[t]) #unsigned
)else(writebyte fstream 0)
)
)
	


for i = 1 to ukn02 do (
g = fopen (fpath+fname+".dtt") "rb"
s = fopen (fpath+fname+(paddstring 3 (i as string))+".xpr") "wb"

fseek f (ukn03+((i-1)*4)) #seek_set
pos = readBElong f
fseek f (ukn04+((i-1)*4)) #seek_set
dumpsize = readBElong f

fseek g (pos+0x1000) #seek_set

writeBElong s 0x58505232
writeBElong s 0x00000800
writeBElong s dumpsize
writeBElong s 0x00000001
writeBElong s 0x54583244
writeBElong s 0x00000030
writeBElong s 0x00000034
writeBElong s 0x00000018
writeBElong s 0x00000000
stringtobytes (fname+(paddstring 3 (i as string))) s
fseek f (ukn07+((i-1)*(4*13))) #seek_set
for x = 1 to (4*11) do (writebyte s (readbyte f #unsigned) #unsigned)
writeBElong s 0x00000000
writeBElong s 0x00000A00
for x = 1 to 1948 do (writebyte s 0)
for x = 1 to dumpsize do (writebyte s (readbyte g #unsigned) #unsigned)

fclose s
fclose g
)
)
"WTA (PS3)":( -- disabled
ukn00 = readBElong f -- "WTB"
ukn01 = readBElong f -- version?
ukn02 = readBElong f -- count
ukn03 = (readBElong f)+datArray.offset[d] -- offset to texture offsets
ukn04 = (readBElong f)+datArray.offset[d] -- offset to texture sizes
ukn05 = (readBElong f)+datArray.offset[d] -- offset to flag data?
ukn06 = (readBElong f)+datArray.offset[d] -- offset to file hashes?
ukn07 = (readBElong f)+datArray.offset[d] -- offset to XPR2 headers

for i = 1 to ukn02 do (
ssource = (fpath+fname+".dtt")
if ((doesFileExist ssource)==true) then (
g = fopen ssource "rb"
s = fopen (fpath+fname+(paddstring 3 (i as string))+".dds") "wb"
fseek f (ukn03+((i-1)*4)) #seek_set;pos = readBElong f
fseek f (ukn04+((i-1)*4)) #seek_set;dumpsize = readBElong f
fseek g (pos+0x1000) #seek_set
struct gft_header (
magic, -- "0x02010100" Version, possibly a fourcc
streamsize,
num_textures, -- forced to 1? :-P
ukn02, -- always 0?
stream_offset,
ukn03, -- offsets to end of stream?
d3d_format, -- fourCC, probably describes d3d compression
ukn04, --offset?
height,
width,
depth,
ukn05, -- always 0?
null -- reserved space
)
gftArray = (gft_header \
magic:(readBElong g) \
streamsize:(readBElong g) \
num_textures:(readBElong g) \
ukn02:(readBElong g) \
stream_offset:(readBElong g) \
ukn03:(readBElong g) \
d3d_format:([(readbyte g #unsigned),(readbyte g #unsigned),(readbyte g #unsigned),(readbyte g #unsigned)]) \
ukn04:(readBElong g) \ --remap?
height:(readBEshort g) \
width:(readBEshort g) \
depth:(readBEshort g) \
ukn05:(readBEshort g) \
null:#() \
);fseek g 88 #seek_cur
format "%: (% x %) \tFormat:%\n" (paddstring 3 i) (paddstring 4 gftArray.width) (paddstring 4 gftArray.height) gftArray.d3d_format
writeDDSheader s gftArray.width gftArray.height 1 (Get_D3DFORMAT gftArray.d3d_format[1])
for x = 1 to dumpsize do (writebyte s (readbyte g #unsigned) #unsigned)

fclose s
fclose g
)else(messagebox "failed to find relating dtt file")
)
)
"WMB":(magic = uppercase (readFixedString f 4)
case magic of (
"WMB4":(


ukn01 = readBElong f -- always -1
ukn02a = readBEshort f -- vertex stride?: 0x00 = 24 | 0x01 = 32
ukn02b = readBEshort f
ukn03a = readBEshort f -- primitive type flag 0x00=trilist | 0x01= trilist
ukn03b = readBEshort f
ukn04 = readBElong f
ukn05 = readBElong f
ukn06 = readBElong f
ukn07 = readBElong f
ukn08 = readBElong f
ukn09 = readBElong f

ukn10 = (readBElong f)+datArray.offset[d] -- offset to vertex buffer header offset? lol

ukn11 = readBElong f -- unknown count?

ukn12 = (readBElong f)+datArray.offset[d] -- offset to unknown data, after faces buffer
ukn13 = readBElong f

ukn14 = (readBElong f)+datArray.offset[d]

ukn15 = (readBElong f)+datArray.offset[d]
ukn16 = readBElong f

ukn17 = (readBElong f)+datArray.offset[d]
ukn18 = readBElong f

ukn19 = (readBElong f)+datArray.offset[d]
ukn20 = readBElong f

ukn21 = (readBElong f)+datArray.offset[d]
ukn22 = readBElong f

ukn23 = (readBElong f)+datArray.offset[d]
ukn24 = readBElong f

ukn25 = (readBElong f)+datArray.offset[d]
ukn26 = readBElong f

ukn27 = (readBElong f)+datArray.offset[d] -- offsets to another table, that then offsets to mesh names

ukn28 = readBElong f -- always 0?
ukn29 = readBElong f -- always 0?
ukn30 = readBElong f -- always 0?
ukn31 = readBElong f -- always 0?




bufferArray = #()
printblockpos ("Mesh/Buffer Table: ("+(ukn11 as string)+")") ukn10
fseek f ukn10 #seek_set
for i = 1 to ukn11 do (
vert_offset = (readBElong f)+datArray.offset[d] -- offset to vertex buffer
ukn33 = (readBElong f)+datArray.offset[d] -- offset to colour buffer
ukn34 = readBElong f -- always 0?
ukn35 = readBElong f -- always 0?
num_verts = readBElong f
face_offset = (readBElong f)+datArray.offset[d]
num_faces = readBElong f -- count
bufferArray[i]=[num_verts,num_faces,vert_offset,face_offset]
printblockpos "Vert" vert_offset
printblockpos "Face" face_offset	
)
printblockpos "\tMesh/Buffer Table END" (ftell f);format "\n"

printblockpos "Buffers" (bufferArray[1][3]);format "\n"




printblockpos ("Element Table: ("+(ukn13 as string)+")") ukn12
fseek f ukn12 #seek_set
struct element (buffer_index,vert_start,face_start,vert_count,face_count)
mshArray=(element buffer_index:#() vert_start:#() face_start:#() vert_count:#() face_count:#())
for i = 1 to ukn13 do (
mshArray.buffer_index[i] = (readBElong f)+1 -- buffer index
mshArray.vert_start[i] = readBElong f -- vert start
mshArray.face_start[i] = readBElong f -- face start
mshArray.vert_count[i] = readBElong f -- vert count
mshArray.face_count[i] = readBElong f -- face count
format "%\n" mshArray.buffer_index[i]
)
printblockpos "\tElement Table END" (ftell f);format "\n"


fseek f ukn14 #seek_set
ukn31 = (readBElong f)+datArray.offset[d]
ukn32 = readBElong f -- count
ukn33 = readBElong f -- always 0?
ukn34 = readBElong f -- always 0?
ukn35 = readBElong f -- always 0?
ukn36 = readBElong f -- always 0?
ukn37 = readBElong f -- always 0?
ukn38 = readBElong f -- always 0?
printblockpos ("Material Names?: ("+(ukn32 as string)+")") ukn14
fseek f ukn31 #seek_set
for i = 1 to ukn32 do (
ukn38 = readBElong f -- index
ukn39 = readBElong f -- indexing to name
ukn40a = readBEshort f -- flag?
ukn40b = readBEshort f -- flag?
ukn41 = readBElong f -- always 0x00 01 00 00 ?
format "% | % | % | %\n" ukn39 ukn39 ukn40a ukn40b
)
printblockpos "\tMaterial Names? END" (ftell f);format "\n"


printblockpos ("Bones: ("+(ukn16 as string)+")") ukn15
fseek f ukn15 #seek_set
for i = 1 to ukn16 do ( -- bones?
ukn42 = readBEshort f -- ???
ukn43 = readBEshort f -- ???
ukn44 = readBEshort f -- parent
ukn45 = readBEshort f -- always 0?
ukn46 = readBEfloat f -- position?
ukn47 = readBEfloat f
ukn48 = readBEfloat f
ukn49 = readBEfloat f
ukn50 = readBEfloat f
ukn51 = readBEfloat f
)
printblockpos "\tBones END" (ftell f);format "\n"

printblockpos ("Block5: ("+(ukn18 as string)+")") ukn17
fseek f ukn17 #seek_set
for i = 1 to ukn18 do (
ukn52 = readbyte f #unsigned --? float, divide by 0xFF
)
printblockpos "\tBlock5 END" (ftell f);format "\n"

printblockpos ("Block6: ("+(ukn20 as string)+")") ukn19
fseek f ukn19 #seek_set
tempArray = #()
for i = 1 to ukn20 do (
ukn53 = (readBElong f)+datArray.offset[d]
ukn54a = readbyte f #unsigned -- count
ukn54b = readbyte f #unsigned -- 0?
ukn54c = readbyte f #unsigned -- 0?
ukn54d = readbyte f #unsigned -- 0?
tempArray[i] = [ukn53,ukn54a]
)
for i = 1 to ukn20 do (
fseek f tempArray[i][1] #seek_set
for x = 1 to tempArray[i][2] do (
ukn57 = readbyte f #unsigned -- indexes
)
)
printblockpos "\tBlock6 END" (ftell f);format "\n"

printblockpos ("Material Table?: ("+(ukn22 as string)+")") ukn21
fseek f ukn21 #seek_set
for i = 1 to ukn22 do (
ukn58 = (readBElong f)+datArray.offset[d] -- offset to string
ukn59 = (readBElong f)+datArray.offset[d] -- offset to stuff after string
ukn60 = readBElong f -- always 0?
ukn61 = (readBElong f)+datArray.offset[d] -- offset to matrix data?
ukn62 = readBEshort f
ukn63 = readBEshort f
ukn64 = readBEshort f
ukn65 = readBEshort f -- string count
)
printblockpos "\tMaterial Table? END" (ftell f);format "\n"

printblockpos ("Block8: ("+(ukn24 as string)+")") ukn23
fseek f ukn23 #seek_set
for i = 1 to ukn24 do (
ukn66 = readBElong f -- count?
ukn67 = readBElong f -- float or hash?
)
printblockpos "\tBlock8 END" (ftell f);format "\n"

printblockpos ("Mesh Properties: ("+(ukn26 as string)+")") ukn25
pos = ukn25
nameArray=#()
for i = 1 to ukn26 do (
fseek f pos #seek_set
ukn68 = (readBElong f)+datArray.offset[d] -- offset to name
ukn69 = readBEfloat f -- position ?
ukn70 = readBEfloat f
ukn71 = readBEfloat f
ukn72 = readBEfloat f -- rotation ?
ukn73 = readBEfloat f
ukn74 = readBEfloat f
ukn75 = (readBElong f)+datArray.offset[d] -- offset to index data that comes after name
ukn76 = readBElong f -- count for above offset
ukn77 = readBElong f -- 0?
ukn78 = readBElong f -- 0?
ukn79 = readBElong f -- 0?
ukn80 = readBElong f -- 0?
ukn81 = readBElong f -- 0?
ukn82 = readBElong f -- 0?
ukn83 = (readBElong f)+datArray.offset[d] -- offset to index data that comes after name
ukn84 = readBElong f -- count for above offset
pos = ftell f
fseek f ukn68 #seek_set
mshName = (readstring f);print mshName
append nameArray mshName
fseek f ukn75 #seek_set
for x = 1 to ukn76 do (
ukn85 = (readBEshort f)+1
)
fseek f ukn83 #seek_set
for x = 1 to ukn84 do (
ukn86 = (readBEshort f)+1
)
)
printblockpos "\tBlock9 END" (ftell f);format "\n"


if ukn03a == 1 do (tristrip = true)
-- ukn13=0 --ignore faces
for i = 1 to ukn13 do (
vertArray=#()
normArray=#()
uvwArray=#()
faceArray=#()
matidArray=#()


num_verts=mshArray.vert_count[i] --bufferArray[(mshArray.buffer_index[i])][1]
num_faces=mshArray.face_count[i] --bufferArray[(mshArray.buffer_index[i])][2]

-- num_verts=bufferArray[(mshArray.buffer_index[i])][1]
-- num_faces=bufferArray[(mshArray.buffer_index[i])][2]

vert_offset=bufferArray[(mshArray.buffer_index[i])][3]
face_offset=bufferArray[(mshArray.buffer_index[i])][4]
-- stride = ((face_offset-vert_offset)/num_verts) as integer
-- format "Calculated Stride: %\n" stride
case ukn02a of (
0x00:(stride = 24)
0x01:(stride = 32)
default:(stride = 32;format "New Stride: %\n" ukn02a)
)
stride = 32

vert_offset+=mshArray.vert_start[i]*stride
face_offset+=mshArray.face_start[i]*2





fseek f vert_offset #seek_set
for x = 1 to num_verts do (
pos = (ftell f)+stride
vx = ReadBEfloat f
vy = ReadBEfloat f
vz = ReadBEfloat f
tu = readBEHalfFloat f
tv = readBEHalfFloat f
-- nx = ReadBEfloat f
-- ny = ReadBEfloat f
-- nz = ReadBEfloat f
-- b1 = readbyte f #unsigned
-- b2 = readbyte f #unsigned
-- b3 = readbyte f #unsigned
-- b4 = readbyte f #unsigned
-- w1 = (readbyte f #unsigned)/255.0
-- w2 = (readbyte f #unsigned)/255.0
-- w3 = (readbyte f #unsigned)/255.0
-- w4 = (readbyte f #unsigned)/255.0
append vertArray ([vx,-vz,vy]*100)
append uvwArray [tu,(1-tv),0]
fseek f pos #seek_set
)






fseek f face_offset #seek_set

format "% Faces % + % @ 0x%\n" i num_faces num_verts ((bit.intAsHex(ftell f))as string)


fa=fb=fc=1
face_flip = false
face_reset = true
face_add = 1
if tristrip == true then (

x=1;while x<= num_faces do (x+=1
if face_reset == true then (
x+=2;face_reset=false;face_flip = false;append matidArray i
fa = (ReadBEshort f) + face_add
fb = (ReadBEshort f) + face_add
fc = (ReadBEshort f) + face_add
if face_flip == true then (append faceArray [fa,fb,fc];face_flip=false)
else(append faceArray [fa,fc,fb];face_flip=true)
)else(fa = fb;fb = fc;fc = ReadBEshort f
if fc!=0xFFFF then (fc += face_add;append matidArray i
if face_flip == true then (append faceArray [fa,fb,fc];face_flip=false)
else(append faceArray [fa,fc,fb];face_flip=true)
)else(face_reset=true)
)
)

)else(

for x = 1 to (num_faces/3) do (
fa = (ReadBEshort f) + face_add
fb = (ReadBEshort f) + face_add
fc = (ReadBEshort f) + face_add
faceArray[x]=[fa,fc,fb]
matidArray[x]=i
)

)

-- while IndexCounter !=num_faces
format "\t\t\t\t\tFaceEnd @ 0x%\n" ((bit.intAsHex(ftell f))as string)


-- faceArray=#()
msh = mesh vertices:vertArray tverts:uvwArray faces:faceArray --materialIDs:matidArray
buildTVFaces msh
-- msh.name = nameArray[i]
msh.material = multimaterial numsubs:ukn13
msh.displayByLayer = false
msh.backfacecull = on
msh.wirecolor = random (color 0 0 0) (color 255 255 255)
-- convertTo msh PolyMeshObject
-- select msh
-- subobjectLevel = 1
for j = 1 to uvwArray.count do setTVert msh j uvwArray[j]
for j = 1 to faceArray.count do setTVFace msh j faceArray[j]
for j = 1 to msh.material.count do (msh.material.materialList[j].Diffuse = random (color 0 0 0) (color 255 255 255))
)





















)
default:(printblockpos ("WMB Not Supported: "+magic) datArray.offset[d])
)
)
default:(printblockpos ("Type Unknown: "+datArray.type[d]) datArray.offset[d])
)
)
)
default:(format "File Unknown: %\n" (magic as string))
)
format "Last Read @ 0x%\n" ((bit.intAsHex(ftell f))as string)
format "Flie Closed: %\n" fname
fclose f
) else (Print "Failed to Locate File")) else (Print "Aborted.")

```
## Post #14
- Username: yanneric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 30, 2011 6:15 am
- Post datetime: 2013-03-10T22:37:44+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

really impressive, great job and thanks for explanations...
## Post #15
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-13T06:43:10+00:00
- Post Title: PS3 - Metal Gear Rising Revengeance - WMB format

lol @mariokart
i almost ate up all my popcorn reading that facepunch thread.
u would think after all stuff that happened with chrrox over there u'd think twice about posting there hahaha.
## Post #16
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2013-03-13T07:14:13+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

How i can extract iso from xbox 360? What program?
## Post #17
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-13T07:18:42+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

google xbox iso extractor
## Post #18
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2013-03-13T07:26:18+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from howfie
>
> google xbox iso extractor

Very nice answer, but i cant extract new isos XDG3.
## Post #19
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-13T07:35:31+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

i just googled those exact terms. first link on google, works for me.
## Post #20
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2013-03-13T09:11:26+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from howfie
>
> i just googled those exact terms. first link on google, works for me.

Ok...very thanks... i did find now...
## Post #21
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2013-03-13T10:19:48+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

How i can take textures from xbox360?
## Post #22
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-13T14:31:58+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from logansan25
>
> How i can take textures from xbox360?

Mario's Script extracts some xpr. Just use chrrox xpr script for noesis and you're done.
## Post #23
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2013-03-13T14:44:09+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from Darko
>
> logansan25 wrote:How i can take textures from xbox360?

Mario's Script extracts some xpr. Just use chrrox xpr script for noesis and you're done.

Where are this script?
## Post #24
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-13T17:06:59+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from logansan25
>
> Darko wrote:logansan25 wrote:How i can take textures from xbox360?

Mario's Script extracts some xpr. Just use chrrox xpr script for noesis and you're done.

Where are this script?

Here:

[viewtopic.php?f=18&t=8102&p=65649&hilit ... ipt#p65649](http://forum.xentax.com/viewtopic.php?f=18&t=8102&p=65649&hilit=noesis+xpr+script#p65649)

Using the search tool doesn't harm... Oh well I did the same things here before.
## Post #25
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-03-13T17:07:28+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

So, if I understand well, the script mariokart posted works with 360 files, right?
## Post #26
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-13T17:08:04+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from RunaWhite
>
> So, if I understand well, the script mariokart posted works with 360 files, right?

Yep.
## Post #27
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-03-13T17:09:09+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

Awesome  will try them soon!
## Post #28
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2013-03-13T17:32:50+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from Darko
>
> RunaWhite wrote:So, if I understand well, the script mariokart posted works with 360 files, right?

Yep.

Lol... very thanks...
## Post #29
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-03-14T04:29:31+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

Wanted to read in the skinning info so had another run through the unknown blocks. found the bones, and alot of indexing data. I'm going to assume they are weight tables for the skinning
I'm heading to bed, but I'll try to read in the weights and apply them when I get time later this weekend




also someone asked about PS3 textures, I just trimmed up my xbox360 one and added dds export for any GTF headers

```
fsource = "D:\\_3DMODELS\\Ripped\\Metal Gear Rising Revengeance\\data000\\em\\em0044.dat"
fsource = "D:\\_3DMODELS\\Ripped\\Metal Gear Rising Revengeance\\data000\\pl3005.dat"
fsource = "D:\\_3DMODELS\\Ripped\\Metal Gear Rising Revengeance\\data000\\em\\em0100.dat"
fsource = "D:\\_3DMODELS\\Ripped\\Metal Gear Rising Revengeance\\data000\\em\\em0110.dat"
-- fsource = "D:\\_3DMODELS\\Ripped\\Metal Gear Rising Revengeance\\data000\\wp\\wp0040.dat"
fsource = "D:\\_3DMODELS\\Ripped\\Metal Gear Rising Revengeance\\data000\\em\\em0110.dat"
-- fsource = "D:\\_3DMODELS\\Ripped\\Metal Gear Rising Revengeance\\data000\\em\\em0110.dtt"
fsource = "D:\\_3DMODELS\\Ripped\\Metal Gear Rising Revengeance\\data000\\Mistral\\tx\\em0110.dat"
fsource = "D:\\_3DMODELS\\Ripped\\Metal Gear Rising Revengeance\\data000\\ps3\\em014a.dat"



fsource = GetOpenFileName \
caption:"Select a File" \
types: "All files (*.*)|*.dat|"

delete $*

tristrip = false


fn readBElong fstream = (bit.swapBytes (bit.swapBytes (readlong fstream #unsigned) 1 4) 2 3)
fn readBEshort fstream = (bit.swapBytes (readshort fstream #unsigned) 1 2)
fn readBEtriplet fstream = (((readbyte f #unsigned)*0x00010000)+((readbyte f #unsigned)*0x00000100)+((readbyte f #unsigned)*0x00000001))
fn ReadBEfloat fstream = (
bit.intAsFloat (bit.swapBytes (bit.swapBytes (readlong fstream #unsigned) 1 4) 2 3)
)
fn readBEHalfFloat fstream = (
hf=bit.swapBytes (readshort fstream #unsigned) 1 2
sign = bit.get hf 16
exponent = (bit.shift (bit.and hf (bit.hexasint "7C00")) -10) as integer - 16
fraction = bit.and hf (bit.hexasint "03FF")
if sign==true then sign = 1 else sign = 0
exponentF = exponent + 127
outputAsFloat = bit.or (bit.or (bit.shift fraction 13) \
(bit.shift exponentF 23)) (bit.shift sign 31)
return bit.intasfloat outputasfloat*2)
fn readFixedString bstream fixedLen = (
local str = ""
for i = 1 to fixedLen do (
str += bit.intAsChar (ReadByte bstream #unsigned))
str
)
fn writeBElong fstream num = (
writelong fstream (bit.swapBytes (bit.swapBytes (num) 1 4) 2 3) #unsigned)
fn paddstring len instring = (
instring=instring as string
local str="";if instring.count <=len then(
for i = 1 to (len-instring.count) do(str+="0")
str = (str+instring))else(
for i = 1 to len do(str+="0";str[i]=instring[i]));str
)
fn uppercase instring = (
local upper, lower, outstring
upper="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
lower="abcdefghijklmnopqrstuvwxyz"
outstring=copy instring
for i=1 to outstring.count do (
j=findString lower outstring[i]
if (j != undefined) do outstring[i]=upper[j])
outstring)
fn printblockpos bname badr = (
str=((bit.intAsHex badr)as string)
if str[str.count]=="L" do(str = substring str 1 (str.count-1))
format "% @ 0xDD%\n" bname (paddstring 6 (uppercase str))
)
fn printblockpos bname badr = (
str=((bit.intAsHex badr)as string)
if str[str.count]=="L" do(str = substring str 1 (str.count-1))
format "% @ 0x%\n" bname (paddstring 8 (uppercase str))
)
fn writeDDSheader fstream texW texH texM texC = (
texP=0
writelong fstream 0x20534444 #unsigned -- File ID
writelong fstream 0x7C #unsigned -- Header Size
case of( -- dwFlags
(texC==#DXT1): (writelong fstream 0x00081007 #unsigned;texP=((texW*texH)/0x02))
(texC==#DXT3): (writelong fstream 0x00081007 #unsigned;texP=(texW*texH))
(texC==#DXT5): (writelong fstream 0x00081007 #unsigned;texP=(texW*texH))
(texC==#ATI1): (writelong fstream 0x000A1007 #unsigned;texP=((texW*texH)/0x20))
(texC==#ATI2): (writelong fstream 0x000A1007 #unsigned;texP=(texW*texH))
(texC==#P8): (writelong fstream 0x000A1007 #unsigned;texP=((texW*texH)/0x02))
(texC==#ARGB16): (writelong fstream 0x00081007 #unsigned;texP=(((texW*texH)/0x8)*0x10))
(texC==#ARBG32): (writelong fstream 0x00081007 #unsigned;texP=(((texW*texH)/0x4)*0x10)))
writelong fstream texW #unsigned -- Texture Width
writelong fstream texH #unsigned -- Texture Height
writelong fstream texP #unsigned -- Pitch (#of bytes in a single row across the texture)
writelong fstream 0x00 #unsigned -- Image Depth? Not Used, for Image Volume
writelong fstream texM #unsigned -- Texture MIP Count
for i = 1 to 11 do writelong fstream 0x00 #unsigned -- Reserved Space
writelong fstream 0x20 #unsigned -- Size of PIXEL_FORMAT info, always 32bytes;
case of(
(texC==#DXT1): (writelong fstream 0x04;writelong fstream 0x31545844 #unsigned
writelong s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writelong fstream 0x00001000 #unsigned)
(texC==#DXT3): (writelong fstream 0x04;writelong fstream 0x33545844 #unsigned
writelong s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte s 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00001000 #unsigned)
(texC==#DXT5): (writelong fstream 0x04;writelong fstream 0x35545844 #unsigned
writelong fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00001000 #unsigned)
(texC==#ATI1): (writelong fstream 0x04;writelong fstream 0x31495441 #unsigned
writelong fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00401008 #unsigned)
(texC==#ATI2): (writelong fstream 0x04;writelong fstream 0x32495441 #unsigned
writelong fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00401008 #unsigned)
(texC==#P8): (writelong fstream 0x20;writelong fstream 0x20203850 #unsigned
writelong fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00401008 #unsigned)
(texC==#ARGB16): (writelong fstream 0x41;writelong fstream 0x00000000 #unsigned
writelong fstream 0x10;writebyte fstream 0x00;writebyte fstream 0x0F;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0xF0;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x0F;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0xF0;writebyte fstream 0x00
writebyte fstream 0x00;writelong fstream 0x00001000 #unsigned)
(texC==#ARBG32): (writelong fstream 0x41;writelong fstream 0x00000000 #unsigned
writelong fstream 0x20;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0xFF
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0xFF;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0xFF;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00;writebyte fstream 0x00
writebyte fstream 0xFF;writelong fstream 0x00001000 #unsigned))
for i = 1 to 4 do writelong fstream 0x00 #unsigned -- Reserved Space for CAPS
)
fn Get_D3DFORMAT id = (
case id of ( -- replaced a few from offical ones, for backwards compatiblity
0x86: #DXT1
-- 0x53: #DXT3 -- DXT2
-- 0x7A: #DXT3A
-- 0x7D: #DXT3A_1111
0x88: #DXT5
-- 0x7B: #DXT5A
-- 0x71: #ATI2 -- DXN
-- 0x7C: #ATI1 -- CTX1
-- 0x02: #L8
-- 0x44: #R5G6B5
-- 0x45: #R6G5B5
-- 0x43: #X1R5G5B5
-- 0x4F: #A4R4G4B4
-- 0x4F: #X4R4G4B4  
-- 0x4A: #A8L8
-- 0x58: #D16
-- 0x5E: #R16F
-- 0x5B: #R16F_EXPAND
-- 0x4C: #UYVY
-- 0x0C: #LE_UYVY
-- 0x4C: #G8R8_G8B8
-- 0x4B: #R8G8_B8G8
-- 0x4B: #YUY2
-- 0x0B: #LE_YUY2
-- 0x86: #A8R8G8B8
-- 0xB6: #A2R10G10B10
-- 0x99: #A16L16
-- 0xB7: #R10G11B11
-- 0xB8: #R11G11B10
-- 0xB7: #W10V11U11
-- 0xB8: #W11V11U10
-- 0x9F: #G16R16F
-- 0x9C: #G16R16F_EXPAND
-- 0xA1: #L32
-- 0xA4: #R32F
-- 0x96: #D24S8
-- 0x97: #D24FS8
-- 0xA1: #D32
-- 0x5A: #A16B16G16R16
-- 0x60: #A16B16G16R16F
-- 0x5D: #A16B16G16R16F_EXPAND
-- 0xA2: #A32L32
-- 0xA5: #G32R32F 
-- 0xA3: #A32B32G32R32
-- 0xA6: #A32B32G32R32F
-- 0xBF: #A2B10G10R10F_EDRAM
-- 0x55: #A16B16G16R16_EDRAM
-- 0x06: #LE_X8R8G8B8
-- 0x36: #LE_X2R10G10B10
-- 0x01: #INDEX16
-- 0x06: #INDEX32
-- 0x00: #LE_INDEX16
-- 0x04: #LE_INDEX32
-- 0x08: #VERTEXDATA
-- 0xFF: #UNKNOWN
default: #UNKNOWN
)
)


if (fsource!=undefined) then (
fpath=getFilenamePath fsource
fname=getFilenameFile fsource
fsize=getFileSize fsource
fext=getFilenameType fsource
if ((doesFileExist fsource)==true) then (
clearlistener ()
f = fopen fsource "rb"



struct package_resource (offset,type,name,size,data)
struct model_binary_4 (header,buffer,element,skeleton,ukn10,ukn11,material,ukn12,mesh)
struct model_binary_4_header (magic,ukn01,ukn02,ukn03,ukn04,ukn05,info,ukn06,ukn07,ukn08,ukn09)
struct offset_and_count (offset,count)
datArray = (package_resource \
	offset:#() \
	type:#() \
	name:#() \
	size:#() \
	data:#())

case (readFixedString f 4) of (
"DAT":(
dat_offsets = #()

dat_01 = readBElong f -- count: files
dat_02 = readBElong f -- offset: offset table
dat_03 = readBElong f -- offset: extension table
dat_04 = readBElong f -- offset: name table
dat_05 = readBElong f -- offset: size table
dat_06 = readBElong f -- offset: ?? unknown data
dat_07 = readBElong f -- Blank? Reserved?

fseek f dat_02 #seek_set
for i = 1 to dat_01 do (datArray.offset[i] = readBElong f)
fseek f dat_03 #seek_set
for i = 1 to dat_01 do (datArray.type[i] = uppercase (readFixedString f 4))
fseek f dat_04 #seek_set;str_len = readBElong f
for i = 1 to dat_01 do (datArray.name[i] = readFixedString f str_len)
fseek f dat_05 #seek_set
for i = 1 to dat_01 do (datArray.size[i] = readBElong f)
for i = 1 to dat_01 do (datArray.data[i] = #())
for d = 1 to dat_01 do (
fseek f datArray.offset[d] #seek_set
case datArray.type[d] of (
"WTA":(
ukn00 = readBElong f -- changes based on platform
ukn01 = readBElong f -- version?
ukn02 = readBElong f -- count
ukn03 = (readBElong f)+datArray.offset[d] -- offset to texture offsets
ukn04 = (readBElong f)+datArray.offset[d] -- offset to texture sizes
ukn05 = (readBElong f)+datArray.offset[d] -- offset to flag data?
ukn06 = (readBElong f)+datArray.offset[d] -- offset to file hashes?
ukn07 = (readBElong f)+datArray.offset[d] -- offset to XPR2 headers

for i = 1 to ukn02 do (
ssource = (fpath+fname+".dtt")
if ((doesFileExist ssource)==true) then (
g = fopen ssource "rb"
s = fopen (fpath+fname+(paddstring 3 (i as string))+".dds") "wb"

fseek f (ukn03+((i-1)*4)) #seek_set;pos = readBElong f
fseek f (ukn04+((i-1)*4)) #seek_set;dumpsize = readBElong f

fseek g (pos+0x1000) #seek_set


-- Configuration of the GTF File Header 

-- A GTF file header has the following basic structure. 

-- typedef struct { 
-- uint32_t Version; 
-- uint32_t Size; 
-- uint32_t NumTexture; 
-- } CellGtfFileHeader; 

-- Field  Type  Description 
-- Version  uint32_t  Version information of the GTF format 
-- Size  uint32_t  Total byte size of textures in file (Does not include sizes of file header and texture attributes) 
-- NumTexture  uint32_t  Number of textures in file 

-- Configuration of the GTF Texture Attribute 

-- A GTF texture attribute has the following structure. 

-- typedef struct { 
-- uint32_t Id; 
-- uint32_t OffsetToTex; 
-- uint32_t TextureSize; 
-- CellGcmTexture tex; 
-- } CellGtfTextureAttribute; 

-- Field  Type  Description 
-- Id  uint32_t  Identification ID 
-- Must be unique within the file 
-- OffsetToTex  uint32_t  Offset from the beginning of the file to the corresponding texture (bytes) 
-- TextureSize  uint32_t  Size of corresponding texture (bytes) 
-- tex  CellGcmTexture  Texture structure defined in libgcm 

-- The CellGcmTexturestructure used in texof the 4th field has exactly the same specifications as the CellGcmTexturestructure defined in libgcm. 

-- This CellGcmTexturestructure, as of this SDK release, has the following configuration. 

-- typedef struct { 
-- uint8_t format; 
-- uint8_t mipmap; 
-- uint8_t dimension; 
-- uint8_t cubemap; 
-- uint32_t remap; 
-- uint16_t width; 
-- uint16_t height; 
-- uint16_t depth; 
-- uint8_t location; 
-- uint8_t _padding; 
-- uint32_t pitch; 
-- uint32_t offset; 
-- } CellGcmTexture;

struct gft_header (
magic, -- "0x02010100" Version, possibly a fourcc
streamsize,
num_textures, -- forced to 1? :-P
ukn02, -- always 0?
stream_offset,
ukn03, -- offsets to end of stream?
d3d_format, -- fourCC, probably describes d3d compression
ukn04, --offset?
height,
width,
depth,
ukn05, -- always 0?
null -- reserved space
)

gftArray = (gft_header \
magic:(readBElong g) \
streamsize:(readBElong g) \
num_textures:(readBElong g) \
ukn02:(readBElong g) \
stream_offset:(readBElong g) \
ukn03:(readBElong g) \
d3d_format:([(readbyte g #unsigned),(readbyte g #unsigned),(readbyte g #unsigned),(readbyte g #unsigned)]) \
ukn04:(readBElong g) \ --remap?
height:(readBEshort g) \
width:(readBEshort g) \
depth:(readBEshort g) \
ukn05:(readBEshort g) \
null:#() \
);fseek g 88 #seek_cur


format "%: (% x %) \tFormat:%\n" (paddstring 3 i) (paddstring 4 gftArray.width) (paddstring 4 gftArray.height) gftArray.d3d_format

writeDDSheader s gftArray.width gftArray.height 1 (Get_D3DFORMAT gftArray.d3d_format[1])
for x = 1 to dumpsize do (writebyte s (readbyte g #unsigned) #unsigned)

fclose s
fclose g
)else(messagebox "failed to find relating dtt file")
)






)
default:(printblockpos ("Type Unknown: "+datArray.type[d]) datArray.offset[d])
)
)
)
default:(format "File Unknown: %\n" (magic as string))
)
format "Last Read @ 0x%\n" ((bit.intAsHex(ftell f))as string)
format "Flie Closed: %\n" fname
fclose f
) else (Print "Failed to Locate File")) else (Print "Aborted.")

```
## Post #30
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-14T05:21:58+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

every time i look at maxscript my eyes go numb ha ha ha ha
## Post #31
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2013-03-14T06:23:22+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

@ mariokart64n

sorry for the max noob question but,i run your maxscript and select em0110.dat from ps3 and nothing happens,what am i doing wrong here?

also you probaly know this but in pl folder are all raiden models
## Post #32
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-14T06:34:51+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

xbox360 only; ps3 model format is totally different
## Post #33
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-03-14T11:19:08+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

Uhm... I have problems unpacking the .dat files. I successfully extracted all the stuff from the .cpk archive, but when I try to extract the characters I get this:

> Error:  invalid command "dat_header" or arguments -1 at line 1
>
> 
>
> Press Return wo quite

Any suggestion? :\ I have the 360 files, used Mario's script for the .dat packages...
## Post #34
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-14T11:31:48+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

hey runa, pm me you know where and let me know what model you want. mario's script isn't completely ready yet.
## Post #35
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-03-14T11:39:42+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from howfie
>
> hey runa, pm me you know where and let me know what model you want. mario's script isn't completely ready yet. i have a sample blender file there.

On my way  thanks!
## Post #36
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-14T11:59:07+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

oh btw, mario's script isn't for the dat files... you have to use quickbms and dataunpack.bms and then run mario's script on the wmb file. i'll send the bms script to you.

edit: actually, you're right runa, you do run it on the dat files lol.
## Post #37
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-30T19:56:48+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

almost ready. say another day or two. all characters, items, weapons, with bones and weights but no textures. you guys will have to use mario's script or whatever script there is to get the textures. don't intend to process the stage meshes, which are in the scr files as the stages aren't all that impressive.
## Post #38
- Username: Tribalizer
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 11:26 pm
- Post datetime: 2013-03-31T11:28:19+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

All of the weapons? How did you manage that if you don't mind me asking. I can only load up a couple, the rest are a broken mess.
## Post #39
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-03-31T19:15:29+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

Earlier I wasn't able to find a FVF table to correctly read the vertex strides. but later figured it is globally defined in the start of the header, I think the first 8 bytes determine vertex stride/type and draw method, tristrip/trilist

I also got the bones and skinning working, but didnt bother updating since getting my ass shot down over at FP

I'm sure howfie's got it all figured out aswell, those guys over at FP will be over joyed lol
## Post #40
- Username: yanneric
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 30, 2011 6:15 am
- Post datetime: 2013-03-31T20:02:06+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

you are right  you shouldn't release it, they don't deserve it, after all the nasty thing they said about you.
## Post #41
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-31T22:36:19+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

i got skinning partially worked out... there are a few models with like an inner body and skinning is funky with that. indeed, within the first 16 bytes are the vertex format and triangle topology flags (i've only encountered triangle lists and tristrips with strip cuts).

anyways, have fun... i don't have textures (use mario's script for that). let me know if any models are screwed up. just use bms script for bayonetta to extract files, put exe in media directory and run. it will generate SMC files. load blender script in Blender 2.49b and run script. load SMC file. since i don't have textures, there may be bugs. lemme know and i see if i can fix.

[http://www.sticklove.com/content/mgrr_xbox360.7z](http://www.sticklove.com/content/mgrr_xbox360.7z)
## Post #42
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-31T22:58:23+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from yanneric
>
> you are right  you shouldn't release it, they don't deserve it, after all the nasty thing they said about you.

the thing about facepunch is that it's models or GTFO. they dont' want scripts or rippers, they want models, preferably in batches. i know better than to post there in the first place LOL! you guys ever see that one thread with chrrox posting a link to a maxscript and to xentax and they let him have it too? like i said, it's models or GTFO hahahahaha .
## Post #43
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-04-01T04:15:17+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

The threads I've seen on facepunch have led me to the conclusion that their culture centers around the elevation of the people who run scripts to rip models and occasionally do the braindead job of reskinning and/or setting up ragdoll bodies before illegally distributing the content that they've butchered. So I imagine that actually providing scripts and/or tools there could make the sad little men who rip and convert models feel insecure in their position of communal knobslobbing, and we certainly can't have that.

I've been meaning to do MGR support for Noesis, because I finished playing through it the other week and it was awesome. I was initially going to plug it into the Bayonetta plugin, but I saw that the format is in fact very different, and I've been too lazy to actually look at it since then. It's easier to pick away at little bugs and crashes that take 5 minutes to fix when I can actually muster the energy to sit down for a second after work or on the weekend. Programming for a living all day really ruins the appeal, and usually when I have a programming job and I start working on Noesis a lot again it just means the job has become boring as shit.

howfie, manually checking index ranges? You just don't get it. I have a dream, that one day every developer on this forum will control their own software. A framework of the truly free, dammit. A framework of action, not design goals, ruled by functionality, not committee! Where the scripting changes to suit the developer, not the other way around. Where the power and flexibility are back where they belong: in the hands of the developer! Where every developer is free to think, to act, for himself! Fuck all these limp-dick script kiddies and chickenshit rippers. Fuck this 24/7 internet spew of model requests and hentai bullshit! Fuck engineer pride! Fuck the common software packages! FUCK ALL OF IT! Blender is diseased. Rotten to the core. There's no saving it. We need to pull it out by the roots. Wipe the slate clean. BURN IT DOWN. And from the ashes, a new Blender will be born. Evolved, but untamed. The framework will be purged and the developers will thrive, to code as they see fit. They'll make Blender great again. In my new Blender, Noesis will target and bridge to it. Not for money, not for users, not because it seems convenient. Noesis will be free to work with software that doesn't suck!
## Post #44
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-01T04:25:05+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

hahahahahahahahaha you looked at mah script? what's wrong with it lol ? i have to admit, my knowledge of python is piss poor and i just do whatever seems to work hahahahaha.

P.S. BTW, your philosophy about life is pretty messed up compared to mines. All I want to do is program, make lots of money, and spend it so as to have lots of sex and make lots of babies .
## Post #45
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2013-04-01T05:26:24+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

Lol, I'm not sure if you've finished the game yet howfie.
I mean, if you have, you'd know where MrAdults' speech came from.
## Post #46
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-01T05:39:52+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

i rarely finish any game unless it's coop and i have friends with the game as well. even with games that i like such as boob raider i get through maybe half and get bored. there are even some games like re orc that i get bored with so quick i dont even bother finishing the first level lol! mgrr is like that for me too. by the time i got to where sam kicks raidens ass on the train i was bored already.

 still, rich was mocking mah python skillz lololol.
## Post #47
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2013-04-01T05:56:05+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

Haha! I see, I guess that makes sense.
Don't know much about Python, so I can't really say much, lol.
Anyway, it looks like you guys have made a huge progress on this.
Keep it up!
## Post #48
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-04-01T12:54:28+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

I just saw that big chunk of code to handle triangle indices in your screenshot, and I was going to remark about how that big mess would be boiled down to a single fast native-side call in the Noesis Python API, but then I thought it would be much more fun to make a MGR boss rant.
## Post #49
- Username: blablukura
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 25, 2012 9:32 pm
- Post datetime: 2013-04-02T01:19:24+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from MrAdults
>
> The threads I've seen on facepunch have led me to the conclusion that their culture centers around the elevation of the people who run scripts to rip models and occasionally do the braindead job of reskinning and/or setting up ragdoll bodies before illegally distributing the content that they've butchered. So I imagine that actually providing scripts and/or tools there could make the sad little men who rip and convert models feel insecure in their position of communal knobslobbing, and we certainly can't have that.

I've been meaning to do MGR support for Noesis, because I finished playing through it the other week and it was awesome. I was initially going to plug it into the Bayonetta plugin, but I saw that the format is in fact very different, and I've been too lazy to actually look at it since then. It's easier to pick away at little bugs and crashes that take 5 minutes to fix when I can actually muster the energy to sit down for a second after work or on the weekend. Programming for a living all day really ruins the appeal, and usually when I have a programming job and I start working on Noesis a lot again it just means the job has become boring as shit.

howfie, manually checking index ranges? You just don't get it. I have a dream, that one day every developer on this forum will control their own software. A framework of the truly free, dammit. A framework of action, not design goals, ruled by functionality, not committee! Where the scripting changes to suit the developer, not the other way around. Where the power and flexibility are back where they belong: in the hands of the developer! Where every developer is free to think, to act, for himself! Fuck all these limp-dick script kiddies and chickenshit rippers. Fuck this 24/7 internet spew of model requests and hentai bullshit! Fuck engineer pride! Fuck the common software packages! FUCK ALL OF IT! Blender is diseased. Rotten to the core. There's no saving it. We need to pull it out by the roots. Wipe the slate clean. BURN IT DOWN. And from the ashes, a new Blender will be born. Evolved, but untamed. The framework will be purged and the developers will thrive, to code as they see fit. They'll make Blender great again. In my new Blender, Noesis will target and bridge to it. Not for money, not for users, not because it seems convenient. Noesis will be free to work with software that doesn't suck!
lmao . looks like someone ripped your speech and put it into the game
## Post #50
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-04-15T06:02:43+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

Updated to handle xbox360 textures now. For the most part, xbox360 textures are a better but quite a few models use the the same low quality textures that the PS3 uses. Now with stage geometry as well. There are bones and weights but no auto-texture yet since textures can be located in folders that are all over place.

[ripper.exe](http://www.sticklove.com/content/semory/mgrr/ripper_fixed.7z)


Instructions:

1. Rip game. There are a number of tools to do this.
2. I forget if this game uses CPK (someone told me they did), if they do, use QuickBMS's CPK script.
3. Make a backup copy of your game and copy game files from the media directory to another directory.
4. Place ripper.exe and Unbundler.exe***  inside the media directory.
5. Run ripper.exe.
6. Come back maybe a half-hour later.
7. A few useless GUI textures may cause errors, just say OK or whatever and it will continue.
8. When done, you will see lots of files.
9. SMC files are intermediate model files for which you can load into Blender 2.49b using the included smcimport.py Blender script.

*** This game uses XBox360 XPR textures. You must either have Unbundler.exe (from the XBox360 SDK) or you can also use Noesis on the XPR files.

Notes:

Some models have UV maps with only a couple dots in it. These are for an outer skin and the textures for these skins are some kind of semi-transparent effects texture. Not sure WTF to do with them but the geometry is there and for the dog sample (the one Raiden meets just before he meets Mistral), I just deleted it.
## Post #51
- Username: EIREXE
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 16, 2012 1:29 am
- Post datetime: 2013-05-05T00:30:01+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from howfie
>
> Updated to handle xbox360 textures now. For the most part, xbox360 textures are a better but quite a few models use the the same low quality textures that the PS3 uses. Now with stage geometry as well. There are bones and weights but no auto-texture yet since textures can be located in folders that are all over place.

ripper.exe


Instructions:

1. Rip game. There are a number of tools to do this.
2. I forget if this game uses CPK (someone told me they did), if they do, use QuickBMS's CPK script.
3. Make a backup copy of your game and copy game files from the media directory to another directory.
4. Place ripper.exe and Unbundler.exe***  inside the media directory.
5. Run ripper.exe.
6. Come back maybe a half-hour later.
7. A few useless GUI textures may cause errors, just say OK or whatever and it will continue.
8. When done, you will see lots of files.
9. SMC files are intermediate model files for which you can load into Blender 2.49b using the included smcimport.py Blender script.

*** This game uses XBox360 XPR textures. You must either have Unbundler.exe (from the XBox360 SDK) or you can also use Noesis on the XPR files.

Notes:

Some models have UV maps with only a couple dots in it. These are for an outer skin and the textures for these skins are some kind of semi-transparent effects texture. Not sure WTF to do with them but the geometry is there and for the dog sample (the one Raiden meets just before he meets Mistral), I just deleted it.
I got it working, how did you managed to get textures working? because I can't seem to do it

BTW anyone knwos where are the codec models? i-m seriuslly needing htem
## Post #52
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-05T03:09:08+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

those models are just heads nothing more.
## Post #53
- Username: EIREXE
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 16, 2012 1:29 am
- Post datetime: 2013-05-05T09:07:06+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from chrrox
>
> those models are just heads nothing more.
maybe you meant half body, even if they are they will come in handy for something, anyone knows where they are?
## Post #54
- Username: EIREXE
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 16, 2012 1:29 am
- Post datetime: 2013-05-05T09:46:14+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

> Reply from EIREXE
>
> chrrox wrote:those models are just heads nothing more.
maybe you meant half body, even if they are they will come in handy for something, anyone knows where they are?

NVM already found it

Full list of stuff:
em00a0 desesperado trimotor plane
em00a1 desesperado trimotor plane2
em01a0 monsoon complete
em01a2 to em01c1 monsoon parts (more detail on the "insides" for a higer res character
em002a to em002f samuel rodriges body, hair.... head, sword carrier and another body
em003f to em03b0 nr
em0010 trooper with packpack and pilot helmet
em011a mistral staff
em011b mistral staff2
em011c mistral with vest2
em011d mistral face
em0012 NR
em014a MAK soldier posed
em014f nr
em015f nr
em0020 samuel rodrigez body3
em020a METAL GEAR RAY MOD missing right arm and turrets
em020b MGray no arms
em020c corupted
em020d corupted
em0021 corupted
em0022 corupted
em0023 
em0024 sam sword holdster2
em0026 sam head 
em0030 MG gekko, no weapons
em031a dude in suit
em031b Sundowner/ no shields
em0033 MG gekko, no weapons2
em0035 MG gekko, no weapons3
em0040 Dwarf gekko
em0044 Dwarf gekko2
em0046 Dwarf gekko ball only
em0048 nr cilinder cable thing
em0060 MG raptor with Dgekko no unnarmed
em060a and em060b corrupted (possible raptors weapons)
em060c MG raptor rail gun
em0070 mastiff
em070a shirtless armstrong body
em070b armstrong head
em070c broken file
em0071 mastiff 2
em0080 heavy biped tank2.obj
em0081 heavy biped tank3
em0091 unmaned turret gun
em0100 tripod sentry
em0110 mistral
em0111 mistral robot arms
em0112 mistral staff
em0113-17 mistral individual arm with pivot piece
em0118 broken file
em0119 mistral staff with knifes at each end
em0120 flying ug raven
em0121 flying ug raven2
em0122 NR
em0140 regular machete trooper
em0142 regular machete trooper2
em0144 world marshal regular trooper
em0152 Samurai trooper
em0160 detroit police (convined)
em0170 Heavy hammer trooper
em0180 APC armored transport
em0181 APC armored transport low poly
em0182 APC armored transport 3
em0190 HAMMERHEAD HELICOPTER
em0200 METAL GEAR RAY COMPLETE WITH BLADE ARM
em0201 METAL GEAR RAY armblade attack mode
em0202 METAL GEAR RAY tail
em0203 nr
em0204 nr
em0205 to em0209 corrupted file
em0220 blade wolf desperado version
em0221 blade wolf maverik version
em0300 nr
em0310 sundowner closed mask
em0312 sundowner gabardine
em0313 sundowner partial face
em0313-319 sundowner shield
em0320-390 nr
em0400 world marshall lobby female android
em0410 african president
em0600 METAL GEAR EXCELSUS
em0601 some ug machinegun
em0602 crane holding a thing
em0603-604 MG excelsus part
em0605-606 MG excelsus crusher legs
em0607-608 MG excelsus crusher legs armor
em0609 MG excelsus head
em0620 NR
em0700 ARMSTRONG shirt and tie
em0701 head normal
EM1000 CARBOARD BOX normal and trashed
EM1010 Armed Camera
em1020 holo points thing
emd000 nr
eme1a0 
eme1a0_us
eme010
eme012
eme012_us and everything else is unredeable

ui for user interface, there's the codec character models
ui206 sunny
ui203 cuntney
4 doctor

wp folder is for weapons from raiden and other npc like rays arm/leg turrets
wp0200 ray turret


et folder some props like power spines and doors and shit

it folder othe props like kife cells

pl folder.. player raiden files

civilians
pl0a00 civilian
pl0a01 civilian2
pl0800_us 
pl0801 civilean3
pl0800 civilian4

pleyable characters
pl0100 raid prologue
pl0110 raid hd
pl0200 ,400 and 800 nothing
pl1010 low res raiden
pl1030 another color variation
pl1040 another color variation
pl1050 another color variation
pl1060 mexican raiden
pl1070 bodyguard suit raiden
pl1080 another color variation
pl1090 another color variation
pl1200 another color variation
pl1210 another color variation
pl1220 another color variation
pl1240 dwarf gekko player model

weapons
pl3005 sam blade
pl3004 corrupt
pl3003 corrupt
pl3002 enemy katana
pl3001 stun katana
pl3000 armor breaker
## Post #55
- Username: DeadpoolMarin3
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 19, 2023 2:05 pm
- Post datetime: 2023-04-19T06:09:13+00:00
- Post Title: Re: PS3 - Metal Gear Rising Revengeance - WMB format

Any way there’s new links for ripper.exe
