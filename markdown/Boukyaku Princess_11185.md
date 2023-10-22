## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-02-03T02:25:44+00:00
- Post Title: Boukyaku Princess

Here's a flash-based online game.
It sends 60 MB worth of data to your machine, half of which are the game's resources.

The resources are stored in a proprietary archive, with the file table at the top, followed by the file data.
The table is compressed using deflate algo, and is straightforward once you decompress it.

The files are encrypted using a custom algorithm.
I found the algorithm in one of the SWF files, but I'm unable to get it working properly myself.

This is the basic algorithm

```
2. Generate the key
3. Use the key to decrypt the data (using simple XOR)

```


The names you find in the file table are MD5-hashed versions of the original name, and mean nothing for the most part when it comes to decryption. It is only used by the program to grab the appropriate entry and return the data. What you need is the original name to feed to the key generator function.

The name of file is what you need to use as the key material. You can verify that MD5 hashing the name will give you the entry in the archive.

These are the functions that you will be using (I just took them from the source).

```
{
    var _loc_3:int = 0;
    var _loc_2:uint = 1234567;
    _loc_3 = 0;
    while (_loc_3 < param1.length)
    {
        
        _loc_2 = (param1.charCodeAt(_loc_3) + _loc_2) * 251;
        _loc_3 = _loc_3 + 1;
    }
    return _loc_2;
}// end function

private static function Decrypt(param1:ByteArray, param2:uint) : void
{
    var _loc_3:int = 0;
    _loc_3 = 0;
    while (_loc_3 < param1.length)
    {
        
        param1[_loc_3] = param1[_loc_3] ^ param2 & 255;
        param2 = param2 * 977 + 1;
        _loc_3 = _loc_3 + 1;
    }
    return;
}// end function


```


I've included my own implementation of an exporter with the package, but I don't think it works (or at least, the output I'm getting is junk). It's written in Ruby.

Here are some files: [http://www.mediafire.com/download/xwnr3 ... incess.zip](http://www.mediafire.com/download/xwnr3dff53aa983/Boukyaku+Princess.zip)

When you are testing your code, use "1.swf" as the input filename.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-04T11:02:39+00:00
- Post Title: Boukyaku Princess

Done. Here my crappy code. Copy files in tool folder.

```
        BPTest <pFileIn> <pFileOut>

[Example]
        BPTest 1.swf 1_dec.swf
```


Source code included. Enjoy 
[BPSWFDecryptor_0.1.rar](https://xentaxbackup.github.io/file/6997_BPSWFDecryptor_0.1.rar)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-02-05T04:27:36+00:00
- Post Title: Boukyaku Princess

Hmm I wonder where I went wrong with the algorithm  
It's really straightforward too.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-05T09:47:40+00:00
- Post Title: Boukyaku Princess

> Reply from finale00
>
> Hmm I wonder where I went wrong with the algorithm  
It's really straightforward too.
Well encrypted SWF's have header

```
{
 	DWORD pCRC; // ???
 	DWORD pFlag; // ???
 	DWORD pDataOffset; // Offset with encrypted SWF data ( + 0xC < header size )
}
```
