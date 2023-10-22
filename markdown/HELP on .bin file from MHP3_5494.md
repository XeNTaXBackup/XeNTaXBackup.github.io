## Post #1
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-12-04T21:16:54+00:00
- Post Title: HELP on .bin file from MHP3

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-12-18T01:49:19+00:00
- Post Title: HELP on .bin file from MHP3

The code to decrypt the DATA.BIN

```
/*************************************************************/

u8 byte_table[256] = {
	0xcb, 0x96, 0x85, 0xa6, 0x5f, 0x3e, 0xab, 0x03, 0x50, 0xb7, 0x9c, 0x5c, 0xb2, 0x40, 0xef, 0xf6, 
	0xff, 0x61, 0x15, 0x29, 0xa2, 0xf1, 0xec, 0x52, 0x35, 0x28, 0xd9, 0x68, 0x24, 0x36, 0xc4, 0x74, 
	0x26, 0xe2, 0xd5, 0x8c, 0x47, 0x4d, 0x2c, 0xfa, 0x86, 0x66, 0xc1, 0x4f, 0x0b, 0x81, 0x5b, 0x1b, 
	0xc0, 0x0a, 0xfd, 0x17, 0xa4, 0xa9, 0x6d, 0x63, 0xad, 0xf3, 0xf4, 0x6e, 0x8d, 0x89, 0x14, 0xdd, 
	0x59, 0x87, 0x4a, 0x30, 0xce, 0xfe, 0x3f, 0x7e, 0x06, 0x49, 0xa5, 0x04, 0x5e, 0xd0, 0xde, 0xe8, 
	0x0f, 0xd4, 0x13, 0x1f, 0xba, 0xb9, 0x69, 0x71, 0x3d, 0xe4, 0xdc, 0x58, 0x90, 0x34, 0x3a, 0x3c, 
	0xca, 0x10, 0x76, 0xc7, 0xc8, 0x45, 0x33, 0xc3, 0x92, 0x1d, 0x2b, 0x1c, 0x8f, 0x6f, 0x05, 0x07, 
	0x38, 0x57, 0x51, 0xd6, 0xda, 0x2d, 0xb3, 0xc6, 0x2e, 0x64, 0x32, 0x1e, 0x43, 0xb1, 0x5d, 0xe1, 
	0xbb, 0x8e, 0x9d, 0x72, 0x77, 0xf2, 0x27, 0xc9, 0x7f, 0x9e, 0xaa, 0x6a, 0x2f, 0x6c, 0xf9, 0x48, 
	0xe7, 0xa0, 0x09, 0x56, 0xb8, 0xbd, 0x20, 0x41, 0xcd, 0x95, 0x80, 0xd7, 0x23, 0x0c, 0x42, 0xe5, 
	0xae, 0x8b, 0x7d, 0xbc, 0x54, 0x39, 0xbf, 0x65, 0x01, 0x88, 0xe0, 0x7b, 0xb6, 0x16, 0x18, 0x4b, 
	0xcc, 0x22, 0x5a, 0xb5, 0xeb, 0xfc, 0xf8, 0x9b, 0x4e, 0xe6, 0xa8, 0xbe, 0x67, 0x73, 0x97, 0x94, 
	0x00, 0x62, 0xb4, 0xd2, 0x21, 0x25, 0x11, 0x82, 0xdb, 0x93, 0x02, 0x84, 0x7c, 0xd3, 0xb0, 0xa3, 
	0x91, 0xa7, 0xf7, 0x55, 0x70, 0x7a, 0x08, 0x75, 0x8a, 0x53, 0x79, 0xfb, 0x9f, 0x46, 0xf5, 0x83, 
	0xd8, 0x0e, 0xe9, 0xed, 0x12, 0xd1, 0xdf, 0xf0, 0x37, 0x2a, 0x44, 0x19, 0x9a, 0x31, 0xcf, 0xa1, 
	0xaf, 0xe3, 0x3b, 0x1a, 0x4c, 0x78, 0xc2, 0x60, 0xee, 0x98, 0x6b, 0x0d, 0x99, 0xea, 0xc5, 0xac, 
};


u32 key0 = 0x00007F8D;
u32 key1 = 0x00002345;

void init_key(u32 seed)
{
	key0 = seed&0xffff;
	if(key0==0)
		key0 = 0x7F8D;

	key1 = seed>>16;
	if(key1==0)
		key1 = 0x2345;
}

u32 get_key(void)
{
	key0 *= 0x7F8D;
	key0 %= 0xFFF1;

	key1 *= 0x2345;
	key1 %= 0xFFD9;

	return key0+(key1<<16);
}

void mhp3_decrypt(u8 *buf, u32 len)
{
	int i;
	u32 key;

	for(i=0; i<len; i+=4){
		buf[0] = byte_table[buf[0]];
		buf[1] = byte_table[buf[1]];
		buf[2] = byte_table[buf[2]];
		buf[3] = byte_table[buf[3]];

		key = get_key();
		*(u32*)buf ^= key;

		buf += 4;
	}
}

/*************************************************************/


```


How to use:
Use LBA offset as the seed: 

```
    mhp3_decrypt(buf, len);

```


Offset of 0 is index table.
## Post #3
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-12-18T18:48:16+00:00
- Post Title: HELP on .bin file from MHP3

can you just give me the compiled exe

dont have a compiler installed..if that;s ok with you..thanks by the way
## Post #4
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-12-19T10:22:09+00:00
- Post Title: HELP on .bin file from MHP3

Here is the program. Put data.bin to same directory and run it 
[mhp3.rar](https://xentaxbackup.github.io/file/3697_mhp3.rar)
## Post #5
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-12-19T13:56:19+00:00
- Post Title: HELP on .bin file from MHP3

oh i think it will just decrypt and not to extract 

anyway.. if you can still manage to do some.. expert moves..

how on earth i could compile back the file?

is there any method? please teach me how..

thanks by the way for the hardwark.. looking forward to it again..
## Post #6
- Username: Nimer
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 12, 2010 5:49 am
- Post datetime: 2010-12-20T02:18:03+00:00
- Post Title: HELP on .bin file from MHP3

I have no idea how you did this tpu, but it is hell of a good work (since today I though that DATA.BIN was encrypted in AES ;])! I would realy like to know as much as you do about asm and PSP - you are damn good!

I have a little problem with your code. Here is my main.cpp using yours functions:

> ifstream ifile("DATA.BIN",ifstream::binary|ifstream::in);
>
> 	ofstream ofile("DeDATA.BIN",ofstream::binary|ifstream::out);
>
> 	u8 tmp[4]={0,0,0,0};
>
> 	init_key(0); //since I start reading from block 0 (relative).
>
> 
>
> 	while(true)
>
> 	{
>
> 		tmp[0]=ifile.get();
>
> 		tmp[1]=ifile.get();
>
> 		tmp[2]=ifile.get();
>
> 		tmp[3]=ifile.get();
>
> 		if(!ifile.good())
>
> 		{
>
> 			break;
>
> 		}
>
> 
>
> 		mhp3_decrypt(tmp,4);
>
> 		ofile<<tmp[0]<<tmp[1]<<tmp[2]<<tmp[3];
>
> 	}
>
> 
>
> 	ifile.close();
>
> 	ofile.close();

There seems to be a little problem with this code - I does not decode file correctly. After decoding I do not see PNG header at adress 01cd5800.
After starting to read at adress 01cd5800 and correcting LBA block nr in init_key only first four bytes of header are decoded correctly (rest is a mess). So if you could tell me what I did wrong I would be greatfull .

On a side note to kenn:
To encode it back you need to write a opposite code table (by the code table I mean byte_table[256]).
My english is quite bad so I will use an example:
lets say you have a code where 0 is coded as 52, 1 is coded as 20, 2 is coded as 11, and so one. The fastest way to do encoding is to make table in which at index 0 is a value 52, at index 1 value 20, at index 2 value 11, and so one. To decode it back fast you need a table where at index 52 you will have value 0, at index 20 value 1, and so one.
## Post #7
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-12-20T02:50:57+00:00
- Post Title: HELP on .bin file from MHP3

TO nimer:
You need to decrypt offset 0 to get index table first. The offset of other files are descript by index table. Then you can use the offset value to decrypt each file.
Some files, .prx and .pmf, are plain data, doesn.t need to decrypt.
## Post #8
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-12-20T07:02:17+00:00
- Post Title: HELP on .bin file from MHP3

> On a side note to kenn:
>
> To encode it back you need to write a opposite code table (by the code table I mean byte_table[256]).
>
> My english is quite bad so I will use an example:
>
> lets say you have a code where 0 is coded as 52, 1 is coded as 20, 2 is coded as 11, and so one. The fastest way to do encoding is to make table in which at index 0 is a value 52, at index 1 value 20, at index 2 value 11, and so one. To decode it back fast you need a table where at index 52 you will have value 0, at index 20 value 1, and so one.

Yeah yeah, understand it correctly 
so is there a possibility to repack it  back after you use some of this code with the help of tpu?
## Post #9
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-12-20T09:30:40+00:00
- Post Title: HELP on .bin file from MHP3

The repack tool come.
Just keep the nessary file in data_bin, and run it.
The tool can repack data into a ISO file: "mhp3imp x:/xxx/xxx.iso"
[mhp3imp.rar](https://xentaxbackup.github.io/file/3701_mhp3imp.rar)
## Post #10
- Username: kenn
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Mar 23, 2010 12:59 am
- Post datetime: 2010-12-20T11:40:38+00:00
- Post Title: HELP on .bin file from MHP3

unfortunately i recently tried the repacker one.. but the game wont load it, the MMS LED is blinking and the screen is black..
my repacking procedure is correct..
by the way did you try the packer tool already? maybe there is something wrong with it
## Post #11
- Username: Nimer
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 12, 2010 5:49 am
- Post datetime: 2010-12-20T12:33:42+00:00
- Post Title: HELP on .bin file from MHP3

Ok... I managed to understand some things you wrote.

Mister tpu, correct my if I am wrong:
1. Index table is in written using Little Endian (I forgot that Sony prefers LE - silly me).
2. Index table is of 34 KB size.
3. There seems to be two tables - one from adress 0x0 to 0x5D10 and second from first ending. First table consist of 5956 elements. I do not gasp the meaning of second table.

> 0x5D00:  31 23 08 00 6c 23 08 00 a3 23 08 00 c5 23 08 00 //heres the line ending first table
>
> 0x5D10:  11 00 00 00 d0 50 00 00 12 00 00 00 60 04 00 00 //heres the line starting second table
So if you could tell me what is the meaning of second table I would be greatfull .
4. From 0x8557 to 0x8800 is a padding data.

What I do not get is from where you got file length, and how to indicate if file is encrypted or not. Are those things written somewhere in that index table?
## Post #12
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-12-20T13:59:56+00:00
- Post Title: HELP on .bin file from MHP3

The second table is the actual length of some files( not all files). The format: [index] [length] [index] [length] .........
## Post #13
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-12-20T14:01:27+00:00
- Post Title: HELP on .bin file from MHP3

Some padding data has fixed pattern. you can detect it and cut it.
## Post #14
- Username: Nimer
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 12, 2010 5:49 am
- Post datetime: 2010-12-20T15:52:27+00:00
- Post Title: HELP on .bin file from MHP3

> Reply from tpu
>
> The second table is the actual length of some files( not all files). The format: [index] [length] [index] [length] .........
So I have to get actual files length from their header? I though they did it simpler XD. Anyways thx - you were verry helpful!

BTW. THX to you I'm able to pull this translation out so I would like to put your name in the credits (if you do not mind) ;P.
## Post #15
- Username: Tonyhunterblade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 20, 2010 7:56 pm
- Post datetime: 2010-12-21T00:43:08+00:00
- Post Title: HELP on .bin file from MHP3

Hi, i recompiled the data.bin with tpu's program ( mhp3imp.exe ). And next i rebuild data.bin in iso file. I put it on my psp, but like kenn, i've black screen and the memory stick load and load and load.... =/

Do you know where is the problem ? My hexadecimal translation is nevertheless correct... I use as many characters as the English translation.

EDIT : I just recompile the data.bin without touching any file bin. Well the game does not work when you run it, so -> the recompilage program has a problem tpu.... Can you post a version without problem soon pliz ? ^^
## Post #16
- Username: Nimer
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 12, 2010 5:49 am
- Post datetime: 2010-12-21T01:02:58+00:00
- Post Title: Re: HELP on .bin file from MHP3

> Reply from Tonyhunterblade
>
> Hi, i recompiled the data.bin with tpu's program ( mhp3imp.exe ). And next i rebuild data.bin in iso file. I put it on my psp, but like kenn, i've black screen and the memory stick load and load and load.... =/

Do you know where is the problem ? My hexadecimal translation is nevertheless correct... I use as many characters as the English translation.
Try following scheme:
Extract the file you wana change (but do not change it) and after that compile it back. If it works (GAME Runs) then it is fault of your changes.

@tpu: I know I'm asking for a lot recently, jet 1 more answer from you would save my some time (you already solved it). Can you write me some details on structure of 16.BIN file? I have few assumptions (I hate making them so I will refrain from writing them), jet there is 1 thing that bothers my - there is some kind of index table at begin of 16.BIN file. Can you share with us its meaning?
## Post #17
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-12-21T01:29:42+00:00
- Post Title: Re: HELP on .bin file from MHP3

> Reply from Tonyhunterblade
>
> Hi, i recompiled the data.bin with tpu's program ( mhp3imp.exe ). And next i rebuild data.bin in iso file. I put it on my psp, but like kenn, i've black screen and the memory stick load and load and load.... =/

Do you know where is the problem ? My hexadecimal translation is nevertheless correct... I use as many characters as the English translation.

Please delete the prx and pmf file from data_bin when repack.
## Post #18
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-12-21T01:46:28+00:00
- Post Title: Re: HELP on .bin file from MHP3

Sorry, I don't know the format of 16.bin.
Looks like there have many parts in 16.bin. First table pointer to each part.  And each part have there own table to pointer each text.
## Post #19
- Username: Nimer
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 12, 2010 5:49 am
- Post datetime: 2010-12-21T02:01:59+00:00
- Post Title: Re: HELP on .bin file from MHP3

> Reply from tpu
>
> Sorry, I don't know the format of 16.bin.
Looks like there have many parts in 16.bin. First table pointer to each part.  And each part have there own table to pointer each text.
Well, I will get to it by myself - It will just take some time. I just heard from someone you are part of ACG Chiness Group and they have already translated MHP3rd (great work btw), so I though you may already know it (I hate reinventing the wheel).

Thx again mr tpu . BTW there is alot of stupid tekst from Capcom in 16.BIN (I lough alot about it - the developers furry XD).
## Post #20
- Username: Tonyhunterblade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 20, 2010 7:56 pm
- Post datetime: 2010-12-21T02:07:42+00:00
- Post Title: Re: HELP on .bin file from MHP3

So, tpu, you tell me to delete prx files and pmf files ?
But I have only prx files, no pmf files...

EDIT : I tried to recompiled the data.bin without touching the content data_bin (I just deleted the folder with the prx). The game does not always start correctly =/

EDIT 2 : During the repacking, i obtain this : [http://img824.imageshack.us/img824/9370 ... tre1zx.jpg](http://img824.imageshack.us/img824/9370/sanstitre1zx.jpg)
Strange lol. What is the exact manipulation to rebuild its data.bin ? Where should I place mhp3imp.exe ? What should you do before recompiling ? Sorry for these questions but it's frustrating because this is the last step so I can play in French =/
## Post #21
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-12-21T03:58:25+00:00
- Post Title: Re: HELP on .bin file from MHP3

Please delete 3349.bin also... and use a clean ISO to try it again.
## Post #22
- Username: Tonyhunterblade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 20, 2010 7:56 pm
- Post datetime: 2010-12-21T09:48:01+00:00
- Post Title: Re: HELP on .bin file from MHP3

> Reply from tpu
>
> Please delete 3349.bin also... and use a clean ISO to try it again.

I try this.

EDIT : I just recompile the Japanese clean version without touching the .bin files.
 Result -> The game does not always start ... =/
## Post #23
- Username: Nimer
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 12, 2010 5:49 am
- Post datetime: 2010-12-21T16:31:02+00:00
- Post Title: Re: HELP on .bin file from MHP3

I managed to fully understand structure of 16.BIN. It is quite easy structure.
First 8 bytes: Header.
Next is BasicIndexTable (Ended with FF FF FF FF).
BasicIndexTable entries are addresses to StringIndexTables.

StringAddressTable is build with addresses (relative from its position in file!) to strings. Each string is ended with 00 char.
Whole block of strings is ended with 00 (so last string entry is ended with 00 00), and after it is another StringAddressTable... and so one and one.

I just need to find in what format jap characters are encoded and 'I am in home' .
## Post #24
- Username: Tonyhunterblade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 20, 2010 7:56 pm
- Post datetime: 2010-12-21T18:20:46+00:00
- Post Title: Re: HELP on .bin file from MHP3

Anybody here can make program ( wich works ) to recompile game ? ^^
## Post #25
- Username: Nimer
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 12, 2010 5:49 am
- Post datetime: 2010-12-21T21:09:31+00:00
- Post Title: Re: HELP on .bin file from MHP3

I can make program that works... hell I already did it.

I also found out all in game strings and I can write program for their changing... so just wait a bit, can you? I wrote on other website that I will release such a tool within next 2 days.
## Post #26
- Username: Tonyhunterblade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 20, 2010 7:56 pm
- Post datetime: 2010-12-21T21:47:53+00:00
- Post Title: Re: HELP on .bin file from MHP3

Great ! =)
I will wait for it, but do not forget to put your program on this site please ^^
## Post #27
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-12-23T14:38:43+00:00
- Post Title: Re: HELP on .bin file from MHP3

Nimer = Atlas?
Tonyhunterblade = DaNS?

Just wondering, those posts remind me of you 
Anyways, what are you gonna do w/ the prog Tonyhunterblade? Some translation? Eager to have one except for aumanx, it is somewhat buggy for me 

Kind regards,
~EyCaramba!~
## Post #28
- Username: Tonyhunterblade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 20, 2010 7:56 pm
- Post datetime: 2010-12-23T23:30:02+00:00
- Post Title: Re: HELP on .bin file from MHP3

I learn to program in C since 4 days ><
I don't know how to program a decrypter lol.

ps : I'm not DaNS ^^
## Post #29
- Username: Nimer
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 12, 2010 5:49 am
- Post datetime: 2010-12-25T16:21:26+00:00
- Post Title: Re: HELP on .bin file from MHP3

> Reply from eycaramba
>
> Nimer = Atlas?
Tonyhunterblade = DaNS?

Just wondering, those posts remind me of you 
Anyways, what are you gonna do w/ the prog Tonyhunterblade? Some translation? Eager to have one except for aumanx, it is somewhat buggy for me 

Kind regards,
~EyCaramba!~
I am not Atlas... do not post your imaginations will you?

I have already posted my translation toolset on some PSP forums... just look around the web.
## Post #30
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-12-26T14:36:04+00:00
- Post Title: Re: HELP on .bin file from MHP3

Oh well, badly guessed xD
Anyways, nice tools
## Post #31
- Username: gabby32
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 30, 2010 12:01 pm
- Post datetime: 2011-01-09T23:02:10+00:00
- Post Title: Re: HELP on .bin file from MHP3

Nimer  Thank you for your toolset. You continue working on it?
In files 4201.bin 4202.bin 4203.bin of text messages in the village.
## Post #32
- Username: gabby32
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 30, 2010 12:01 pm
- Post datetime: 2011-02-10T05:53:50+00:00
- Post Title: Re: HELP on .bin file from MHP3

Succesfully generated all encypted bins and patched them in the iso.
items are translated well but everytime i try to take a mission the game freeze.
I've tried to use another iso but nothing changed.
I've also tried to patch the iso without translating anything (just as downloaded) but the game still freeze when i'm selecting a mission.
## Post #33
- Username: obmas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 04, 2011 3:43 pm
- Post datetime: 2011-04-14T03:45:29+00:00
- Post Title: Re: HELP on .bin file from MHP3

Is it possible to extract icons or textures from the bin file?
