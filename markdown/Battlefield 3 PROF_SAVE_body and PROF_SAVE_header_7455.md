## Post #1
- Username: Hyperz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 14, 2010 12:45 am
- Post datetime: 2011-10-04T13:42:40+00:00
- Post Title: Battlefield 3: PROF_SAVE_body and PROF_SAVE_header

Hi 

I was wondering if anyone has looked into the BF3 PROF_SAVE_body/PROF_SAVE_header files yet (located in  the folder C:\Users\<username>\Documents\Battlefield 3 Open Beta\settings\)? I've been trying to parse PROF_SAVE_body but I'm having a bit of difficulty understanding what the meaning of certain bytes are   . Here's what I understand about the files format so far:

PROF_SAVE_header (8 bytes):

```
uint8 header[8]; // no idea what these are for
```


PROF_SAVE_body (1024000 bytes):

```
struct name_value_pair[?] // array of what seems to be key-value pairs
{
    // sometimes there are 1 or more uint32 values that come before value_type
    // no idea what they are for or how to predict them during parsing
    uint32 value_type; // not 100% sure, seems to indicate the data type of the value in value_str
    uint32 name_length;
    char name_str[name_length];
    uint32 value_length;
    char value_str[value_length];
};
uint8 unknown[?]; // lots of null bytes, not sure if they are there just to fill 1024000 bytes

```


The biggest problem for me so far is figuring out why sometimes the name_value_pair struct has additional data coming before the value_type field. Does anyone have more information on this file type and/or how to read/write it? I have attached a copy of these 2 files. Thanks in advance  .
[settings.zip](https://xentaxbackup.github.io/file/4756_settings.zip)
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2011-11-19T14:27:37+00:00
- Post Title: Battlefield 3: PROF_SAVE_body and PROF_SAVE_header

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: godzcheater
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 04, 2012 3:37 am
- Post datetime: 2012-10-13T21:52:33+00:00
- Post Title: Battlefield 3: PROF_SAVE_body and PROF_SAVE_header

Well the first 4 bytes of each if an MC02 hash, I think. Its that on xbox(well in an MC02 package) but never seen on PC before.
In fairly sure the int in header is the could of property collections, not 100% tho.

body
4 byte hash
for(System.Int32 i =0;i<headerint;i++)
{
int32 property count
for < property count
{
int32 type
int32 namelength
string[length] name//null terminated aswell
int32 value length
value//usually string then casted to type, except binary, thats just byte[]
}
}
null padded

type
1 float(string)
2 byte(string)
3 ...
4 bool(string(int))
5 binary
## Post #4
- Username: P@S@f
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 23, 2011 7:33 pm
- Post datetime: 2017-08-05T00:26:47+00:00
- Post Title: Battlefield 3: PROF_SAVE_body and PROF_SAVE_header

I'm sorry for asking in such old thread, but I'm interested in format of this file as well.
Anyone know how to calculate this hash value for PROF_SAVE_body?
If I change something and keep old hash - game reset all progress to default.
