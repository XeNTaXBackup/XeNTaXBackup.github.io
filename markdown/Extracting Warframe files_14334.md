## Post #1
- Username: grammerrock
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 12, 2016 1:10 pm
- Post datetime: 2016-05-13T00:02:31+00:00
- Post Title: Extracting Warframe files

Hi,

Not sure where to go with this. I've extracted most of the meat of Warframe's .cache files with QuickBMS and the Evolution Engine Cache Extractor, and have been able to decompile most of the game's .bin files (Packages.bin, B.Cache.bin, etc. from H.Misc.cache) using IDA, but there are some files that are either obfuscated or encrypted: I can't tell which. I'm not able to figure out what the method to extracting the drop tables is. Apparently, a while back they started being encrypted and/or obfuscated, but people have gotten through that issue: [https://github.com/VoiDGlitch/WarframeData](https://github.com/VoiDGlitch/WarframeData)

Is there a way to look into EXEs or cache files to find out what unpacks them? For example, somehow this file in the image below (H.Misc.cache/Lotus/Types/Game/MissionDecks/ArchwingCacheCoordsReward) decompiles/deobfuscates/decrypts to something like [this](https://github.com/VoiDGlitch/WarframeData/blob/master/MissionDecks.txt#L1-L22).

Thanks for any help.
## Post #2
- Username: Nodus Cursorius
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 08, 2016 3:31 pm
- Post datetime: 2016-06-28T13:36:06+00:00
- Post Title: Extracting Warframe files

Going to carry on this thread by contributing my own findings and productions while also answering one of your questions. First, [VoiD_Glitch](https://www.reddit.com/user/VoiD_Glitch) is the "middleman", in that he collaborates with other people who make progress on the decryption side of things. They improve upon the internal program that they all share and VoiDGlitch releases the results to the public, from time to time. I can assure you that despite best efforts, they are absolutely uninterested in sharing their findings, code, methods, or programs. The reasons have varied from "but then they'll patch it" ( -Void) to "you haven't earned it, and it is kinda cool that only a few people know, right?" (- others) . Disagreements aside, Void is still good people.

Hopefully that changes in time.

> Reply from grammerrock
>
> and have been able to decompile most of the game's .bin files (Packages.bin, B.Cache.bin, etc. from H.Misc.cache)

I'm supplying my discoveries and information for people who will find this through Google, or otherwise. But if you'd be so kind, I'm also curious how you managed to sort things in IDA. I'm more than familiar with how to use it for true binaries, but not for data blobs like .bins.

Attached to this post is WFPackageParser.7z, which contains a precompiled PackagesLexer.dll from [Deathmax's WFPackageParser](https://github.com/Deathmax/WFPackageParser), a WFPackageParser_readme.txt file, and a Powershell script named getdata.ps1. Why Powershell? It allows you to load a library into Powershell assembly and directly call the functions. No third-party programs needed. Below is the mirrored readme file to explain how to use the files to convert Packages.bin and Languages.bin into readable human formats (mostly). On a few glances, all of the data seems accurate but only time and testing will tell.†

† There are minor issues with the parsing so far that I am not sure how to solve, but they seem to be mostly uncommon. Any help would be appreciated:

* Example Failure:
```
483561        BasePackage : EmberFireBlastEntity
483562        HeaderPath  : /Lotus/Powersuits/Ember/
483563         ParsedChunk : {[Range, System.String[]], [AttackData, System.Collections.Generic.Dictionary`2[System.String,System.Object]], [AttackTime, 1], [TargetHitScript, System.Collections.Generic.Dictionary`2[System.String,System.Object]]}
```
* Expected Values from a reference-only format: [http://hastebin.com/ayoquqixuy](http://hastebin.com/ayoquqixuy)

----

WFPackageParser_readme.txt

```
* Included getdata.ps1 Powershell script to automate the process of using PackagesLexer.dll
(!) The PackagesLexer.dll may require .NET 4.0/4.5
-------------

- Extract the compressed folder to anywhere
- Copy Packages.bin and Languages.bin to the newly extracted folder
- Run the Powershell script (getdata.ps1) or open Powershell, navigate to the extracted folder, and run the commands from getdata.ps1 one at a time.
	* You may receive quick closure of the Powershell window. This is NORMAL BEHAVIOR, but it means the script did not run. Default security settings disallow scripts.
		+ To resolve, run Powershell as Admin then execute this command: Set-ExecutionPolicy RemoteSigned
			+ When asked, enter Y to confirm the new setting. Rerun the script afterwards

		+ Documentation about the above security: http://www.adminarsenal.com/admin-arsenal-blog/powershell-how-to-write-your-first-powershell-script/


	(!) If the above is uncomfortable: open a normal Powershell window, navigate to the newly extracted folder, then run these commands one at a time:

		$absolutePath= (Get-Item -Path ".\" -Verbose).FullName
		[Reflection.Assembly]::LoadFile($absolutePath+"\PackagesLexer.dll");
		$PackagesLexer= New-Object "PackagesLexer.Packages" ($absolutePath+"\Packages.bin")
		$LanguagesLexer= New-Object "PackagesLexer.Languages" ($absolutePath+"\Languages.bin")
		$PackagesLexer > Packages.txt
		$LanguagesLexer > Languages.txt


	(!) What are those commands doing?!

		$absolutePath= (Get-Item -Path ".\" -Verbose).FullName
			* This is getting the full path name of where you are in Powershell, required for the next three lines.

		[Reflection.Assembly]::LoadFile($absolutePath+"\PackagesLexer.dll");
			* Here we manually loading PackagesLexer.dll into Powershell's Assembly "memory"

		$PackagesLexer= New-Object "PackagesLexer.Packages" ($absolutePath+"\Packages.bin")
			* Next, load the non-static function of classname: PackagesLexer function:Packages and tell it to use the string "Packages.bin"

		$LanguagesLexer= New-Object "PackagesLexer.Languages" ($absolutePath+"\Languages.bin")
			* Then, load the non-static function of classname: PackagesLexer function:Languages and tell it to use the string "Languages.bin"

		$PackagesLexer > Packages.txt
			* Execute the Packages function and store the output into Packages.txt within the same folder

		$LanguagesLexer > Languages.txt
			* Execute the Languages function and store the output into Languages.txt within the same folder

```

WFPackageParser.7z Mirrors:
https://mega.nz/#!7RJVSACA!rzyxq2HWRgmR ... OVH-eH1CWs


 WFPackageParser.7z
Pre-compiled PackagesLexer.dll from Deathmax's WFPackageParser project and getdata.ps1 Powershell script to automate the process. READ THE README. (5.01 KiB) Downloaded 69 times


WFPackageParser_readme.txt Mirrors (for Powershell script preservation):
http://hastebin.com/qejemufaku.tex
https://gist.github.com/NodusCursorius/ ... f90b9e4764
