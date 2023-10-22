## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-12T21:04:49+00:00
- Post Title: Sleeping Dogs DLC DAT (Translation and Unlock) Tool

Well tool for decrypt and encrypt DAT files inside game folder. Output file just simple editable XML file. There translation text's for DLC as well as you can unlock it.

```
        SDDATTool <szInFile> <szOutFile>

[Examples]
        SDDATTool BCF931BB.dat DLC1.xml
        SDDATTool DLC1.xml BCF931BB.dat
```


Example for BCF931BB.dat (filename hashed, you can found original name in DLC_2.0.434913_Info.txt or DLC_2.1.435919_Info.txt)

```
	<Version>1</Version>
	<ProductId>DLC1_POLICE_PROTECTION_PACK</ProductId>
	<ShortDescription>$DLC_PRESALE_POLICE_PROTECTION_PACK_SHORT_DESCRIPTION</ShortDescription>
	<LongDescription>$DLC_PRESALE_POLICE_PROTECTION_PACK_LONG_DESCRIPTION</LongDescription>
	<PackDescription>
		<TITLE>Sleeping Dogs™ - Police Protection Pack</TITLE>
		<TITLE_JAPANESE>Sleeping Dogs™ - 警察の保護パックで本物のSWATさながらに犯罪者を検挙せよ！</TITLE_JAPANESE>
		<TITLE_ENGLISH>Sleeping Dogs™ - Police Protection Pack</TITLE_ENGLISH>
		<TITLE_FRENCH>Sleeping Dogs™ - Pack Protection policière</TITLE_FRENCH>
		<TITLE_SPANISH>Sleeping Dogs™ - Paquete Protección policial</TITLE_SPANISH>
		<TITLE_GERMAN>Sleeping Dogs™ - Polizeischutz-Pack</TITLE_GERMAN>
		<TITLE_ITALIAN>Sleeping Dogs™ - Pacchetto Protezione della polizia</TITLE_ITALIAN>
		<TITLE_RUSSIAN>Sleeping Dogs™ - Набор ''Под защитой полиции''</TITLE_RUSSIAN>
		<TITLE_POLISH>Sleeping Dogs™ - Pakiet Ochrony Policyjnej</TITLE_POLISH>
	</PackDescription>
	<ClothingUnlocks>
	</ClothingUnlocks>
	<VehicleUnlocks>
	</VehicleUnlocks>
	<BoatUnlocks>
	</BoatUnlocks>
	<MoveUnlocks>
	</MoveUnlocks>
	<MissionUnlocks>
		<Entry>DLC_PRESALE_POLICE_PROTECTION</Entry>	
	</MissionUnlocks>
	<OverrideBigFiles>
	</OverrideBigFiles>
	<OverrideAudioPacks>
	</OverrideAudioPacks>
	<SafehouseItems>
	</SafehouseItems>
	<PropUnlocks>		
	</PropUnlocks>
</DLCManifest>

```
 
ect. And of course example result [here](http://img856.imageshack.us/img856/5082/hkship2013021300541403.png). I hope maybe for some one useful. Enjoy 
[SDDATTool_0.1.rar](https://xentaxbackup.github.io/file/6190_SDDATTool_0.1.rar)
## Post #2
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-02-13T10:45:53+00:00
- Post Title: Sleeping Dogs DLC DAT (Translation and Unlock) Tool

Does this work for the main game too as in translation? Or just the DLCs?
## Post #3
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2013-02-13T11:59:55+00:00
- Post Title: Sleeping Dogs DLC DAT (Translation and Unlock) Tool

what is the name of the file has the text of the full game?
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-13T12:56:00+00:00
- Post Title: Sleeping Dogs DLC DAT (Translation and Unlock) Tool

Tools for edit game files inside archives will not be because files inside compressed with ugly method. This tool created in order to unlock DLC's basically.
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-13T14:29:54+00:00
- Post Title: Sleeping Dogs DLC DAT (Translation and Unlock) Tool

> Reply from Ekey
>
> Tools for edit game files inside archives will not be because files inside compressed with ugly method. This tool created in order to unlock DLC's basically.

Might game runs without the compression ?
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-13T15:36:39+00:00
- Post Title: Sleeping Dogs DLC DAT (Translation and Unlock) Tool

> Reply from michalss
>
> Ekey wrote:Tools for edit game files inside archives will not be because files inside compressed with ugly method. This tool created in order to unlock DLC's basically.

Might game runs without the compression ?
Seems yes. Because files inside BIG not all compressed as well as always check header. If PCQM need decompress else simple read.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-13T19:20:29+00:00
- Post Title: Sleeping Dogs DLC DAT (Translation and Unlock) Tool

> Reply from Ekey
>
> michalss wrote:Ekey wrote:Tools for edit game files inside archives will not be because files inside compressed with ugly method. This tool created in order to unlock DLC's basically.

Might game runs without the compression ?
Seems yes. Because files inside BIG not all compressed as well as always check header. If PCQM need decompress else simple read.

So s there a chance to make repacker without compression pls ?
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-14T14:51:37+00:00
- Post Title: Sleeping Dogs DLC DAT (Translation and Unlock) Tool

Well [unpacker](http://forum.xentax.com/viewtopic.php?p=83035#p83035) updated. Now decompression work, tested on WinXP, Win7
