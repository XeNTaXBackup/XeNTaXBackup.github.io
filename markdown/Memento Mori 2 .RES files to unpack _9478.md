## Post #1
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-15T00:57:11+00:00
- Post Title: Memento Mori 2 .RES files to unpack ?

There is a file name: MEMENTO2_loc_ge.res
This is the german version of the game.

And there more res files in the main installation directory of the game.
Im pretty sure this file MEMENTO2_loc_ge.res or maybe other .res file contain the text of the game the language.
I want to translate it.


Is there any way to unpack this files ?
I searched forums and found some topics about Memento Mori the first one but all the tools i tried on memento mori 2 didnt work.
I tried: Centauri Production Resource File 3.10 Manager
Its unpacking i see the bar on the bottom moving in the end i see a plux(+) and i can see a lot of files like: D000X0000....something very long wich is .OGG 
And i cant do anything with it and cant open or see .OGG files.

Then i tried the program: CenResTool101.exe
Tried to open the file: MEMENTO2_loc_ge.res but it didnt do anything.

Can someone create a program to unpack memento mori 2 .res files ? So i can retrive the text language to translate it and then to put back to the same place the text back ?
I dont know how to do it.

Thank you very much.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-17T00:49:36+00:00
- Post Title: Memento Mori 2 .RES files to unpack ?

this should be posted in archive research - [viewforum.php?f=10](http://forum.xentax.com/viewforum.php?f=10)

```

# QuickBMS script by WRS (xentax.com)
# http://aluigi.altervista.org/quickbms.htm

comtype zlib

idstring "\x43\0\x65\0\x6E\0\x74\0\x61\0\x75\0\x72\0\x69\0\x20\0\x50\0\x72\0\x6F\0\x64\0\x75\0\x63\0\x74\0\x69\0\x6F\0\x6E\0\x20\0\x52\0\x65\0\x73\0\x6F\0\x75\0\x72\0\x63\0\x65\0\x20\0\x46\0\x69\0\x6C\0\x65\0\x20\0\x33\0\x2E\0\x32\0\x30\0\x0A\0\x0A\0\0\x0" # "Centauri Production Resource File 3.20\xa\xa"

get fcount long
get eocdpntr long
get null long

goto eocdpntr

for f = 0 < fcount
  get fname unicode
  getdstring unknown 8
  get fflag long
  get foffset long
  get funknown long
  get fsize long
  get fzsize long
  get fhash long # not crc32
  
  if fflag = 0
    log fname foffset fsize
  elif fflag = 2
    clog fname foffset fzsize fsize
  else
    print "Flag %fflag% for file %fname%"
  endif
  
next f

```
## Post #3
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-17T02:25:30+00:00
- Post Title: Memento Mori 2 .RES files to unpack ?

Working Thank you
## Post #4
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-17T04:36:19+00:00
- Post Title: Memento Mori 2 .RES files to unpack ?

How can i pack back the file and directories to the original .res file ?

I just added attached an image file that show the directories i want to add them back.
The file i extracted them from is: MEMENTO2.res
I tried to use the import file and your script but it didnt work i selected the directory on my hard disk new folder (6) but instead import back the directories and sub and files inside it just went inside one of the directories in the image and did nothing.



Could you please build a script for importing the directories and files back ? Use your other script to extract this file to see what i mean and then try to import it all back.

Here is a link for the file: [http://www.mediafire.com/?vpa8movb77z5804](http://www.mediafire.com/?vpa8movb77z5804)
[resmem2.jpg](https://xentaxbackup.github.io/file/5675_resmem2.jpg)
## Post #5
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-17T06:08:59+00:00
- Post Title: Memento Mori 2 .RES files to unpack ?

WRS ,

The importing is not working good. The importing is starting but then in some places im getting errors.
Attached image so you can see .

After 3-4 times it stop say currupd something like that and its not creating the big file.
Just i can quit.

And i didnt change this files.
I changed one file: TEXTS_GE.DB
It was from a smaller memnto 2 res file it was TEXTS_EN.DB
So i copied it to the directory of the big res extracted file and changed renamed it to TEXTS_GE.DB

But all this errors im getting have nothing to do with this file i guess.

Maybe you could look over the script or the errors like in the image i attached ? Im getting like 3-4 errors like that on some files but not on the TEXTS_GE.DB

Thanks.
[error.jpg](https://xentaxbackup.github.io/file/5680_error.jpg)
## Post #6
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-18T00:39:18+00:00
- Post Title: Memento Mori 2 .RES files to unpack ?

Can someone please take a look at my problem ? Can reimport back the directories and files.
