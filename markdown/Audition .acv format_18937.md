## Post #1
- Username: Jakup
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 08, 2014 10:32 pm
- Post datetime: 2018-10-16T10:34:35+00:00
- Post Title: Audition .acv format

Hey guys!
Right now im working on a unpacker for Audition.
The game is using a archive format inside the acv. (zlib)
Its encrypted with blowfish.
I found out the ACV Header Key and the decryption key.
To unpack the files i need to know the offset etc but i couldnt find them yet.

Example:

> unsigned char acv4key[] =
>
> {
>
> 	0xB5, 0xA5, 0xC0, 0xCC, 0xC5, 0xB8, 0xC6, 0xC4,
>
> 	0xC0, 0xCF, 0x20, 0xBF, 0xA3, 0xC5, 0xA9, 0xB8,
>
> 	0xB3, 0xC6, 0xAE, 0x2F, 0xB5, 0xF0, 0xC5, 0xA9,
>
> 	0xB8, 0xB3, 0xC6, 0xAE, 0x20, 0xC5, 0xB0, 0x00, 
>
> 	0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 
>
> 	0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00,
>
> 	0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00
>
> };
>
> 
>
> unsigned char acvkey4header[] =
>
> {
>
> 	0x41, 0x43, 0x56, 0xB5, 0xA5, 0xC0, 0xCC, 0xC5,
>
> 	0xB8, 0xC6, 0xC4, 0xC0, 0xCF, 0x20, 0xC7, 0xEC,
>
> 	0xB4, 0xF5, 0x20, 0xC5, 0xB0, 0x00, 0x00, 0x00,
>
> 	0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 
>
> 	0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 
>
> 	0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00,
>
> 	0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00
>
> };

This is the example how i call it:

> int main(int argc, char * argv[] )
>
> {
>
> BlowFish::CBlowFish crypt( &acvkey4header[0], 56);
>
> 	FILE *  in = fopen("077.acv","rb");
>
> 	int filecount=0;
>
> 	unsigned short csize;
>
> 	unsigned char * bufin  = new unsigned char[1024*1024];
>
> 	unsigned char * bufout = new unsigned char[1024*1024];
>
> 	//fread( bufin, 4, 1, in);
>
> 	fread( &filecount, 4, 1, in );
>
> 	fread( &csize, 2, 1, in );
>
> 
>
> 	fread( bufin, csize, csize, in );
>
> 	crypt.Decrypt( bufin, bufout, csize );
>
> 	uncompress(bufin, (uLongf *)&filecount, bufout, 1024*1024 );
>
> 
>
> 	fclose(in);
But its completly wrong since i dont know how to get filecount csize and bufin.

I attached a acv file here what is using the new acv format.
The acv header is FF 03 00. 
Maybe i got the keys wrong but i reversed them.
Maybe someone is smart and could help me out.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-16T13:57:41+00:00
- Post Title: Audition .acv format

> Reply from Jakup
>
> 
I attached a acv file here what is using the new acv format.
Forgot your attachment?
## Post #3
- Username: Jakup
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 08, 2014 10:32 pm
- Post datetime: 2018-10-16T15:04:24+00:00
- Post Title: Audition .acv format

oh im sorry

[https://www.file-upload.net/download-13 ... 7.acv.html](https://www.file-upload.net/download-13352198/077.acv.html)

idk how i can do that in quickbms
