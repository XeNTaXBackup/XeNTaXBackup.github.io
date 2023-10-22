## Post #1
- Username: Castiel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 13, 2011 5:09 am
- Post datetime: 2019-05-15T03:02:11+00:00
- Post Title: State of Decay 2 - Unreal Engine

I'm having trouble determining the structure of one of SoD2's save files.

[Save FIles](https://mega.nz/#F!GBJUzABQ!ahZ6izWlQpkybvXJHC1tHQ)

The file is 7964C6DE5F9449B3B28AAE67CCB4EEB5.

I'm trying to map out the structure of the file. This [GitHub repo](https://github.com/13xforever/gvas-converter) has some useful stuff, but there's a block of data that I can't figure out.

I've included the .h and .bt files above. Hoping someone can lend a hand.

The block of data in question is named TextProperty in the file itself.

```
class UETextProperty
{
	public Name { get; set; }
	public ulong Size { get; set; }
	public byte UnknownByte { get ; set; }
	public byte[] Content { get; set; } // A byte array of size Size
}


```


My issue is the structure of the content across different save files appears to fluctuate. Any advice is appreciated.

EDIT: May 17, 2019

At the urging of a discord member, I've looked through the UE4 source code to try and pin down how data is serialized.

\UnrealEngine-release\Engine\Source\Runtime\CoreUObject\Private\UObject\PropertyTag.cpp
\UnrealEngine-release\Engine\Source\Runtime\CoreUObject\Private\Serialization\Formatters\TaggedBinaryArchiveOutputFormatter.cpp
\UnrealEngine-release\Engine\Source\Runtime\CoreUObject\Private\UObject\Class.cpp
\UnrealEngine-release\Engine\Source\Runtime\Core\Public\Serialization\Formatters\BinaryArchiveFormatter.h


There are 3 classes that implement the binary formatter: TaggedBinaryArchiveOutputFormatter, JsonArchiveOutputFormatter, and BinaryArchiveFormatter. Json is out, leaving the base formatter and the tagged formatter.

The tagged formatter emits a byte to indicate the type of data, then the data itself. The untagged formatter just writes the data the byte prefix.

However, I still can't match the structure to the properties I can find in the source. 

This is what I'm using to try and map this property:

```
{
    FString Name;
    FString Type;
    int Size;
    int ArrayIndex;

    if (Type == "StructProperty")
    {
        FString StructName;
        byte _Guid[16];
    }
    else if (Type == "BoolProperty")
    {
        ubyte BoolVal;
    }
    else if (Type == "ByteProperty" || Type == "EnumProperty")
    {
        FString EnumName;
    }
    else if (Type == "ArrayProperty")
    {
        FString InnerType;
    }

    if (Tag.Type == "SetProperty")
	{
		FString InnerType;
	}
	else if (Tag.Type == "MapProperty")
	{
		FString InnerType;
        FString ValueType;
	}
} FPropertyTagImpl;

typedef struct FString
{
    int length <hidden=true>;
    if (length > 0)
        char value[length];
    else if (length < 0)
        wchar_t value[length];
} FStringImpl;
```


Here's an excerpt of a property:

```
1:5EA1h: 0D 00 00 00 54 65 78 74 50 72 6F 70 65 72 74 79  ....TextProperty 
1:5EB1h: 00 02 15 00 00 00 00 00 00 00 01 00 00 00 0B C8  ...............È 
1:5EC1h: 00 00 00 00 00 70 00 00 00 44 61 79 74 6F 6E 2E  .....p...Dayton. 
1:5ED1h: 4D 69 73 73 69 6F 6E 2E 41 72 63 5F 4C 65 67 61  Mission.Arc_Lega 
1:5EE1h: 63 79 5F 53 68 65 72 69 66 66 5F 53 74 61 6E 64  cy_Sheriff_Stand 
1:5EF1h: 41 6C 6F 6E 65 2E 4C 65 67 61 63 79 5F 53 68 65  Alone.Legacy_She 
1:5F01h: 72 69 66 66 5F 53 41 5F 50 72 65 4C 65 61 64 65  riff_SA_PreLeade 
1:5F11h: 72 5F 53 74 72 61 6E 67 65 72 73 4E 65 65 64 48  r_StrangersNeedH 
1:5F21h: 65 6C 70 2E 4D 69 73 73 69 6F 6E 53 74 61 72 74  elp.MissionStart 
1:5F31h: 45 76 65 6E 74 73 2E 35 00 0C 00 00 00 44 65 73  Events.5.....Des 
1:5F41h: 63 72 69 70 74 69 6F 6E 00 1E 00 00 00 41 20 64  cription.....A d 
1:5F51h: 61 6E 67 65 72 6F 75 73 20 67 72 6F 75 70 20 6F  angerous group o 
1:5F61h: 66 20 74 68 69 65 76 65 73 2E 00 23 00 00 00 0E  f thieves..#.... 
1:5F71h: 00 00 00 4D 65 64 73 49 74 65 6D 2E 54 79 70 65  ...MedsItem.Type 
1:5F81h: 00 04 00 00 00 00 00 25 00 00 00 44 61 79 74 6F  .......%...Dayto 
1:5F91h: 6E 2E 52 65 73 6F 75 72 63 65 49 74 65 6D 2E 4D  n.ResourceItem.M 
1:5FA1h: 65 64 73 52 65 73 6F 75 72 63 65 42 61 73 65 00  edsResourceBase. 
1:5FB1h: 05 00 00 00 54 79 70 65 00 19 00 00 00 52 75 63  ....Type.....Ruc 
1:5FC1h: 6B 73 61 63 6B 20 2D 20 4D 65 64 73 20 52 65 73  ksack - Meds Res 
1:5FD1h: 6F 75 72 63 65 00 0E 00 00 00 4D 65 64 73 49 74  ource.....MedsIt 
1:5FE1h: 65 6D 2E 4E 61 6D 65 00 04 00 00 00 00 00 2A 00  em.Name.......*. 
1:5FF1h: 00 00 44 61 79 74 6F 6E 2E 52 65 73 6F 75 72 63  ..Dayton.Resourc 
1:6001h: 65 49 74 65 6D 2E 54 6F 6F 6C 73 4D 65 64 73 52  eItem.ToolsMedsR 
1:6011h: 65 73 6F 75 72 63 65 49 74 65 6D 00 05 00 00 00  esourceItem..... 
1:6021h: 4E 61 6D 65 00 1D 00 00 00 53 65 74 7B 5B 30 2C  Name.....Set{[0, 
1:6031h: 2B 5D 73 7D 20 6F 66 20 4D 65 64 69 63 61 6C 20  +]s} of Medical  
1:6041h: 54 6F 6F 6C 73 00 18 00 00 00 42 61 64 48 6F 6D  Tools.....BadHom 
1:6051h: 62 72 65 73 4C 6F 63 61 74 69 6F 6E 2E 4E 61 6D  bresLocation.Nam 
1:6061h: 65 00 04 00 00 00 00 00 35 00 00 00 44 61 79 74  e.......5...Dayt 
1:6071h: 6F 6E 2E 4C 6F 63 61 74 69 6F 6E 2E 38 61 36 39  on.Location.8a69 
1:6081h: 32 33 61 63 2D 34 36 30 63 2D 35 39 63 32 2D 61  23ac-460c-59c2-a 
1:6091h: 66 63 39 2D 33 36 61 36 64 61 33 31 39 34 62 62  fc9-36a6da3194bb 
1:60A1h: 00 05 00 00 00 4E 61 6D 65 00 0F 00 00 00 48 75  .....Name.....Hu 
1:60B1h: 6E 74 65 72 27 73 20 48 6F 75 73 65 00 17 00 00  nter's House.... 
1:60C1h: 00 49 6E 6A 75 72 65 64 53 74 72 61 6E 67 65 72  .InjuredStranger 
1:60D1h: 2E 47 65 6E 64 65 72 00 04 02 00 00 00 00 00 00  .Gender......... 
1:60E1h: 00 00 00 00 00 00 06 00 00 00 7B 21 3C 6D 7D 00  ..........{!<m}. 
1:60F1h: 19 00 00 00 49 6E 6A 75 72 65 64 53 74 72 61 6E  ....InjuredStran 
1:6101h: 67 65 72 2E 53 74 61 6E 64 69 6E 67 00 04 01 00  ger.Standing.... 
1:6111h: 00 00 0B C8 08 00 00 00 00 17 00 00 00 44 61 79  ...È.........Day 
1:6121h: 74 6F 6E 2E 43 68 61 72 61 63 74 65 72 52 65 63  ton.CharacterRec 
1:6131h: 6F 72 64 00 15 00 00 00 53 74 61 6E 64 69 6E 67  ord.....Standing 
1:6141h: 4E 61 6D 65 53 74 72 61 6E 67 65 72 00 09 00 00  NameStranger.... 
1:6151h: 00 4F 75 74 73 69 64 65 72 00 01 00 00 00 11 00  .Outsider....... 
1:6161h: 00 00 43 68 61 72 61 63 74 65 72 2E 47 65 6E 64  ..Character.Gend 
1:6171h: 65 72 00 04 02 00 00 00 00 00 00 00 00 00 00 00  er.............. 
1:6181h: 00 06 00 00 00 7B 21 3C 6D 7D 00 00 00 01 21 FF  .....{!<m}....!ÿ 
1:6191h: 00 00 00 00 15 00 00 00 49 6E 6A 75 72 65 64 53  ........InjuredS 
1:61A1h: 74 72 61 6E 67 65 72 2E 4E 61 6D 65 00 04 01 00  tranger.Name.... 
1:61B1h: 00 00 0A 06 00 00 00 72 75 2D 52 55 00 01 00 00  .......ru-RU.... 
1:61C1h: 00 0B 90 00 00 00 00 00 4C 00 00 00 44 4E 4C 2E  .......L...DNL. 
1:61D1h: 4E 61 6D 65 4C 69 73 74 2E 44 65 66 61 75 6C 74  NameList.Default 
1:61E1h: 5F 5F 41 6E 67 6C 6F 41 6D 65 72 69 63 61 6E 5F  __AngloAmerican_ 
1:61F1h: 43 6F 6D 6D 6F 6E 5F 4D 61 6C 65 4D 69 64 64 6C  Common_MaleMiddl 
1:6201h: 65 5F 43 2E 4E 61 6D 65 73 2E 34 2E 4E 69 63 6B  e_C.Names.4.Nick 
1:6211h: 6E 61 6D 65 73 2E 32 00 05 00 00 00 4E 61 6D 65  names.2.....Name 
1:6221h: 00 08 00 00 00 41 6E 74 6F 6E 69 6F 00 01 00 00  .....Antonio.... 
1:6231h: 00 11 00 00 00 43 68 61 72 61 63 74 65 72 2E 47  .....Character.G 
1:6241h: 65 6E 64 65 72 00 04 02 00 00 00 00 00 00 00 00  ender........... 
1:6251h: 00 00 00 00 06 00 00 00 7B 21 3C 6D 7D 00 00 00  ........{!<m}... 
1:6261h: 01 21 FF 00 00 00 00 00 00 00 00 00 4C 00 00 00  .!ÿ.........L... 
1:6271h: 44 4E 4C 2E 4E 61 6D 65 4C 69 73 74 2E 44 65 66  DNL.NameList.Def 
1:6281h: 61 75 6C 74 5F 5F 41 6E 67 6C 6F 41 6D 65 72 69  ault__AngloAmeri 
1:6291h: 63 61 6E 5F 43 6F 6D 6D 6F 6E 5F 4D 61 6C 65 4D  can_Common_MaleM 
1:62A1h: 69 64 64 6C 65 5F 43 2E 4E 61 6D 65 73 2E 34 2E  iddle_C.Names.4. 
1:62B1h: 4E 69 63 6B 6E 61 6D 65 73 2E 32 00 05 00 00 00  Nicknames.2..... 
1:62C1h: 4E 61 6D 65 00 08 00 00 00 41 6E 74 6F 6E 69 6F  Name.....Antonio 
1:62D1h: 00 19 00 00 00 49 6E 6A 75 72 65 64 53 74 72 61  .....InjuredStra 
1:62E1h: 6E 67 65 72 2E 4C 61 73 74 4E 61 6D 65 00 04 00  nger.LastName... 
1:62F1h: 00 00 00 00 45 00 00 00 44 4E 4C 2E 4E 61 6D 65  ....E...DNL.Name 
1:6301h: 4C 69 73 74 2E 44 65 66 61 75 6C 74 5F 5F 41 6E  List.Default__An 
1:6311h: 67 6C 6F 41 6D 65 72 69 63 61 6E 5F 43 6F 6D 6D  gloAmerican_Comm 
1:6321h: 6F 6E 5F 53 75 72 6E 61 6D 65 73 5F 43 2E 4E 61  on_Surnames_C.Na 
1:6331h: 6D 65 73 2E 32 34 34 2E 4E 61 6D 65 00 05 00 00  mes.244.Name.... 
1:6341h: 00 4E 61 6D 65 00 05 00 00 00 46 69 6E 6E 00 1A  .Name.....Finn.. 
1:6351h: 00 00 00 49 6E 6A 75 72 65 64 53 74 72 61 6E 67  ...InjuredStrang 
1:6361h: 65 72 2E 46 69 72 73 74 4E 61 6D 65 00 04 00 00  er.FirstName.... 
1:6371h: 00 00 00 45 00 00 00 44 4E 4C 2E 4E 61 6D 65 4C  ...E...DNL.NameL 
1:6381h: 69 73 74 2E 44 65 66 61 75 6C 74 5F 5F 41 6E 67  ist.Default__Ang 
1:6391h: 6C 6F 41 6D 65 72 69 63 61 6E 5F 43 6F 6D 6D 6F  loAmerican_Commo 
1:63A1h: 6E 5F 4D 61 6C 65 4D 69 64 64 6C 65 5F 43 2E 4E  n_MaleMiddle_C.N 
1:63B1h: 61 6D 65 73 2E 34 2E 4E 61 6D 65 00 05 00 00 00  ames.4.Name..... 
1:63C1h: 4E 61 6D 65 00 08 00 00 00 41 6E 74 68 6F 6E 79  Name.....Anthony 
1:63D1h: 00 10 00 00 00 42 61 64 48 6F 6D 62 72 65 73 2E  .....BadHombres. 
1:63E1h: 4E 61 6D 65 00 04 00 00 00 00 00 2A 00 00 00 44  Name.......*...D 
1:63F1h: 61 79 74 6F 6E 2E 45 6E 63 6C 61 76 65 4E 61 6D  ayton.EnclaveNam 
1:6401h: 65 2E 41 67 67 72 65 73 73 69 76 65 45 6E 63 6C  e.AggressiveEncl 
1:6411h: 61 76 65 4E 61 6D 65 73 00 25 00 00 00 62 32 39  aveNames.%...b29 
1:6421h: 38 37 39 32 37 2D 63 37 64 39 2D 34 33 32 64 2D  87927-c7d9-432d- 
1:6431h: 62 32 37 61 2D 61 32 61 35 64 35 65 30 36 33 65  b27a-a2a5d5e063e 
1:6441h: 63 00 0A 00 00 00 48 65 61 72 74 6C 65 73 73 00  c.....Heartless. 
1:6451h: 11 00 00 00 42 61 64 48 6F 6D 62 72 65 2E 47 65  ....BadHombre.Ge 
1:6461h: 6E 64 65 72 00 04 02 00 00 00 00 00 00 00 00 00  nder............ 
1:6471h: 00 00 00 06 00 00 00 7B 21 3C 66 7D 00 13 00 00  .......{!<f}.... 
1:6481h: 00 42 61 64 48 6F 6D 62 72 65 2E 53 74 61 6E 64  .BadHombre.Stand 
1:6491h: 69 6E 67 00 04 01 00 00 00 0B C8 08 00 00 00 00  ing.......È..... 
1:64A1h: 17 00 00 00 44 61 79 74 6F 6E 2E 43 68 61 72 61  ....Dayton.Chara 
1:64B1h: 63 74 65 72 52 65 63 6F 72 64 00 15 00 00 00 53  cterRecord.....S 
1:64C1h: 74 61 6E 64 69 6E 67 4E 61 6D 65 53 74 72 61 6E  tandingNameStran 
1:64D1h: 67 65 72 00 09 00 00 00 4F 75 74 73 69 64 65 72  ger.....Outsider 
1:64E1h: 00 01 00 00 00 11 00 00 00 43 68 61 72 61 63 74  .........Charact 
1:64F1h: 65 72 2E 47 65 6E 64 65 72 00 04 02 00 00 00 00  er.Gender....... 
1:6501h: 00 00 00 00 00 00 00 00 06 00 00 00 7B 21 3C 66  ............{!<f 
1:6511h: 7D 00 00 00 01 21 FF 00 00 00 00 0F 00 00 00 42  }....!ÿ........B 
1:6521h: 61 64 48 6F 6D 62 72 65 2E 4E 61 6D 65 00 04 01  adHombre.Name... 
1:6531h: 00 00 00 0A 06 00 00 00 72 75 2D 52 55 00 01 00  ........ru-RU... 
1:6541h: 00 00 0B 90 00 00 00 00 00 42 00 00 00 44 4E 4C  ........B...DNL 
1:6551h: 2E 4E 61 6D 65 4C 69 73 74 2E 44 65 66 61 75 6C  .NameList.Defaul 
1:6561h: 74 5F 5F 45 74 68 69 6F 70 69 61 6E 49 6D 6D 69  t__EthiopianImmi 
1:6571h: 67 72 61 6E 74 5F 53 75 72 6E 61 6D 65 73 5F 43  grant_Surnames_C 
1:6581h: 2E 4E 61 6D 65 73 2E 31 31 2E 4E 61 6D 65 00 05  .Names.11.Name.. 
1:6591h: 00 00 00 4E 61 6D 65 00 06 00 00 00 41 73 65 66  ...Name.....Asef 
1:65A1h: 61 00 01 00 00 00 11 00 00 00 43 68 61 72 61 63  a.........Charac 
1:65B1h: 74 65 72 2E 47 65 6E 64 65 72 00 04 02 00 00 00  ter.Gender...... 
1:65C1h: 00 00 00 00 00 00 00 00 00 06 00 00 00 7B 21 3C  .............{!< 
1:65D1h: 66 7D 00 00 00 01 21 FF 00 00 00 00 00 00 00 00  f}....!ÿ........ 
1:65E1h: 00 42 00 00 00 44 4E 4C 2E 4E 61 6D 65 4C 69 73  .B...DNL.NameLis 
1:65F1h: 74 2E 44 65 66 61 75 6C 74 5F 5F 45 74 68 69 6F  t.Default__Ethio 
1:6601h: 70 69 61 6E 49 6D 6D 69 67 72 61 6E 74 5F 53 75  pianImmigrant_Su 
1:6611h: 72 6E 61 6D 65 73 5F 43 2E 4E 61 6D 65 73 2E 31  rnames_C.Names.1 
1:6621h: 31 2E 4E 61 6D 65 00 05 00 00 00 4E 61 6D 65 00  1.Name.....Name. 
1:6631h: 06 00 00 00 41 73 65 66 61 00 13 00 00 00 42 61  ....Asefa.....Ba 
1:6641h: 64 48 6F 6D 62 72 65 2E 4C 61 73 74 4E 61 6D 65  dHombre.LastName 
1:6651h: 00 04 00 00 00 00 00 42 00 00 00 44 4E 4C 2E 4E  .......B...DNL.N 
1:6661h: 61 6D 65 4C 69 73 74 2E 44 65 66 61 75 6C 74 5F  ameList.Default_ 
1:6671h: 5F 45 74 68 69 6F 70 69 61 6E 49 6D 6D 69 67 72  _EthiopianImmigr 
1:6681h: 61 6E 74 5F 53 75 72 6E 61 6D 65 73 5F 43 2E 4E  ant_Surnames_C.N 
1:6691h: 61 6D 65 73 2E 31 31 2E 4E 61 6D 65 00 05 00 00  ames.11.Name.... 
1:66A1h: 00 4E 61 6D 65 00 06 00 00 00 41 73 65 66 61 00  .Name.....Asefa. 
1:66B1h: 14 00 00 00 42 61 64 48 6F 6D 62 72 65 2E 46 69  ....BadHombre.Fi 
1:66C1h: 72 73 74 4E 61 6D 65 00 04 00 00 00 00 00 3D 00  rstName.......=. 
1:66D1h: 00 00 44 4E 4C 2E 4E 61 6D 65 4C 69 73 74 2E 44  ..DNL.NameList.D 
1:66E1h: 65 66 61 75 6C 74 5F 5F 4F 6C 64 54 65 73 74 61  efault__OldTesta 
1:66F1h: 6D 65 6E 74 5F 46 65 6D 61 6C 65 4F 6C 64 5F 43  ment_FemaleOld_C 
1:6701h: 2E 4E 61 6D 65 73 2E 32 30 2E 4E 61 6D 65 00 05  .Names.20.Name.. 
1:6711h: 00 00 00 4E 61 6D 65 00 06 00 00 00 54 61 6D 61  ...Name.....Tama 
1:6721h: 72 00 14 00 00 00 53 74 72 61 6E 67 65 72 73 52  r.....StrangersR 
1:6731h: 65 70 2E 47 65 6E 64 65 72 00 04 02 00 00 00 00  ep.Gender....... 
1:6741h: 00 00 00 00 00 00 00 00 06 00 00 00 7B 21 3C 6D  ............{!<m 
1:6751h: 7D 00 16 00 00 00 53 74 72 61 6E 67 65 72 73 52  }.....StrangersR 
1:6761h: 65 70 2E 53 74 61 6E 64 69 6E 67 00 04 01 00 00  ep.Standing..... 
1:6771h: 00 0B C8 08 00 00 00 00 17 00 00 00 44 61 79 74  ..È.........Dayt 
1:6781h: 6F 6E 2E 43 68 61 72 61 63 74 65 72 52 65 63 6F  on.CharacterReco 
1:6791h: 72 64 00 15 00 00 00 53 74 61 6E 64 69 6E 67 4E  rd.....StandingN 
1:67A1h: 61 6D 65 53 74 72 61 6E 67 65 72 00 09 00 00 00  ameStranger..... 
1:67B1h: 4F 75 74 73 69 64 65 72 00 01 00 00 00 11 00 00  Outsider........ 
1:67C1h: 00 43 68 61 72 61 63 74 65 72 2E 47 65 6E 64 65  .Character.Gende 
1:67D1h: 72 00 04 02 00 00 00 00 00 00 00 00 00 00 00 00  r............... 
1:67E1h: 06 00 00 00 7B 21 3C 6D 7D 00 00 00 01 21 FF 00  ....{!<m}....!ÿ. 
1:67F1h: 00 00 00 12 00 00 00 53 74 72 61 6E 67 65 72 73  .......Strangers 
1:6801h: 52 65 70 2E 4E 61 6D 65 00 04 01 00 00 00 0A 06  Rep.Name........ 
1:6811h: 00 00 00 72 75 2D 52 55 00 01 00 00 00 0B 90 00  ...ru-RU....... 
1:6821h: 00 00 00 00 53 00 00 00 44 61 79 74 6F 6E 2E 43  ....S...Dayton.C 
1:6831h: 68 61 72 61 63 74 65 72 54 72 61 69 74 2E 4D 65  haracterTrait.Me 
1:6841h: 63 68 61 6E 69 63 73 5F 45 6E 67 69 6E 65 65 72  chanics_Engineer 
1:6851h: 69 6E 67 5F 43 61 72 65 65 72 5F 41 65 72 6F 6E  ing_Career_Aeron 
1:6861h: 61 75 74 69 63 73 45 6E 67 69 6E 65 65 72 2E 4E  auticsEngineer.N 
1:6871h: 69 63 6B 6E 61 6D 65 73 2E 36 00 05 00 00 00 4E  icknames.6.....N 
1:6881h: 61 6D 65 00 07 00 00 00 52 61 6D 6A 65 74 00 01  ame.....Ramjet.. 
1:6891h: 00 00 00 11 00 00 00 43 68 61 72 61 63 74 65 72  .......Character 
1:68A1h: 2E 47 65 6E 64 65 72 00 04 02 00 00 00 00 00 00  .Gender......... 
1:68B1h: 00 00 00 00 00 00 06 00 00 00 7B 21 3C 6D 7D 00  ..........{!<m}. 
1:68C1h: 00 00 01 21 FF 00 00 00 00 00 00 00 00 00 53 00  ...!ÿ.........S. 
1:68D1h: 00 00 44 61 79 74 6F 6E 2E 43 68 61 72 61 63 74  ..Dayton.Charact 
1:68E1h: 65 72 54 72 61 69 74 2E 4D 65 63 68 61 6E 69 63  erTrait.Mechanic 
1:68F1h: 73 5F 45 6E 67 69 6E 65 65 72 69 6E 67 5F 43 61  s_Engineering_Ca 
1:6901h: 72 65 65 72 5F 41 65 72 6F 6E 61 75 74 69 63 73  reer_Aeronautics 
1:6911h: 45 6E 67 69 6E 65 65 72 2E 4E 69 63 6B 6E 61 6D  Engineer.Nicknam 
1:6921h: 65 73 2E 36 00 05 00 00 00 4E 61 6D 65 00 07 00  es.6.....Name... 
1:6931h: 00 00 52 61 6D 6A 65 74 00 16 00 00 00 53 74 72  ..Ramjet.....Str 
1:6941h: 61 6E 67 65 72 73 52 65 70 2E 4C 61 73 74 4E 61  angersRep.LastNa 
1:6951h: 6D 65 00 04 00 00 00 00 00 48 00 00 00 44 4E 4C  me.......H...DNL 
1:6961h: 2E 4E 61 6D 65 4C 69 73 74 2E 44 65 66 61 75 6C  .NameList.Defaul 
1:6971h: 74 5F 5F 43 68 69 6E 65 73 65 41 6D 65 72 69 63  t__ChineseAmeric 
1:6981h: 61 6E 5F 4D 61 69 6E 6C 61 6E 64 5F 53 75 72 6E  an_Mainland_Surn 
1:6991h: 61 6D 65 73 5F 43 2E 4E 61 6D 65 73 2E 34 38 2E  ames_C.Names.48. 
1:69A1h: 4E 61 6D 65 00 05 00 00 00 4E 61 6D 65 00 04 00  Name.....Name... 
1:69B1h: 00 00 59 61 6F 00 17 00 00 00 53 74 72 61 6E 67  ..Yao.....Strang 
1:69C1h: 65 72 73 52 65 70 2E 46 69 72 73 74 4E 61 6D 65  ersRep.FirstName 
1:69D1h: 00 04 00 00 00 00 00 46 00 00 00 44 4E 4C 2E 4E  .......F...DNL.N 
1:69E1h: 61 6D 65 4C 69 73 74 2E 44 65 66 61 75 6C 74 5F  ameList.Default_ 
1:69F1h: 5F 41 6E 67 6C 6F 41 6D 65 72 69 63 61 6E 5F 43  _AngloAmerican_C 
1:6A01h: 6F 6D 6D 6F 6E 5F 4D 61 6C 65 4D 69 64 64 6C 65  ommon_MaleMiddle 
1:6A11h: 5F 43 2E 4E 61 6D 65 73 2E 33 31 2E 4E 61 6D 65  _C.Names.31.Name 
1:6A21h: 00 05 00 00 00 4E 61 6D 65 00 06 00 00 00 4B 65  .....Name.....Ke 
1:6A31h: 76 69 6E 00 18 00 00 00 53 74 72 61 6E 67 65 72  vin.....Stranger 
1:6A41h: 73 49 6E 54 72 6F 75 62 6C 65 2E 4E 61 6D 65 00  sInTrouble.Name. 
1:6A51h: 04 00 00 00 00 00 27 00 00 00 44 61 79 74 6F 6E  ......'...Dayton 
1:6A61h: 2E 45 6E 63 6C 61 76 65 4E 61 6D 65 2E 44 65 66  .EnclaveName.Def 
1:6A71h: 61 75 6C 74 45 6E 63 6C 61 76 65 4E 61 6D 65 73  aultEnclaveNames 
1:6A81h: 00 25 00 00 00 63 39 31 36 35 62 63 61 2D 37 31  .%...c9165bca-71 
1:6A91h: 32 30 2D 34 39 64 66 2D 38 63 34 64 2D 31 38 63  20-49df-8c4d-18c 
1:6AA1h: 33 32 39 61 39 63 39 38 31 00 10 00 00 00 52 6F  329a9c981.....Ro 
1:6AB1h: 77 64 79 20 4E 65 69 67 68 62 6F 72 73 00 12 00  wdy Neighbors... 
1:6AC1h: 00 00 50 72 65 53 68 65 72 69 66 66 2E 47 65 6E  ..PreSheriff.Gen 
1:6AD1h: 64 65 72 00 04 02 00 00 00 00 00 00 00 00 00 00  der............. 
1:6AE1h: 00 00 06 00 00 00 7B 21 3C 6D 7D 00 14 00 00 00  ......{!<m}..... 
1:6AF1h: 50 72 65 53 68 65 72 69 66 66 2E 53 74 61 6E 64  PreSheriff.Stand 
1:6B01h: 69 6E 67 00 04 01 00 00 00 0B C8 08 00 00 00 00  ing.......È..... 
1:6B11h: 17 00 00 00 44 61 79 74 6F 6E 2E 43 68 61 72 61  ....Dayton.Chara 
1:6B21h: 63 74 65 72 52 65 63 6F 72 64 00 11 00 00 00 53  cterRecord.....S 
1:6B31h: 74 61 6E 64 69 6E 67 4E 61 6D 65 48 65 72 6F 00  tandingNameHero. 
1:6B41h: 05 00 00 00 48 65 72 6F 00 01 00 00 00 11 00 00  ....Hero........ 
1:6B51h: 00 43 68 61 72 61 63 74 65 72 2E 47 65 6E 64 65  .Character.Gende 
1:6B61h: 72 00 04 02 00 00 00 00 00 00 00 00 00 00 00 00  r............... 
1:6B71h: 06 00 00 00 7B 21 3C 6D 7D 00 00 00 01 21 FF 00  ....{!<m}....!ÿ. 
1:6B81h: 00 00 00 10 00 00 00 50 72 65 53 68 65 72 69 66  .......PreSherif 
1:6B91h: 66 2E 4E 61 6D 65 00 04 01 00 00 00 0A 06 00 00  f.Name.......... 
1:6BA1h: 00 72 75 2D 52 55 00 01 00 00 00 0B 90 00 00 00  .ru-RU......... 
1:6BB1h: 00 00 45 00 00 00 44 4E 4C 2E 4E 61 6D 65 4C 69  ..E...DNL.NameLi 
1:6BC1h: 73 74 2E 44 65 66 61 75 6C 74 5F 5F 41 6E 67 6C  st.Default__Angl 
1:6BD1h: 6F 41 6D 65 72 69 63 61 6E 5F 43 6F 6D 6D 6F 6E  oAmerican_Common 
1:6BE1h: 5F 4D 61 6C 65 4D 69 64 64 6C 65 5F 43 2E 4E 61  _MaleMiddle_C.Na 
1:6BF1h: 6D 65 73 2E 38 2E 4E 61 6D 65 00 05 00 00 00 4E  mes.8.Name.....N 
1:6C01h: 61 6D 65 00 08 00 00 00 43 68 61 72 6C 65 73 00  ame.....Charles. 
1:6C11h: 01 00 00 00 11 00 00 00 43 68 61 72 61 63 74 65  ........Characte 
1:6C21h: 72 2E 47 65 6E 64 65 72 00 04 02 00 00 00 00 00  r.Gender........ 
1:6C31h: 00 00 00 00 00 00 00 06 00 00 00 7B 21 3C 6D 7D  ...........{!<m} 
1:6C41h: 00 00 00 01 21 FF 00 00 00 00 00 00 00 00 00 45  ....!ÿ.........E 
1:6C51h: 00 00 00 44 4E 4C 2E 4E 61 6D 65 4C 69 73 74 2E  ...DNL.NameList. 
1:6C61h: 44 65 66 61 75 6C 74 5F 5F 41 6E 67 6C 6F 41 6D  Default__AngloAm 
1:6C71h: 65 72 69 63 61 6E 5F 43 6F 6D 6D 6F 6E 5F 4D 61  erican_Common_Ma 
1:6C81h: 6C 65 4D 69 64 64 6C 65 5F 43 2E 4E 61 6D 65 73  leMiddle_C.Names 
1:6C91h: 2E 38 2E 4E 61 6D 65 00 05 00 00 00 4E 61 6D 65  .8.Name.....Name 
1:6CA1h: 00 08 00 00 00 43 68 61 72 6C 65 73 00 14 00 00  .....Charles.... 
1:6CB1h: 00 50 72 65 53 68 65 72 69 66 66 2E 4C 61 73 74  .PreSheriff.Last 
1:6CC1h: 4E 61 6D 65 00 04 00 00 00 00 00 41 00 00 00 44  Name.......A...D 
1:6CD1h: 4E 4C 2E 4E 61 6D 65 4C 69 73 74 2E 44 65 66 61  NL.NameList.Defa 
1:6CE1h: 75 6C 74 5F 5F 42 72 61 7A 69 6C 69 61 6E 41 6D  ult__BrazilianAm 
1:6CF1h: 65 72 69 63 61 6E 5F 53 75 72 6E 61 6D 65 73 5F  erican_Surnames_ 
1:6D01h: 43 2E 4E 61 6D 65 73 2E 32 37 2E 4E 61 6D 65 00  C.Names.27.Name. 
1:6D11h: 05 00 00 00 4E 61 6D 65 00 06 00 00 00 43 75 6E  ....Name.....Cun 
1:6D21h: 68 61 00 15 00 00 00 50 72 65 53 68 65 72 69 66  ha.....PreSherif 
1:6D31h: 66 2E 46 69 72 73 74 4E 61 6D 65 00 04 00 00 00  f.FirstName..... 
1:6D41h: 00 00 45 00 00 00 44 4E 4C 2E 4E 61 6D 65 4C 69  ..E...DNL.NameLi 
1:6D51h: 73 74 2E 44 65 66 61 75 6C 74 5F 5F 41 6E 67 6C  st.Default__Angl 
1:6D61h: 6F 41 6D 65 72 69 63 61 6E 5F 43 6F 6D 6D 6F 6E  oAmerican_Common 
1:6D71h: 5F 4D 61 6C 65 4D 69 64 64 6C 65 5F 43 2E 4E 61  _MaleMiddle_C.Na 
1:6D81h: 6D 65 73 2E 38 2E 4E 61 6D 65 00 05 00 00 00 4E  mes.8.Name.....N 
1:6D91h: 61 6D 65 00 08 00 00 00 43 68 61 72 6C 65 73 00  ame.....Charles. 
1:6DA1h: 1A 00 00 00 50 72 61 67 6D 61 74 69 63 44 69 73  ....PragmaticDis 
1:6DB1h: 73 65 6E 74 65 72 2E 47 65 6E 64 65 72 00 04 02  senter.Gender... 
1:6DC1h: 00 00 00 00 00 00 00 00 00 00 00 00 06 00 00 00  ................ 
1:6DD1h: 7B 21 3C 66 7D 00 1C 00 00 00 50 72 61 67 6D 61  {!<f}.....Pragma 
1:6DE1h: 74 69 63 44 69 73 73 65 6E 74 65 72 2E 53 74 61  ticDissenter.Sta 
1:6DF1h: 6E 64 69 6E 67 00 04 01 00 00 00 0B C8 08 00 00  nding.......È... 
1:6E01h: 00 00 17 00 00 00 44 61 79 74 6F 6E 2E 43 68 61  ......Dayton.Cha 
1:6E11h: 72 61 63 74 65 72 52 65 63 6F 72 64 00 11 00 00  racterRecord.... 
1:6E21h: 00 53 74 61 6E 64 69 6E 67 4E 61 6D 65 48 65 72  .StandingNameHer 
1:6E31h: 6F 00 05 00 00 00 48 65 72 6F 00 01 00 00 00 11  o.....Hero...... 
1:6E41h: 00 00 00 43 68 61 72 61 63 74 65 72 2E 47 65 6E  ...Character.Gen 
1:6E51h: 64 65 72 00 04 02 00 00 00 00 00 00 00 00 00 00  der............. 
1:6E61h: 00 00 06 00 00 00 7B 21 3C 66 7D 00 00 00 01 21  ......{!<f}....! 
1:6E71h: FF 00 00 00 00 18 00 00 00 50 72 61 67 6D 61 74  ÿ........Pragmat 
1:6E81h: 69 63 44 69 73 73 65 6E 74 65 72 2E 4E 61 6D 65  icDissenter.Name 
1:6E91h: 00 04 01 00 00 00 0A 06 00 00 00 72 75 2D 52 55  ...........ru-RU 
1:6EA1h: 00 01 00 00 00 0B 90 00 00 00 00 00 4A 00 00 00  ...........J... 
1:6EB1h: 44 4E 4C 2E 4E 61 6D 65 4C 69 73 74 2E 44 65 66  DNL.NameList.Def 
1:6EC1h: 61 75 6C 74 5F 5F 49 6E 64 69 61 6E 41 6D 65 72  ault__IndianAmer 
1:6ED1h: 69 63 61 6E 5F 47 75 6A 61 72 61 74 5F 46 65 6D  ican_Gujarat_Fem 
1:6EE1h: 61 6C 65 4D 69 64 64 6C 65 5F 43 2E 4E 61 6D 65  aleMiddle_C.Name 
1:6EF1h: 73 2E 32 38 2E 4E 61 6D 65 00 05 00 00 00 4E 61  s.28.Name.....Na 
1:6F01h: 6D 65 00 06 00 00 00 50 69 6E 61 6C 00 01 00 00  me.....Pinal.... 
1:6F11h: 00 11 00 00 00 43 68 61 72 61 63 74 65 72 2E 47  .....Character.G 
1:6F21h: 65 6E 64 65 72 00 04 02 00 00 00 00 00 00 00 00  ender........... 
1:6F31h: 00 00 00 00 06 00 00 00 7B 21 3C 66 7D 00 00 00  ........{!<f}... 
1:6F41h: 01 21 FF 00 00 00 00 00 00 00 00 00 4A 00 00 00  .!ÿ.........J... 
1:6F51h: 44 4E 4C 2E 4E 61 6D 65 4C 69 73 74 2E 44 65 66  DNL.NameList.Def 
1:6F61h: 61 75 6C 74 5F 5F 49 6E 64 69 61 6E 41 6D 65 72  ault__IndianAmer 
1:6F71h: 69 63 61 6E 5F 47 75 6A 61 72 61 74 5F 46 65 6D  ican_Gujarat_Fem 
1:6F81h: 61 6C 65 4D 69 64 64 6C 65 5F 43 2E 4E 61 6D 65  aleMiddle_C.Name 
1:6F91h: 73 2E 32 38 2E 4E 61 6D 65 00 05 00 00 00 4E 61  s.28.Name.....Na 
1:6FA1h: 6D 65 00 06 00 00 00 50 69 6E 61 6C 00 1C 00 00  me.....Pinal.... 
1:6FB1h: 00 50 72 61 67 6D 61 74 69 63 44 69 73 73 65 6E  .PragmaticDissen 
1:6FC1h: 74 65 72 2E 4C 61 73 74 4E 61 6D 65 00 04 00 00  ter.LastName.... 
1:6FD1h: 00 00 00 46 00 00 00 44 4E 4C 2E 4E 61 6D 65 4C  ...F...DNL.NameL 
1:6FE1h: 69 73 74 2E 44 65 66 61 75 6C 74 5F 5F 49 6E 64  ist.Default__Ind 
1:6FF1h: 69 61 6E 41 6D 65 72 69 63 61 6E 5F 47 75 6A 61  ianAmerican_Guja 
1:7001h: 72 61 74 5F 53 75 72 6E 61 6D 65 73 5F 43 2E 4E  rat_Surnames_C.N 
1:7011h: 61 6D 65 73 2E 31 33 2E 4E 61 6D 65 00 05 00 00  ames.13.Name.... 
1:7021h: 00 4E 61 6D 65 00 08 00 00 00 47 6F 73 77 61 6D  .Name.....Goswam 
1:7031h: 69 00 1D 00 00 00 50 72 61 67 6D 61 74 69 63 44  i.....PragmaticD 
1:7041h: 69 73 73 65 6E 74 65 72 2E 46 69 72 73 74 4E 61  issenter.FirstNa 
1:7051h: 6D 65 00 04 00 00 00 00 00 4A 00 00 00 44 4E 4C  me.......J...DNL 
1:7061h: 2E 4E 61 6D 65 4C 69 73 74 2E 44 65 66 61 75 6C  .NameList.Defaul 
1:7071h: 74 5F 5F 49 6E 64 69 61 6E 41 6D 65 72 69 63 61  t__IndianAmerica 
1:7081h: 6E 5F 47 75 6A 61 72 61 74 5F 46 65 6D 61 6C 65  n_Gujarat_Female 
1:7091h: 4D 69 64 64 6C 65 5F 43 2E 4E 61 6D 65 73 2E 32  Middle_C.Names.2 
1:70A1h: 38 2E 4E 61 6D 65 00 05 00 00 00 4E 61 6D 65 00  8.Name.....Name. 
1:70B1h: 06 00 00 00 50 69 6E 61 6C 00 17 00 00 00 44 61  ....Pinal.....Da 
1:70C1h: 72 69 6E 67 44 69 73 73 65 6E 74 65 72 2E 47 65  ringDissenter.Ge 
1:70D1h: 6E 64 65 72 00 04 02 00 00 00 00 00 00 00 00 00  nder............ 
1:70E1h: 00 00 00 06 00 00 00 7B 21 3C 78 7D 00 19 00 00  .......{!<x}.... 
1:70F1h: 00 44 61 72 69 6E 67 44 69 73 73 65 6E 74 65 72  .DaringDissenter 
1:7101h: 2E 53 74 61 6E 64 69 6E 67 00 04 01 00 00 00 0B  .Standing....... 
1:7111h: C8 08 00 00 00 00 17 00 00 00 44 61 79 74 6F 6E  È.........Dayton 
1:7121h: 2E 43 68 61 72 61 63 74 65 72 52 65 63 6F 72 64  .CharacterRecord 
1:7131h: 00 14 00 00 00 53 74 61 6E 64 69 6E 67 4E 61 6D  .....StandingNam 
1:7141h: 65 52 65 63 72 75 69 74 00 08 00 00 00 52 65 63  eRecruit.....Rec 
1:7151h: 72 75 69 74 00 01 00 00 00 11 00 00 00 43 68 61  ruit.........Cha 
1:7161h: 72 61 63 74 65 72 2E 47 65 6E 64 65 72 00 04 02  racter.Gender... 
1:7171h: 00 00 00 00 00 00 00 00 00 00 00 00 06 00 00 00  ................ 
1:7181h: 7B 21 3C 78 7D 00 00 00 01 21 FF 00 00 00 00 15  {!<x}....!ÿ..... 
1:7191h: 00 00 00 44 61 72 69 6E 67 44 69 73 73 65 6E 74  ...DaringDissent 
1:71A1h: 65 72 2E 4E 61 6D 65 00 04 01 00 00 00 0A 06 00  er.Name......... 
1:71B1h: 00 00 72 75 2D 52 55 00 01 00 00 00 0B 90 00 00  ..ru-RU........ 
1:71C1h: 00 00 00 44 00 00 00 44 4E 4C 2E 4E 61 6D 65 4C  ...D...DNL.NameL 
1:71D1h: 69 73 74 2E 44 65 66 61 75 6C 74 5F 5F 41 6E 67  ist.Default__Ang 
1:71E1h: 6C 6F 41 6D 65 72 69 63 61 6E 5F 52 61 72 65 5F  loAmerican_Rare_ 
1:71F1h: 4D 61 6C 65 4D 69 64 64 6C 65 5F 43 2E 4E 61 6D  MaleMiddle_C.Nam 
1:7201h: 65 73 2E 34 31 2E 4E 61 6D 65 00 05 00 00 00 4E  es.41.Name.....N 
1:7211h: 61 6D 65 00 04 00 00 00 49 61 6E 00 01 00 00 00  ame.....Ian..... 
1:7221h: 11 00 00 00 43 68 61 72 61 63 74 65 72 2E 47 65  ....Character.Ge 
1:7231h: 6E 64 65 72 00 04 02 00 00 00 00 00 00 00 00 00  nder............ 
1:7241h: 00 00 00 06 00 00 00 7B 21 3C 78 7D 00 00 00 01  .......{!<x}.... 
1:7251h: 21 FF 00 00 00 00 00 00 00 00 00 44 00 00 00 44  !ÿ.........D...D 
1:7261h: 4E 4C 2E 4E 61 6D 65 4C 69 73 74 2E 44 65 66 61  NL.NameList.Defa 
1:7271h: 75 6C 74 5F 5F 41 6E 67 6C 6F 41 6D 65 72 69 63  ult__AngloAmeric 
1:7281h: 61 6E 5F 52 61 72 65 5F 4D 61 6C 65 4D 69 64 64  an_Rare_MaleMidd 
1:7291h: 6C 65 5F 43 2E 4E 61 6D 65 73 2E 34 31 2E 4E 61  le_C.Names.41.Na 
1:72A1h: 6D 65 00 05 00 00 00 4E 61 6D 65 00 04 00 00 00  me.....Name..... 
1:72B1h: 49 61 6E 00 19 00 00 00 44 61 72 69 6E 67 44 69  Ian.....DaringDi 
1:72C1h: 73 73 65 6E 74 65 72 2E 4C 61 73 74 4E 61 6D 65  ssenter.LastName 
1:72D1h: 00 04 00 00 00 00 00 45 00 00 00 44 4E 4C 2E 4E  .......E...DNL.N 
1:72E1h: 61 6D 65 4C 69 73 74 2E 44 65 66 61 75 6C 74 5F  ameList.Default_ 
1:72F1h: 5F 41 6E 67 6C 6F 41 6D 65 72 69 63 61 6E 5F 43  _AngloAmerican_C 
1:7301h: 6F 6D 6D 6F 6E 5F 53 75 72 6E 61 6D 65 73 5F 43  ommon_Surnames_C 
1:7311h: 2E 4E 61 6D 65 73 2E 36 32 39 2E 4E 61 6D 65 00  .Names.629.Name. 
1:7321h: 05 00 00 00 4E 61 6D 65 00 09 00 00 00 4F 27 43  ....Name.....O'C 
1:7331h: 6F 6E 6E 6F 72 00 1A 00 00 00 44 61 72 69 6E 67  onnor.....Daring 
1:7341h: 44 69 73 73 65 6E 74 65 72 2E 46 69 72 73 74 4E  Dissenter.FirstN 
1:7351h: 61 6D 65 00 04 00 00 00 00 00 44 00 00 00 44 4E  ame.......D...DN 
1:7361h: 4C 2E 4E 61 6D 65 4C 69 73 74 2E 44 65 66 61 75  L.NameList.Defau 
1:7371h: 6C 74 5F 5F 41 6E 67 6C 6F 41 6D 65 72 69 63 61  lt__AngloAmerica 
1:7381h: 6E 5F 52 61 72 65 5F 4D 61 6C 65 4D 69 64 64 6C  n_Rare_MaleMiddl 
1:7391h: 65 5F 43 2E 4E 61 6D 65 73 2E 34 31 2E 4E 61 6D  e_C.Names.41.Nam 
1:73A1h: 65 00 05 00 00 00 4E 61 6D 65 00 04 00 00 00 49  e.....Name.....I 
1:73B1h: 61 6E 00 00 00 01 21 FF 00 00 00 00              an....!ÿ....

```
