## Post #1
- Username: YourResidentFireMage
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 27, 2017 3:51 am
- Post datetime: 2017-05-26T20:53:13+00:00
- Post Title: Jojo's Bizzare Adventure Eyes of Heaven PS3 XFBIN Decryption

Hey everyone,

So I'm currently working on a mod to translate the PS3 version of Jojo's Bizarre Adventure: Eyes of Heaven from Japanese to English. For those who don't know, the game did receive an international release, but only on PS4. The PS3 version was never localized in any form. Writing out exactly how I plan for this mod to work would do nothing but waste everyone's time, so I'll leave a link here to my Reddit post where I describe this project in greater detail for those who are interested.

[https://www.reddit.com/r/StardustCrusad ... h=d8e38521](https://www.reddit.com/r/StardustCrusaders/comments/68ine6/eyes_of_heaven_ps3_english_patch/?st=j369rqvp&sh=d8e38521)

The main reason I'm on here is that I need some decryption help when it comes to the game's .XFBIN files. The game itself was developed by CyberConnect2 and uses a similar encoding and file format as the Naruto: Ultimate Ninja Storm games (UTF-8, to be specific). So far, I've managed to parse the ISO and extract and decompress the CPKs. However, the XFBIN files have been giving me some trouble currently, as I can access the base code of some files normally, but others appear to be encrypted in some form. 

Specifically, all of the game's text files (adv_storymenu_txt, csel_txt, glossary_txt, and so on) all seem to have a similar encryption, with the shared key in question being (c)CRIITOCï£^3 . In hex, that equates to 28 63 29 43 52 49 49 54 4f 43 ef a3 b3 . Additionally, a string containing 2 random characters and TP3 or the string CRILAYLA (43 52 49 4c 41 59 4c 41) can also be found within the encryption (N'TP3, XﾐTP3).

Here are some examples: 

```
T      %  1R  9R  AR  JR  PR  WR  fT  jZ  r  xT  T  ・  山  婬  ｩ[  ｱ                                 X     ・                               ｺ                        <NULL> CpkHeader UpdateDateTime FileSize ContentOffset ContentSize TocOffset TocSize TocCrc HtocOffset HtocSize EtocOffset EtocSize ItocOffset ItocSize ItocCrc GtocOffset GtocSize GtocCrc HgtocOffset HgtocSize EnabledPackedSize EnabledDataSize TotalDataSize Tocs Files Groups Attrs TotalFiles Directories Updates Version Revision Align Sorted EnableFileName EID CpkMode Tvers Comment Codec DpkItoc EnableTocCrc EnableFileCrc CrcMode CrcTable N/A, DLL3.15.00   +(W

```


```
(c)CRIITOC   H      @UTF  @   ,   D   x        T   T   [   ![   '             `   `   h<NULL> CpkItocInfo FilesL FilesH DataL DataH        @UTF   X   '   -   X        R   R   R    38・NULL> CpkItocL ID FileSize ExtractSize    @UTF   `   +   7   `        R   T   4          Zｸ   ~<NULL> CpkItocH ID FileSize ExtractSize
```


```
CRILAYLA  ｨY       ﾔﾇﾓ・ﾍ・ﾍ・9N</ﾀ_ｾpﾟ#tS・・瓊｡ｨ`橆 5 5猗・r・・gﾎ.j犧瞑#陲M< ﾄ'ﾓﾐ)ﾓ・哭B	sｦ iﾜ・エ|pN7o猯I3錮
```


A decrypted file should look like this: 
```
<root>
	<AtomId id='1sdw_Main_BattleTime2'>
		<GroupType value='1'/>
		<MyId value='71'/>
		<Id00 value=''/>
		<Id01 value=''/>
		<Id02 value=''/>
		<VoiceId value='71'/>
		<VoiceMorE value='1'/>
		<MessageId value='Live_1sdw_Main_BattleTime2'/>
		<Pri value='10'/>
		<EventId value='1'/>
		<EventParam value='0.6'/>
		<TargetId value=''/>
```


The blanks are just nulls that obviously don't render in this text box. Also, the character set is Shift-JS, but that can easily just be switched back to ANSI or regular UTF-8.

If anyone is skilled at PS3 modding or decryption and would like to help me out, I would be extremely grateful.

Sincerely, 

YourResidentFireMage
