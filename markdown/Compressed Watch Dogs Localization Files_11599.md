## Post #1
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-06-16T06:43:52+00:00
- Post Title: Compressed Watch Dogs Localization Files

Hi,
I think .loc files of the Watch Dogs uses similar compression used in the Assassins Creed series. 
Anyone has any idea with these files? I added a sample of file.

<link removed due forum rules violation>
## Post #2
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-10-12T13:12:47+00:00
- Post Title: Compressed Watch Dogs Localization Files

I found that

I hope someone helps to investigate further.
[sample.7z](https://xentaxbackup.github.io/file/7922_sample.7z)
## Post #3
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2015-01-26T15:43:36+00:00
- Post Title: Compressed Watch Dogs Localization Files

Hi people, I made a good progress.

I finally build string fragments table. But, I do not know how this fragment table is indexed from the file.

I successfuly build string fragments table for both small file provided in previous entry and main_english.loc file.
However, I do not know how indexing works. I tried 1 byte indexing to this string fragment table in small file, meaningful texts are appeared.
However, in main_english.loc file, we need more advanced indexing since there is more than 255 entries in the string fragments table. 

Here the output for DBD82924.loc(small file)

```
- d enESinthf*[202]*onthe ai*[206]*vis ine is pitayIBloo a*[217]*.Bloos : playoois Bad Blooy*[226]*atchother tr*[230]**[231]*/pear_®*[237]**[238]*re*[240]*T-Bone playf a *[245]*WE*[248]*f*[250]*loothew ®f*[256]*A savegame for the Bad Blood DLC has been detected but the DLC is not installed. Install the DLC to use this savegame.*[305]*gYou must complete [CSS_BLUE]FADING SIGNAL[CSS_END] to access Bad Blood online features.:C Car qOnline Street Sweep: The GPS destination of the other player [GPSGWICON] is displayed on your map.gamethT-BontA*[422]*o*[424]* MBad Blood inoWce f*[432]*aisioner z*[437]* atch_Dunline Street Sweep: en*[443]*R/C Car othea Mear the R/C Car  s : *[454]*D*[456]*oanplayll e atT-Bone e playother E*[469]*trll*[472]*ear*[474]**[475]*with R/C Car is earine T-Bone dE*[484]*llth*[487]**[488]*c*[490]*NR/C Car *[493]**[494]*l.Gl- T-Bone Campaign : Play as T-Bone in his own story campaign.
- Street Sweep Missions : Weaken Chicago’s gangs to earn new rewards.
- Co-op Mode : Play Street Sweep missions with other players.
- 10 new Perks : Discover 10 new exclusive Perks to deal with 
```


Here the string fragments for DBD82924.loc(small file)

```
" "
"e"
"e "
"c"
"t"
"s"
"n "
"s "
"in"
"u"
"i"
"C"
"o"
"P"
"a"
" the "
"f"
"."
"l"
"d"
"S"
"m"
"g"
"to"
"on"
"A"
"G"
"n"
"ea"
"r"
"h"
". "
"is "
"re"
"play"
"I"
"p"
"b"
"N"
"us"
" M"
"is"
"er"
"y "
"de"
"to "
"You "
"ur"
"R/C Car "
"ll"
" a"
"am"
"d "
"1"
"k"
","
"v"
"D"
"av"
"re "
"ce "
"ai"
"t the "
"ep"
"ear"
"s : "
" a "
"Bad Blood DLC "
"Watch_Dog"
"an"
"it"
"ted "
"en"
"game"
"tin"
"cannot join"
"s.{\n}- "
"stall"
" new "
"trac"
"T-Bone "
"sion"
"Online Street Sweep: "
"with "
"other play"
"er "
"ca"
"at"
"DLC "
"Bad Blood "
"ou"
"r "
"the "
"t "
"]"
"["
"y"
"W"
"wi"
"s."
"not "
"gam"
"Street Sweep"
"te"
"You"
"ew"
"DL"
": "
"lay"
"ee"
"0"
"O"
"E"
"M"
"L"
"w"
"_"
"oth"
"line "
"ion"
"T-Bon"
"ac"
"new "
"sta"
"{\n}- "
"- "
"ar "
"st"
"ew "
"Bad Bloo"
"loo"
"ay"
"th"
"R"
"q"
"‘"
"z"
"x"
"’"
"{\n}"
"F"
"U"
"-"
"T"
"B"
"®"
"atch_Dog"
"atch_Do"
"atch_D"
"atch_"
"atch"
"atc"
"nnot join"
"not join"
"not jo"
"not j"
"nline Street Sweep: "
"line Street Sweep: "
"line Street Sweep"
"th "
"other "
"ine "
"-Bon"
"Bon"
"/C Car "
"C Car "
"Car "
"ot "
"treet Sweep"
"treet Swee"
"treet Sw"
"treet S"
"treet "
"tree"
"ad Bloo"
"d Bloo"
"Bloo"
"tr"
"oo"
"C "
"/"
":"
"j"
"Y"

```


I hope there are people who can help me. 

I just simply run the C# code in the attachment. It prints stringFragmentsTable entries, and output using 1 byte indexing.
My code is based on DerPlaya's code for Assassins Creed game. 

Also, here my guess for loc file structure as template.

```
//--- 010 Editor v5.0.2 Binary Template
//--------------------------------------

uint magic;
ushort languageCode;
ushort count1;
uint stringFragmentsOffset;
struct{
uint a,b;
}t[count1];
FSeek(stringFragmentsOffset);
int count2;//includes zero-zero node,but it is not written here
struct{
    short right,left;
}nodes[count2-1];

```

[Watch_Dogs_Loc.7z](https://xentaxbackup.github.io/file/8568_Watch_Dogs_Loc.7z)
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-26T22:04:20+00:00
- Post Title: Compressed Watch Dogs Localization Files

had a few minutes to look at this quickly.

the bit ops are already quite confusing - but the c# is very easy to follow.

i've modified the loop to spit out the string chunks:

```
            {
                byte b = r.ReadByte();
                ++numConsumedCodes;

                if( b == 0 )
                {
                    Console.WriteLine("Line: '{0}'", sb.ToString());
                    sb.Clear();
                   // sb.Append("\n");
                }

                else if (b < maxStringFragmentIndex)
                {
                    string val = stringFragments[b+1].ToString() ;

                    Console.WriteLine("{0} '{1}'", (int)(b), val);
                    sb.Append(val);
                }
                else
                {
                    Console.WriteLine("UNKNOWN: {0}", (int)b);
                }

```


but there doesn't seem to be much data left for string sizes or offsets.

any idea what the 1x 8 byte tables does? are the string chunks split across multiple tables?


pm me another sample file if you can
## Post #5
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2015-01-28T08:08:18+00:00
- Post Title: Compressed Watch Dogs Localization Files

I do not know what those bytes mean. Probably, ID of string block.
Yes, there should be offsets somewhere. Because, when I look at the memory of the game, stings are loaded when needed.
Hence, game should be able to seek the needed string.
## Post #6
- Username: defult06
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 29, 2017 12:58 pm
- Post datetime: 2017-05-29T07:18:45+00:00
- Post Title: Compressed Watch Dogs Localization Files

+up
## Post #7
- Username: Requizm
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 29, 2017 9:32 pm
- Post datetime: 2017-05-29T13:35:30+00:00
- Post Title: Compressed Watch Dogs Localization Files

Up+
## Post #8
- Username: Omris
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 01, 2018 11:04 pm
- Post datetime: 2018-07-25T06:08:02+00:00
- Post Title: Compressed Watch Dogs Localization Files

up.
## Post #9
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2019-01-25T06:59:52+00:00
- Post Title: Compressed Watch Dogs Localization Files

Hi everyone,

I finally managed to unpack loc files. Unfortunately, the loc file does not have ids, therefore you have to give min and max ids.

I attached unpacker with Watch_Dogs 1 main_english.loc file and unpacked main_english.txt file.

I won't spend time on writing tool to repack.

[Unpacked main_english.txt here](https://www93.zippyshare.com/v/H4KFAgzn/file.html)
[wd_loc_only.rar](https://xentaxbackup.github.io/file/15577_wd_loc_only.rar)
## Post #10
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2019-02-16T10:07:12+00:00
- Post Title: Compressed Watch Dogs Localization Files

> Reply from rengareng
>
> Hi everyone,

I finally managed to unpack loc files. Unfortunately, the loc file does not have ids, therefore you have to give min and max ids.

I attached unpacker with Watch_Dogs 1 main_english.loc file and unpacked main_english.txt file.

I won't spend time on writing tool to repack.

Unpacked main_english.txt here

Thanks a lot
## Post #11
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2019-05-29T04:02:58+00:00
- Post Title: Compressed Watch Dogs Localization Files

You can find source code of the tool below:
[Source Code](https://github.com/ahmet-celik/watch-dogs-loc-tool)
## Post #12
- Username: DeathScreen213
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Mar 15, 2019 5:38 pm
- Post datetime: 2019-12-25T18:13:53+00:00
- Post Title: Compressed Watch Dogs Localization Files

> Reply from rengareng ↑Wed May 29, 2019 12:02 pm at Wed May 29, 2019 12:02 pm
>
> 
You can find source code of the tool below:
Source Code
Can you reup your source code ?
## Post #13
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2020-11-01T12:51:04+00:00
- Post Title: Compressed Watch Dogs Localization Files

Does anyone know min/max ids for Watch Dogs: Legion? 
"wd_loc.exe main_english.loc 4555 234124" works quite well but some of the texts are incorrect.

i.e. 

there is:

Infiltrate I want a revenge on the thug that killed my brother.and shut down Project THEMIS.

it should be:

Infiltrate  Tidis and shut down Project THEMIS.


Could someone reup source code please?
## Post #14
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2020-11-10T03:31:42+00:00
- Post Title: Compressed Watch Dogs Localization Files

I tried that file with the tool, and it extracted fine. Source code should be accessible, but there would not be anyone who can write packer for this file. It's very complex.
