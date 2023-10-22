## Post #1
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-08T22:34:22+00:00
- Post Title: Dead to rights 2 - PAK format 80% done

Okay, so by request I've been working on this .PAK format from Dead to Rights 2 (PC)

(actual archive files can be requested)

Okay, so let's get to it.

I'm talking about the English PC format PAK file. I need to know the compression method used. I've pretty much figured out the format, and encryption. 

First of all, the PAK file starts off like this in hex values:

```

```

or in ASCII: 

```

```


Right. The low-down is this. 
There are a number of resource entry types, all tagged: 

TMSAMVOF
TMSAMVOH
TMSAMIDX
TMSAMFIL
TMSAMUCL
TMSAMAUT

The PAK format has a table at it's tail. To get to the offset check the back of the file. There will be a "TMSAMVOF" entry. In that TAIL info entry, there is a pointer to the start of the tail table, with important info. 

Now, here's the catch. This TAIL table is encrypted. By deduction I learned the first 20 bytes of the encryption sequence. 

```

```


Here's a file with the sequence 

 encrkey1.zip
(142 Bytes) Downloaded 36 times



What happens is: each entry type has this TMSAMVOH or whatever magic word first and then a number of other important values particular to that entry type. Now, each variable, including the magic word is XORed using the above values. So, instead of encrypting a whole table, each variable is XORed individually. That means that an unsigned int of 32 bits (uint32), which has 4 bytes, is encrypted using F0D6AEBE sequentially. Shorts (uint16) that are two bytes, with F0D6 alone (starting with F0) and longer variables, such as filenames or other longer values with at least these 20 bytes of encryption. 

This way, you can have a decrypted table to work with:


 decrypted_table.zip
(128.47 KiB) Downloaded 35 times



When you take a good look at this table, you notice the 

TMSAMFIL which has info on a file. Notice the first is /content/raw. 
Now that file is actually the whole archive. And the main problem here. 
It gives information of 3821 following pieces of TMSAMUCL. These are compressed pieces of the TMSAMFIL. And actually, there are 3820 blocks of 65536 bytes compressed, and one final block of about 10000 bytes. So the whole content/raw file was chopped into pieces of 65336 in size which were compressed using some method. I think I have ruled out ZLib and deflate. Deflat gives an error -3, which is data corrupt error. Zlib has similar issues. Note also the three final FIL entries in the table, a log.txt file and a content/info filem followed by a single TMSAMUCL. These files could be compressed in a single run, as they were less that 65536 in size. Of note: these are actually in Zlib format and could be decompressed: 

```
Ampackager version: 5.41.1210
Amlibtool  revision: 
Amlibtool  capabilities: amvfs,amcrypt,amperl,amlicense,amencode,amjava
Ampetool   revision: 
Ampetool   capabilities: pefile,peglue,pelock,pecompress

```


and

```

```


respectively. 

The final entry is a TMSAMAUT type, that does not point somewhere before the TABLE for the relevant file data, but has it stored inside the entry itself. 

Interestingly, each raw data entry, pointed to by the table, had a personal header (of 55 bytes in size), again starting off with a TMSAMxxx tag that is encrypted using the above XORkeys. However, apart from that tag, all the other variables in the personal headers are NOT encrypted. So the authors went to great lenghts to encrypt the tail table (which basically consists of the headers to all the raw date entries in the archive!), but forgot to encrypt each header before the file data. 

Anyway, be that as it may, I am left with the question: what compression was used to compress each block of 65536 bytes (TMSAMUCL entries) ? I've attached two examples. Importantly, I've also added an ODS file (Open Office CALC) that shows the whole table in ODS format (MS Excel also (converted)). That will help you in appreciating my work and acknowledge the format. 


 mikes.zip
(87.82 KiB) Downloaded 29 times




 mikes_xls.zip
(125.34 KiB) Downloaded 27 times



Here are the examples of the compressed blocks. 
I've taken the first two compressed data entries of the "content/raw" huge file. See also the ODS or Excel table, the first two TMSAMUCL. 

THe first is Compressed Size = 27511 the other is Compressed Size = 1288. 
Presumably, the blocks that were compressed were 65536 for both, so Uncompressed size = 65536. Now the TMSAMUCL have some interesting unknown values. They all have an entry of 20 bytes that even decrypted don't look like anything legible, and they each have an entry of 8 bytes, that also doesn't ring a bell. I imagine they may be either encrypted in yet another way, or denote important CRC32 or whatever info for the used compressor!


 examples.zip
(28.33 KiB) Downloaded 31 times



Note that most start off with E7 31 and then 2X. Perhaps that will tip you off.

Any help is greatly appreciated!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-09T09:36:16+00:00
- Post Title: Dead to rights 2 - PAK format 80% done

the TMSA signature remembers me the Trymedia stuff for which already exist tools for doing the decryption/unpacking job (and so with the only remaining job of extracting the files from the clean archive).
have you already tried with it?

[http://arteam.accessroot.com/arteam/sit ... p?view.270](http://arteam.accessroot.com/arteam/site/download.php?view.270)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-09T11:57:01+00:00
- Post Title: Dead to rights 2 - PAK format 80% done

Excellent! That tool did the trick. 

The encryption key is 16 bytes long: 

```

```


Of course the algorithm uses that key that will result in the XORvalues as mentioned before. Anyway, with this tool it is possible to extract the huge content/raw file. 

I've attached the tool here as well, for safekeeping.


 ActiveMARKDecrypter_11_by_Nacho-dj.rar
(473.09 KiB) Downloaded 56 times



Surprisingly, that will result in another .PAK file, that is similar to the Russian .PAK file. 

This MexScript can extract the contents of those files easily. 

```
GoTo 12 0;
Get FileNum Long 0;
For T = 1 To FileNum;
GetCT FN String 10 0;
SavePos OO 0;
Get OFF Long 0;
SavePos SO 0;
Get SIZE Long 0;
Get U1 Long 0;
Log FN OFF SIZE OO SO;
Next T;

```


Here's the BMS file to add to your MultiEx Commander resource file using the BMS->Add BMS to MRF option in MultiEx Commander.


 pak.zip
(257 Bytes) Downloaded 44 times



The big pack file has a number of other PAK files that can also be opened using the MexScript above. In those files are the actual resources. 

Please note that these resources are also somehow compressed, like the PNG files seem to have the correct header, apart from the first two bytes, but then become fishy. So the new task at hand is figuring out the different resource formats! 

It is interesting to see that the authors have included Python code as well, they have coded a lot in Python then. 

Anyway, good to see we have together unravelled yet another mystery! Now for that Polish PAK version of Dead to Rights 2....
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-10T18:27:39+00:00
- Post Title: Dead to rights 2 - PAK format 80% done

Anyone got any experience with StarForce protection?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-10T19:28:08+00:00
- Post Title: Dead to rights 2 - PAK format 80% done

[http://m0006.gamecopyworld.com/games/pc ... ts_2.shtml](http://m0006.gamecopyworld.com/games/pc_dead_to_rights_2.shtml)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-10T23:11:47+00:00
- Post Title: Dead to rights 2 - PAK format 80% done

Yes, but the Polish GAME.PAK is encrypted somehow, and I was wondering if StarForce protection had something to do with it.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-11T01:02:57+00:00
- Post Title: Dead to rights 2 - PAK format 80% done

the specific starforce encryption applied to files/archives can be recognized by the SFFS signature in the files, do you see it in them?
anyway I'm not aware of tools able to decrypt it
