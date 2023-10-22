## Post #1
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-29T18:02:42+00:00
- Post Title: GE   IES Datatable

Attached a zip which contains two examples

Datatable_Itemcharge.ies is the one which I will be talking about for now

Datatable so obviously its table format, opens up first with the "IDSpace" which in the example is ItemCharge

Now I will start with the contents of the file.

Numeric Values are stored as Float
ASCII now it just seems jumbled up however heres an algorithm to "decrypt" it (I use it in a program I made to read this file)

VB6 Code:

```
If TmpString <> "" Then
TmpString = Asc(TmpString)
    If TmpString Mod 2 Then
        TmpString = TmpString - 1
    Else
        TmpString = TmpString + 1
    End If
TmpString = Chr(TmpString)
End If

Decode = TmpString
End Function

```


Other Information

[http://i64.photobucket.com/albums/h193/ ... creen1.jpg](http://i64.photobucket.com/albums/h193/SWG-Uli/Screen1.jpg)

Reverse the Hex (FF 17 00 00) to 000017FF = FileSize (6143 - Not a Float)

[http://i64.photobucket.com/albums/h193/ ... creen2.jpg](http://i64.photobucket.com/albums/h193/SWG-Uli/screen2.jpg)

Reverse the hex again, this gives you the number of Rows

[http://i64.photobucket.com/albums/h193/ ... creen3.jpg](http://i64.photobucket.com/albums/h193/SWG-Uli/screen3.jpg)

Number of Columns

[http://i64.photobucket.com/albums/h193/ ... creen4.jpg](http://i64.photobucket.com/albums/h193/SWG-Uli/screen4.jpg)

Number of Columns which contain a Numeric Value (So the Data will be stored as a 4 byte float value)

[http://i64.photobucket.com/albums/h193/ ... creen5.jpg](http://i64.photobucket.com/albums/h193/SWG-Uli/screen5.jpg)

Number Of Columns which contain a string


Then its got an extra 2 byte of Null and probably the third Null is a terminator for data.

Each Column name is placed twice. (So I pretty much ignore the second time the Column Name gets mentioned)
First Column Name starts at 93 byte, next one is Last Column Name Start + 134 (So it would be 93 + 134 for next start of next name then 93 + 134 + 134 for the third etc)

There is a bit of Null padding however before some of the column names it will be 01, 02 etc (Depends sometimes theres not a single one) and I'm not sure what they are meant to represent.

The last Column location + 140 = where data starts 


Now the main problem is there are some things at the start just before FileSize i got no idea represent and I can not work out what they mean at all.

Next is when it hits the data in the example its the float first now its easy to get how many bytes i should read for it before the text but I'm not sure which go into which columns, after the data has been read I do not know how to get where the next piece starts.

If you look at the other IES i attached called datatable_item_consume.ies you can see that the first data in it is String then it comes to float so there has to be some indicators around which Currently I can not see.

My very messy VB code (The Code has been changed with dynamic arrays and also uses Erase to empty the arrays however the link has not been updated):
[http://pastebin.com/f34380d97](http://pastebin.com/f34380d97)


Any Help Will Be Appreciated thanks!
[IES Datatables.zip](https://xentaxbackup.github.io/file/2681_IES Datatables.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2009-12-31T05:39:40+00:00
- Post Title: GE   IES Datatable

> Reply from Uli
>
> Now the main problem is there are some things at the start just before FileSize i got no idea represent and I can not work out what they mean at all.

64-byte datatable name, then 4-bytes which equal 1 in both samples

The next 3 4-byte values after swapping their endian:

1608  4443  6143 (the last being filesize)

 = 6143 - (4443 + 1608)
 = 6143 - 6051
 = 92

if you where to skip to that relative position, you'd only be 2 bytes along.
just an observation, but happens with both samples.


You can pick out the column datatypes fairly easily (0 = Number, 1 = String):

> datatable_item_consume.ies
>
> 
>
> Table: Item
>
> 
>
> 171 Columns:
>
>  [Num]:	AR
>
>  [Num]:	ASPD
>
>  [Num]:	ATK
>
>  [Num]:	AddSkl1ID
>
>  [Num]:	AddSkl1Lv
>
>  [Num]:	AddSkl2ID
>
>  [Num]:	AddSkl2Lv
>
>  [Num]:	AddSkl3ID
>
>  [Num]:	AddSkl3Lv
>
>  [Num]:	AddSkl4ID
>
>  [Num]:	AddSkl4Lv
>
>  [Num]:	AddSkl5ID
>
>  [Num]:	AddSkl5Lv
>
>  [Str]:	AtkSound
>
>  [Str]:	AutoCheckUse
>
>  [Str]:	AutoInspect
>
>  [Num]:	BLK
>
>  [Num]:	BaseATK
>
>  [Num]:	BaseDEF
>
>  [Num]:	BeastBane
>
>  [Str]:	BlkSound
>
>  [Str]:	BlowSound
>
>  [Num]:	BrLv
>
>  [Str]:	Buff
>
>  [Str]:	BuffDesc
>
>  [Num]:	BuffFreq
>
>  [Str]:	BuffName
>
>  [Num]:	CRT
>
>  [Str]:	Category1
>
>  [Str]:	Category1Name
>
>  [Str]:	Category2
>
>  [Str]:	Category2Name
>
>  [Num]:	ClassID
>
>  [Str]:	ClassName
>
>  [Str]:	ClassType
>
>  [Str]:	DBLHand
>
>  [Num]:	DEF
>
>  [Str]:	DeadDrop
>
>  [Num]:	DefEA
>
>  [Num]:	DefIP
>
>  [Str]:	DefaultEqpSlot
>
>  [Num]:	DemonBane
>
>  [Str]:	Desc
>
>  [Num]:	DinoBane
>
>  [Num]:	DropAngle
>
>  [Num]:	DropOffset
>
>  [Str]:	DropRule
>
>  [Str]:	DropSound
>
>  [Str]:	Dummy_A_LH
>
>  [Str]:	Dummy_A_RH
>
>  [Str]:	Dummy_B
>
>  [Str]:	Dummy_F
>
>  [Str]:	Dummy_N_LH
>
>  [Str]:	Dummy_N_RH
>
>  [Str]:	EQUP
>
>  [Num]:	EffectLength
>
>  [Str]:	EmitterName
>
>  [Str]:	EngName
>
>  [Str]:	EqpType
>
>  [Str]:	EquipSound
>
>  [Num]:	FesoPrice
>
>  [Num]:	FesoSellPrice
>
>  [Str]:	FesoVenderable
>
>  [Str]:	FileName
>
>  [Num]:	FireATK
>
>  [Num]:	FireIP
>
>  [Num]:	GolemBane
>
>  [Str]:	GroupName
>
>  [Num]:	HPDrain
>
>  [Num]:	HR
>
>  [Num]:	HumanBane
>
>  [Num]:	IMP
>
>  [Num]:	IceATK
>
>  [Num]:	IceIP
>
>  [Num]:	IncAGI
>
>  [Num]:	IncCHA
>
>  [Num]:	IncCON
>
>  [Num]:	IncDEX
>
>  [Num]:	IncINT
>
>  [Num]:	IncSTR
>
>  [Str]:	ItemClass
>
>  [Str]:	ItemIndicator
>
>  [Num]:	ItemLv
>
>  [Str]:	ItemName
>
>  [Str]:	ItemType
>
>  [Num]:	KDRank
>
>  [Num]:	LODDist
>
>  [Num]:	LghtATK
>
>  [Num]:	LgtIP
>
>  [Str]:	LockWarpUse
>
>  [Str]:	LogoutSave
>
>  [Num]:	MHP
>
>  [Num]:	MKP
>
>  [Num]:	MSP
>
>  [Num]:	MSPD
>
>  [Str]:	MaterialSet
>
>  [Num]:	MaxR
>
>  [Num]:	MaxSocketCount
>
>  [Num]:	MaxStack
>
>  [Num]:	MinR
>
>  [Num]:	Option1ID
>
>  [Num]:	Option1MaxValue
>
>  [Num]:	Option1MinValue
>
>  [Num]:	Option2ID
>
>  [Num]:	Option2MaxValue
>
>  [Num]:	Option2MinValue
>
>  [Num]:	Option3ID
>
>  [Num]:	Option3MaxValue
>
>  [Num]:	Option3MinValue
>
>  [Str]:	OptionGroup
>
>  [Num]:	PR
>
>  [Str]:	Pair
>
>  [Num]:	ParticleCount
>
>  [Str]:	ParticleName
>
>  [Str]:	PreCheckScp
>
>  [Num]:	Price
>
>  [Num]:	PromotionLv
>
>  [Num]:	PsyATK
>
>  [Num]:	PsyIP
>
>  [Num]:	RFIRE
>
>  [Num]:	RHP
>
>  [Num]:	RICE
>
>  [Num]:	RLGHT
>
>  [Num]:	RPSY
>
>  [Num]:	RSP
>
>  [Num]:	RSTAT
>
>  [Num]:	Rank
>
>  [Str]:	RecordUsingLog
>
>  [Num]:	RedFIRE
>
>  [Num]:	RedICE
>
>  [Num]:	RedLGHT
>
>  [Num]:	RedMAG
>
>  [Num]:	RedMEL
>
>  [Num]:	RedPSY
>
>  [Num]:	RedSHT
>
>  [Num]:	RendBlind
>
>  [Num]:	RendBurning
>
>  [Num]:	RendFear
>
>  [Num]:	RendFreeze
>
>  [Num]:	RendPoison
>
>  [Num]:	RendShock
>
>  [Num]:	RendStun
>
>  [Str]:	ReqToolTip
>
>  [Num]:	SaleEA
>
>  [Num]:	SaleID
>
>  [Str]:	SaveBuff
>
>  [Str]:	SaveBurlonPoint
>
>  [Str]:	SaveExp
>
>  [Num]:	Scale
>
>  [Str]:	ScpType
>
>  [Num]:	SellPrice
>
>  [Num]:	ShldDR
>
>  [Str]:	SocketRef
>
>  [Str]:	Spec
>
>  [Str]:	Suffix
>
>  [Str]:	TargetHitEffect
>
>  [Str]:	TownUsable
>
>  [Str]:	Tradable
>
>  [Num]:	UndeadBane
>
>  [Str]:	UniqueBone
>
>  [Str]:	Unstack
>
>  [Str]:	UseGender
>
>  [Str]:	UseGravity
>
>  [Str]:	UseInverse
>
>  [Num]:	UseLv
>
>  [Str]:	Venderable
>
>  [Num]:	WLv
>
>  [Str]:	WeaponTail
>
>  [Num]:	Weight
>
>  [Num]:	arg1
>
>  [Num]:	arg2
>
> 
>
> 
>
> datatable_itemcharge.ies
>
> 
>
> 
>
> Table: Itemcharge
>
> 
>
> 12 Columns:
>
>  [Str]:	CashItemGroup
>
>  [Num]:	ClassID
>
>  [Num]:	RicoExchange
>
>  [Str]:	ability
>
>  [Num]:	arg1
>
>  [Num]:	arg2
>
>  [Num]:	cost
>
>  [Num]:	hour
>
>  [Num]:	itemID
>
>  [Str]:	itemname
>
>  [Num]:	min
>
>  [Num]:	period

Strings are stored as:

short stringsize
char string[stringsize]

*edit*
removed incorrect row structure definition
## Post #3
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-31T23:49:58+00:00
- Post Title: GE   IES Datatable

> Reply from WRS
>
> 
You can pick out the column datatypes fairly easily (0 = Number, 1 = String):

Edit: Nevermind just seen what you mean by that, i would of never noticed it, thanks for helping its very appreciated.

And

I feel kinda stupid not noticing the String Len before the actual string >.>

As for everything else awesome thanks for it! 

Edit:
[http://pastebin.com/f7f0c808b](http://pastebin.com/f7f0c808b)

A bit of source code, it still has some problems which im trying to work out why they appear.

Edit2:

Bleh just tried to open another IES file and it seems its got an extra string in there (I got no idea why)

Edit3:

Source Code added
Added some notes to it as well
~Just updated the source~
[Updated.zip](https://xentaxbackup.github.io/file/2690_Updated.zip)
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-01-03T00:56:43+00:00
- Post Title: GE   IES Datatable

I don't code with VB, but I don't like the way you handle string types. Use the string length declared in the file, instead of reading to the next null byte.

Ignore how I previously mentioned rows are stored as    

I've attached my 010 template which can parse your supplied samples (included the ones in your second attachment). The language is based on C++, but it's still fairly easy to understand   


notes -

As I'm not interested in the data, you can finish making sense of the values.

I'm assuming strings are never stored in plaintext (decrypt.ies is something you've writen out?)

Sometimes 'none' is written as 'none', so you might want to check that before scrambling it back   


good luck with your project
[ies.zip](https://xentaxbackup.github.io/file/2691_ies.zip)
## Post #5
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2010-01-03T14:36:30+00:00
- Post Title: GE   IES Datatable

> Reply from WRS
>
> I don't code with VB, but I don't like the way you handle string types. Use the string length declared in the file, instead of reading to the next null byte.

Ignore how I previously mentioned rows are stored as    

I've attached my 010 template which can parse your supplied samples (included the ones in your second attachment). The language is based on C++, but it's still fairly easy to understand   


notes -

As I'm not interested in the data, you can finish making sense of the values.

I'm assuming strings are never stored in plaintext (decrypt.ies is something you've writen out?)

Sometimes 'none' is written as 'none', so you might want to check that before scrambling it back   


good luck with your project

decrypt.ies was just one that been through the character switching so it was readable when, i had one which hadnt been converted and one which had been so i know when text started and stopped.

Reading to Next Null was due to it not being able to read the consume datatable, i seems there are only 41 readable strings so the rest confused me a little.

yeah i can read C++, thanks for the help 
Only reason why I like VB is it is a lot easier to do a decent interface  (When it comes to interfaces if i can see it then i can do it if i cant i end up with god knows what.)

Edit:

First time using 010 and i have to say i love it very helpful, thank you
## Post #6
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2010-01-08T18:39:24+00:00
- Post Title: GE   IES Datatable

Update:

Okay Finished it,
Reads the data, puts it under the correct column etc.

Attached to post:

If you get an error saying about the OCX can not be found then register it.


Updated it with latest code
[GE IES Reader.zip](https://xentaxbackup.github.io/file/2704_GE IES Reader.zip)
## Post #7
- Username: skiwi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 11, 2010 8:29 pm
- Post datetime: 2010-04-11T18:52:51+00:00
- Post Title: GE   IES Datatable

It can't open a table (datatable_monster.ies), which is 2.73 MB.

Is there a solution to that?

Maybe releasing a version without a filesize limit?
## Post #8
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2010-04-12T14:17:01+00:00
- Post Title: GE   IES Datatable

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: phoenik
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 21, 2010 5:13 pm
- Post datetime: 2010-06-21T21:18:27+00:00
- Post Title: GE   IES Datatable

Wow amazing work!

I've been working on my own IES reader so I can easily automate certain tasks (mysql queries and the like) and this has been a huge help! Although there's one thing I can't quite figure out and that's matching the columns to the data. I have a feeling order has something to do with the short in front of each column name and the short that appears just before all of the row data, but I can't quite see the pattern and I'm sure it's staring me right in the face.

Anything to point me in the right direction will be a big help. Thanks in advance.

[edit]clarification[/edit]
## Post #10
- Username: scvn80
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 07, 2011 5:57 pm
- Post datetime: 2011-01-08T10:36:32+00:00
- Post Title: GE   IES Datatable

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: mosawa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 24, 2011 2:09 am
- Post datetime: 2011-06-01T04:48:55+00:00
- Post Title: GE   IES Datatable

> Reply from Uli
>
> Update:

Okay Finished it,
Reads the data, puts it under the correct column etc.

Attached to post:

If you get an error saying about the OCX can not be found then register it.


Updated it with latest code

Hi, I know this is inapropriate. I'm sorry. Could you please share the source to the attached files? I wanted to know the algorithm, for me to write on another programming language.

Thank you very much for your help!
## Post #12
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2011-11-30T17:55:23+00:00
- Post Title: GE   IES Datatable

The contents of this post was deleted because of possible forum rules violation.
