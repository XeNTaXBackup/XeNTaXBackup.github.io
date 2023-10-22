## Post #1
- Username: Phantom Genius
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 16, 2014 9:34 pm
- Post datetime: 2015-08-04T09:38:56+00:00
- Post Title: help with .xcp format

hey guys iv been looking around for a way to extract .xcp format
please help!
its free dlc for Skullgirls xbox 360


0.02 MB

```
http://download.xbox.com/content/584111db/c979d158400cf48d18929086fd7c61d425bcd08e.xcp
```

or

```
http://www73.zippyshare.com/v/IXm6g9fU/file.html
```



upd:
this is extracted file from .xcp above (for compare)

```
http://www41.zippyshare.com/v/LS2KvuVi/file.html
```
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-08-09T12:19:36+00:00
- Post Title: help with .xcp format

These files are encrypted, and there are no publicly available tools to decrypt them.
## Post #3
- Username: Phantom Genius
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 16, 2014 9:34 pm
- Post datetime: 2015-08-12T14:35:27+00:00
- Post Title: help with .xcp format

> Reply from barti
>
> These files are encrypted, and there are no publicly available tools to decrypt them.

ah,
not good  

found some info:

```
confirmed working.

props to all the people in #360hrcpublic who were working on it and jester for showing us that the PIR was 44kb and not 52kb 

split the xcp into 3 peices
0-7FFD44CB
7FFD44CC-FFEEDB35
FFEEDB36-end of file

extract each peice:
offzip -a -1 reach1.xcp reach1 0
offzip -a -1 reach2.xcp reach2 0
offzip -a -1 reach3.xcp reach3 0
cut 44kb from reach1 folder 0000000000.dat (0-AFFF)
save as haloreach (no extension)
merge all 3 dat files
split merged file into 170,459,136 byte sized files. there should be 42
make sure first filename is Data0000
then rename all others (in order) ie: Data0001 Data0002
take Data00xx files and put them inside haloreach.data folder
put haloreach file (no extension) inside root folder
load god2iso and select the haloreach file (no extension)
create iso
extract contents from iso. 

done
```


```
offzip.exe -r -a test.xcp output 0
to extract the dat files. then using
copy /b "*.dat" "output.pirs"
to combine them into a single file. just looking for an indication if I am on the right track for when the file completes.
```
