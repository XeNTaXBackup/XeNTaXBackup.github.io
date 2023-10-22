## Post #1
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-01-05T10:38:54+00:00
- Post Title: Dat file from nexusTK

Could you please look at the *.Dat archives from [NexusTK](http://www.nexustk.com/). 
Well, this file is not coming from the latest version. (mine is ver 5.33). 
I need to extract the data for creating some MAPs  
[Tile.dat1.zip](https://xentaxbackup.github.io/file/559_Tile.dat1.zip)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-05T15:19:06+00:00
- Post Title: Dat file from nexusTK

Please test this DAT tool  
[Nexus_DAT_Tool.rar](https://xentaxbackup.github.io/file/560_Nexus_DAT_Tool.rar)
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-05T15:24:12+00:00
- Post Title: Dat file from nexusTK

Source code   

```
    Copyright 2005 Luigi Auriemma

    This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation; either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program; if not, write to the Free Software
    Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307 USA

    http://www.gnu.org/licenses/gpl.txt
*/

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#ifdef WIN32
    #include <direct.h>

    typedef unsigned char   u_char;
    typedef unsigned short  u_short;
    typedef unsigned int    u_int;
    #define PATHSLASH   '\\'
#else
    #include <unistd.h>
    #include <sys/stat.h>

    #define strnicmp    strncasecmp
    #define stristr     strcasestr
    #define PATHSLASH   '/'
#endif



#define VER     "0.1"
#define SIGN    "nexus" "\x01\x00\x00"



void nexus_seek(FILE *fd, u_int off);
void nexus_read(FILE *fd, void *data, int len);
void nexus_extract(FILE *fd, u_char *fname, int len);
void nexus_dec(u_char *data, int len);
void nexus_alternative_extract(FILE *fd, u_char *fname, u_char method);
void create_dir(u_char *name);
void std_err(void);



u_char  xor;



int main(int argc, char *argv[]) {
    FILE    *fd;
    u_int   i,
            tmp,
            off,
            nameoff,
            diroff,
            totlen,
            tot,
            len;
    int     listonly = 0,
            decode_only = 0;
    u_short nlen;
    u_char  type,
            boh,
            *fname,
            *buff,
            *folder = ".",
            *pattern = NULL;

    setbuf(stdout, NULL);

    fputs("\n"
        "Nexus files extractor "VER"\n"
        "by Luigi Auriemma\n"
        "e-mail: aluigi@autistici.org\n"
        "web:    http://aluigi.altervista.org\n"
        "\n", stdout);

    if(argc < 2) {
        printf("\n"
            "Usage: %s [options] <file.DAT>\n"
            "\n"
            "Options:\n"
            "-l       list files without extracting them\n"
            "-d DIR   the folder where the files will be extracted (default %s)\n"
            "-p PAT   extracts only the files containing PAT, like -p .ogg for example\n"
            "-x       decodes the entire file without extracting the data (useless)\n"
            "\n",
            argv[0], folder);
        exit(1);
    }

    argc--;
    for(i = 1; i < argc; i++) {
        switch(argv[i][1]) {
            case 'l': listonly = 1;         break;
            case 'd': folder   = argv[++i]; break;
            case 'p': pattern  = argv[++i]; break;
            case 'x': decode_only = 1;      break;
            default: {
                printf("\nError: wrong command-line argument (%s)\n\n", argv[i]);
                exit(1);
                } break;
        }
    }

    printf("- open file %s\n", argv[argc]);
    fd = fopen(argv[argc], "rb");
    if(!fd) std_err();

    printf("- enter in folder %s\n", folder);
    if(chdir(folder) < 0) std_err();

    buff = malloc(0xffff + 1);
    if(!buff) std_err();

    xor = 0x2a;

    nexus_read(fd, buff, 8);
    if(memcmp(buff, SIGN, sizeof(SIGN) - 1)) {
        fputs("\n"
            "Alert: the file is not a valid nexus_00.DAT file, want you decode it using\n"
            "       the second method?\n"
            "       Remember that this other method doesn't give readable results, it is\n"
            "       implemented only for compatibility reasons and is really used by the\n"
            "       game (example: nexus_11.dat)\n"
            "       (y/N): ", stdout);
        fflush(stdin);
        tmp = fgetc(stdin);
        if((tmp | 32) == 'y') {
            sprintf(buff, "%s.decoded", argv[argc]);
            printf("- output file: %s\n", buff);
            nexus_alternative_extract(fd, buff, 1);
        }
        fclose(fd);
        return(0);
    }

    if(decode_only) {
        sprintf(buff, "%s.decoded", argv[argc]);
        printf("- output file: %s\n", buff);
        nexus_alternative_extract(fd, buff, 0);
        return(0);
    }

    nexus_read(fd, &tmp, 4);            // zero
    nexus_read(fd, &totlen, 4);         // total package length
    nexus_read(fd, &tmp, 4);            // don't know
    nexus_read(fd, &boh, 1);            // don't know

    nameoff = ftell(fd);

    for(tot = 0; !feof(fd); tot++) {
        nexus_read(fd, &type, 1);       // 0 for files, 1 for folders
        nexus_read(fd, &nlen, 2);       // length of the filename
        nexus_read(fd, buff, nlen);     // filename

        if(listonly) {
            buff[nlen] = 0;
            if(!pattern || (pattern && stristr(buff, pattern))) {
                printf("  %s\n", buff);
            }
        }

        if(type) {
            nexus_read(fd, &tmp, 4);    // offset
            nexus_read(fd, &tmp, 4);    // don't know (length???)
            nexus_read(fd, &tmp, 4);    // don't know
            off = len = 0;
        } else {
            nexus_read(fd, &off, 4);    // offset
            nexus_read(fd, &len, 4);    // length
        }

        nexus_read(fd, &boh, 1);        // don't know

        if((off + len) >= totlen) break;
    }

    if(listonly) {
        printf("- %u files listed\n\n", tot);
        return(0);
    }

    diroff = ftell(fd);
    fname  = buff;

    for(i = 0; i < tot; i++) {
        nexus_seek(fd, nameoff);

        nexus_read(fd, &type, 1);
        nexus_read(fd, &nlen, 2);

        if(type) {
            nexus_read(fd, buff, nlen);
            buff[nlen++] = PATHSLASH;
            buff[nlen] = 0;
            fname = buff + nlen;

            nexus_read(fd, &tmp, 4);
            nexus_read(fd, &tmp, 4);
            nexus_read(fd, &tmp, 4);
        } else {
            nexus_read(fd, fname, nlen);
            fname[nlen] = 0;
            nexus_read(fd, &off, 4);
            nexus_read(fd, &len, 4);
        }

        nexus_read(fd, &boh, 1);

        nameoff = ftell(fd);

        if(type) continue;
        if(pattern && !stristr(fname, pattern)) continue;

        create_dir(buff);
        printf("  %s\n", buff);

        nexus_seek(fd, diroff + off);
        nexus_extract(fd, buff, len);
    }

    fclose(fd);
    printf("- %u files extracted\n\n", i);
    return(0);
}



void nexus_seek(FILE *fd, u_int off) {
    fseek(fd, off, SEEK_SET);
    xor = 0x2a + (off * 0x55);
}



void nexus_read(FILE *fd, void *data, int len) {
    fread(data, len, 1, fd);
    nexus_dec(data, len);
}



void nexus_extract(FILE *fd, u_char *fname, int len) {
    FILE    *fdo;
    int     rlen;
    static u_char   buff[16384];

    fdo = fopen(fname, "wb");
    if(!fdo) std_err();

    for(rlen = sizeof(buff); len; len -= rlen) {
        if(len < rlen) rlen = len;
        fread(buff, rlen, 1, fd);
        nexus_dec(buff, rlen);
        fwrite(buff, rlen, 1, fdo);
    }

    fclose(fdo);
}



void nexus_dec(u_char *data, int len) {
    u_char  *limit;

    for(limit = data + len; data < limit; data++) {
        *data ^= xor;
        xor += 0x55;
    }
}



void nexus_alternative_extract(FILE *fd, u_char *fname, u_char method) {
    FILE    *fdo;
    int     len;
    u_char  *p,
            *l;
    static u_char   buff[16384];

    fdo = fopen(fname, "wb");
    if(!fdo) std_err();

    fseek(fd, 0, SEEK_SET);

    if(method) {
        fread(&xor, 1, 1, fd);
        fwrite(&xor, 1, 1, fdo);
        method = 0xAA;
    } else {
        xor = 0x2a;
        method = 0x55;
    }

    while((len = fread(buff, 1, sizeof(buff), fd))) {

        l = buff + len;
        for(p = buff; p < l; p++) {
            *p ^= xor;
            xor += method;
        }

        fwrite(buff, len, 1, fdo);
    }

    fclose(fdo);
}


void create_dir(u_char *name) {
    u_char  *p,
            *l;

    p = name;
    for(;;) {
        l = strchr(p, '\\');
        if(!l) {
            l = strchr(p, '/');
            if(!l) break;
        }
        *l = 0;
        p = l + 1;
#ifdef WIN32
        mkdir(name);
#else
        mkdir(name, 0755);
#endif
        *l = PATHSLASH;
    }
}



void std_err(void) {
    perror("\nError");
    exit(1);
}
```
## Post #4
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-01-06T01:57:13+00:00
- Post Title: Dat file from nexusTK

I already try it before I post the request here  , that program is for nexus the Jupiter Incident not for Nexus The Kindom of the Winds. Any others tool?
## Post #5
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-06T15:17:35+00:00
- Post Title: Dat file from nexusTK

Sure ... Download Game Extractor 1.5507... Watto writing plugin for this game
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2006-01-06T17:00:50+00:00
- Post Title: Dat file from nexusTK

Anyway if somebody is curious, the format is the following:

4 bytes = number of files (the final is NULL, just a delimiter due to the method used for calculating the file size (next_offset - prev_offset))

for each file:
4 bytes = absolute offset
X bytes = filename, NULL terminated

little endian format.
## Post #7
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-01-06T18:09:21+00:00
- Post Title: Dat file from nexusTK

> Reply from Bugtest
>
> Anyway if somebody is curious, the format is the following:

4 bytes = number of files (the final is NULL, just a delimiter due to the method used for calculating the file size (next_offset - prev_offset))

for each file:
4 bytes = absolute offset
X bytes = filename, NULL terminated

little endian format.
Actually, it seems like the length for the filenames are fixed:

```

// for each file:
04 - absolute offset
13 - filename (null terminated, filled with junk)
```

Anyway, here's a MexCom BMS-script for this archive. 

```
Get FILENUM Long 0 ;
Math FILENUM -= 1 ;
For F = 1 To FILENUM ;
SavePos FOFFSETX 0 ;
Get FOFFSET Long 0 ;
GetDString FNAME 13 0 ;
SavePos NEXTFILE 0 ;
Get FSIZE Long 0 ;
Math FSIZE -= FOFFSET ;
Log FNAME FOFFSET FSIZE FOFFSETX 0 ;
GoTo NEXTFILE 0 ;
Next F ;
```

[DAT.rar](https://xentaxbackup.github.io/file/566_DAT.rar)
## Post #8
- Username: coolmib
- Rank: VIP member
- Number of posts: 19
- Joined date: Wed Jan 04, 2006 11:59 am
- Post datetime: 2006-01-07T01:52:58+00:00
- Post Title: Dat file from nexusTK

Thank you everyone !!  I really appreciate  this
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-07T06:54:57+00:00
- Post Title: Dat file from nexusTK

Awesome, PXR
## Post #10
- Username: splinterz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 14, 2011 1:20 am
- Post datetime: 2014-07-22T05:24:55+00:00
- Post Title: Dat file from nexusTK

hi,

can u help me how to extract dat files from nexustk ver 7.0.3

[NexusTK703single.exe](http://files.kru.com/NexusTK/Client/Single/NexusTK703single.exe)
## Post #11
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2017-09-21T18:54:13+00:00
- Post Title: Dat file from nexusTK

Figured that I would offer my Python equivalent.

First the quick-n-dirty implementation (handles 1 DAT file -- like PXR's QuickBMS script):

Usage:

```
./script.py <input_dat_file> <out_directory>
```


```

import array
import os
import sys

int_read = array.array('I')
_FILE_NAME_LENGTH = 13

in_file = sys.argv[1]
out_dir = sys.argv[2]

dat_file_handler = open(in_file, 'rb')
int_read.fromfile(dat_file_handler, 1)

num_of_files = int_read.pop() - 1
next_file_location = 0

for k in range(num_of_files):
    int_read.fromfile(dat_file_handler, 1)
    data_location = int_read.pop()

    name = dat_file_handler.read(13).split(b'\0', 1)[0].decode()
    next_file_location = dat_file_handler.tell()

    int_read.fromfile(dat_file_handler, 1)
    size = int_read.pop() - data_location

    fn = os.path.join(out_dir, name)
    inner_file_handler = open(fn, 'wb')

    dat_file_handler.seek(data_location)
    inner_file_handler.write(dat_file_handler.read(size))

    inner_file_handler.close()
    dat_file_handler.seek(next_file_location)

dat_file_handler.close()
```

I also attached a more organized version that allows for an input_directory instead of a single file. It also has verbose printing of what is going on.

Usage:

```
./dat_extractor.py <input_directory> <output_directory>
```

I pointed the attached script to the NexusTK "Data" directory and it extracted the following types from the dat files that were there:

```
.map
.dna
.dsc
.eft
.epd
.epf
.lst
.mid
.mp3
.pal
.pcx
.str
.tbl
.wav
```

Cheers!
[dat_extractor.zip](https://xentaxbackup.github.io/file/13332_dat_extractor.zip)
## Post #12
- Username: Sittah
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 27, 2018 9:24 am
- Post datetime: 2018-02-27T04:29:46+00:00
- Post Title: Dat file from nexusTK

Cheers, Thank you for your source.

I apply to your source code dat_extractor.py.

And I use like this -- > dat_extractor.py c:\Test_Indir C:\Test_Outdir

This is responce (Result) 

-- >> 

Traceback (most recent call last):
  File "C:\dat_extractort.py", line 94, in <module>
    main(sys.argv)
  File "C:\dat_extractor.py", line 83, in main
    inner_file_handler.write(dat_file_handler.read(size))
ValueError: read length must be positive or -1


I thought about this error .. I try little effort.

 * Original Code

            # Read File Size (minus offset)
            int_read.fromfile(dat_file_handler, 1)
            size = int_read.pop() - data_location

* Change Code

            # Read File Size (minus offset)
            int_read.fromfile(dat_file_handler, 1)
            size = int_read.pop() + data_location


It is excute !  But... This have other problem.

Traceback (most recent call last):
  File "C:\dat_extractor.py", line 94, in <module>
    main(sys.argv)
  File "C:\dat_extractor.py", line 75, in main
    inner_file_handler = open(fn, 'wb')
FileNotFoundError: [Errno 2] No such file or directory: 'C:\\Test_Outdir\\'

Hmm...  I don't know why this problem has occurred.

Do you have key for this problem ? ~ T. T
## Post #13
- Username: DizzyThermal
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Aug 30, 2017 8:20 am
- Post datetime: 2018-02-27T17:03:18+00:00
- Post Title: Dat file from nexusTK

Hi, does the input directory contain the NexusTK Dat files that you are trying to extract?

I've added this functionality to TKViewer:
[https://github.com/DizzyThermal/TKViewer](https://github.com/DizzyThermal/TKViewer)

File > Extract > Data Files (*.dat)

Let me know if this works for you
