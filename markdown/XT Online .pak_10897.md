## Post #1
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-10-23T04:00:25+00:00
- Post Title: XT Online *.pak

Official Site: [http://xt.ztgame.com/index.shtml](http://xt.ztgame.com/index.shtml)
Downloads: [http://download12.ztgame.com.cn/xt_clie ... 091713.exe](http://download12.ztgame.com.cn/xt_client_2013091713.exe)

Header: !PAK
Looks compressed？
Samples: [http://www62.zippyshare.com/v/39351838/file.html](http://www62.zippyshare.com/v/39351838/file.html)

could u try to extract the pak files???
[20131023115539.gif](https://xentaxbackup.github.io/file/6724_20131023115539.gif)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-23T17:02:19+00:00
- Post Title: XT Online *.pak

Well here small info

```
{
	DWORD	pID;		        // !PAK
	DWORD	pVersion;
	DWORD	pTotalFiles;
	DWORD	pTableOffset;
	DWORD	pTableSize;
	BYTE	 pComent[30];		// The author is Xuzhao(xuzhao@ztgame.com)
};
```


Table encrypted by 3DES (modified). Key initialized like this: generate MD5 from string xuzhao20041108 (hash uses as key = F2A237FD6D3FDDEE1DBC556335325511 + 6D3FDDEE1DBC5563, key length 24 bytes). Each entry size 64 bytes

```
{
   DWORD   pNameIndex;
   DWORD   pOffset;
   DWORD   pZSize;
   DWORD   pZSize2;
   BYTE    pMD5[16];
   DWORD   pSize;
   BYTE    pRealMD5[16];
   DWORD   pUnknown2;
   DWORD   pUnknown3;
   DWORD   pUnknown4;
};
```


```
pNamesOffset = PAKHeader.pTotalFiles * 64 + PAKEntry.pNameIndex;
```
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-23T23:19:40+00:00
- Post Title: XT Online *.pak

I hate Korean / Chinese games  Anyway job done.



PS: I dont test it on big PAKs. Let me know if tool stuck or show error's.

Download: See blow.
## Post #4
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-10-24T00:36:29+00:00
- Post Title: XT Online *.pak

> Reply from Ekey
>
> I hate Korean / Chinese games  Anyway job done.



PS: I dont test it on big PAKs. Let me know if tool stuck or show error's.

god job！！！have big pak extracted is ok,but get A bunch of empty byte file.

Samples:
[http://www15.zippyshare.com/v/40306392/file.html](http://www15.zippyshare.com/v/40306392/file.html)
[http://www15.zippyshare.com/v/55215826/file.html](http://www15.zippyshare.com/v/55215826/file.html)
[http://www15.zippyshare.com/v/14927275/file.html](http://www15.zippyshare.com/v/14927275/file.html)
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-24T06:46:20+00:00
- Post Title: XT Online *.pak

Fixed.
[XTPAKUnpacker_0.3.rar](https://xentaxbackup.github.io/file/6729_XTPAKUnpacker_0.3.rar)
## Post #6
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-10-24T14:34:32+00:00
- Post Title: XT Online *.pak

cool，Thanks ekey!
