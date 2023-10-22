## Post #1
- Username: Shiranui
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 13, 2012 6:45 am
- Post datetime: 2012-07-13T01:43:05+00:00
- Post Title: [Wii] Arc Rise Fantasia fantranslation

Hello guys, I'm new in this forum. Since Arc Rise Fantasia was released in English and Japanese only, a group of friends and I are planning on translating it into Spanish. The thing is, does anyone know which are the ingame text files? I've searched the forum but I found models-related-topics only, apart from several tools to open .vol and .cxd files. Any help would be really appreciated.
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-07-21T14:12:34+00:00
- Post Title: [Wii] Arc Rise Fantasia fantranslation

Did you even tried to unpack some archives and see for yourself?

Here is what i documented some time ago:

> wtm-File (WTMD) imageformat
>
> 
>
> The format is VERY similar to the standard texture-format of the GC/Wii, TPL. See http://hitmen.c02.at/files/yagcd/yagcd/ ... sec15.20.1
>
> There are still some unknown bytes but the folowing offsets should be enough to convert the images:
>
> 
>
> Offset Size Description
>
> 0x06 2byte Palette Offset - offset to Palette Data
>
> 0x08 2byte Width
>
> 0x0A 2byte Height
>
> 0x0C 1byte Imageformat - RGB565/RGBA8/CI4/CI4... see yagcd for more info
>
> 0x12 2byte Data Offset - offset to image Data
>
> 
>
> Imageformat Description
>
> 0 			I4 (4 bit intensity, 8x8 tiles)
>
> 1 			I8 (8 bit intensity, 8x4 tiles)
>
> 2 			IA4 (4 bit intensity with 4 bit alpha, 8x4 tiles)
>
> 3 			IA8 (8 bit intensity with 8 bit alpha, 4x4 tiles)
>
> 4 			RGB565 (4x4 tiles) OK
>
> 5 			RGB5A3 (*) (4x4 tiles)
>
> 6 			RGBA8 (4x4 tiles in two cache lines - first is AR and second is GB) OK
>
> 8 			CI4 (4 bit color index, 8x8 tiles) OK
>
> 9 			CI8 (8 bit color index, 8x4 tiles) OK
>
> A 			CI14X2 (14 bit color index, 4x4 tiles)
>
> E 			CMP (S3TC compressed, 2x2 blocks of 4x4 tiles)
>
> 
>
> Arc Rise Fantasia Experience Table (LVL 0-99)
>
> Values are set in exp_tbl.bin.
>
> 0
>
> 10
>
> 84
>
> 286
>
> 679
>
> 1328
>
> 2294
>
> 3644
>
> 5439
>
> 7745
>
> 10624
>
> 14141
>
> 18359
>
> 23342
>
> 29154
>
> 35858
>
> 43519
>
> 52199
>
> 61963
>
> 72875
>
> 84998
>
> 98396
>
> 113133
>
> 129272
>
> 146877
>
> 166012
>
> 186741
>
> 209128
>
> 233236
>
> 259128
>
> 286870
>
> 316524
>
> 348154
>
> 381824
>
> 417598
>
> 455539
>
> 495711
>
> 538179
>
> 583005
>
> 630253
>
> 679988
>
> 732273
>
> 787171
>
> 844747
>
> 905064
>
> 968187
>
> 1034177
>
> 1103101
>
> 1175020
>
> 1249999
>
> 1328102
>
> 1409393
>
> 1493935
>
> 1581791
>
> 1673027
>
> 1767705
>
> 1865889
>
> 1967642
>
> 2073030
>
> 2182115
>
> 2294961
>
> 2411633
>
> 2532192
>
> 2656705
>
> 2785233
>
> 2917842
>
> 3054594
>
> 3195553
>
> 3340784
>
> 3490350
>
> 3644314
>
> 3802741
>
> 3965694
>
> 4133237
>
> 4305433
>
> 4482347
>
> 4664042
>
> 4850582
>
> 5042031
>
> 5238452
>
> 5439909
>
> 5646466
>
> 5858187
>
> 6075136
>
> 6297375
>
> 6524969
>
> 6757982
>
> 6996478
>
> 7240519
>
> 7490171
>
> 7745496
>
> 8006558
>
> 8273422
>
> 8546151
>
> 8824808
>
> 9109458
>
> 9400163
>
> 9696989
>
> 9999999
>
> 
>
> 
>
> Folders on the DVD of ARF and what they contain
>
> 
>
> _sasaki\ fonts (not the fonts of the menus or the chat, etc.)
>
> _viewer\ unknown
>
> Btl\btl_enemy vld files are Lz77 compressed files the offsets for the files inside the vld are stored in vlh files (found in btl_usual.vol). the format is size:offset (booth 4 bytes) and starts at 0x20 in the vlh-file. 
>
> Btl\sound battlemusic
>
> Btl\ btl_weapon.vld contains the weaponmodels, btl_voice.afs is a container for the battlevoices the rest of the files contains misc data for the battlemodus like images, textures, models and so on
>
> Char\ 3d-models
>
> Event\ the loc_...-files containing model/scene data and sometimes the map of the location. the EV... files are for model and 3d scenes too
>
> Event\c_rank\ more model/scene data in the EV... files
>
> Event\c_rank\voice\ only one adx soundfile
>
> Event\endroll\ images for the endingsequence of the game
>
> Event\exp\ 	exp_fc_000.vol contains bscr (scriptfile), for guildquests
>
> 			exp_fc_001.vol contains bscr (scriptfile), for slotmachine in casino
>
> 			exp_fc_002.vol contains bscr (scriptfile), for poker in casino
>
> 			exp_fc_003.vol contains bscr (scriptfile), for blackjack in casino
>
> 			exp_fc_004.vol contains bscr (scriptfile), for copinrace in casino
>
> 			exp_fc_005.vol contains bscr (scriptfile), for arena
>
> Event\fc\ the vol-archives containing bscr files, with plain text (and data for skits ???)
>
> Event\se\ adx soundfiles. mostly background noise and soundeffects for the cutscenes
>
> Event\voice\ more adx soundfiles
>
> Event\wld\ archives containing bscr files. there is text for every conversation that happens on the worldmap (signs too)
>
> interface\ the data_map...-files containig images and text that is used in the Map->World Map menu of the game. the if_... are for casino-related files (wtm-images and other files (.bin)). tex_...-files are textures only
>
> Map\ compressed vol-archives for every location in the game. archives contain bscr-files and other files. the bscr contains the text of the npcs and conversions between them and the group.
>
> Map\sound\ adx-files for the backgroundmusic
>
> Map\sound\jingle\ various adx-files
>
> Map\image\ archives containing the images and other data needed for the Map->Area Map menu
>
> minigame\ data as sound, models and images etc. for the minigames
>
> Movies\ sfd-files for the movies (rendered videos)
>
> Sys\ ...-bin files containing some plain text and other unknown data, some images and the system.vol. monster_book.bin contains the Monsterlibrary from the pausemenu (changing values here will not affect the outcome from fights) system.vol contains informations for the weapons, abilities, quests, magic, rogress, some icons (elements), statusfont2 are symbold (AP, RP...),statusfont are symbols (atk,res,rico,select...), exp-table, merchantnames, list of skits and other unknown stuff
>
> Title\ data for the "3d-titlescreen-scene"
>
> world\ most folders contain LZ77 compressed files but I dont know what the files are for
>
> world\texture lz77 (0x11) compressed files with wtm file inside
>
> 
>
> Fileformats
>
> Most files are compressed with either LZ77 (0x10 or 0x11 followed by the original size in !!little endian byte order!!). Big endian byte order is used for all files. What kind of file is inside a compressed file is visible from looking at the first few bytes. After the compressionflag and the uncompressed size (4byte) the filetype is written.
>
> 
>
> adx.-files A common format for soundfiles on the Wii
>
> afs.-files A common container-format on the Wii used to store adx. files
>
> .bin-files There are different types of these files, they can be compressed too or they are just some text, systemdata for the game or something else.
>
> SSCR some of these .bin-files have text in it (see sys\arena.bin). It looks like the pointers to the text and other data are near the top of the file. Example: For "Stalwart Soldiers" its h0DEA this value is stored at h48 in the file (the pointers are 4 byte in size).
>
> 
>
> .vol-files Archives that can be extraced with the following bms script and quickbms (http://aluigi.org/papers.htm#quickbms)
>
> props to WRS for finding out:
>
> # -- WRS
>
> #    xentax.com
>
> #    .vol BMS script
>
> 
>
> idstring "RTDP"
>
> 
>
> endian big
>
> 
>
> get EOH long
>
> get FILES long
>
> get THISSIZE long
>
> 
>
> goto 0x20
>
> 
>
> for i = 1 to FILES
>
> 
>
>   getdstring FILENAME 32
>
>   get FILESIZE long
>
>   get FILEOFFSET long # relative to EOH
>
> 
>
>   filexor 0x55
>
>   math FILEOFFSET += EOH
>
>   log FILENAME FILEOFFSET FILESIZE
>
>   filexor 0
>
> 
>
> next i
>
> 
>
> Just a reminder... As you can see from the script it is necessary to alter the FILESIZE and FILEOFFSET valuess according to your edited files if you want to recreate a vol-archive. 
>
> 
>
> For the 3d models the game uses the brmdl model format with bress textures.
>
> 
>
> Text is NOT Shift-JIS but contains all chracters of it (EUC28-0.wtm - EUC28-8.wtm). Its http://www.rikai.com/library/kanjitable ... .euc.shtml
>
> 
>
> RetroHelix

I'm not entirely sure anymore since its some time since I last had a look at this but I think all ingame text is in the bscr files. They are ordered by locations and events etc.

Would be nice to hear from you if you make progress.

EDIT:
Found some even older documentation about the items

> full itemdescription - includes name, description, number, price, weapondescription, weaponsecrets and other atributes of items
>
> itemdescription - textual description, without any other data
>
> weapondescription - textual description, without any other data
>
> 
>
> items are stored in chunks of h11F bytes
>
> 
>
> 
>
> h0A = linebreak
>
> h15 = introduces an icon/symbol for (secret) boosts/negative atributes like ATK+10 for example
>
> symbols/icons for atributes of weapons/armor/magic etc. (plain ASCIItext stands for a symbol):
>
> 01 = Secret
>
> 90 = ATK
>
> 91 = DEF
>
> 92 = MAG
>
> 93 = RES
>
> 94 = SPD
>
> 97 = LUK
>
> E0 = Fire
>
> E1 = Water
>
> E2 = Wind
>
> E3 = Earth
>
> E4 = Ice
>
> E5 = Thunder
>
> E6 = Light
>
> E7 = Dark
>
> D0 = R
>
> D1 = Lvl
>
> D2 = HP
>
> D3 = MP
>
> D4 = AP
>
> D5 = Sp
>
> D6 = EX
>
> D7 = DP
>
> D8 = <- arrow left
>
> D9 = -> arrow right
>
> 
>
> Example:
>
> D1:1 = Lvl-symbol:1
>
> D1:2 = Lvl-symbol:2
>
> 
>
> 
>
> 
>
> h11F = Size of full itemdescription (one chunk)
>
> h72 = size of itemdescription (itemname + descritiontext) not including boosts/atributes/secrets
>
> relative 0xD3 long = number of the item (used in shop.bin)
>
> relative 0xD5 = kind of item
>
> relative 0xD6 = itemsymbol (depends of kind of item)
>
> relative 0xD9 long = heal ammount of item				itemspecific
>
> relative 0xDA = for magicgems it specifics the symbol	itemspecific
>
> relative 0xE9 long = WP for first lvl
>
> relative 0xED long = WP for second lvl
>
> relative 0xEE long = ability given to the item by number of an ability from ability.bin ( 0x66 of each chunk in ability.bin) only for accessoary?
>
> relative 0xF1 long = WP for third lvl
>
> relative 0x101 long = price of the item
>
> relative 0x105 long = sellprice of the item
>
> 
>
> 
>
> (singed) int32 in size (Double Word)
>
> relative 0xD7 = atk of item
>
> relative 0xDB = def of item
>
> relative 0xDF = mag of item
>
> relative 0xE3 = res of item
>
> relative 0xE7 = spd of item
>
> 
>
> 
>
> 
>
> ???relative 0xD5 long = kind of item? (maybe symbol for it)
>
> ???relative 0xF7 short = kind of item? (maybe symbol for it)
Without engagement.
