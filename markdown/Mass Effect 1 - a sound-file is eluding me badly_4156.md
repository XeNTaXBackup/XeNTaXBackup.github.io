## Post #1
- Username: Okogawa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 7:16 am
- Post datetime: 2010-02-20T19:49:32+00:00
- Post Title: Mass Effect 1 - a sound-file is eluding me badly

Partially relevant information: I am doing a remake of Mass Effect 1 in 2D (ruby), but are having a slight issue with a voiceover file which cannot be found. For my sound extraction needs I use Dragon UnPACKer 5 on individual *.isb files in the Mass Effect 1 ISACT directory.

The Problem 

Normally (as with all other files), I have always found a *.isb (file with voiceovers) "counterpart" for any *.upk file, but for this file "nor10_char_creation_D.upk" I cannot find any *.isb

Why I greatly need to find the cabinet with the "voiceover" data is because it's for the character generation screen. I can live without this data, but I would do so with a sad heart.

I'll provide some more info if it might help to track up the missing file with the "ogg" files inside:


******************************

Name                  = tlk
Object number         = 1
Class                 = BioTlkFile
Object Flags          = 00 00 00 00 04 00 0f 00
Object size           = 2 K
Object adress         = 20602
Export line adress    = 2190
Next object           = nor10_char_creation_dlg
Number of String Ref  = 57 
Number of valid String    = 15
Number of Huffman nodes   = 93
Number of string          = 15
168926	Please log in to access your profile.
168924	Establishing secure connection.
168980	Profile reconstruction complete.
168930	Confirm psychological profile.
168923	Classified information requested.
168928	Please reconstruct profile.
168931	Confirm military specialization.
168929	Confirm pre-service history.
168925	Secure connection confirmed.
168979	Confirm facial identification.
168981	Identification confirmed.
168922	Welcome to Alliance Military database.
168933	Confirm secondary training.
168927	Warning: Data corruption detected.
168932	Confirm primary training.

******************************

Number of labels         = 76
Number of import element = 6
Number of export element = 14
Adress of labels         = 137
Adress of import element = 1950
Adress of export element = 2118

Imported elements :  ElementNumber  ElementClass  DefinedInto.ElementName
------------------
0  Class  BIOC_Base.BioConversation
1  Class  BIOC_Base.BioTlkFile
2  Class  BIOC_Base.BioTlkFileSet
3  Package  .BIOC_Base
4  Package  .nor10_char_creation_N
5  Sequence  nor10_char_creation_N.Node_Data_Sequence

Exported standalone elements :  Size  ElementNumber  ElementClass  ElementName
-----------------------------
View         17420      0  BioConversation  nor10_char_creation_dlg

******************************

Any kind assistance would be most welcome

O.
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-02-22T07:01:30+00:00
- Post Title: Mass Effect 1 - a sound-file is eluding me badly

Guess you'll have to go thru every *.isb as game likely uses 'em globally for assets, in worst case scenario said audio is held in some upk file with adpcm compression like sfx are.
## Post #3
- Username: Okogawa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 7:16 am
- Post datetime: 2010-02-23T11:54:53+00:00
- Post Title: Mass Effect 1 - a sound-file is eluding me badly

> Reply from Apollo
>
> Guess you'll have to go thru every *.isb as game likely uses 'em globally for assets, in worst case scenario said audio is held in some upk file with adpcm compression like sfx are.

That explains it all...! the *.isb files does not have it, so... can you recommend any tool that can open/scan ME1 upk files and extract the adpcm compression data. While at it, I might want to date the sfx files too, what are they named?

Cheers!

O.
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-02-23T18:52:16+00:00
- Post Title: Mass Effect 1 - a sound-file is eluding me badly

I found some sfx files, namely weapons/explosions and such under the Audio_Content\VFX folder in the upk files there

attached Derplaya's experimental upk extractor for the adpcm data but many of the wavs can be false or otherwise wrong with it and sadly I don't know of better tool for the job of converting the custom riff files with adpcm.

Got it from [http://meforums.bioware.com/forums/view ... =125&sp=58](http://meforums.bioware.com/forums/viewtopic.html?topic=635466&forum=125&sp=58)

enjoy.

Also additional note, Psychonauts explorer tool will open the *.ISB files with their proper names for the ogg files.
[MEPCAudioUPK.rar](https://xentaxbackup.github.io/file/2797_MEPCAudioUPK.rar)
## Post #5
- Username: Okogawa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 7:16 am
- Post datetime: 2010-02-26T17:38:58+00:00
- Post Title: Mass Effect 1 - a sound-file is eluding me badly

Wonderfully great, you MADE MY DAY!!!!! The tool worked perfect and after just 30 min I got the sound files I need + others I did not know I needed until I heard them (alien theme base siren as an example)...

WOW! Not used to so much luck at the same time!

Cheers and thanks!!!   

O.
## Post #6
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-03-28T03:35:47+00:00
- Post Title: Mass Effect 1 - a sound-file is eluding me badly

Do any one have a Extractor tool for isb sound file format of Mass Effect 1 ?

I remember I had got a exe File for *.isb in CoockedPC/Packages/ISACT folder last 2009 earlier.
It may be February~March 2009.

Now I can't find out the files in WEB.
The file is just one file of MS-Dos type

Inform me!
## Post #7
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-03-29T14:43:06+00:00
- Post Title: Mass Effect 1 - a sound-file is eluding me badly

> Reply from wuixntx
>
> Do any one have a Extractor tool for isb sound file format of Mass Effect 1 ?

I remember I had got a exe File for *.isb in CoockedPC/Packages/ISACT folder last 2009 earlier.
It may be February~March 2009.

Now I can't find out the files in WEB.
The file is just one file of MS-Dos type

Inform me!

After having eventually found it out, I attach the address below.
[http://meforums.bioware.com/forums/view ... =125&sp=30](http://meforums.bioware.com/forums/viewtopic.html?topic=635466&forum=125&sp=30)

And isbextract which I've found attached here.
[isbextract.7z](https://xentaxbackup.github.io/file/2897_isbextract.7z)
