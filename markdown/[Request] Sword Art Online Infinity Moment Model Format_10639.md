## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-07-28T07:51:26+00:00
- Post Title: [Request] Sword Art Online Infinity Moment Model Format

Hi, I'm wondering if anyone here could be so kind as to figure out the file format of the SAO models and make a script for Noesis, 3ds max, maya or lightwave, any of those. I'm still new to this so I don't quite understand how to do this myself. Heres some samples: [link down]
The files don't have any extension so I'm not 100% sure on its file format. I think it might be .OMG.00.1PSP or .OFS3
Thanks in advance
## Post #2
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-09-29T14:59:45+00:00
- Post Title: [Request] Sword Art Online Infinity Moment Model Format

OFS3 is a file container, and the models inside are standard MGO (OGM) models used in psp games.
as far as i know, noesis is able to view them already. I dont work with 3d data much though, so havent looked at it any more.

i mapped the ofs3 file container while examining this game for a possible translation back when it released though,
it's something along these lines:

> OFS3 filesystem:
>
> (Example file: psp/ui/storage.bin)
>
> 0x00: 4F46 5333 1000 0000 0200 4000 30A3 0200
>
> 0x10: 0300 0000 3000 0000 00DF 0100 30A3 0200
>
> 0x20: 30DF 0100 0CC3 0000 41A3 0200 70A2 0200
>
> 0x30: A000 0000 4FA3 0200 0000 0000 0000 0000
>
> 
>
> (OFS3 header (16-bytes))
>
> 0x00: [4-bytes] OFS3 file signature (it's always 4F46 5333)
>
> 0x04: [4-bytes] OFS3 Header size (it's always 1000 0000)
>
> 0x08: [4-bytes] Unknown value
>
> 0x0c: [4-bytes] Nametable Start address (this points to the end of the file if nametable doesnt exist)
>
> 
>
> ( OFS3 Filetable (variable size))
>
> data table starts with a 4-byte value indicating file count.
>
> each file entry consists of 12-bytes
>
> 
>
> 0x10: [4-bytes] Number of files
>
> 
>
> 0x14: [4-bytes] File Start Address
>
> 0x18: [4-bytes] File Length
>
> 0x1c: [4-bytes] Filename Position
>
> 
>
> [the pattern of 0x14 -> 0x1C repeats as many times as there are files inside the container]
>
> 
>
> Note: If 0xC points to file end (no nametable present) the value of 0x1C (name position) is omitted, and the
>
> structure only consists of File Start Address + File Length values.
>
> 
>
> Note: the addresses displayed within OFS3 Filetable are relative to Data, which means you need to either add 0x10 (16 bytes) to every address, or delete the first 16 bytes (the OFS3 File header) prior to extracting.

it's worth a note that i found more than 6 types of OFS3 containers from within the game, it seems it was slightly altered to accomondate different types of data.

extracting/repacking textures with the above data is entirely possible though.

example.


hope this helps
