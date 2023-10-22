## Post #1
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-10T18:52:26+00:00
- Post Title: help indentifying a mystery format

Hello, I am working on a format from the game Operation Darkness for 360.  
I am wondering if I describe it someone might realize it sounds familiar and can share some info.  (will describe at bottom of post) This format is complex and robust enough that I am thinking it is not custom to this game but probably for some 3d modeling software or tools pipeline (or some engine).  The files hold models, textures, animations, and shader info.

I have got most of the way through the format so I know how its layed out but the trouble is the format doesn't use offsets or anything to seek to a resource you want, so you have to account for everything which is placed backtoback and eventualy you will get to that resource you want.  



Here is a description of the format.
---------------------------------------------------
overall file structure is main header, bunch of string tables and data lists, then back to back raw buffers at the end(the buffers have no headers, headers for the buffers are up in the data lists)


heres some detail (i use dw to mean 32bit int)
----------------------------------------

file starts with a small header which has
dwSize dwCount dwSize dwCount dwSize dwCount  etc
dwSize is the size of a section and dwCount is how many items is in that section (these header items are not in the same order as the sections appear in the file)

the funny thing is the file also holds sections that are not accounted for in the header, these sections begin with a dwSize dwCount instead of having that info in the header

I would say this is not a very well designed/organized format.



-first section is a string table usually has about 300 strings in it

-second section is another string table that has about 5 strings in it
(the file has 5 different string tables each of which is stored in a different way! very sloppy)  one might have num items then array of lengths then array of strings, another might just have array of strings each with the length before the characters, another might have an array of null terminated strings with no lengths stored, etc)


-3rd section is a data list, each item references a string for the name of the entry (might be ucVertexArray  or ucVertexShaderConstant, etc, and has 0 or more sub entries, a sub entry is 3 16bit shorts

-4rth section is a string table with one string "System"
-5th section is a string table with names which represent shader entities i think, like Texture,Vertex,Matrix,user1,user2,user3,user4,etc

-6rth section is another data list, that is one of two types, a simple type and a more complex type.  the simple type references an item from the last datalist, a complex type has a buffer length, possibly a string references from the string table, and other unknown data

-7th section is a list of 16bit shorts which are indexes to the last datatable.
this list has more items then the last datatable so many items are repeated.

-8th and last section is the one I am working on now (the most difficult) (following this section is the raw databuffers)

this section has a bunch of record entries. somewhere in each entry is an index to that last list of shorts, which is in index to the last datalist...

a record entry starts with a record type (a number like 37,50,24,34,etc) then a length of the record.  one record type i understand is the texture one, it has a dds header in it, a link to the string table for the name of the file, and other data.  but there is no offset to the texture buffer!  so i think you need to read the buffers for each record in order and assume the next buffer will be whereever the file pointer is at when you finishing reading the last one.  This means i need to understand every single record type in the file! i cant just skip over them because i need to understand how long its buffer is. and some record types have no buffer. there is about 30 different record types and its hard to figure out what some of them are.


Does this seem familiar to anyone?

Thanks.
## Post #2
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-11T07:36:45+00:00
- Post Title: help indentifying a mystery format

upon further work i have a better description of the format
------------------------------------
1 [file header]
2 
3 
4 
5  each 5 is a header for the corresponding 6
6  each field info object has a list of field_definitions which has an index to field type strings (4) and a size of the field type
7  these are the ones that link to a raw data buffer (some of them anyways)
8 
9 
10 [master object list which references list of objects)  10 is a list of indexes to 7, there are more 10s than 7s so many 7s are in fact repeated in this list
11  each record has a list of fields, it has an index to 6 which has the field info type and size for each field (field examples: matrix, vector3, int, memoryobjectref, objectref, entry in name table, etc.)
12 [raw data buffers]


 records (11) link to (10) which in turn links to (7) and some (7)s are called memoryReferences which will have a databuffer and others are called objectReferences which have no data buffer and link to (6 possibly)

the raw buffers(12) appear in the order of the (10) list


Anyone seen this format?
## Post #3
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-22T16:16:44+00:00
- Post Title: help indentifying a mystery format

Finally figured this one out.
## Post #4
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-06-23T00:33:41+00:00
- Post Title: help indentifying a mystery format

Awesome, anything special about it?
## Post #5
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-23T18:08:20+00:00
- Post Title: help indentifying a mystery format

Well by this one I mean this format, not the particular model.
The format is used for levels, objects, and models.
