## Post #1
- Username: TheMathDoc
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2013 11:57 pm
- Post datetime: 2013-09-06T17:25:00+00:00
- Post Title: Dragon's Prophet idx and .p### files

Just putting this here in case anyone in the future wants a go at these files for the MMO Dragon's Prophet (the game is still in beta so this may change):

.idx file structure (index file for each package)

Bytes 0 -23: 24 byte header

Followed by file table entries which are 33 bytes + the file name

Bytes 0-11 ?
Bytes 12-15: Offset in package
Bytes 16-19: ?
Bytes 20-23: Zipped Size in package, not including the file's 28 byte header (see below)
Byte 24: Package file number (the data is in packages with extensions .p###, where this byte is the ### as a three digit number)
Bytes 25-28: ?
Bytes: 29-32: File name Length
Then the file name itself

.p### file structure:

Bytes 0-3: Header

Then, in succession, the file data which is of the form:
28 byte header, zlib file stream


I know this is far from complete, but if anyone wants to go out there an make an extractor for this game, I figure this is a nice start. Feel free to add in any extra details I missed.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-06T19:08:18+00:00
- Post Title: Dragon's Prophet idx and .p### files

You can upload small packages p0x and idx?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-07T23:02:56+00:00
- Post Title: Dragon's Prophet idx and .p### files

If I understand correctly it should look like this:

```
{
	BYTE    pHeader[16]; //"Rx.1.2.1157.tw + \x00
	DWORD	pNulls;
	DWORD	pTotalFiles;
};

struct IDXEntry
{
	DWORD	pUnknown1;        // unknown.. can be 1/2
	DWORD	pUnknown2;
	DWORD	pUnknown3;
	DWORD	pOffset;
	DWORD	pUnknown4;
	DWORD	pSize;
	BYTE    pArchiveNum;
	DWORD	pUnknown5;        // always 1
	DWORD	pFileNameLength;
};
```



About compression : It's not Zlib..

And additional :
[lzham](http://code.google.com/p/lzham/) -> D:\Works\trunk\Libraries\lzham\lzhamdecomp\
[crunch](http://code.google.com/p/crunch) -> D:\Works\trunk\Libraries\crunch\crnlib\

All files with header 28 bytes looks like :

```
{
	DWORD	pZSize;           // compressed size
	DWORD	pUnknown1;        // unknown.. can be 1/2
	DWORD	pUnknown2;        // hash1 ???
	DWORD	pUnknown3;        // hash2 ???
	DWORD	pUnknown4;        // 4
	DWORD	pSize;            // uncompressed size
	DWORD	pBSize;           // compressed data block size
};
```


After will be the compressed data with size > pBSize. Very similar to LZMA but comtype scanner gave no results.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-08T11:32:44+00:00
- Post Title: Dragon's Prophet idx and .p### files

Well here unpacker. Currently can't decompress compressed files because algo is unknown. And as an evil game does not support WinXP 

Not Compressed files can be read. Example

data\luascript\70000442.lua

```
function PE02_giveitem()
	GiveBodyItem(OwnerID(),20001123,1) 
end
```


Download: See below
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-08T19:36:31+00:00
- Post Title: Dragon's Prophet idx and .p### files

Okay one compression algo 100% is LZMA but a little bit of modified 

Just for example file data\luascript\70000021.lua

Original header (skip 28 bytes)

```
5D 00 00 00 01 6C 04 00 00
```

Normal LZMA header must be

```
5D 00 00 80 01 6C 04 00 00 00 00 00 00
```


and we get like this

```
function TestZoneSysKey()
	Say( OwnerID() , GetZoneKeyValue( -1 , 1 , EM_RegZoneKeyValue_RoomCount ) );
	RegZoneKeyValue( -1 , 1 , EM_RegZoneKeyValue_RoomCount );
	Sleep( 30 );
	Yell( OwnerID() , GetZoneKeyValue( -1 , 1 , EM_RegZoneKeyValue_RoomCount ) );
end

function TestZoneSysKey_Reg( zoneid , type )
	RegZoneKeyValue( -1 , zoneid  , type );
end

function TestZoneSysKey_Set( type , value  )
	SetZoneKeyValue(type, value );
end

function TestZoneSysKey_Get( zoneid , type  )
	Yell( OwnerID() , GetZoneKeyValue( -1 , zoneid  , type ) );
end

function Test_CreateInstance()
	OpenCreateInstaneMenu( ownerID() , -1 , 903 , 0 , 0 , 0 , 0 , 0 );
end

function SysOpenAllPaletteBank()

	for i = 1 , 1024 do
		WriteRoleValue ( OwnerID() ,RoleValueName_Arrary_ColorBankFlag*1000000 +i ,1 );
	end
end

function SysSendSummonPlayer()
		SendSummonPlayer( TargetID() )
end

function SysSetTitleInfo(id)
	SetTitleInfo( OwnerID() , id )
end

function Test_GetRoleName()
	Yell( OwnerID() , " Owner=" .. GetPlayerName( OwnerID() ) .. " Target=" .. GetPlayerName( TargetID() ) );
end
```


With the textures have a problem. Examples

File compressed by LZMA

```
interface\icons\cooking\food_bread_01.dds
```


But another file from this folder have unknown compression... crunch maybe?  

```
interface\icons\cooking\foodfish_01.dds
```
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-09T11:44:27+00:00
- Post Title: Dragon's Prophet idx and .p### files

Updated. Now decompressing (LZMA only) files while unpacking. DDS with other compression (100% crunch) currently not supported.

Download: See below
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-09T13:07:16+00:00
- Post Title: Dragon's Prophet idx and .p### files

Final Build - All compression methods are is supported LZMA/Crunch.

[](http://imageshack.us/photo/my-images/9/fqwh.png/)

Enjoy 
[IDXUpacker_0.0.2b_r49.rar](https://xentaxbackup.github.io/file/6610_IDXUpacker_0.0.2b_r49.rar)
## Post #8
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2013-09-13T06:58:31+00:00
- Post Title: Dragon's Prophet idx and .p### files

Thanks Ekey.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-20T22:32:44+00:00
- Post Title: Dragon's Prophet idx and .p### files

nice ekey, but jesus mother of god, atlas.idx, with only a 30 MB or so p00 file is still unpacking after 20 minutes . anything you can do to make this stuff unpack a little faster ? there's like 9 GB of this stuff.
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-20T23:00:49+00:00
- Post Title: Dragon's Prophet idx and .p### files

ekey, my friend, i will be more than happy to do this game, it looks very doable.

i see why you were interested in it now LOL!
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-21T08:54:40+00:00
- Post Title: Dragon's Prophet idx and .p### files

> Reply from howfie
>
> nice ekey, but jesus mother of god, atlas.idx, with only a 30 MB or so p00 file is still unpacking after 20 minutes . anything you can do to make this stuff unpack a little faster ?
Nope 

> Reply from howfie
>
> ekey, my friend, i will be more than happy to do this game, it looks very doable.

i see why you were interested in it now LOL!
Well i see now you too are interested, LOL
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-21T16:19:35+00:00
- Post Title: Dragon's Prophet idx and .p### files

hahahaha well in-game the models actually look quite bad, but i think either the vertex normals or the lighting is bad in the game and that's fixable. the hair has no alpha either so that looks bad too (but neither did saints row: the third and lots of other games, and that's fixable too).
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-21T17:16:03+00:00
- Post Title: Dragon's Prophet idx and .p### files

> Reply from howfie
>
> well in-game the models actually look quite bad
Well okay
## Post #14
- Username: LordDragonus
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 16, 2013 8:47 am
- Post datetime: 2013-11-16T07:37:03+00:00
- Post Title: Dragon's Prophet idx and .p### files

Hello!

I'm new here, registered to get this great program. I tested the program and... What should i say?! It's so great! Very fast unpacker  Thanks for that great work!

And BTW: Do someone know, how to open the .db files? Its not an SQLite databse
## Post #15
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-16T09:39:10+00:00
- Post Title: Dragon's Prophet idx and .p### files

> Reply from LordDragonus
>
> And BTW: Do someone know, how to open the .db files? Its not an SQLite databse
Seems it's custom binary base.
## Post #16
- Username: qbasic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 17, 2012 4:49 am
- Post datetime: 2013-11-16T10:42:14+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

what are you need from db?
## Post #17
- Username: LordDragonus
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 16, 2013 8:47 am
- Post datetime: 2013-11-16T14:29:26+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

> Reply from qbasic
>
> what are you need from db?
I want to open them and read some details, such as items or dragons, to create a list for me
## Post #18
- Username: LordDragonus
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 16, 2013 8:47 am
- Post datetime: 2013-11-16T18:08:39+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

Sorry for posting again. But, is it possible to open a model? There are some ros and ras files with the textures in dds format. I spend the whole day now to open them, but didnt find anything  Can someone help me?
## Post #19
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-11-16T21:08:26+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

Send me some characters models with textures, I'll see what I can do.
## Post #20
- Username: LordDragonus
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 16, 2013 8:47 am
- Post datetime: 2013-11-17T18:18:51+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

> Reply from qbasic
>
> what are you need from db?

Can anyone help me to decrypt the databases? I see some strings there, but its to hard for me -.-
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-17T18:38:07+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

> Reply from LordDragonus
>
> qbasic wrote:what are you need from db?

Can anyone help me to decrypt the databases? I see some strings there, but its to hard for me -.-
They not encrypted.
## Post #22
- Username: LordDragonus
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 16, 2013 8:47 am
- Post datetime: 2013-11-17T18:43:10+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

> Reply from Ekey
>
> LordDragonus wrote:qbasic wrote:what are you need from db?

Can anyone help me to decrypt the databases? I see some strings there, but its to hard for me -.-
They not encrypted.

Oh, yeah, my fault  But i dont know how i can transfer them into a better format, eg. SQLite or something like that or CSV?
## Post #23
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-17T19:44:09+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

You can share simple files here maybe someone can convert to txt, xml or cvs and ect.
## Post #24
- Username: LordDragonus
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 16, 2013 8:47 am
- Post datetime: 2013-11-17T19:52:39+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

Here is a small database.

[EDIT: Deleted file]
## Post #25
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2013-12-26T00:04:30+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

Sorry for digging up an older topic, but I think creating a new one would be the same, kinda.

Is there any progress on extracting 3d models and opening them somehow? Maybe even with bones and rig?

Would love to tinker around with 'em.

Also:

It might be a false positive, but the IDXUnpacker app is flagged as suspicious by BitDefender. BD also just allowed itself to remove the EXE from my pc. Just a bit paranoid.
## Post #26
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-12-26T13:24:25+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

ekey's program works great; it's not a virus.
model format is not hard but i lost interest due to low quality of the models.
## Post #27
- Username: SomeTemp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 27, 2014 6:49 pm
- Post datetime: 2014-10-05T13:44:43+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

I'm Sorry for resume this old topic:
But I'm a very idiot.
My idea is make a use-personal translate of the game:
Translate the following files: string.db and stringeneu.db ✔ (I used a UltraEdit for translate some text, I don't know if it work)
and repack the data.p000.
It is possible?
Or I'm a crazy?

Thanks for the reply.
## Post #28
- Username: the1domo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 13, 2012 4:15 pm
- Post datetime: 2015-11-08T09:41:30+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

have progress, on make tool for editing 
[http://prntscr.com/902fkw](http://prntscr.com/902fkw)
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-08T10:35:31+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

> Reply from the1domo
>
> have progress, on make tool for editing
Localization tool?
## Post #30
- Username: Cippman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 18, 2017 1:25 am
- Post datetime: 2018-02-07T21:54:52+00:00
- Post Title: Re: Dragon's Prophet idx and .p### files

I'm just some years late about these topics   ... but someone gone more far on Dragon's Prophet files?
