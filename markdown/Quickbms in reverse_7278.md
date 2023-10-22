## Post #1
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-09-01T16:38:01+00:00
- Post Title: Quickbms in reverse?

Is it possible to encrypt a file and put it back into the archive, using Quickbms, if the decryption method is already known?

aluigi  was kind enough to decrypt EU files [here](http://forum.xentax.com/viewtopic.php?f=21&t=6041).

Is there any way to use the existing script to create an archiver?
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-02T13:35:02+00:00
- Post Title: Quickbms in reverse?

The script itself is a packer and unpacker.
Read the section in the readme on repacking. I think it mentions encryption, compression, chunk formats, and other stuff that should be important to note.
## Post #3
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-09-02T19:48:49+00:00
- Post Title: Quickbms in reverse?

Thanks! I found and followed the instructions.

The problem I'm having now is that after re-import, the original archive is not modified.

I successfully unpack files from an archive, modify them, and then re-import back, Quickbms says they've been re-imported, no errors.

But the archive is not modified, and when I extract the same files again into a different folder to check, I see original files...

I tried it on different files in different archives a few times, it always works like this.

Can anyone please tell me what I might be doing wrong here?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-03T20:18:05+00:00
- Post Title: Quickbms in reverse?

If you're using command-line, post the command you use.

On one computer, I had an issue where all of the files were being output in the Documents and Settings folder (under my profile). I have no idea why, but whenever I say "current directory" (ie: .), everything goes there.

But who knows.
## Post #5
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-09-03T21:14:14+00:00
- Post Title: Quickbms in reverse?

Yes, I'm using command line. 

I uploaded the archive and the script [here](http://www.4shared.com/folder/6ep35pY8/_online.html).

First, I extract a file into "output" folder:

```

QuickBMS generic files extractor and reimporter 0.5.2
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file territories_arkadia_10.pak
- open script entropia.bms
- set output folder output

  offset   filesize   filename
------------------------------

- the script has requested to load a function from the dll
  MEMORY_FILE4
  do you want to continue (y/N)? y
- library MEMORY_FILE4 loaded at address 00F23D00
- function found at offset 68801300
  00000000 699184     territories/arkadia/textures/weapons/rif_law_main_col01.dds

- 1 files found in 3 seconds
```


Then I change it in Photoshop and re-inject it back:

```

QuickBMS generic files extractor and reimporter 0.5.2
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- REIMPORT mode enabled!
- open input file territories_arkadia_10.pak
- open script entropia.bms
- set output folder output

  offset   filesize   filename
------------------------------

- the script has requested to load a function from the dll
  MEMORY_FILE4
  do you want to continue (y/N)? y
- library MEMORY_FILE4 loaded at address 00CA3D68
- function found at offset 68801300
< 00000000 322667     territories/arkadia/textures/weapons/rif_law_main_col01.dds

- 1 files reimported in 4 seconds
```


Then I extract the file again to see if it's been modified:

```

QuickBMS generic files extractor and reimporter 0.5.2
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file territories_arkadia_10.pak
- open script entropia.bms
- set output folder check

  offset   filesize   filename
------------------------------

- the script has requested to load a function from the dll
  MEMORY_FILE4
  do you want to continue (y/N)? y
- library MEMORY_FILE4 loaded at address 00C93CF8
- function found at offset 68801300
  00000000 699184     territories/arkadia/textures/weapons/rif_law_main_col01.dds

- 1 files found in 5 seconds
```


Unfortunately, the file in "check" folder is the original one.

Also, the archive's modification date is not changed, so I have a feeling it's not being modified in the process.

Any help is appreciated, thanks!
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-09-04T10:25:31+00:00
- Post Title: Quickbms in reverse?

entropia.bms is not valid for reimporting (because it contains the "*log NAME" instructions with MEMORY_FILEs).

obviously if you are a programmer you can write a tool that performs the reimporting because everything I released is open source included the decryption algorithm that should be the same also for the reencryption (rc4 is a two ways algorithm).
## Post #7
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-09-05T02:03:29+00:00
- Post Title: Quickbms in reverse?

I'm not good enough to write my own encryptor   

Is there any chance I can get help with that?

Extraction by itself doesn't give me much, I need to use the modified files in game...
## Post #8
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-09-15T06:50:35+00:00
- Post Title: Quickbms in reverse?

Still looking for a way to re-inject files into EU .pak archives.

Please contact me if you can write an injector based on Quickbms decryption, or you know any other program that could do it.

Thanks!
## Post #9
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-15T16:24:25+00:00
- Post Title: Quickbms in reverse?

> Reply from tempo
>
> Still looking for a way to re-inject files into EU .pak archives.

Please contact me if you can write an injector based on Quickbms decryption, or you know any other program that could do it.

Thanks!

If you're just trying to replace textures, you could give TexMod a try. It's designed to grab textures while the game is running and replace them with files stored elsewhere. It doesn't permanently replace the files themselves, it simply makes the game use a different file at runtime.

It can also be used to dump textures.
## Post #10
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-09-17T15:32:08+00:00
- Post Title: Quickbms in reverse?

> Reply from Satoh
>
> 
If you're just trying to replace textures, you could give TexMod a try. It's designed to grab textures while the game is running and replace them with files stored elsewhere. It doesn't permanently replace the files themselves, it simply makes the game use a different file at runtime.

It can also be used to dump textures.

I need to replace different files, not only textures, so I'm looking for a way to inject any file back into the archive.

Since the encryption/decryption algorithm is known, I hope there is a program that can pick it up and use.

Unfortunately, Quickbms can not work in reverse
## Post #11
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-09-25T21:07:18+00:00
- Post Title: Quickbms in reverse?

bump bump
## Post #12
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-10-02T22:30:04+00:00
- Post Title: Quickbms in reverse?

Bump, still looking for help
## Post #13
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-10-30T13:27:54+00:00
- Post Title: Quickbms in reverse?

still have hope... bumping
## Post #14
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-11-28T14:43:11+00:00
- Post Title: Quickbms in reverse?

bump!
## Post #15
- Username: tempo
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Sep 01, 2011 8:44 am
- Post datetime: 2011-12-20T00:21:06+00:00
- Post Title: Quickbms in reverse?

still need to inject files back, bumping...
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-12-23T19:17:51+00:00
- Post Title: Re: Quickbms in reverse?

Bumping is not going to be further allowed. Closed.
