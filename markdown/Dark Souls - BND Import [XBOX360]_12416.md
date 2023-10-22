## Post #1
- Username: AniFox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 05, 2014 11:43 am
- Post datetime: 2014-12-23T14:53:28+00:00
- Post Title: Dark Souls - BND Import [XBOX360]

Please help me with importing the files back to the BND. Found this script, but it is only for the PC version. The only difference between the PC and XBOX, it's endiand. In the XBOX 360 uses a large endiand. Please, help me with convert this script under XBOX 360.

Sorry for my bad English.

```
If @error = 1 Then Exit
$bndfile = FileOpen($bndpath, 16)
$dir = FileSelectFolder("Select the folder...", "", "", @ScriptDir)
If $dir = "" Then
	Exit
EndIf
Dim $names, $pos = 33
_filereadtoarray($dir & "\" & "names.txt", $names)
FileSetPos($bndfile, 20, 0)
$baseoffset = _binarytoint32(FileRead($bndfile, 4))
$basepad = 16 - Mod($baseoffset, 16)
If $basepad < 16 Then
	$baseoffset += $basepad
EndIf
FileSetPos($bndfile, 0, 0)
$newfilehead = FileRead($bndfile, $baseoffset)
$newfiletext = Binary("0x00")
For $i = 1 To $names[0]
	$file = FileOpen($dir & "\" & $names[$i], 0 + 16)
	$size = FileGetSize($dir & "\" & $names[$i])
	$padding = 16 - Mod($size, 16)
	If $padding < 16 Then
		$newfiletext &= FileRead($file) & _binaryrandom($padding, 0, 0)
	Else
		$newfiletext &= FileRead($file)
	EndIf
	$newfilehead = _binarypoke($newfilehead, $pos + 4, $size, "dword")
	$newfilehead = _binarypoke($newfilehead, $pos + 8, $baseoffset, "dword")
	$newfilehead = _binarypoke($newfilehead, $pos + 20, $size, "dword")
	$pos += 24
	If $padding < 16 Then
		$baseoffset += $size + $padding
	Else
		$baseoffset += $size
	EndIf
	FileClose($file)
Next
$hnewfile = FileOpen(compgetfilename($bndpath), 2 + 16)
FileWrite($hnewfile, $newfilehead & BinaryMid($newfiletext, 2))
FileClose($hnewfile)
TrayTip("Importer", "Finish!", 3)

Func compgetfilename($path)
	If StringLen($path) < 4 Then Return -1
	$ret = StringSplit($path, "\", 2)
	If IsArray($ret) Then
		Return $ret[UBound($ret) - 1]
	EndIf
	If @error Then Return -1
EndFunc
```

[xbox 360 example.rar](https://xentaxbackup.github.io/file/8358_xbox 360 example.rar)
## Post #2
- Username: AniFox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 05, 2014 11:43 am
- Post datetime: 2014-12-23T14:55:29+00:00
- Post Title: Dark Souls - BND Import [XBOX360]

An additional attach BND example of a PC.
[pc example.rar](https://xentaxbackup.github.io/file/8359_pc example.rar)
## Post #3
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-12-24T09:57:53+00:00
- Post Title: Dark Souls - BND Import [XBOX360]

> Reply from AniFox
>
> Please help me with importing the files back to the BND. Found this script, but it is only for the PC version. The only difference between the PC and XBOX, it's endiand. In the XBOX 360 uses a large endiand. Please, help me with convert this script under XBOX 360.
Tell me the site name, where you found this script, please.
## Post #4
- Username: AniFox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 05, 2014 11:43 am
- Post datetime: 2014-12-24T12:05:11+00:00
- Post Title: Dark Souls - BND Import [XBOX360]

> Reply from swuforce
>
> AniFox wrote:Please help me with importing the files back to the BND. Found this script, but it is only for the PC version. The only difference between the PC and XBOX, it's endiand. In the XBOX 360 uses a large endiand. Please, help me with convert this script under XBOX 360.

Tell me the site name, where you found this script, please.

From your post on Xentax. From this link: [https://www.sendspace.com/file/cbhe3v](https://www.sendspace.com/file/cbhe3v)

In this link you give autoit3 exe. A code autoit is not encrypted. I'm got a source code using a decompiler. I guess I had to ask permission. I need to remove the code?
## Post #5
- Username: TON
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 13, 2014 9:47 pm
- Post datetime: 2014-12-24T13:29:01+00:00
- Post Title: Dark Souls - BND Import [XBOX360]

Agree. An unpack/repack script for Dark Souls Xbox360 version would be awesome.
## Post #6
- Username: RangerRus
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Apr 19, 2011 1:17 am
- Post datetime: 2014-12-25T09:28:25+00:00
- Post Title: Dark Souls - BND Import [XBOX360]

Dark Souls BND files is the same as in Demon's Souls (PS3), as I remember since I had work on translation PS3 version DS to Russian.
Try to search public tools for Demon's Souls.
