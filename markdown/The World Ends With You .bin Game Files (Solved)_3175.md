## Post #1
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-10-03T17:57:20+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-04-22T10:37:48+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-04-27T18:20:14+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

At least I'd like to hear why I got rejected.
## Post #4
- Username: McCuñao
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-28T08:05:32+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

You know, I think you did not get rejected at all. The problem is probably that no-one has found a solution yet. This is usually the case, and especially with encrypted/compressed files of unknown origin it is a rather difficult task. So someone downloads the files, takes the time to look at it, fails to find a solution and then just waits for others to come with an answer. 

Perhaps we should make it a common policy to at least acknowledge that you try to work on it and reply. So the person that asks for help knows he or she is heard.
## Post #5
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-04-28T09:31:11+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

Thanks for the answer.
## Post #6
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-05-08T14:54:51+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

Got some new intel from this guy:

> long    4 bytes   = offset of each file (add with 0x20) //did not understand the comment, 0x20 is 32, header size for values 1 2 and 3 is 32. So value 4 is the start of the header for each file?
>
> (add with 0x20 ) is mean , you need to add 0x20 to value at that offset. e.g. in file 'Grp_Tutoial.bin' at offset 0x28 has value = 0xA00000 , you need to reverse byte to 0x000000A0 then add 0x20 to that value so you 'll get 0xC0 that mean first pack file 'll locate at offset 0xC0 , so far at offset 0x2C 'll tell you that the first file has size = 0x1480 bytes. Similarly, at offset 0x30 add 0x20 to its value , 0x1520 + 0x20 = 0x1540 that means the 2nd file is locate at 0x1540
## Post #7
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-05-30T12:05:21+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

Any progress?
## Post #8
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-06-29T13:14:00+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

Situation solved thanks to other people I managed to talk about. Admins can close this topic.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-29T14:02:14+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

Ok, so what was the solution? We can't close if we don't have the solution.
## Post #10
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-06-29T14:10:24+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

This format wasn't a Graphics format, but actually a Game Archive stuff, as it was a Game Archive. Can't say anything about the solution, as it's not public yet. Sorry.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-29T14:16:31+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

> Reply from McCuñao
>
> This format wasn't a Graphics format, but actually a Game Archive stuff, as it was a Game Archive. Can't say anything about the solution, as it's not public yet. Sorry.

Oh it's like that, is it? You come here for help and if people had given you the answer you'd be more than happy to take it for granted, while you now keep the solution secret to others? I don't like this.
## Post #12
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-06-29T14:29:27+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

I'm not keeping it secret because I like to troll around, sorry, I'm keeping it secret because the team where this program belongs to has not said anything about releasing yet. I'm sure that the tool will be released to public, and I'll try to make them do so, but until then, you guys asked me a lot of patience, and I put that on, now I'm asking you the exact same thing, but on a smaller scale.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-29T14:38:53+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

As long as people don't pay us, they'll have to wait until we have time to figure out all formats. You know as well as I do that you can't expect anyone to help you out for free. And still, we do this all for free. So please don't complain. 

If the others who are working on a tool want to have first release, so be it. We don't care about tools, we just want to have the format description.
## Post #14
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-06-29T14:49:10+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

I'm not the one who started complaining, but I'll try to see what can I do about it, as I just received the final tool, not the data from the creator. All the hints I currently have were already published here.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-29T14:57:28+00:00
- Post Title: The World Ends With You .bin Game Files (Solved)

Allright.
## Post #16
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-06-29T18:21:10+00:00
- Post Title: Re: The World Ends With You .bin Game Files (Solved)

Alrighty, here's the stuff that the coder sent me to publish:

> _______________________________________________________________________________________________
>
>     FORMATO PACK por Barracuda - 15 Jun 2009
>
> _______________________________________________________________________________________________
>
> 
>
>  Todos los datos son Little Endian.
>
>  Todos los datos excepto el índice, se encuentran en bloques con un tamaño fijo de 32 bytes.
>
>  El índice se encuentra en bloques con un tamaño fijo de 64 bytes.
>
> 
>
>  Un archivo pack (por llamarle de algún modo), consta de tres secciones, cabecera,índice y
>
>  datos. La cabecera tiene un tamaño fijo de 32 bytes. El índice está compuesto por estructuras
>
>  de 8 bytes, y tiene un tamaño mínimo  de 64 bytes (8 estructuras). O sea, si el número de 
>
>  estructuras es 1, el índice tendrá espacio para 8, teniendo 7 estructuras vacías, si el número
>
>  de estructuras fuese 9, el índice tendría espacio para 16, teniendo 7 vacías.
>
> 
>
>  Cabecera - 32 bytes (un bloque)
>
> 
>
>  offset tamaño     descripción
>
>  ------ -------    -----------
>
>  0-3    4  bytes - identificador en ascii 'pack'
>
>  4-7    4  bytes - número máximo de archivos que podría contener en el pack (multiplicado por 8 = tamaño del índice)
>
>  8-11   4  bytes - tamaño de la sección de datos
>
>  12-15  4  bytes - ¿relleno? siempre está a 0X00
>
>  16-31  16 bytes - siempre a 0x00, relleno para cumplir el límite de 32 bytes.
>
> 
>
>  Índice - Tamaño variable, mínimo 64 bytes (un bloque, capacidad para 8 archivos)
>
> 
>
>  offset tamaño     descripción
>
>  ------ -------    ----------- 
>
>  32-35  4  bytes - offset del archivo desde el offset del índice
>
>  36-39  4  bytes - tamaño del archivo
>
>  ..............  - Esta estructura se repite hasta completar el tamaño del índice.
>
> 
>
>  Datos - Los datos comienzan en el offset indicado por la primera entrada en el índice
>
>          y están almacenados en bloques de 32 bytes. Si el tamaño de un archivo no es
>
>          múltiplo de 32, el último bloque de ese archivo se rellenará con 0x00 hasta 
>
>          completar los 32 bytes.
>
> 
>
> _______________________________________________________________________________________________
A translation made by myself just so you guys try to avoid Engrish:

> _______________________________________________________________________________________________
>
>     PACK FORMAT by Barracuda - June 15, 2009
>
> _______________________________________________________________________________________________
>
> 
>
>  All the data is in Little Endian encoding.
>
>  Every data except the index, is located in blocks with a fixed size of 32 bytes.
>
>  Index is found in blocks with a fixed size of 64 bytes.
>
> 
>
>  A pack file (just to put a name to it), has three sections, header, index and data. Header has a fixed 32 bytes size. Index is made by 8 bytes structures, and has a minimum size of 64 bytes (8 structures). Which means, if the number of structures is 1, the index will have space for 8, having 7 empty structures, and if the number of structures is 9, the index would have room for 16, 7 of them empty.
>
> 
>
>  Header - 32 bytes (one block)
>
> 
>
>  offset size       description
>
>  ------ -------    -----------
>
>  0-3    4  bytes - ascii identifier 'pack'
>
>  4-7    4  bytes - maximum number a pack file can contain (multiply per 8 = size of the index)
>
>  8-11   4  bytes - size for the data section
>
>  12-15  4  bytes - ¿padding? always at 0X00
>
>  16-31  16 bytes - always at 0x00, padding in order to achieve the 32 bytes limit.
>
> 
>
>  Index - Variable size, 64 bytes minimum (one block, capacity for 8 files)
>
> 
>
>  offset size       description
>
>  ------ -------    ----------- 
>
>  32-35  4  bytes - file offset starting from the index offset
>
>  36-39  4  bytes - file size
>
>  ..............  - This structure repeats until the index size is filled.
>
> 
>
>  Data - Data start at the indicated offset at the first entry on the index and they are
>
>          stored in 32 bytes blocks. If the file size is not a multiple of 32, the last block of
>
>          that file will be filled with 0x00 until 32 bytes are completed.
>
> 
>
> _______________________________________________________________________________________________
'Ave fun.
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-29T19:16:23+00:00
- Post Title: Re: The World Ends With You .bin Game Files (Solved)

Muchas gracias, senor!
