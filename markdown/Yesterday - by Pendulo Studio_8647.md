## Post #1
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-03-27T16:45:23+00:00
- Post Title: Yesterday - by Pendulo Studio

Just wanted to share my short research about that game (it's probably the same for the rest of Pendulo Studio games like the "Runaway" series or "The Next Big Thing")

Image and scripts(engine) files:

```
// Resource\RESOURCE.IFZ - Cursors
// Resource\RESOURCE.A00 - Items
// Resource\RESOURCE.A01 - / Scene
// Resource\RESOURCE.A02 - |
// Resource\RESOURCE.A03 - |
// Resource\RESOURCE.A05 - \
// Resource\RESOURCE.B00 - Items
// Resource\RESOURCE.B01 / Scene
// Resource\RESOURCE.B02 |
// Resource\RESOURCE.B03 |
// Resource\RESOURCE.B04 |
// Resource\RESOURCE.B05 |
// Resource\RESOURCE.B06 |
// Resource\RESOURCE.B07 |
// Resource\RESOURCE.B11 \
// Resource\RESOURCE.C00 - Items
// Resource\RESOURCE.C02 / Scene
// Resource\RESOURCE.C03 |
// Resource\RESOURCE.C04 |
// Resource\RESOURCE.C05 |
// Resource\RESOURCE.C06 \
// Resource\RESOURCE.D00 - Items
// Resource\RESOURCE.D01 / Scene
// Resource\RESOURCE.D02 |
// Resource\RESOURCE.D03 |
// Resource\RESOURCE.D04 |
// Resource\RESOURCE.D06 |
// Resource\RESOURCE.D07 |
// Resource\RESOURCE.D11 \
// Resource\RESOURCE.E00 - Items
// Resource\RESOURCE.E01 / Scene
// Resource\RESOURCE.E02 |
// Resource\RESOURCE.E03 \
// Resource\RESOURCE.F00 - Items
// Resource\RESOURCE.F01 / Scene
// Resource\RESOURCE.F02 |
// Resource\RESOURCE.F04 \
// Resource\RESOURCE.H00 - Items
// Resource\RESOURCE.H01 / Scene
// Resource\RESOURCE.H02 |
// Resource\RESOURCE.H03 |
// Resource\RESOURCE.H10 |
// Resource\RESOURCE.H11 |
// Resource\RESOURCE.H13 \
// Resource\RESOURCE.X03 - Dedication message
// Resource\RESOURCE.X69 - Game interface
structure {
	numRows[DWORD] { 14 00 00 00 } // divide by 4
	fileBof {
		bof[1] { 2C 00 00 00 }
		...
		bof[n] { ... }
	}
	fileSize {
		size[1] { 93 56 00 00 }
		...
		size[n] { ... }
	}
	data { ... }
}
```


Sounds and music:

```
// Resource\RESOURCE.S01 |
// Resource\RESOURCE.S02 |
// Resource\RESOURCE.S03 |
// Resource\RESOURCE.S05 |
// Resource\RESOURCE.S06 |
// Resource\RESOURCE.S08 \
// Dataa\uk\DATAA0.000 - empty bank
// Dataa\uk\DATAA1.000
// Dataa\uk\DATAA2.000
// Dataa\uk\DATAA3.000
// Dataa\uk\DATAA4.000
// Dataa\uk\DATAA5.000
// Dataa\uk\DATAA6.000
// Dataa\uk\DATAA7.000 - empty bank
// Dataa\uk\DATAA8.000
// Dataa\uk\DATAAV.000 - Dialogue voiceover (WAV,OGG)
structure {
	numRows[DWORD] { 4C 00 00 00 }
	rows {
		row[0] {
			fileBof[DWORD] { E0 03 00 00 }
			fileSize[DWORD] { 6C 1A 00 00 }
			unknown[DWORD] { 00 00 00 00 }
			fileType[byte] {
				00 = WAV
				02 = OGG
			}
		...
		row[n] { ... }
	}
	data { ... }
}
```
## Post #2
- Username: gyeben
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 19, 2011 10:43 pm
- Post datetime: 2012-04-06T08:40:10+00:00
- Post Title: Yesterday - by Pendulo Studio

Hi XpoZed!

I've just tried to extract the files of 'Runaway - A road adventure' and found out that it uses a similar structure for files, but not the same one.

Can you give an explanation of Items and Scene? What kind of file extensions should I expect in those archives?

Also, there is a part like this in your research:

```
   numRows[DWORD] { 4C 00 00 00 }
   rows {
      row[0] {
         fileBof[DWORD] { E0 03 00 00 }
         fileSize[DWORD] { 6C 1A 00 00 }
         unknown[DWORD] { 00 00 00 00 }
         fileType[byte] {
            00 = WAV
            02 = OGG
         }
      ...
      row[n] { ... }
   }
   data { ... }
}
```

How can this piece of information can help me in extracting the files?
## Post #3
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-06T08:49:14+00:00
- Post Title: Yesterday - by Pendulo Studio

> Reply from gyeben
>
> Hi XpoZed!

I've just tried to extract the files of 'Runaway - A road adventure' and found out that it uses a similar structure for files, but not the same one.

Can you give an explanation of Items and Scene? What kind of file extensions should I expect in those archives?

Also, there is a part like this in your research:
Code: Select allstructure {
   numRows[DWORD] { 4C 00 00 00 }
   rows {
      row[0] {
         fileBof[DWORD] { E0 03 00 00 }
         fileSize[DWORD] { 6C 1A 00 00 }
         unknown[DWORD] { 00 00 00 00 }
         fileType[byte] {
            00 = WAV
            02 = OGG
         }
      ...
      row[n] { ... }
   }
   data { ... }
}
How can this piece of information can help me in extracting the files?

That's a pseudo structure to give overall look at the format.
First we have a numRows DWORD (4 bytes) that identify the number of entries in the archive.
Then follows the "rows" or entries, that describes the file parameters - bof (begin of file or file offset), size, some unknown value that is always zero and finally a byte value that defines the file type - if that byte is 0, the file is .WAV, of it's 2 then the file is .OGG
finally is the file data, or the file contents.
Knowing that structure you can easily navigate through the archive with a HEX editor or if you know how, you can write your own BMS script.
## Post #4
- Username: gyeben
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 19, 2011 10:43 pm
- Post datetime: 2012-04-06T21:45:02+00:00
- Post Title: Yesterday - by Pendulo Studio

I am trying to edit the translation. Does Yesterday have a file called Resource.003?
I found out that both The Next Big Thing and Runaway have this file and probable it contains the texts of the game. But unfortunately I couldn't open it...   

Also, Runaway has two files called Resource.000 and Resource.001 - both of them are around 100 MBs, but couldn't extract them.

// Resource\RESOURCE.D00 - Items
// Resource\RESOURCE.D01 / Scene
// Resource\RESOURCE.D02 |
// Resource\RESOURCE.D03 |
// Resource\RESOURCE.D04 |
// Resource\RESOURCE.D06 |
// Resource\RESOURCE.D07 |
// Resource\RESOURCE.D11 \

Here you mention Items and Scene. What kinds of files are these?
## Post #5
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-07T07:58:51+00:00
- Post Title: Yesterday - by Pendulo Studio

Like i said, these games uses their own format that is connected with the game engine. Yesterday I've checked "Runaway I" and seems like its files are different from the "Yesterday"'s.
Where i wrote "Items", it means that the archive contains items images and "Scenes" contains the backgrounds of the game scenes.
I've unpacked the whole game, but didn't find any text file, so translating it wont be that easy.
## Post #6
- Username: gyeben
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 19, 2011 10:43 pm
- Post datetime: 2012-04-07T17:16:54+00:00
- Post Title: Yesterday - by Pendulo Studio

Hmmm, can you tell me how to unpack the game?

I've tried with every method I found on the net, but I could only extract Runaway's music.

Sorry, for being a noob   but I'm a beginner in modding games.
## Post #7
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-07T19:43:13+00:00
- Post Title: Yesterday - by Pendulo Studio

Since i'm not familiar with QuickBMS, i'm posting my crappy PHP parsers that i used for my research. With them you can only unpack "Yesterday", so you better not use them on the rest of the Pendulo games.

For unpacking the image banks:

```
	$file = 'RESOURCE.X69'; // This is your input file
	$dump = 'RESOURCE_X69'; // This is where the file will be unpacked
	// Dont touch anything below that point
	if (!is_dir($dump)) {
		mkdir($dump, 0777, true);
	}
	$fh = fopen($file, 'r');
	if ($fh) {
		$entries = dword2int(fread($fh,4));
		if ($entries > 0) {
			$structutre_size = $entries*2;
			echo "Entries: ".($entries/4)."\n";
			$structure = fread($fh, $structutre_size);
			$ii = 0;
			for($i = 0; $i < $entries/4; $i++) {
				$offset = dword2int(substr($structure,($i*4),4));
				$size = dword2int(substr($structure,($i*4)+$entries,4));
				printf("%08X; %08X\n", $offset, $size);
				fseek($fh, $offset);
				$data = "";
				$ext = "null";
				if ($size > 0) {
					$ext = "bin";
					$data = fread($fh, $size);
					$t = substr($data,0,4);
					switch($t) {
						case "\x89\x50\x4E\x47": $ext = "png"; break;
						case "\xFF\xD8\xFF\xE0": $ext = "jpg"; break;
						case "\xFF\xD8\xFF\xE1": $ext = "jpeg"; break; // headless JPG
					}
				}
				if ($fho = fopen(sprintf("%s%02d.%s",$dump,$ii,$ext), "w+")) {
					fwrite($fho, $data, $size);
					fclose($fho);
				}
				$ii++;
			}
		}
		fclose($fh);
	}
	function dword2int($s) {
		return hexdec(bin2hex(strrev($s)));
	}
?>
```


For unpacking the sound banks:

```
	$file = 'DATAAV.000'; // This is your input file
	$dump = 'DATAAV_000'; // This is where the file will be unpacked
	// Dont touch anything below that point
	$filetypes = array(
		0x00 => 'wav',
		0x02 => 'ogg'
	);
	if (!is_dir($dump)) {
		mkdir($dump, 0777, true);
	}
	$fh = fopen($file, 'r');
	if ($fh) {
		$entries = dword2int(fread($fh,4));
		if ($entries > 0) {
			$structutre_size = $entries*13;
			echo "Entries: ".$entries."\n";
			$structure = fread($fh, $structutre_size);
			$ii = 0;
			for($i = 0; $i < $structutre_size; $i+=13) {
				$offset = dword2int(substr($structure,$i,4));
				$size = dword2int(substr($structure,$i+4,4));
				$c = dword2int(substr($structure,$i+8,4));
				$type = dword2int(substr($structure,$i+12,1));
				printf("%08X; %08X; %08X; %X\n", $offset, $size, $c, $type);
				fseek($fh, $offset);
				$data = fread($fh, $size);
				if ($fho = fopen(sprintf("%s%02d_%08X.%s",$dump,$ii,$c,$filetypes[$type]), "w+")) {
					fwrite($fho, $data, $size);
					fclose($fho);
				}
				$ii++;
			}
		}
		fclose($fh);
	}
	function dword2int($s) {
		return hexdec(bin2hex(strrev($s)));
	}
?>
```


You can run those scripts as PHP-CLI or under HTTP.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-07T19:47:30+00:00
- Post Title: Yesterday - by Pendulo Studio

If someone uploads one of each, someone else can write a (tested) bms script. I'm not confident enough to just translate from one language to another without testing lol
## Post #9
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2012-04-08T02:33:51+00:00
- Post Title: Yesterday - by Pendulo Studio

to unpack audio files:

```
For I = 0 < FILES
  Get OFFSET long
  Get SIZE long
  Get FILEID long
  Get TYPE byte
  If TYPE == 0
    Set EXT string ".wav"
  ElseIf TYPE == 1
    Set EXT string ".mp3"
  ElseIf TYPE == 2
    Set EXT string ".ogg"
  Else
    Set EXT string ".dat"
  EndIf
  String NAME p= "%04u_%08x%s" I FILEID EXT
  Log NAME OFFSET SIZE
Next I

```


to unpack images:

```
Math FILES = FAT2
Math FAT2 += 4
Math FILES /= 4
For I = 0 < FILES
  String NAME p= "%08u.bin" I
  Get OFFSET long
  SavePos FAT1
  Goto FAT2
  Get SIZE long
  SavePos FAT2
  Goto FAT1
  Log NAME OFFSET SIZE
Next I
```

images are PNGs/JPGs, regardless .bin extension. (in runaway series they was raw images, and data file formats slightly differs)
like in all other pendulo games texts are in main exe file, so you don't need to unpack any of data files for translation.
