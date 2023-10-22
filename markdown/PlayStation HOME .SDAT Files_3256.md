## Post #1
- Username: CakeIsALie
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 05, 2007 4:04 am
- Post datetime: 2008-12-19T01:42:27+00:00
- Post Title: PlayStation HOME .SDAT Files

See, the reason I really want this is this:

HOME uses a very horribly made server so all the files are COMPLETELY OPEN to ANYONE to Upload, Delete, and Download. Now, You can set up an Apache Server + Simple DNS to change the files on HOME by placing a folder in Htdocs called C.HOME and name the folders inside to correspond to the HOME files. Here is a list of stuff from Wireshark.

c.home/prod/live/CommercePoints/ThreadsCP.xml
;--------------------------------------------
c.home/prod/live/CommercePoints/Thumbnails/feet.dds
c.home/prod/live/CommercePoints/Thumbnails/Head.dds
c.home/prod/live/CommercePoints/Thumbnails/Hands.dds
c.home/prod/live/CommercePoints/Thumbnails/torso.dds
c.home/prod/live/CommercePoints/Thumbnails/legs.dds
c.home/prod/live/CommercePoints/Thumbnails/***ellery.dds
c.home/prod/live/CommercePoints/Thumbnails/accessories.dds
;-------------------------------------------------------------
;c.home/prod/live/CommercePoints/FurnitureCP.xml
;-----------------------------------------------
c.home/prod/live/CommercePoints/Thumbnails/Category_appliances.dds
c.home/prod/live/CommercePoints/Thumbnails/Category_Sofas.dds
c.home/prod/live/CommercePoints/Thumbnails/Category_Lights.dds
c.home/prod/live/CommercePoints/Thumbnails/Category_Cubes.dds
c.home/prod/live/CommercePoints/Thumbnails/Categoryvases.dds
c.home/prod/live/CommercePoints/Thumbnails/Category_Flooring.dds
c.home/prod/live/CommercePoints/Thumbnails/Category_Storage.dds
c.home/prod/live/CommercePoints/Thumbnails/Category_Tables.dds
c.home/prod/live/CommercePoints/Thumbnails/footstools.dds
c.home/prod/live/CommercePoints/Thumbnails/Category_Chairs.dds
c.home/prod/live/CommercePoints/Thumbnails/Category_PictureFrames.dds
;-------------------------------------------------------------
;c.home/prod/live/CommercePoints/EstatesCP.xml
;---------------------------------------------
c.home/prod/live/CommercePoints/Thumbnails/home.png
c.home/prod/live/Objects/2519FAC0-18AA4FCB-A1214F6B-65F5F001/small.png
Objects/2519FAC0-18AA4FCB-A1214F6B-65F5F001/object.sdat
;================================================= ====================
;Home Square to Bowling Zone
;---------------------------
c.home/prod/live/Objects/B856BC62-F3FC43FE-87C5EB83-117FACBD/object.sdat
c.home/prod/live/Objects/00000000-00000000-00000000-0000000F/object.sdat
;-----------------------------------------------------------------------
;Carriage Return:
;----------------
c.home/prod/live/Objects/A086E0D3-11D24F85-90DE7257-A53C1E3D/object.sdat
c.home/prod/live/Objects/A086E0D3-11D24F85-90DE7257-A53C1E3D/object.odc
;-----------------------------------------------------------------------
;Echochrome:
;-----------
c.home/prod/live/Objects/581E558D-B83E4A4C-BBE5206B-3ABBEEF0/object.sdat
Game: c.home/prod/live/Objects/B856BC62-F3FC43FE-87C5EB83-117FACBD/object.odc
;------------------
;Echochrome Prizes
;------------------
c.home/prod/live/Objects/AEDE0715-A5244447-8BF6F25C-926792B7/object.odc
c.home/prod/live/Objects/73352A25-FD554BA9-B792EEDD-79A25B85/object.odc
c.home/prod/live/Objects/5B6E6E51-B8A04E98-9EE27FFB-12FEF108/object.odc
c.home/prod/live/Objects/2519FAC0-18AA4FCB-A1214F6B-65F5F001/object.odc
c.home/prod/live/Objects/DC631B86-ECCD4D35-9C80C20B-5920677A/object.odc
c.home/prod/live/Objects/2344A58E-D3424735-94158DA7-51A3C8FE/object.odc
c.home/prod/live/Objects/D17B708F-E0FA4696-80A954DC-38C1A621/object.odc
c.home/prod/live/Objects/7B5D95DF-F3A44641-8DE067BB-F552EF01/object.odc
c.home/prod/live/Objects/B22ED42D-B9BF469A-A12AF042-867133A4/object.odc
;================================================= =====================
;Appartment Arcade Machines:
;---------------------------
PACMAN:
Object: /c.home/prod/live/Objects/AD3FB153-328647C4-A6B962CB-EF41ACF7/object.sdat
Game: /c.home/prod/live/Objects/41C2F23E-8E704EA1-99FD02BF-73A256F6/object.sdat
;--------------------------------------------------------------------------------
Galaga:
Object: /c.home/prod/live/Objects/EE688794-028B40DF-BE55C5DF-2D79B519/object.sdat
Game: /c.home/prod/live/Objects/CCC21498-F1D74A33-883EB82D-4FA60565/object.sdat
;================================================= =====================
;Home Square:
;------------
c.home/prod/live/Objects/00000000-00000000-00000000-01060005/object.sdat
c.home/prod/live/Objects/00000000-00000000-00000000-01010007/object.sdat
c.home/prod/live/Objects/00000000-00000000-00000000-00010008/object.sdat
c.home/prod/live/Objects/AB172FBC-D5AC45F5-B586BEBD-3E11A9D6/object.sdat
c.home/prod/live/Objects/54ED1821-9AAA4679-9941D858-0954A13D/object.sdat
c.home/prod/live/Objects/00000000-00000000-00000000-00030054/object.sdat
c.home/prod/live/Objects/00000000-00000000-00000000-00010022/object.sdat
c.home/prod/live/Objects/4570FEA4-29DE401B-8A74C9BC-46730EA8/object.sdat
;================================================= ===================== 
Now, just copy + paste this after [http://scee-home.playstation.net/](http://scee-home.playstation.net/) in your Web Browser and the file downloads. Now, with the Apache Server idea, people have made custom posters, and vids by editing the XML files. The .sdat files for the games contain JAVA Scripts for the games so in theory, someone could unpack the .sdat and edit the script and repack it and then you could use the Server and load the new files and play whatever you want on the arcade machines in HOME. The .sdats header is "NPD" and the end of the file says "SDATA 2.2.0".

Anyone know this filetype/can crack it?
