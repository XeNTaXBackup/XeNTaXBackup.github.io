## Post #1
- Username: WillWNTD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 15, 2022 3:54 am
- Post datetime: 2022-03-14T19:58:30+00:00
- Post Title: True Crime: New York City .DAT Language Files

Hi, i need some help to export and import the texts from .dat files. I tried to edit the texts via hex editor, but the game crashed. Can someone take a look at the file structure, please? If it is possible to create a tool. Thanks in advance!

Sample files:
[Eng.7z](https://xentaxbackup.github.io/file/21949_Eng.7z)
## Post #2
- Username: WillWNTD
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-14T21:16:27+00:00
- Post Title: True Crime: New York City .DAT Language Files

I have checked it and it seems that file format is this:

```

num_of_texts *
{
   4 bytes (uint32) - text CRC
   4 bytes (uint32) - text relative offset
}

num_of_texts *
{
   x bytes (char) - text + null
}
```


So if it's true what you said that game crashes after simple hex edit, then nothing can be done until someone will figure out how to calculate those CRC fields correctly.
## Post #3
- Username: WillWNTD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 15, 2022 3:54 am
- Post datetime: 2022-03-15T00:36:33+00:00
- Post Title: True Crime: New York City .DAT Language Files

Thanks for responding! I did some more tests, and in fact the game doesn't crash after hex edit, but the text spacing/formatting is wrong if the edited text has more or less characters than the original text. I took some screenshots:

[https://imgur.com/a/JCQdC4W](https://imgur.com/a/JCQdC4W)

Do u think it's possible to make a text tool?
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-03-15T01:03:46+00:00
- Post Title: True Crime: New York City .DAT Language Files

> Reply from ikskoks ↑Tue Mar 15, 2022 5:16 am at Tue Mar 15, 2022 5:16 am
>
> 
I have checked it and it seems that file format is this:
Code: Select all4 bytes (uint32) - base offset

num_of_texts *
{
   4 bytes (uint32) - text CRC
   4 bytes (uint32) - text relative offset
}

num_of_texts *
{
   x bytes (char) - text + null
}

So if it's true what you said that game crashes after simple hex edit, then nothing can be done until someone will figure out how to calculate those CRC fields correctly.
I don't think it is CRC.
its just pointers.
@op
its ps2 game?
## Post #5
- Username: WillWNTD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 15, 2022 3:54 am
- Post datetime: 2022-03-15T01:35:11+00:00
- Post Title: True Crime: New York City .DAT Language Files

Nop, it's the PC version.
## Post #6
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-03-15T17:24:02+00:00
- Post Title: True Crime: New York City .DAT Language Files

> Reply from ikskoks ↑Tue Mar 15, 2022 5:16 am at Tue Mar 15, 2022 5:16 am
>
> 
I have checked it and it seems that file format is this:
Code: Select all4 bytes (uint32) - base offset

num_of_texts *
{
   4 bytes (uint32) - text CRC
   4 bytes (uint32) - text relative offset
}

num_of_texts *
{
   x bytes (char) - text + null
}

So if it's true what you said that game crashes after simple hex edit, then nothing can be done until someone will figure out how to calculate those CRC fields correctly.

here how its work the file.

[](https://ibb.co/DQZgCnz)

You have take the baseoffset + 0x04 and sum with pointers of the photo above.

Example:

C0570000
LITTLE ENDIAN ALWAYS
000057C0 + 0X04 = 57C4 = first string
57C4 + 00 00 00 2F = 57F3

57F3 = second string

57C4 + 00 00 01 03 = 58C7

58C7 = third string

just keeping sum
BASEOFF + 0X04 + POINTERS.

as per you can see in the next image, to offset let us to the exactly begin of the second string.

[](https://ibb.co/ChMD0v2)

Here the bms script to extract the text individually as per pointers that i show above.
its kind useless but, it will be very easy to create a tool with these informations.

```
#rabatini (luke)

get baseoff long
xmath mainoff "(baseoff + 0x04)"
goto 0x10
get size long
math i = 0
string NAME p "%01x.txt" i
log name mainoff size
xmath filecount "(baseoff * 2)"
xmath entries "(filecount / 16)"
xmath entries "(entries - 1)"
goto 0x10


for rip = 1 to entries

get offset long
xmath offset "(mainoff + offset)"
get null long
savepos temp
get size long
xmath sizeking "(mainoff + size)"
xmath size "(sizeking - offset)"
get null long
goto temp
String FILENAME P "%rip%.txt"
if size == 0x741e4fec
get size asize
xmath size "(size - offset)"
log FILENAME offset size
endif
log FILENAME offset size

next rip



```


works on langtable.dat
i think is the main text.
