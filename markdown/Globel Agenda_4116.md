## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-02-04T22:35:55+00:00
- Post Title: Globel Agenda

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-05T08:57:42+00:00
- Post Title: Globel Agenda

uhmm a bad format because it doesn't have a real format.
it's only a chunk based sequence of data composed by a zip file at the beginning and unknown content (probably encrypted with CryptEncrypt) from offset 0x34AC59.

so till offset 0x34AC59 you can extract all the files in that chunked zip archive simply adding the following lines:

```
    goto offset
```
in the loop of zip.bms and setting the "name" variable to "" because all the files have the name "zip".

but from that offset starts the encryption.
I have also tried to use the password "FA00CDF5-8D87-4a76-BEE1-D9E483220C13" but seems (judging the usage of wscat) that it's appended to a string passed to the Create.Cryptography function of the dll.
debugger's job
