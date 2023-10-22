## Post #1
- Username: LuigiBlood
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 29, 2010 5:26 am
- Post datetime: 2011-12-25T01:03:28+00:00
- Post Title: Another World DOS Compression

So...
I've been studying the file format stuff with the "official" documentation that's on the 15th Anniversary Edition, but i want to unpack the files... except that there's a compression i can't figure out, even if i'm watching this source code:
[https://github.com/fabiensanglard/Anoth ... nterpreter](https://github.com/fabiensanglard/Another-World-Bytecode-Interpreter)

But i can't figure it out. It's maybe simple, but C++ has never been something i'm good at.

Compression part:
[https://github.com/fabiensanglard/Anoth ... r/bank.cpp](https://github.com/fabiensanglard/Another-World-Bytecode-Interpreter/blob/master/bank.cpp)

I have also done a QuickBMS script. It should be ran with MEMLIST.BIN as input file.

I will maybe do some modding for fun if i get this compression...

```
# TODO: Compression.

ComType ahuff
# Should be changed.
Endian big
Set DataType 0
# 0=Sound, 1=Music, 2=PolyAnim, 3=Pal, 4=ByteCode, 5=Cutscene, 6=Other
# 0.snd, 1.mus, 2.pol, 3.pal, 4.bin, 5.cin, 6.dat
Set DataBank 0
Set DataOffset 0
Set DataCSize 0
Set DataSize 0

Set IsFile 0
Get NbFiles asize
Math NbFiles /= 20
Math NbFiles -= 2

# 0x01:DataType (Byte)
# 0x07:DataBank (Byte)
# 0x08:DataOffset (32-bit)
# 0x0e:DataCSize (16)
# 0x12:DataSize (16)
# 20 bytes

Set DataNb 0

Do
	Set MEM_offset 1
	Set MEM_Nb DataNb
	Math MEM_Nb *= 20
	Math MEM_offset += MEM_Nb
	GoTo MEM_offset 0
	Get DataType BYTE 0
	# Got DataType
	
	If DataType == 0
		Set MEM_NAME "sound"
		String MEM_NAME += DataNb
		String MEM_NAME += ".snd"
	Elif DataType == 1
		Set MEM_NAME "music"
		String MEM_NAME += DataNb
		String MEM_NAME += ".mus"
	Elif DataType == 2
		Set MEM_NAME "polyanim"
		String MEM_NAME += DataNb
		String MEM_NAME += ".pol"
	Elif DataType == 3
		Set MEM_NAME "palette"
		String MEM_NAME += DataNb
		String MEM_NAME += ".pal"
	Elif DataType == 4
		Set MEM_NAME "code"
		String MEM_NAME += DataNb
		String MEM_NAME += ".bin"
	Elif DataType == 5
		Set MEM_NAME "cine"
		String MEM_NAME += DataNb
		String MEM_NAME += ".cin"
	Else
		Set MEM_NAME "other"
		String MEM_NAME += DataNb
		String MEM_NAME += ".dat"
	EndIf
	
	Math MEM_offset += 6
	GoTo MEM_offset 0
	Get DataBank BYTE 0
	# Got Bank data
		
	If DataBank == 0x00
		Set BANKNAME "BANK00"
	Elif DataBank == 0x01
		Set BANKNAME "BANK01"
	Elif DataBank == 0x02
		Set BANKNAME "BANK02"
	Elif DataBank == 0x03
		Set BANKNAME "BANK03"
	Elif DataBank == 0x04
		Set BANKNAME "BANK04"
	Elif DataBank == 0x05
		Set BANKNAME "BANK05"
	Elif DataBank == 0x06
		Set BANKNAME "BANK06"
	Elif DataBank == 0x07
		Set BANKNAME "BANK07"
	Elif DataBank == 0x08
		Set BANKNAME "BANK08"
	Elif DataBank == 0x09
		Set BANKNAME "BANK09"
	Elif DataBank == 0x0A
		Set BANKNAME "BANK0A"
	Elif DataBank == 0x0B
		Set BANKNAME "BANK0B"
	Elif DataBank == 0x0C
		Set BANKNAME "BANK0C"
	Elif DataBank == 0x0D
		Set BANKNAME "BANK0D"
	Elif DataBank == 0x0E
		Set BANKNAME "BANK0E"
	Elif DataBank == 0x0F
		Set BANKNAME "BANK0F"
	EndIf
	
	Math MEM_offset += 1
	GoTo MEM_offset 0
	Get DataOffset LONG 0
	# Got Offset
	
	Math MEM_offset += 6
	GoTo MEM_offset 0
	Get DataCSize SHORT 0
	# Got CSize
	
	Math MEM_offset += 4
	GoTo MEM_offset 0
	Get DataSize SHORT 0
	# Got Size
	
	# TODO: Bank Read
	Open FDSE BANKNAME 1
	
#	If DataSize != 0
		If DataCSize == DataSize
			Log MEM_NAME DataOffset DataSize 1
		Else
			CLog MEM_NAME DataOffset DataCSize DataSize 1
		EndIf
#	EndIf
	
	Math DataNb += 1

While DataNb <= NbFiles

```
## Post #2
- Username: LuigiBlood
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 29, 2010 5:26 am
- Post datetime: 2012-11-16T18:12:49+00:00
- Post Title: Another World DOS Compression

Sorry for bumping the topic with a double post, but it's just to let know that the file extractor is done:

```
# Load a MEMLIST.BIN to work, BANK files must be in the same folder as the MEMLIST.BIN.

Endian big
Set DataType 0
# 0=Sound, 1=Music, 2=PolyAnim, 3=Pal, 4=ByteCode, 5=Cutscene, 6=Other
# 0.snd, 1.mus, 2.bma, 3.pal, 4.mac, 5.mat, 6.dat
Set DataBank 0
Set DataOffset 0
Set DataCSize 0
Set DataSize 0

Set IsFile 0
Get NbFiles asize
Math NbFiles /= 20
Math NbFiles -= 2

# 0x01:DataType (Byte)
# 0x07:DataBank (Byte)
# 0x08:DataOffset (32-bit)
# 0x0e:DataCSize (16)
# 0x12:DataSize (16)
# 20 bytes

Set DataNb 0

Do
	log TEMPORARY_FILE 0 0
	Set MEM_offset 1
	Set MEM_Nb DataNb
	Math MEM_Nb *= 20
	Math MEM_offset += MEM_Nb
	GoTo MEM_offset 0
	Get DataType BYTE 0
	# Got DataType
	
	If DataType == 0
		Set MEM_NAME "sound"
		String MEM_NAME += DataNb
		String MEM_NAME += ".snd"
	Elif DataType == 1
		Set MEM_NAME "music"
		String MEM_NAME += DataNb
		String MEM_NAME += ".mus"
	Elif DataType == 2
		Set MEM_NAME "polyanim"
		String MEM_NAME += DataNb
		String MEM_NAME += ".pol"
	Elif DataType == 3
		Set MEM_NAME "palette"
		String MEM_NAME += DataNb
		String MEM_NAME += ".pal"
	Elif DataType == 4
		Set MEM_NAME "code"
		String MEM_NAME += DataNb
		String MEM_NAME += ".bin"
	Elif DataType == 5
		Set MEM_NAME "cine"
		String MEM_NAME += DataNb
		String MEM_NAME += ".cin"
	Else
		Set MEM_NAME "other"
		String MEM_NAME += DataNb
		String MEM_NAME += ".dat"
	EndIf
	
	Math MEM_offset += 6
	GoTo MEM_offset 0
	Get DataBank BYTE 0
	# Got Bank data
		
	If DataBank == 0x00
		Set BANKNAME "BANK00"
	Elif DataBank == 0x01
		Set BANKNAME "BANK01"
	Elif DataBank == 0x02
		Set BANKNAME "BANK02"
	Elif DataBank == 0x03
		Set BANKNAME "BANK03"
	Elif DataBank == 0x04
		Set BANKNAME "BANK04"
	Elif DataBank == 0x05
		Set BANKNAME "BANK05"
	Elif DataBank == 0x06
		Set BANKNAME "BANK06"
	Elif DataBank == 0x07
		Set BANKNAME "BANK07"
	Elif DataBank == 0x08
		Set BANKNAME "BANK08"
	Elif DataBank == 0x09
		Set BANKNAME "BANK09"
	Elif DataBank == 0x0A
		Set BANKNAME "BANK0A"
	Elif DataBank == 0x0B
		Set BANKNAME "BANK0B"
	Elif DataBank == 0x0C
		Set BANKNAME "BANK0C"
	Elif DataBank == 0x0D
		Set BANKNAME "BANK0D"
	Elif DataBank == 0x0E
		Set BANKNAME "BANK0E"
	Elif DataBank == 0x0F
		Set BANKNAME "BANK0F"
	EndIf
	
	Get DataOffset LONG 0
	# Got Offset
	
	Get DataCSize LONG 0
	# Got CSize
	
	Get DataSize LONG 0
	# Got Size
	
	Open FDSE BANKNAME 1
	
	If DataSize != 0
		If DataCSize == DataSize
			Encryption "" ""
			Log MEM_NAME DataOffset DataSize 1
		Else
			CallFunction unpack 1
			Encryption reverse ""
			Log MEM_NAME 0 DataSize 2
		EndIf
	EndIf
	
	Math DataNb += 1

While DataNb <= NbFiles

StartFunction unpack
	Set _unpaksize 0
	Set _unpakdsize 0
	Set _unpakcrc 0
	Set _unpakchk 0
	
	Set _unpakOffset DataOffset
	Math _unpakOffset u+= DataCSize
	Math _unpakOffset u-= 4
	GoTo _unpakOffset 1
	Get _unpakdsize LONG 1
	Math _unpakOffset u-= 4
	
	Open "." TEMPORARY_FILE 2
	
	GoTo _unpakOffset 1
	Get _unpakcrc LONG 1
	Math _unpakOffset u-= 4
	GoTo _unpakOffset 1
	Get _unpakchk LONG 1
	Math _unpakcrc u^= _unpakchk
	Math _unpakOffset u-= 4
	
	Do
		CallFunction NextChunk 1
		If NextChunkReturn == 0
			Set _unpaksize 1
			CallFunction NextChunk 1
			If NextChunkReturn == 0
				Set _decUnk1_numchunk 3
				Set _decUnk1_addcount 0
				CallFunction decUnk1 1
			Else
				Set _decUnk2_numchunk 8
				CallFunction decUnk2 1
			EndIf
		Else
			Set _getCode_numChunks 2
			CallFunction getCode 1
			Set _unpack_c getCodeReturn
			If _unpack_c == 3
				Set _decUnk1_numchunk 8
				Set _decUnk1_addcount 8
				CallFunction decUnk1 1
			Else
				If _unpack_c < 2
					Set _unpaksize _unpack_c
					Math _unpaksize u+= 2
					Set _decUnk2_numchunk _unpack_c
					Math _decUnk2_numchunk u+= 9
					CallFunction decUnk2 1
				Else
					Set _getCode_numChunks 8
					CallFunction getCode 1
					Set _unpaksize getCodeReturn
					Set _decUnk2_numchunk 12
					CallFunction decUnk2 1
				EndIf
			EndIf
		EndIf
	While _unpakdsize > 0
EndFunction

StartFunction NextChunk
	Set NextChunkReturn 0
	Set CF 0
	Set CFRCR 0
	CallFunction RCR 1
	Set CF RCRReturn
	If _unpakchk == 0
		GoTo _unpakOffset 1
		Get _unpakchk LONG 1
		Math _unpakcrc u^= _unpakchk
		Math _unpakOffset u-= 4
		Set CFRCR 1
		CallFunction RCR 1
		Set CF RCRReturn
	EndIf
	Set NextChunkReturn CF
EndFunction

StartFunction RCR
	# CFRCR
	
	Set rCF _unpakchk
	Math rCF &= 1
	Math _unpakchk u>= 1
	If CFRCR == 1
		Math _unpakchk u|= 0x80000000
	EndIf
	Set RCRReturn rCF
EndFunction

StartFunction decUnk1
	# _decUnk1_numchunk
	# _decUnk1_addcount
	
	Set _getCode_numChunks _decUnk1_numchunk
	CallFunction getCode 1
	Set _decUnk1_count getCodeReturn
	Math _decUnk1_count u+= _decUnk1_addcount
	Math _decUnk1_count u+= 1
	Math _unpakdsize u-= _decUnk1_count
	If _decUnk1_count > 0
	Do
		Set _getCode_numChunks 8
		CallFunction getCode 1
		Math getCodeReturn u&= 0xFF
		Put getCodeReturn BYTE 2
		Math _decUnk1_count u-= 1
	While _decUnk1_count > 0
	EndIf
EndFunction

StartFunction decUnk2
	# _decUnk2_numchunk
	
	Set _getCode_numChunks _decUnk2_numchunk
	CallFunction getCode 1
	
	Set _decUnk2_i getCodeReturn
	Set _decUnk2_count _unpaksize
	Math _decUnk2_count u+= 1
	
	Set _decUnk2_offset 0
	Set _decUnk2_offset2 0
	Set _decUnk2_byte 0
	Math _unpakdsize u-= _decUnk2_count
	If _decUnk2_count > 0
	Do
		SavePos _decUnk2_offset 2
		Set _decUnk2_offset2 _decUnk2_offset
		Math _decUnk2_offset2 u-= _decUnk2_i
		GoTo _decUnk2_offset2 2
		Get _decUnk2_byte BYTE 2
		GoTo _decUnk2_offset 2
		Put _decUnk2_byte BYTE 2
		Math _decUnk2_count u-= 1		
	While _decUnk2_count > 0
	EndIf
EndFunction

StartFunction getCode
	# _getCode_numChunks
	
	Set _getCode_c 0
	If _getCode_numChunks > 0
	Do
		Math _getCode_numChunks u-= 1
		Math _getCode_c u<= 1
		CallFunction NextChunk 1
		If NextChunkReturn != 0
			Math _getCode_c u|= 1
		EndIf
	While _getCode_numChunks > 0
	EndIf
	Set getCodeReturn _getCode_c
EndFunction
```


I finally got the compression right, now it extracts all files.
