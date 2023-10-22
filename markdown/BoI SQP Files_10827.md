## Post #1
- Username: TheMathDoc
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2013 11:57 pm
- Post datetime: 2013-10-01T20:43:23+00:00
- Post Title: BoI SQP Files

Hello!

I know this is a somewhat older game, but I've been doing some work on it for the purposes of learning how to reverse archive formats. The game is Battle of the Immortals, and the file extension is .sqp. 

What I've figured out so far: 
The file looks something like

Header
---unknown----
zeroes
----blocks----

Where the blocks section is a consecutive list of file entries grouped into blocks of variable size.  I've written a small program which can summarize the blocks section no problem.

My issue is with the unknown section that comes right after the opening 32 byte header. It looks like a bunch of gibberish to me, but I have strong reason to believe that this is where the file name information is stored. I've also read online that they aren't stored in the archive as plaintext but instead as hashes, which is making decompressing or decrypting the section very difficult for me. I've tried some basic XOR decryption using various keys without much luck, but I'm kind of flailing in the dark when it comes to key size and content. 

Anyways if anyone here wants to help me out and take a whack at it, I would be very grateful. Since I'm really trying to learn here, I'm also very interested in how you manage to figure it out.

I'm attaching a sample file "Others.sqp". The unknown section spans bytes 0x20 to 0x1114A0. I've also included my program output detailing the block section.

Thanks in advance!

File: [https://www.dropbox.com/s/9chmdlb328ma7 ... output.zip](https://www.dropbox.com/s/9chmdlb328ma775/Other.output.zip)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-05T10:19:33+00:00
- Post Title: BoI SQP Files

The archives modified MPQ (Mo'PaQ) format written by Mike O'Brien used in several of Blizzard Entertainment's games.

Header and Entries looks :

```
{
    DWORD dwID;					// MPQ\x1A
    DWORD dwHeaderSize;
    DWORD dwArchiveSize;
    DWORD dwHashTablePos;
    DWORD dwBlockTablePos;
    DWORD dwHashTableSize;	 // Shifted to << 4
    DWORD dwBlockTableSize;	// Shifted to << 4 (Unshifted value used as -> dwTotalFiles)
    SHORT wBlockSize;
    SHORT wFormatVersion;
};

struct TSQPHash
{
    DWORD dwNull;		 // Always 0
    DWORD dwIndex;		// Index for Block Table = dwIndex * 16 & 0xFFFFFFFF
    DWORD dwName1;		// Hash (part A)
    DWORD dwName2;		// Hash (part B)
};

struct TSQPBlock
{
    DWORD dwFilePos;
    DWORD dwFlags;		// 0x80000200 (MPQ_FILE_EXISTS + MPQ_FILE_COMPRESS) ???
    DWORD dwCSize;
    DWORD dwFSize;
};
```


Some values shifted by << 4. Hash table differently filled by 0xFFFFFFFF (-1) and 0xFFFFFFFE (-2)

SQP have 2 blocks. First block contained only hashes of file name, second block contained info about offset, size, compressed size and .ect.
Here my decryptor for SQP files, also can dump tables (hashes and entries) and hasher (string to hash). Source code included.

```
        SQPDecrypt <szFileName>

[Example]
        SQPDecrypt Other.sqp
```


```
        SQPHasher <szText>

[Example]
        SQPHasher ../data/slk.string
```

[Here](http://www.sendspace.com/file/orbhwz) founded file names.
[SQP_Decrypt_Hasher_0.1.rar](https://xentaxbackup.github.io/file/6669_SQP_Decrypt_Hasher_0.1.rar)
## Post #3
- Username: TheMathDoc
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2013 11:57 pm
- Post datetime: 2013-10-07T13:41:51+00:00
- Post Title: BoI SQP Files

Ekey,

Thanks a bunch! Do you mind sharing how you got the info? I'm fairly interested in the process behind this as well.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-07T21:35:45+00:00
- Post Title: BoI SQP Files

> Reply from TheMathDoc
>
> Ekey,

Thanks a bunch! Do you mind sharing how you got the info? I'm fairly interested in the process behind this as well.
Info about what?
## Post #5
- Username: TheMathDoc
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2013 11:57 pm
- Post datetime: 2013-10-08T12:03:00+00:00
- Post Title: BoI SQP Files

I was interested in the process behind how you were able to determine the workings of the format. Did you find it out somewhere else? Were you using a disassembler or just attacking the format without one?
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-08T12:48:51+00:00
- Post Title: BoI SQP Files

> Reply from TheMathDoc
>
> I was interested in the process behind how you were able to determine the workings of the format. Did you find it out somewhere else? Were you using a disassembler or just attacking the format without one?
Yep i use disassembler for reversing. [here](http://www.progamercity.net/game-files/1607-release-desqp-sqp-archive-packer-unpacker.html) simple sqp unpacker but outdated. Don't contain new file names hashes.
## Post #7
- Username: TheMathDoc
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2013 11:57 pm
- Post datetime: 2013-10-08T12:59:36+00:00
- Post Title: BoI SQP Files

In that case, can you recommend any good tutorials for learning about reversing formats via a disassembler? So far I've been working through [http://thelegendofrandom.com/blog/sample-page](http://thelegendofrandom.com/blog/sample-page). 

Obviously I'm not expecting to be able to pull this stuff off overnight, but I would appreciate a nudge in the right direction. Thanks again for all your help.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-09T18:17:26+00:00
- Post Title: BoI SQP Files

[here](http://tuts4you.com/download.php?list.19) you can found all what you need
## Post #9
- Username: TheMathDoc
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2013 11:57 pm
- Post datetime: 2013-10-09T18:35:22+00:00
- Post Title: BoI SQP Files

Well I better get cracking! Thanks again for all the help.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-09T21:57:39+00:00
- Post Title: BoI SQP Files

Btw: i updated info about SQP structure (see my 1st post)
