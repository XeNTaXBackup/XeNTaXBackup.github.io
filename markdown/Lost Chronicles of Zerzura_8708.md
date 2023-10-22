## Post #1
- Username: djokay
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jun 05, 2010 2:44 pm
- Post datetime: 2012-04-07T07:12:13+00:00
- Post Title: Lost Chronicles of Zerzura

Hi
Does one of you tried or how can extract the dialogues of the game Lost Chronicles of Zerzura.
Apparently the dialogues are in the file loca.bin but I think the file is linked loca.dat2
Currently no tools that I used has succeeded in extracting (Gobread, bin file extractor, etc. ...)
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-04-07T10:49:20+00:00
- Post Title: Lost Chronicles of Zerzura

This script can unpack the dat2 file

```
getdstring UNK 0x8
get FILES long
get NAMETABLESIZE long
savepos OFF
math NTABLE = FILES
math NTABLE *= 16
math NTABLE += OFF
log MEMORY_FILE NTABLE NAMETABLESIZE
for i = 0 < FILES
get OFFSET long
get ZSIZE long
get SIZE long
get NAMEOFF long
goto NAMEOFF MEMORY_FILE
get NAME string MEMORY_FILE
clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #3
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-04-09T23:25:16+00:00
- Post Title: Lost Chronicles of Zerzura

This is a tool for the loca.bin file. [http://www.sendspace.com/file/5yg9ba](http://www.sendspace.com/file/5yg9ba)
## Post #4
- Username: djokay
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Jun 05, 2010 2:44 pm
- Post datetime: 2012-04-11T16:48:34+00:00
- Post Title: Lost Chronicles of Zerzura

Thank you for your answers.
I started wanting to translate loca.bin with HexWorkshop but with great difficulty  
I hope that with the tools it will go much better.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-20T07:28:41+00:00
- Post Title: Lost Chronicles of Zerzura

The original post contained links to game files. Removed. The new rules are clear.
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-08-03T20:39:40+00:00
- Post Title: Lost Chronicles of Zerzura

So guys, have anybody tried to translate this game?
Importer posted here by swuforce throws me an error while importing non-changed .txt file back to the loca.bin. :-/

EDIT: swuforce updated his exporter/importer, so error is gone. Thank you very much
## Post #7
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2013-08-22T19:39:41+00:00
- Post Title: Lost Chronicles of Zerzura

Now, don't laugh too much, but here's a bin2csv<->csv2bin converter written in PHP:

```

//csv2bin('loca.csv', 'loca.bin');
//bin2csv('loca.bin', 'loca.csv');

function csv2bin($file_input, $file_output) {
	$structure = array(
		'header' => '',
		'entries' => 0,
		'unknown' => 0,
		'header_size' => 0,
		'str_delta' => '',
		'data' => array()
	);

	if ($FHo = fopen($file_output, 'wb+')) {
		$structure['entries'] = 0;
		$size_var = 0;
		$size_val = 0;
		if ($FHi = fopen($file_input, "r")) {
			while (($data = fgetcsv($FHi)) !== FALSE) {
				$size_var += strlen($data[0])+1;
				$size_val += strlen($data[1])+strlen($data[2])+4;
				$structure['data'][] = array('var' => $data[0], 'val' => $data[1], 'more' => $data[2]);
				$structure['entries']++;
			}
			fclose($FHi);
		}
		
		fwrite($FHo, "LOCA");
		putDword($FHo, count($structure['data']));
		putDword($FHo, 1);
		putDword($FHo, 0x18);
		fwrite($FHo, "delta\x00\x00\x00");
		
		$offset_var = (count($structure['data'])*8)+0x18;
		$offset_val = $offset_var+$size_var;

		$data_structure = '';
		$data_variable = '';
		$data_value = '';
		foreach($structure['data'] AS $row) {
			$data_variable .= $row['var']."\x00";
			$data_value .= $row['val']."\x00\x00".$row['more']."\x00\x00";
			putDword($FHo, $offset_var);
			putDword($FHo, $offset_val);
			$offset_var += strlen($row['var'])+1;
			$offset_val += strlen($row['val'])+strlen($row['more'])+4;
		}
		fwrite($FHo, $data_variable);
		fwrite($FHo, $data_value);
		fclose($FHo);
	}
}

function bin2csv($file_input, $file_output) {
	$structure = array(
		'header' => '',
		'entries' => 0,
		'unknown' => 0,
		'header_size' => 0,
		'str_delta' => '',
		'data' => array()
	);

	if ($FHi = fopen($file_input, 'rb')) {
		$file_input_data = '';
		while(!feof($FHi)) {
			$file_input_data .= fread($FHi, 4000);
		}
		fclose($FHi);

		$structure['header'] = getString($file_input_data, 0, 4);
		$structure['entries'] = getDword($file_input_data, 4);
		$structure['unknown'] = getDword($file_input_data, 8);
		$structure['header_size'] = getDword($file_input_data, 12);

		if ($structure['header'] != 'LOCA') {
			echo "Bad header\n";
			exit;
		}
		echo "Header: '".$structure['header']."' - OK!\n";
		echo "Number of entries: ".$structure['entries']."\n";
		echo "Unknown flag: ".$structure['unknown']."\n";
		echo "Size of header: ".$structure['header_size']."\n";
		
		
		$structure['str_delta'] = getString($file_input_data, 16, $structure['header_size']-16);
		if ($structure['str_delta'] != 'delta') {
			echo "Delta is unknown";
		}
		echo "Delta is: '".$structure['str_delta']."' - OK!\n";
		if ($FHo = fopen($file_output, 'wb+')) {	
			for ($i = 0; $i < $structure['entries']; $i++) {
				$offset_var = getDword($file_input_data, $structure['header_size']+(($i*4)*2));
				$offset_val = getDword($file_input_data, $structure['header_size']+((($i*4)*2)+4));

				$str_var = getString($file_input_data, $offset_var);
				$str_val = getString($file_input_data, $offset_val);
				$str_val2 = getString($file_input_data, $offset_val+strlen($str_val)+2);

				fwrite($FHo, $str_var.",\"".$str_val."\",\"".$str_val2."\"\n");
			}

			fclose($FHo);
		}
		
		echo "Done!\n";
	}
}

function putDword($hwnd, $value) {
	fwrite($hwnd, strrev(hex2bin(sprintf("%08X", $value))), 4);
}

function getDword($source, $offset) {
	return hexdec(bin2hex(strrev(substr($source, $offset, 4))));
}

function getString($source, $offset, $size = NULL) {
	if ($size == NULL) {
		return trim(strstr(substr($source, $offset, strlen($source)), "\x00", true));
	}
	return trim(substr($source, $offset, $size));
}

?>
```

*BOF:EPIC BULLSHIT*
It works just fine as long as you are using a latin alphabet. For some reason, it doesn't work for Cyrillic alphabet (i'm a Bulgarian so f*ck me   ). Also, make sure you are editing the CSV as ANSI encoding, and not UTF-8 for example.
*EOF:EPIC BULLSHIT*

Now, it DOES work with Cyrillic alphabet, and it SHOULD be UTF-8 encoded. Still the original fonts doesn't support Cyrillic alphabet, but oh well...   

About the DAT2 files (loca.dat2, speech.dat2, gui.dat2, scripts.dat2 and sfx.dat2), i've already released an Unpakke module that supports both unpacking and packing.

Good luck!  

-- note to self
Don't drink and post at late hours.
## Post #8
- Username: deant
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jul 15, 2013 6:11 pm
- Post datetime: 2013-10-23T20:52:41+00:00
- Post Title: Lost Chronicles of Zerzura

oh wow, nice to see another bulgarian here:)
