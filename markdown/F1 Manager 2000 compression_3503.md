## Post #1
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2009-05-21T17:05:18+00:00
- Post Title: F1 Manager 2000 compression

Hi,

Hector Tealdi contacted me last week for help on the game F1 Manager 2000. He wants to mod the game (he is already doing it, but needs access to the ressources of the game).

The game F1 Manager 2000 uses a similar file format as of Emperor: Battle for Dune RFH/RFD (but slightly different, there is a third file with RFC extension which contains a little bit more information than the RFH file). The problem is, some files in RFD uses an unknown compression type 1 (in Emperor Battle for Dune, the type is 2 and the compression is Zlib). I have been working of this the whole day, but I am just out of ideas.

From what I can see it seems a dictionnary compression, with the dictionnary being given for decompression in the header.

Here is what I have gathered, but I don't know if it is correct:

```
   4    1 bytes    Max frequency? Frequencia maxima?
   5    1 bytes    Init frequency? Frequencia initial? 
   6 1026 bytes    Empty / Vacio (00)
1032 1024 bytes    Dictionnary / Diccionario
                     (word 1 byte + type 1 byte [0 or 1]) / (caracter 1 byte + tipo 1 byte [0 o 1])
					 (if the type is 1, increase current frequency, word is meaningless) / (si el tipo es 1, incrementar la frequencia actual, el caracter no tiene sentido en este caso)
					 (if the type is 0, keep word with current frequency) / (si el tipo es 0, guardar el caracter con la frequencia actual)
2056    y bytes    Compressed data expanding to x bytes (Huffman with frequency table as described?)
                   Dataos comprimidos que se descomprimen como x bytes (Huffman con la tabla de frequencia descrita?)

```


I attach to this message a ZIP file containing:
 A text file with what I found (obviously I am mistaken, but maybe not too far from the truth)
 A little Delphi program with Huffman decompression which doesn't work... But you can check how I tried to retrieve the dictionnary with word frequencies from the header of the file
 2 compressed files extracted from the game archive (vdisk.rfd) the .cmp1 extension was added by Dragon UnPACKer, it is not like that in the RFC/RFH file
 2 non-compressed files from the same series, extracted from the game archive (vdisk.rfd), this should give an idea of the resulting extracted files (likely to use same colors [sky with clouds], header & footer).

Here is the link to the beta version of the plugin used by Dragon UnPACKer to extract the files:
http://download2..elberethzone.net/dup5/drv/default207beta1.d5p

If you are interested in the differences between RFH of Emperor: Battle for Dune & RFC/RFH of F1 Manager 2000, you can check the diff of the source of the plugin here (Delphi/Pascal):
[http://dragonunpacker.cvs.sourceforge.n ... 43&r2=1.44](http://dragonunpacker.cvs.sourceforge.net/viewvc/dragonunpacker/DragonUnPACKer/plugins/drivers/default/drv_default.dpr?r1=1.43&r2=1.44)

I hope someone can help, I am very bad at guessing compression...
[F1M-RFD_compression_guess.zip](https://xentaxbackup.github.io/file/2049_F1M-RFD_compression_guess.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-24T15:04:12+00:00
- Post Title: F1 Manager 2000 compression

just to not leave the post unanswered, some days ago I gave a look at that file and at the executable of the game but nothing, I found no matches with known algorithms or references to known algorithms in them
P.S.: uhmmm in reality not much known, I have verified those dictionary based I reversed in some games and something else which I don't remember
## Post #3
- Username: Elbereth
- Rank: VVIP member
- Number of posts: 21
- Joined date: Thu Jun 26, 2003 10:44 pm
- Post datetime: 2009-05-26T15:43:09+00:00
- Post Title: F1 Manager 2000 compression

Thanks for the feedback.
