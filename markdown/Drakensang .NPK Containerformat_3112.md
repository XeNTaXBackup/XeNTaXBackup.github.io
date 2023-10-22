## Post #1
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2008-08-02T16:51:39+00:00
- Post Title: Drakensang .NPK Containerformat

hey guys, this game is out since a few days in germany now and i've been trying to rip and reinject textures into the bigfiles...with SOME success

the folder structure is like this:

```

02.08.2008  18:29    <DIR>          .
02.08.2008  18:29    <DIR>          ..
05.07.2008  20:02        16.674.816 drakensang.exe
02.08.2008  13:06    <DIR>          export
05.07.2008  17:24     1.020.211.374 export.npk
01.08.2008  17:10     1.020.187.932 export_1.npk
05.07.2008  17:25     1.020.947.992 export_2.npk
05.07.2008  17:26       542.653.179 export_3.npk
01.08.2008  17:05    <DIR>          in

```


the .npk get loaded one after another like in quakeengine games, then the export folder is checked for files as an override (atleast i think so)  

anyway on to the good stuff... when i opened one of the .npks with my hex editor i saw... READABLE FILESNAMES -> AWESOME... no compresion or encryption is used as far as i can tell 

i copied some dds textures to a new file and edited them, then imported them back in:


ingame:
[](http://img231.imagevenue.com/img.php?image=73569_draken01_122_447lo.jpg)

inventory:
[](http://img148.imagevenue.com/img.php?image=73571_draken02_122_624lo.jpg)

ingame2:
[](http://img198.imagevenue.com/img.php?image=73577_draken03_122_497lo.jpg)

skin:
[](http://img215.imagevenue.com/img.php?image=73583_drakentex_122_176lo.jpg)

ii'd like to browse the whole bigfiles... this is what i've figured out so far:

the .npk files contain a simple structure like this (i used export_3.npk for testing):

0KPN = file header
export_RID = export folder (the one that already exists in the game dir)
textures_RID = textures folder under export folder
then follows: _location_04_elementsELIF im not sure if this is another folder or just an identifier cause the folders end with _RID (=DIR backwards) normally...

ANYWAY!

shortly after that comes moorbrueck_mausoleum_putz_bump.dds the first filename 
and after that ELIF(end of filename terminator i think)
4 bytes further @offset 00000089 the value is 1398256 in unsigned integer, when i extract the moorbrueck_mausoleum_putz_bump.dds (starts at offset FD16) the filesize is 1.398.256 Bytes woohoo!   

and im kinda stuck there now 

i have cut the first few mb of the export_3.npk here for someone else to check out, it contains the first too dds textures (atleast i hope so lol)

heres the package: [http://www.zippyshare.com/v/11596093/file.html](http://www.zippyshare.com/v/11596093/file.html)

i hope that i made atleast SOME sense... im not good at this stuff... but learning
## Post #2
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2008-08-05T17:19:48+00:00
- Post Title: Drakensang .NPK Containerformat

i think they use a version from their nebula engine which is open source. you should take a look at.

[http://nebuladevice.cubik.org/](http://nebuladevice.cubik.org/)
## Post #3
- Username: jaycenornin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 28, 2007 7:07 am
- Post datetime: 2009-04-16T00:12:24+00:00
- Post Title: Drakensang .NPK Containerformat

I'm downloading Nebula right now to see if it comes with a packer/unpacker. What other news might there be in this area?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-16T02:37:08+00:00
- Post Title: Drakensang .NPK Containerformat

the format seems very simple here is a quick look I took at it.
[](http://xs.to/xs.php?h=xs538&d=09163&f=npk_format201.jpg)
## Post #5
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-04-16T20:58:01+00:00
- Post Title: Drakensang .NPK Containerformat

To modify something in DRAKENSANG, just extract the NPK's, edit and save your files into the correct path. Then the game will load these files first. (Tested with version from 09/2008)
## Post #6
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-16T22:13:43+00:00
- Post Title: Drakensang .NPK Containerformat

There is actually a whole modding community for this game.
The company themselves released an extractor for these archives.
[http://mods.jo-ge.net/dsa4/dl/nnpktool.zip](http://mods.jo-ge.net/dsa4/dl/nnpktool.zip)

and the website that tells how to use this.
[http://forum.dtp-entertainment.com/view ... 63&t=11985](http://forum.dtp-entertainment.com/viewtopic.php?f=63&t=11985)

```
#include <stdio.h> # include <stdio.h>
#include <direct.h> # include <direct.h>



struct NPKheader struct NPKheader
{ (
char sig[8]; char sig [8];
unsigned int dataoffset; unsigned int dataoffset;
}sHeader; ) sHeader;

struct NPKsubheader struct NPKsubheader
{ (
char sig[4];//_RID //ELIF //DEND char sig [4 ];//_ RID / / ELIF / / DEND
unsigned int id; unsigned int id;
unsigned int offset; unsigned int offset;
unsigned int size; unsigned int size;
unsigned short len; unsigned short len;
char *name; char * name;
}sSubHeader; ) sSubHeader;

int main(int argc,char **argv) int main (int argc, char ** argv)
{ (
char sig[5]; char sig [5];
FILE *f; FILE * f;
printf("Drakensang NPK files unpacker by Bourn v1.0\n"); printf ( "Drakensang NPK files unpacker by Bourn v1.0 \ n");
if(argc!=2||(GetFileAttributes(argv[1])==DWORD(-1))) if (argc! = 2 | | (GetFileAttributes (argv [1]) == DWORD (-1)))
{ (
printf("Usage: UNPNPK <filename>\n"); printf ( "Usage: UNPNPK <filename> \ n");
system("pause"); system ( "pause");
return 0; return 0;
} )
f=fopen(argv[1],"rb"); f = fopen (argv [1], "rb");
if(!f) if (! f)
return 1; return 1;
fread(&sHeader,sizeof(NPKheader),1,f); fread (& sHeader, sizeof (NPKheader), 1, f);
while(ftell(f)<sHeader.dataoffset) while (ftell (f) <sHeader.dataoffset)
{ (
fread(sig,sizeof(char),4,f); fread (sig, sizeof (char), 4, f);
sig[4]=0; sig [4] = 0;
if(!strcmp(sig,"_RID")) if (! strcmp (sig, "_RID"))
{ (
fread(&sSubHeader.id,sizeof(unsigned int),1,f); fread (& sSubHeader.id, sizeof (unsigned int), 1, f);
fread(&sSubHeader.len,sizeof(unsigned short),1,f); fread (& sSubHeader.len, sizeof (unsigned short), 1, f);
//int ftell0=ftell(f); / / int ftell0 = ftell (f);
char *name=new char[sSubHeader.len+1]; char * name = new char [sSubHeader.len +1];
fread(name,sSubHeader.len,1,f); fread (name, sSubHeader.len, 1, f);
name[sSubHeader.len]=0; name [sSubHeader.len] = 0;
mkdir(name); mkdir (name);
chdir(name); chdir (name);
printf("Create directory: %s\n",name); printf ( "Create directory:% s \ n", name);
delete [] name; delete [] name;
} )
else if(!strcmp(sig,"ELIF")) else if (! strcmp (sig, "ELIF"))
{ (
fread(&sSubHeader.id,sizeof(unsigned int),1,f); fread (& sSubHeader.id, sizeof (unsigned int), 1, f);
fread(&sSubHeader.offset,sizeof(unsigned int),1,f); fread (& sSubHeader.offset, sizeof (unsigned int), 1, f);
fread(&sSubHeader.size,sizeof(unsigned int),1,f); fread (& sSubHeader.size, sizeof (unsigned int), 1, f);
fread(&sSubHeader.len,sizeof(unsigned short),1,f); fread (& sSubHeader.len, sizeof (unsigned short), 1, f);
char *name=new char[sSubHeader.len+1]; char * name = new char [sSubHeader.len +1];
fread(name,sSubHeader.len,1,f); fread (name, sSubHeader.len, 1, f);
name[sSubHeader.len]=0; name [sSubHeader.len] = 0;
FILE *fl=fopen(name,"wb"); FILE * fl = fopen (name, "wb");
if(fl) if (fl)
{ (
char *buf=new char[sSubHeader.size]; char * buf = new char [sSubHeader.size];
int curpos=ftell(f); int curpos = ftell (f);
fseek(f,sSubHeader.offset+sHeader.dataoffset+8,SEEK_SET); fseek (f, sSubHeader.offset + sHeader.dataoffset +8, SEEK_SET);
fread(buf,sSubHeader.size,1,f); fread (buf, sSubHeader.size, 1, f);
fwrite(buf,sSubHeader.size,1,fl); fwrite (buf, sSubHeader.size, 1, fl);
fclose(fl); fclose (fl);
fseek(f,curpos,SEEK_SET); fseek (f, curpos, SEEK_SET);
delete [] buf; delete [] buf;
} )
printf("Create file: %s\n",name); printf ( "Create file:% s \ n", name);
delete [] name; delete [] name;
} )
else if(!strcmp(sig,"DNED")) else if (! strcmp (sig, "DNED"))
{ (
fread(&sSubHeader.id,sizeof(unsigned int),1,f); fread (& sSubHeader.id, sizeof (unsigned int), 1, f);
chdir(".."); chdir ("..");
} )
else if(!strcmp(sig,"ATAD")) else if (! strcmp (sig, "ATAD"))
{ (
fread(&sSubHeader.size,sizeof(unsigned int),1,f); fread (& sSubHeader.size, sizeof (unsigned int), 1, f);
} )
} )
fclose(f); fclose (f);
system("pause"); system ( "pause");
return 0; return 0;
} )
```
