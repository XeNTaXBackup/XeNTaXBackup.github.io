## Post #1
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-01-23T23:29:54+00:00
- Post Title: Help with Gust Games Extraciton - Nights of Azure 2 (+More)

Hey there. for about... 4-5 months now I've been attempting to crack a simple conundrum I have and I Just, can't do it. As each months go buy I get increasingly fusterated with being unable to find help, or figure out what exactly I need to do. My problem is this. there are 5 Gust games I'm tryign to extract, all of which I was attempting to do through 1 program, Steven's Gas Machine.
The games are, Atelier Sophie and Firis, Nights of Azure 1 and 2, and Blue Relfections. 4 of those 5 games can be extracted indirectly using at the very least 3 different programs


My biggest issue, and the one I want the most help with is my issue with nights of Azure 2. I can extract the elixir.gz to it elixir base. Its CREA meaning its Little Endian. I have an edited Xentax program that fixed Little/Big Endian math just for Sophie at the time after doing a little something with 2 other programs which removed issue number 1 for Sophie (Invalid EARC File).

However, I am still hit with another issue using the sophie fix. "Unknown Filename Size"

Secondly, I am hoping to extend out a asking hand for help on merging all the source codes into Stevens gas machine so I can mas unpak without havign to go through 3-4 different programs for each individual model. I collected all sorts of source codes, and I am hoping someone might be able to help. PM me if able.

However, issue number 2 is not as important. I want to solve my current predicament. Do you need any test files? I am not sure exactly what to give so let me know. At the very least, here is the character I am attempting to extract

[https://mega.nz/#!1MEiTChS!oH-yMqMDND-C ... FPFBnrE89c](https://mega.nz/#!1MEiTChS!oH-yMqMDND-C42auuuf4PD2p2YamPTQNsFPFBnrE89c)

this is the edited xentax if you want to see the error, but I don't have the source code, unfortunately. The only thing I remember is that the person who helped me 4 months ago did something to Steven's Little Big Endian math to help fix. I have no idea if it helps but you can try using it.

[https://mega.nz/#!0V8mjKhD!568zjueC6m0_ ... NR56v6ikmY](https://mega.nz/#!0V8mjKhD!568zjueC6m0_-2YOWdncZGX2h7S2W6ZjWNR56v6ikmY)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-24T06:29:44+00:00
- Post Title: Help with Gust Games Extraciton - Nights of Azure 2 (+More)

> Reply from kurokairaku
>
> At the very least, here is the character I am attempting to extract
https://mega.nz/#!1MEiTChS!oH-yMqMDND-C ... FPFBnrE89c
this bms script will decompress and extract the files from your gz sample  

```

//Decompression
comtype zlib_noerror
get NAME basename
do
   get ZSIZE long
   savepos OFFSET
   append
   clog memory_file OFFSET ZSIZE ZSIZE
   append
   math OFFSET + ZSIZE
   goto OFFSET
while ZSIZE != 0
//Extraction
goto 0x0 -1
idstring -1 "CRAE" 
get UNK long -1 
get TOTAL_DATA_SZ long -1
get START_TABLE long -1
get TABLE_SZ long -1
get FILES long -1
get UNK2 long -1
for i = 0 < FILES
	get OFFSET long -1
	get SIZE long -1
	getdstring NAME 0x40 -1
	log NAME OFFSET SIZE -1
next i

```
## Post #3
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-01-24T06:44:55+00:00
- Post Title: Help with Gust Games Extraciton - Nights of Azure 2 (+More)

> Reply from AceWell
>
> kurokairaku wrote:At the very least, here is the character I am attempting to extract
https://mega.nz/#!1MEiTChS!oH-yMqMDND-C ... FPFBnrE89c
this bms script will decompress and extract the files from your gz sample

Dude, fuck. It worked. I really have to thank you, its been so long since I been trying to ask the original creator xentax tool for help, and 3 other guys, only to get ignored or something like that. It works, so I honestly don't care that it isn't integrated into 1 program now, thanks so much. I was a bit worried at first because then the g1m was being hit with a "invalid g1m version" or something but I tried to extract it using a different setting of a more recent game made by Koei and it worked. 

No problems (so far). I don't think there will be any problems honestly. So thanks.
## Post #4
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-04-12T20:07:33+00:00
- Post Title: Help with Gust Games Extraciton - Nights of Azure 2 (+More)

> Reply from kurokairaku
>
> 
this is the edited xentax if you want to see the error, but I don't have the source code, unfortunately. The only thing I remember is that the person who helped me 4 months ago did something to Steven's Little Big Endian math to help fix. I have no idea if it helps but you can try using it.

https://mega.nz/#!0V8mjKhD!568zjueC6m0_ ... NR56v6ikmY

can someone please reupload this?
