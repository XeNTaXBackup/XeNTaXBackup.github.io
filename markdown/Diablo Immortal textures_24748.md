## Post #1
- Username: rman1234
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 03, 2021 2:51 am
- Post datetime: 2021-11-18T22:08:20+00:00
- Post Title: Diablo Immortal textures

Hello!

I am trying to uncompress the Diablo Immortal textures that come with the game. It uses the Netease Messiah engine.

It looks like they are compressed all in the same file with different mipmap levels. Luckily, I managed to extract the bytes from the compression part and it looks like it is ZZZ4 (LZ4?).

However, when I used the [Dishonored Messiah LZ4 script](http://aluigi.altervista.org/bms/disorder_messiah.bms) it creates a file that I don't know how to open 

I uploaded one example (it should be a coin image) on each step:

Step 1, original file: [https://www.mediafire.com/file/3x7yw9mp ... ure2D/file](https://www.mediafire.com/file/3x7yw9mpeo5o2ho/01_coin_bj.Texture2D/file)
Step 2, compression section: [https://www.mediafire.com/file/8a181w2e ... 2.lz4/file](https://www.mediafire.com/file/8a181w2ed09qde7/text2.lz4/file)
Step 3, LZ4 uncompressed: [https://www.mediafire.com/file/bi3jbcks ... 1.lz4/file](https://www.mediafire.com/file/bi3jbckssvkv05j/text2_00000001.lz4/file)

Could you please help me out with this? All texture files seem to have the same format, so with this example I should be able to get all of them.

Thanks!!
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2022-02-17T12:18:44+00:00
- Post Title: Diablo Immortal textures

Yeah, I need help with those textures aswell! Here's info template, it might be useful. 

[https://github.com/CucFlavius/Zee-010-T ... Texture.bt](https://github.com/CucFlavius/Zee-010-Templates/blob/main/DiabloImmortal_Texture.bt)

 Meanwhile I'll be looking at model format, which looks pretty okay for now
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2022-02-18T16:11:17+00:00
- Post Title: Diablo Immortal textures

Managed to decompress highest mip from texture, now it's headerless astc (should be lol) texture, which isn't very useful for me, since I have no idea how to convert it

[https://www.mediafire.com/file/bfk9bvwo ... _n.7z/file](https://www.mediafire.com/file/bfk9bvwo8y5ibv9/m_necromancer_yifu_t00_000_n.7z/file)
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-02-18T22:07:16+00:00
- Post Title: Diablo Immortal textures

@zaramot: You can convert such images through PVRTexTool, it has option for wrapping raw data with desired parameters. Here is converted example from the first post with parameters from template you've linked (43 = ASTC 8x8). I suppose it can be also automated with batch scripts, as the tool works in cli mode too. Alternatively, you can write a script to convert texture2d file into valid astc file with proper header, which can be converted with the same tool in more convenient way.

[https://drive.google.com/file/d/1lnkk01 ... sp=sharing](https://drive.google.com/file/d/1lnkk01OLVLEGTmnsDuoJXNx3zPRPK5r6/view?usp=sharing)
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2022-02-19T08:39:25+00:00
- Post Title: Diablo Immortal textures

Thanks a lot! At least I know for sure in which location I should look. I must admit, that I'm very unfamiliar with this pvrtextool, though I tried it before posting here. Just for some reason it looks like tool can't see astcenc.exe, I think so, even if pvrtextool not saying it. Though in list of compressions in "wrap raw data", there's nothing about astc.

EDIT: Thanks a lot! Downloaded proper tool and encoder and everything worked! That's great, much appreciated for all the help!
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-02-19T12:17:27+00:00
- Post Title: Diablo Immortal textures

Here is sample script for converting texture2d files into astc files, compatible with PVRTexTool directly (suitable for batch convert). Not all formats are covered though, only some ASTC ones, but I don't have any samples for tests. Also, I'm not sure about alpha channel flag, probably it's one of those byte fields.

Update: Script is updated with proper support for texture2D files with multiple mips. Also, it now supports BC7 format as well. For more info read [this post](https://zenhax.com/viewtopic.php?f=9&t=16089&p=71884#p71884).
Update 2: Script is updated with support for uncompressed data chunks.



 diablo_texture_convert_v2.zip
(1.04 KiB) Downloaded 63 times
## Post #7
- Username: rman1234
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 03, 2021 2:51 am
- Post datetime: 2022-03-10T21:40:33+00:00
- Post Title: Diablo Immortal textures

Yes! It was as easy as that, just an ASTC file 

I am now trying to get the strings and database to see if I can get a list of item names, skill descriptions and so on but I am facing an encrypted file:

I could open the Resources.mpk and Resources.mpkinfo thanks to the mpk.bms script and now I get a bunch of files that are probably encrypted but I can't figure out how to go from here.

Here are some examples: 

[https://www.mediafire.com/file/0t38kkqw ... cfc3a/file](https://www.mediafire.com/file/0t38kkqwvjxkqxd/e46a07c1c54d66e3e77251ce383cfc3a/file)
[https://www.mediafire.com/file/hslml9a0 ... 281b1/file](https://www.mediafire.com/file/hslml9a0qddk75z/0f98fac7babf2dfab4c388ff67a281b1/file)
[https://www.mediafire.com/file/yl58ph0y ... 7d578/file](https://www.mediafire.com/file/yl58ph0ytj96hxm/ef2f6ecf63a082be43aa04f839f7d578/file)

I can only tell that the first two hex characters are always "E2 06" but I can't find any other coincidences. Any idea about what encryption or compression method they used on these files?

I am trying to get the item and skill database with all the descriptions.

Thanks!

PS: Resources.mpk and Resources.mpkinfo here:
[https://www.mediafire.com/file/wwzxvst2 ... s.mpk/file](https://www.mediafire.com/file/wwzxvst2bt3z4d7/Resources.mpk/file)
[https://www.mediafire.com/file/m051zcnp ... kinfo/file](https://www.mediafire.com/file/m051zcnpiho4ajz/Resources.mpkinfo/file)
## Post #8
- Username: Rushster
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 08, 2021 9:55 pm
- Post datetime: 2022-06-02T18:47:23+00:00
- Post Title: Diablo Immortal textures

Looking to grab the map files out of the game. Not sure where to start. Any tips to help get me on my way?
## Post #9
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-06-07T00:05:31+00:00
- Post Title: Diablo Immortal textures

Apparently PC version is using more of BC formats, so script for textures above is updated with support for at least BC7 format. Also, fixed mpk script is available through linked post as well, since original one has particular issue with PC version of the game.
## Post #10
- Username: sharase
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 02, 2023 5:47 pm
- Post datetime: 2023-02-02T09:54:24+00:00
- Post Title: Diablo Immortal textures

Once you have the appropriate tool, you can use it to decompress the extracted bytes to obtain the original textures [subway surfers](https://subwaysurf.io/)
## Post #11
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2023-02-28T10:09:19+00:00
- Post Title: Diablo Immortal textures

Thanks for the tool. I don't know if this 2 problem is only for me and I messed some where but.
1.this file don't convert. This is the bms error

  offset           filesize   filename
--------------------------------------
This format is not supported! Add it to definitions first.

- 0 files found in 0 seconds
  coverage file 0     0%   140        114812     . offset 0000000000007234
  coverage file -1    0%   0          16         . offset 0000000000000000
  coverage file -2    0%   0          148        . offset 0000000000000000
texturnotconvert.rar

2.some texture are broken I think.
## Post #12
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2023-02-28T10:12:19+00:00
- Post Title: Diablo Immortal textures

The broken texture


 broktex.rar
(179.44 KiB) Downloaded 18 times
## Post #13
- Username: werwerwerwewww
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 28, 2023 1:43 pm
- Post datetime: 2023-05-28T18:20:32+00:00
- Post Title: Diablo Immortal textures

You can do the following:
Using DIDT, download the game files. Rename and decompress from DIDT to a folder:
C:\Data_BetaROW_Android

Run from admin Powershell ISE:
Get a list of files from a folder of subfolders by extension .Texture2D:
Get-ChildItem -Path C:\Data_BetaROW_Android -Recurse -Include *.Texture2D | Select-Object FullName | Out-File C:/Data_BetaROW_Android/Texture2D_path.txt

Open C:/Data_BetaROW_Android/Texture2D_path.txt via Notepad++, delete at the beginning of the file:
full name
--------
We remember the finite number of lines.

After downloading quickbms, and putting it in the C:\Data_BetaROW_Android folder, create a quickbms_listfiles.txt file containing the text below, for an equal number of lines in the Texture2D_path.txt file:
C:\Data_BetaROW_Android\quickbms.exe -F "{}.Texture2D" -o "C:\Data_BetaROW_Android\diablo_texture_convert_v2.bms" "ABCD" "C:\Data_BetaROW_Android\_\"
C:\Data_BetaROW_Android\quickbms.exe -F "{}.Texture2D" -o "C:\Data_BetaROW_Android\diablo_texture_convert_v2.bms" "ABCD" "C:\Data_BetaROW_Android\_\"
C:\Data_BetaROW_Android\quickbms.exe -F "{}.Texture2D" -o "C:\Data_BetaROW_Android\diablo_texture_convert_v2.bms" "ABCD" "C:\Data_BetaROW_Android\_\"
etc...

Replace values in lines containing "ABCD" with file paths from C:/Data_BetaROW_Android/Texture2D_path.txt:
$psFilePath = "C:\Data_BetaROW_Android\quickbms_listfiles.txt"
$list2FilePath = "C:\Data_BetaROW_Android\Texture2D_path.txt"
$tempFilePath = "C:\Data_BetaROW_Android\tempFile.txt"
$list2Content = Get-Content -Path $list2FilePath
$list2ContentIndex = 0
Get-Content -Path $psFilePath | ForEach-Object {
    $line = $_
    if ($line -match "ABCD") {
        # Замена ABCD на соответствующую строку из файла list2
        $line = $line -replace "ABCD", $list2Content[$list2ContentIndex]        
        $list2ContentIndex++;
    }
    $line | Add-Content -Path $tempFilePath
}
Remove-Item -Path $psFilePath
Move-Item -Path $tempFilePath -Destination $psFilePath
Get-Content -Path $psFilePath

We open quickbms_listfiles.txt through Notepad++, we see that "ABCD" is replaced by empty to *.Texture2D
Copy everything and paste it into Powershell ISE. We are waiting for quickbms to work on all textures and drop *.astc into the C:\Data_BetaROW_Android\_\ folder
Then we get again a list of files in txt:
Get-ChildItem -Path C:\Data_BetaROW_Android\_ -Recurse -Include *.astc | Select-Object FullName | Out-File C:/Data_BetaROW_Android/astc_path.txt

Open C:/Data_BetaROW_Android/astc_path.txt via Notepad++, delete at the beginning of the file:
full name
--------
We remember the finite number of lines.

Create C:\Data_BetaROW_Android\_\astc_to_tga.txt with the text below, equal to the number of lines from the file C:/Data_BetaROW_Android/astc_path.txt
astcenc -d AAAA BBBB

Replace values in lines containing "BBBB" with file paths from C:/Data_BetaROW_Android/astc_path.txt:
$psFilePath = "C:\Data_BetaROW_Android\_\astc_to_tga.txt"
$list2FilePath = "C:/Data_BetaROW_Android/astc_path.txt"
$tempFilePath = "C:\Data_BetaROW_Android\tempFile.txt"
$list2Content = Get-Content -Path $list2FilePath
$list2ContentIndex = 0
Get-Content -Path $psFilePath | ForEach-Object {
    $line = $_
    if ($line -match "BBBB") {
        # Замена ABCD на соответствующую строку из файла list2
        $line = $line -replace "BBBB", $list2Content[$list2ContentIndex]        
        $list2ContentIndex++;
    }
    $line | Add-Content -Path $tempFilePath
}
Remove-Item -Path $psFilePath
Move-Item -Path $tempFilePath -Destination $psFilePath
Get-Content -Path $psFilePath

As a result, opening C:\Data_BetaROW_Android\_\astc_to_tga.txt in Notepad++, we will see something like:
astcenc -d AAAA C:\Data_BetaROW_Android\_\2019_feidao_01_xzx.Texture2D.astc
astcenc -d AAAA C:\Data_BetaROW_Android\_\2019_jiaoying_01_xzx.Texture2D.astc
astcenc -d AAAA C:\Data_BetaROW_Android\_\2019_jiaoying_02_xzx.Texture2D.astc
etc...

Ctrl+F from Notepad++ -> Replace .astc to .tga, check'n'save:
astcenc -d AAAA C:\Data_BetaROW_Android\_\2019_feidao_01_xzx.Texture2D.tga
astcenc -d AAAA C:\Data_BetaROW_Android\_\2019_jiaoying_01_xzx.Texture2D.tga
astcenc -d AAAA C:\Data_BetaROW_Android\_\2019_jiaoying_02_xzx.Texture2D.tga
etc...

Replace values in lines containing "AAAA" with file paths from C:/Data_BetaROW_Android/astc_path.txt:
$psFilePath = "C:\Data_BetaROW_Android\_\astc_to_tga.txt"
$list2FilePath = "C:/Data_BetaROW_Android/astc_path.txt"
$tempFilePath = "C:\Data_BetaROW_Android\tempFile.txt"
$list2Content = Get-Content -Path $list2FilePath
$list2ContentIndex = 0
Get-Content -Path $psFilePath | ForEach-Object {
    $line = $_
    if ($line -match "AAAA") {
        # Замена ABCD на соответствующую строку из файла list2
        $line = $line -replace "AAAA", $list2Content[$list2ContentIndex]        
        $list2ContentIndex++;
    }
    $line | Add-Content -Path $tempFilePath
}
Remove-Item -Path $psFilePath
Move-Item -Path $tempFilePath -Destination $psFilePath
Get-Content -Path $psFilePath

See:
astcenc -d C:\Data_BetaROW_Android\_\2019_feidao_01_xzx.Texture2D.astc C:\Data_BetaROW_Android\_\2019_feidao_01_xzx.Texture2D.tga
astcenc -d C:\Data_BetaROW_Android\_\2019_jiaoying_01_xzx.Texture2D.astc C:\Data_BetaROW_Android\_\2019_jiaoying_01_xzx.Texture2D.tga
astcenc -d C:\Data_BetaROW_Android\_\2019_jiaoying_02_xzx.Texture2D.astc C:\Data_BetaROW_Android\_\2019_jiaoying_02_xzx.Texture2D.tga
etc...

Finally downloading astcenc.zip [http://www.mediafire.com/file/mbxqu39zw ... c.zip/file](http://www.mediafire.com/file/mbxqu39zwbuw220/astc.zip/file)
Unpack everything in C:\Data_BetaROW_Android\_ , rename C:\Data_BetaROW_Android\_\astc_to_tga.txt -> C:\Data_BetaROW_Android\_\astc_to_tga.bat
Run command promt from admin:
cd C:\Data_BetaROW_Android\_\
astc_to_tga.bat
Waiting a million hours

Delete *.astc:
Get-ChildItem -Path "C:\Data_BetaROW_Android\_\" -Filter "*.astc" -Recurse | Remove-Item -Force


Result on the picture. The script is still running...
[](https://ibb.co/gDMdb79)
