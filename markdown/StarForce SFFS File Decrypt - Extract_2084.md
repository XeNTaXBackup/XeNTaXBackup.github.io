## Post #1
- Username: Infinity
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Sep 09, 2006 11:42 pm
- Post datetime: 2006-09-09T15:47:40+00:00
- Post Title: StarForce SFFS File Decrypt - Extract

SFFS consists of 2 major parts: the container files that contain the game
content and a filesystem filter driver (sfvfs02.sys) that handles all file-io.
when a game has sffs'ed files and uses some file-io api like CreateFile, the
sffs filterdriver sees this request and handles it if needed. that way, sffs is
totally transparent to the game, since it never knows if the data is coming from
real file api or from the sffs filterdriver. during sf initialization, the
sf-process registers itself as a sffs process in a processid list, maintained
from the filterdriver. part of that registration are the names of the
containerfiles, the process uses and an application key, that is needed to
decrypt headerinfos. note that sffs itself is completly vm-free.

```
--------------------------------------------------------------------------------
containerlayout:

4byte 'SFFS'

4byte version (0x00000001)

8byte number of files in the container (encrypted with application key)
      minimal number here is usually 65h, so its not real file count
      in some cases, more like index size

for each file (24bytes):
 16bytes md5 hash of filename (not encrypted, plz)
 8bytes index of fileheader (encrypted with filename)

for each fileheader (56bytes):
 8byte start of filecontent (encrypted with filename)
 48bytes fileinfo (timestamps, size, data position, encrypted)

filecontent.

// as you can see, the filename itself is key of some decryptions, so there is no
// way to extract a file without valid filename.



decryption
--------------------------------------------------------------------------------
to decrypt data, sffs uses a 0x1048byte big decryption key buffer. this key
buffer is always derrived from a key. sample (decryption of number of files
info):

BYTE keyBuf[0x1048];
makeKeyBuf(keyBuf, appKey, 8);
decryptBuf(keyBuf, header + 8, 8, 0, 0, 0);
DWORD64 numFiles = *(DWORD64 *)(header + 8);


to decrypt filecontents:
wchar_t nameCopy[1024];
wcscpy(nameCopy, name);		<------ name = name of file beeing accessed, relative to gamedir
wcsupr(nameCopy);

int nameLen = wcslen(nameCopy);
reverseName(nameCopy, nameLen);		<---- reverses the now uppercase name: GFX.GTL -> LTG.XFG

BYTE keyBuf[0x1048];
makeKeyBuf(keyBuf, nameCopy, nameLen * 2);	<---- as already mentioned, keyBuf is needed

first lets decrypt index of fileinfos:
ULARGE_INTEGER index;		<--- index is very same val as mentioned in header, but it was encrypted, remember?
index.QuadPart = header->index;
decryptBuf(keyBuf, &index, 8, 0, 0, 0);

LARGE_INTEGER fileInfoPos;
fileInfoPos.QuadPart = 0x10 + header->container->numFiles * 0x18 + index.QuadPart * 0x38;

SetFilePointer(containerFile, fileInfoPos.LowPart, &fileInfoPos.HighPart, FILE_BEGIN);

DWORD read;
BYTE fileInfo[0x38];
ReadFile(containerFile, fileInfo, 0x38, &read, NULL);
CloseHandle(containerFile);



now decryption of 0x38 fileinfo header (2 parts, to make it extra super duper secure):

decryptBuf(keyBuf, fileInfo, 0x38, 0, 0, 0);
for (DWORD i = 0; i < 0x38; i++)
	fileInfo[i] ^= appKey[i & 7];		<----- whoohoo
decryptBuf(keyBuf, fileInfo, 0x38, 0, 0, 0);

now fileInfos are decrypted and ready to use:

DWORD64 fileSize = *(DWORD *)(fileInfo + 8);

FILETIME writeTime;
writeTime.dwLowDateTime = *(DWORD *)(fileInfo + 32);
writeTime.dwHighDateTime = *(DWORD *)(fileInfo + 36);

decryption of filedata:

memcpy(outBuf, file->info->data + file->readPos, len);
DWORD64 containerPos = file->info->dataPos + file->readPos;
decryptBuf(file->info->keyBuf, outBuf, len, 0, (DWORD)containerPos, (DWORD)(containerPos >> 32));
file->readPos += len;

note: fileposition affects decryption
```


See source ( writen in C++ ) 
PS : Mr.Mouse i am KorNet , I forgot my password   
[SFFS_Decrypt_Scr.zip](https://xentaxbackup.github.io/file/851_SFFS_Decrypt_Scr.zip)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-11-01T00:00:36+00:00
- Post Title: StarForce SFFS File Decrypt - Extract

i don't know why, but i can't compile, can attach compiled version?
Thanks
## Post #3
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-11-02T17:30:07+00:00
- Post Title: StarForce SFFS File Decrypt - Extract

compiled version would be a killer toy!!

never found those nasty sffs unpacker.
## Post #4
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-11-09T14:30:47+00:00
- Post Title: StarForce SFFS File Decrypt - Extract

news about compiled version for brainless user??
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-11-21T23:36:03+00:00
- Post Title: StarForce SFFS File Decrypt - Extract

The only thing directly compileable here is the code within the "init" directory. The resulting program will, however, just extract resources from the StarForce software itself. You will mainly end up with the background images seen during disc validation, the drivers themselves and similar stuff.

This program cannot extract data from SFFS-formatted files. The code in the sffs directory is probably part of a routine performing this kind of work, but it is not directly usable in this form -- somebody would have to write an application around it.

Additionally, according to the description, you always need to know the names of the files you want to extract from SFFS archives beforehand, as the decryption process depends on these names. Thus, even if you built an application around the code snippets posted, you would still need to get a list of file names for decryption and extraction.

Also note that the information posted here is only part of what is floating around the net. There are more descriptions, but most of them refer to the virtual machine techniques employed by StarForce.
## Post #6
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-11-24T17:22:00+00:00
- Post Title: StarForce SFFS File Decrypt - Extract

useless in this state then...thanks.
