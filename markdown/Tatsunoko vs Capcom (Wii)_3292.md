## Post #1
- Username: TheLeader
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 09, 2009 4:47 am
- Post datetime: 2009-01-12T12:24:36+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-01-13T16:35:04+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

I did watch them too a while ago..yes, the archive structure is very easy but files seems to be compressed with ZLS but without a debugger, or at least a decompressed file........
## Post #3
- Username: TheLeader
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 09, 2009 4:47 am
- Post datetime: 2009-01-15T09:28:54+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-16T20:54:15+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

I believe Naruto uses the same fpk files as this game and naruto actually includes all the un compressed files as well as the compressed files. It even includes the bat file they use to compress them into one file all that was missing was fpack.exe.
Hope this helps I can upload the files in both forms if it would help crack this format.
## Post #5
- Username: TheLeader
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 09, 2009 4:47 am
- Post datetime: 2009-01-17T18:28:03+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

It couldn't hurt. I take it that format was never figured out either?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-17T21:02:59+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: TheLeader
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 09, 2009 4:47 am
- Post datetime: 2009-01-17T21:37:39+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-28T03:05:31+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

Here is the file format

```
2nd set of bytes total files in archive
4 unkown bytes
4 unkown bytes
starts with file name string 32 bytes long remove trailing 0's
4 dummy bytes
4 bytes file offset
4 bytes compresed size
4 bytes un compressed file size
string file name
```

The values to get location and size are not reversed like in most other archives.
now we just need to identify the compression.
Here is a compressed and un compressed set of files.
[http://www.MegaShare.com/822675](http://www.MegaShare.com/822675)
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-03T13:08:08+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

so this is a big edian archive and also here is some more info on the compression.
[http://www.emutalk.net/showthread.php?p=421720](http://www.emutalk.net/showthread.php?p=421720)
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-21T17:34:23+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-02T01:42:19+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

this extracts the files can anyone help with the decompression lzss almost seems to work.

```
endian BIG
get FILES long
get NULL long
get ARCSIZE long
endian little
for i = 0 < files
getdstring NAME 0x24
endian BIG
get OFFSET long
get ZSIZE long
get SIZE long
endian little
log NAME OFFSET ZSIZE
#comtype lzss
#clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-08T21:39:36+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

Here is the ram dump of a psp during the fpk unpacking which is the same as in this game.
searching for fpk I found an interesting section that may provide some light on this format.
[http://delete.MegaShare.com/?id=1036749 ... 7f533b36e3](http://delete.MegaShare.com/?id=1036749&DELETE_FILE=089f3e9afc28e2d4d7ef587f533b36e3)
and here is a small section attached here that seemed to stand out.
[function.rar](https://xentaxbackup.github.io/file/2088_function.rar)
## Post #13
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T12:13:56+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

Unfortunately most people use a custom LZSS with some parameters changed, this might be the cause that it doesn't fully work.

EDIT: Indeed this is a quite strange encoding.

EDIT2: This drives me round the bend, I can't recognize anything.

Obviously a 1 encodes a literal byte.
No matter how offset and length are encoded (tried with 1,2,3 bytes), it doesn't match for the following bytes.
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-09T14:02:03+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

@rheini
do you have a list of games that use modified lzss parameters (N, F and THRESHOLD) and these customized values?
if I'm not in error I saw only a customized N value one time (I don't remember well) but for the rest I have never seen games which use the LZSS algorithm with customized F and THRESHOLD values.
## Post #15
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T14:07:42+00:00
- Post Title: Tatsunoko vs Capcom (Wii)

Settlers 2 games use custom LZSS, think it was N=10,F=4,T=3 (which is totally senseless, since it wastes 2 bits)
You can not only change those parameters.
Sometimes the bit semantic is changed (0 representing a literal byte) and offset/length encoding differs.
Furthermore how the sliding window is initialized is arbitrary.

EDIT: Also this file here, what a strange reference:

3 literal bytes, followed by a reference. But it can only reference to the single '-' read before.
If FF F8 4B is the reference 0A and 3F would have to be literals, but 3F is not present in the decompressed data.
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-09T14:23:25+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

N=10? so basically the data is almost uncompressed :)
other games other than s2?
## Post #17
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T14:31:40+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

Oh I meant the number of bits used for encoding.
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-09T14:34:12+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

another interesting thing I noticed some months ago about LZSS.
the following is the latest source of Okumura 
[http://oku.edu.mie-u.ac.jp/~okumura/compression/lzss.c](http://oku.edu.mie-u.ac.jp/~okumura/compression/lzss.c)
but even if you change the EI, EJ and P parameter to make them compatible with the classical algorithm it's not compatible at all.
## Post #19
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T14:40:57+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

Oh yeah I forgot that one.
There the bit is saved immediately followed by the data. This is the original LZSS.
Grouping 8 (16) bits together to ease reading and writing is more common though.
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-09T14:54:04+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

uhmm maybe I'm wrong but I think that the lzss.c version with N, F and THRESHOLD (like [http://dev.gameres.com/Program/Other/LZSS.C](http://dev.gameres.com/Program/Other/LZSS.C)) is the oldest one, or at least is the most used.
## Post #21
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T15:01:36+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

I was refering to the paper ("Data compression via textual substitution")
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-10T01:08:12+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

There is an ida Pro 5.2 plugin to load the game executable for this game would this make it possible to see the compression used in this game if I upload the main exe and the plugin?
## Post #23
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2009-07-09T08:26:01+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

The .fpk file use PRS compress method(a little change). This is the fpk tool:

```
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <string.h>
#include <fcntl.h>
#include <sys/stat.h>
#include <dirent.h>


typedef unsigned int   u32;
typedef unsigned short u16;
typedef unsigned char  u8;


int endian=1;

u32 BE32(u32 data)
{
	if(endian)
		return ( (data<<24) | ((data<<8)&0x00ff0000) |
				((data>>8)&0x0000ff00) | (data>>24) );
	else
		return data;
}

int blen;
int fbuf;

/* PRS get bit form lsb to msb, FPK get it form msb to lsb */
int get_bits(int n, char *sbuf, int *sptr)
{
	int retv;

	retv = 0;
	while(n){
		retv <<= 1;
		if(blen==0){
			fbuf = sbuf[*sptr];
			//if(*sptr<256) 
				//{ printf("[%02x] ", fbuf&0xff); fflush(0); }
			(*sptr)++;
			blen = 8;
		}

		if(fbuf&0x80)
			retv |= 1;

		fbuf <<= 1;
		blen --;
		n --;
	}

	return retv;
}

int uncomp(char *dbuf, int dlen, char *sbuf, int slen)
{
	int sptr;
	int dptr;
	int i, flag, len, pos;

	blen = 0;

	sptr = 0;
	dptr = 0;
	while(sptr<slen){
		flag = get_bits(1, sbuf, &sptr);
		if(flag==1){
			//if(sptr<256) 
				//{ printf("%02x ", (u8)sbuf[sptr]); fflush(0); }
			if(dptr<dlen)
				dbuf[dptr++] = sbuf[sptr++];
		}else{
			flag = get_bits(1, sbuf, &sptr);
			if(flag==0){
				len = get_bits(2, sbuf, &sptr)+2;
				pos = sbuf[sptr++]|0xffffff00;
			}else{
				pos = (sbuf[sptr++]<<8)|0xffff0000;
				pos |= sbuf[sptr++]&0xff;
				len = pos&0x07;
				pos >>= 3;
				if(len==0){
					len = (sbuf[sptr++]&0xff)+1;
				}else{
					len += 2;
				}
			}
			//if(sptr<256) 
				//{ printf("<%08x(%08x): %08x %d> \n", dptr, dlen, pos, len); fflush(0); }
			pos += dptr;
			for(i=0; i<len; i++){
				if(dptr<dlen)
					dbuf[dptr++] = dbuf[pos++];
			}
		}
	}

	return dptr;
}


void mkdir_p(char *dname)
{
	char name[256];
	char *p, *cp;

	strcpy(name, dname);

	cp = name;
	while(1){
		p = strchr(cp, '/');
		if(p==NULL)
			p = strchr(cp, '\\');
		if(p==NULL)
			break;

		*p = 0;
		//mkdir(name, 0777);
		mkdir(name);
		*p = '/';
		cp = p+1;
	};
}

int process_file(char *infname)
{
	FILE *fp, *outfp;
	char *fname, *dptr, *buf, *dbuf;
	int i, fcnt, flen, dlen, offset;
	char dname[256], tname[256], *p;

	p = strchr(infname, '.');
	if(p==NULL)
		return -1;
	if(strcmp(p+1, "fpk"))
		return -1;

	printf("process file %s ...\n", infname);

	/* Open fpk file */
	fp = fopen(infname, "rb");
	if(fp==NULL){
		printf("Can't open %s!\n", infname);
		return -1;
	}

	/* Make directory */
	strcpy(dname, infname);
	p = strchr(dname, '.');
	if(p)
		*p = '_';
	//mkdir(dname, 0777);
	mkdir(dname);

	fseek(fp, 0, SEEK_END);
	flen = ftell(fp);
	fseek(fp, 0, SEEK_SET);

	buf = (char*)malloc(flen);
	fread(buf, flen, 1, fp);
	fclose(fp);

	if(*(short*)(buf+0)==0){
		endian = 1;
	}else{
		endian = 0;
	}

	fcnt = BE32(*(int*)(buf+4));
	for(i=0; i<fcnt; i++){
		dptr = buf+0x10+i*0x30;
		fname = dptr;
		flen = BE32(*(int*)(dptr+0x28));
		offset = BE32(*(int*)(dptr+0x24));
		dlen = BE32(*(int*)(dptr+0x2c));
		printf("offset: %08x flen: %08x length: %08x file: %s\n", offset, flen, dlen, fname);

		dbuf = malloc(dlen+256);
		uncomp(dbuf, dlen, buf+offset, flen);


		sprintf(tname, "%s/%s", dname, fname);
		mkdir_p(tname);

		outfp = fopen(tname, "wb");
		if(outfp==NULL){
			printf("Can't open output file %s !\n", tname);
		}else{
			fwrite(dbuf, dlen, 1, outfp);
			fclose(outfp);
		}
		free(dbuf);
	}

	free(buf);
	return 0;
}

////////////////////////////////////////////////////////////////////////////

int process_dir(char *dname)
{
	DIR *pdir;
	struct dirent *d;
	struct stat statbuf;
	char fname[256];
	int i, ndir;

	/* process file */
	memset(&statbuf, 0, sizeof(statbuf));
	stat(dname, &statbuf);
	if((statbuf.st_mode&S_IFMT) != S_IFDIR){
		return process_file(dname);
	}

	/* open directory */
	pdir = opendir(dname);
	if(pdir==NULL){
		printf("Can't open directory <%s>\n", dname);
		return -1;
	}

	/* get number of files in dircetory */
	ndir = 0;
	while((d=readdir(pdir))){
		ndir++;
	}
	d = malloc(sizeof(struct dirent)*ndir);

	/* read dirent first */
	rewinddir(pdir);
	for(i=0; i<ndir; i++){
		memcpy(&d[i], readdir(pdir), sizeof(struct dirent));
	}

	/* process each files */
	printf("Enter directory <%s> ...\n", dname);
	for(i=0; i<ndir; i++){
		if( d[i].d_name[0]=='.' &&( d[i].d_name[1] =='\0' || (d[i].d_name[1] == '.' && d[i].d_name[2] == '\0') ))
			continue;

		if(dname[0]=='.'){
			sprintf(fname, "%s", d[i].d_name);
		}else{
			sprintf(fname, "%s/%s", dname, d[i].d_name);
		}
		process_dir(fname);
	}
	printf("Leave directory <%s> ...\n", dname);

	free(d);
	closedir(pdir);
	return 0;
}

int main(int argc, char *argv[])
{
	if(argc==1){
		return process_dir(".");
	}else{
		return process_dir(argv[1]);
	}
}

```
## Post #24
- Username: simple
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-09T10:02:45+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

THANK YOU SO MUCH 
here is a compiled exe for everyone.
[FPK extractor.rar](https://xentaxbackup.github.io/file/2182_FPK extractor.rar)
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-09T12:33:07+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

Don't you just love this forum ?  Another mystery solved.   Thanks all!
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-16T00:18:43+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

I found this crashing on some archives for some reason I was wondering if someone could help with this problem. Here are some archives it crashes on.
also is it possible for the program to offer an option to skip a file if it has trouble instead of closing down?
[http://www.MegaShare.com/1257504](http://www.MegaShare.com/1257504)
Thanks in advance to anyone who can help
## Post #27
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2009-09-11T17:44:23+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

Same here, also crashes on MHG 0000.fpk
## Post #28
- Username: simple
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Sep 29, 2007 6:52 am
- Post datetime: 2010-01-06T10:58:24+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

Sorry for the bump but I am wondering if someone can repost the compressed and uncompressed files of TvC again since the old links expired...

Thanks
## Post #29
- Username: fconb2
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 04, 2010 9:04 am
- Post datetime: 2011-04-20T13:52:07+00:00
- Post Title: Re: Tatsunoko vs Capcom (Wii)

Late bump. How would I compile the compressor to exe (or, does anyone have the original exe)?
