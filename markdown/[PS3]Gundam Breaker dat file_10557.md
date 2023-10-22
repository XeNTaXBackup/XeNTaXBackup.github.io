## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2013-06-30T04:37:33+00:00
- Post Title: [PS3]Gundam Breaker dat file

Hi
.dat extension with GDAT header from PS3 Gundam Breaker.
Help for .dat extension with GDAT header!!

Somebody can make a bms script for unpacking?
I've attached cut of the .dat files.
[http://www.mediafire.com/?iic1048l7qd61kp](http://www.mediafire.com/?iic1048l7qd61kp)
Any help would be greatly appreciated. 

Thanks.
## Post #2
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2013-07-08T14:25:14+00:00
- Post Title: [PS3]Gundam Breaker dat file

Can someone help me figure this out?
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2013-08-10T04:45:53+00:00
- Post Title: [PS3]Gundam Breaker dat file

As you can know, it's impossible to extract. because they were not interested
## Post #4
- Username: alon
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-08-10T11:43:31+00:00
- Post Title: [PS3]Gundam Breaker dat file

Well i made a quick rough script, anyone can edit it to perfection if they like but it does the job. It will extract the .DAT (GDAT) to .PCK files which can be then decompressed with the same script, the compression used is ZLIB.

If i helped press the thanks button!
Cheers.

```
# Also works on the .PCK
# Script v1.1
# By Gh0stblade!

endian big

#Header
get SIGN long			#"GDAT"
get FILES long			#File count

#If it's the GDAT container!
if SIGN == 0x47444154

#Filetable
for i = 0 < FILES
get UNK00 long			#???
get HASH long			#File hash?
get OFFSET long			#File offset.
get SIZE long			#File size.

#Set the filename
get NAME basename
string NAME += "_"
string NAME += i
string NAME += ".pck"

log NAME OFFSET SIZE		#Save the file
next i

else
#This is for the .pck

goto 0x0			#Reset the offset
get TYPE long			#File Extension
goto 0x80
getdstring ZTYPE 0x4		#Compression type

#Check if the compression type is valid!
if ZTYPE != "BILZ"
	print "Warning: Unknown Compression type! %ZTYPE%"
	cleanexit
else
	comtype unzip_dynamic	#Set the compression type
endif

get SIZE long			#Uncompressed size
get ZSIZE long			#Compressed size

#Set the name
get NAME basename
string NAME += "."
string NAME += TYPE

clog NAME 0x90 ZSIZE SIZE	#Decompress and store the file
endif

```
## Post #5
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2013-08-11T11:59:05+00:00
- Post Title: [PS3]Gundam Breaker dat file

> Reply from Gh0stBlade
>
> Well i made a quick rough script, anyone can edit it to perfection if they like but it does the job. It will extract the .DAT (GDAT) to .PCK files which can be then decompressed with the same script, the compression used is ZLIB.

If i helped press the thanks button!
Cheers.
I really appreciate what you're done for me
## Post #6
- Username: yiwang
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Apr 28, 2012 9:30 am
- Post datetime: 2014-12-30T14:49:25+00:00
- Post Title: [PS3]Gundam Breaker dat file

> Reply from alon
>
> Gh0stBlade wrote:Well i made a quick rough script, anyone can edit it to perfection if they like but it does the job. It will extract the .DAT (GDAT) to .PCK files which can be then decompressed with the same script, the compression used is ZLIB.

If i helped press the thanks button!
Cheers.

I really appreciate what you're done for me
pckHow to open？
[1.png](https://xentaxbackup.github.io/file/8398_1.png)
## Post #7
- Username: cosmos28
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 08, 2012 1:56 am
- Post datetime: 2015-09-13T19:36:26+00:00
- Post Title: [PS3]Gundam Breaker dat file

thanks for the script. I have also uncompressed tge pck files but i have no idea to convert the extracted files wich I assume that is hexadecimal data to obj.
Is there a way to get those files to obj?
thanks
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-14T06:45:06+00:00
- Post Title: [PS3]Gundam Breaker dat file

> Reply from cosmos28
>
> uncompressed tge pck filesdunno those

> Is there a way to get those files to obj?
>
> thanksdepends on the signature - if it's 00 6C 64 6D (' ldm') in .pck I'd say 'yes'.
## Post #9
- Username: cosmos28
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 08, 2012 1:56 am
- Post datetime: 2015-09-14T21:17:06+00:00
- Post Title: [PS3]Gundam Breaker dat file

Hi Shatokay2

unfortunately i dom't have the skills to know about what you ask 
I'm a texture artist and always looking for new gundam to texture.
If by any chance you manage to get the obj files I would really appreciate that.
Thanks for answering although
