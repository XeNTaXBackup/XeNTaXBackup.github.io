## Post #1
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-05-07T00:23:34+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

Hi guys. I got these .aba files from Pokemon HOME but I don't know how to extract them. Can someone look into them to see how to decrypt them?
[files.zip](https://xentaxbackup.github.io/file/22198_files.zip)
## Post #2
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-05-26T16:33:48+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

They first 1024 bytes of the bundles are encrypted with Rijndael using a 256 bit Block and Key size.

```
IV:  X6TU@VYU$HyqKy57PfwWg7.t7wk2oqtg

```


Example C# code can be found [here](https://gist.github.com/barncastle/30e4261dbc956b1eb2404480f2112b4e).
Just to note, you need to target .Net Framework as RijndaelManaged does not support 256 bit Block/Key sizes in Standard/Core.

EDIT: I've added an app to the above gist that wraps this code. Put in a directory of *.aba files and it'll run through, decrypt and save them as *.unity3d.
## Post #3
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-05-26T16:54:34+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

> Reply from barncastle ↑Fri May 27, 2022 12:33 am at Fri May 27, 2022 12:33 am
>
> 
They first 1024 bytes of the bundles are encrypted with Rijndael using a 256 bit Block and Key size.
Code: Select allKey: lrZ6++Ln5tLnBsJk.ae6J8BLaLbMhVn@
IV:  X6TU@VYU$HyqKy57PfwWg7.t7wk2oqtg


Example C# code can be found here.
Just to note, you need to target .Net Framework as RijndaelManaged does not support 256 bit Block/Key sizes in Standard/Core.

Will this extract models from Pokémon HOME as well?
## Post #4
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-05-26T17:32:07+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

Yes. The example file you provided contains mesh and texture files. [](https://ibb.co/cbPQXDG).
## Post #5
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-05-26T18:08:15+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

> Reply from barncastle ↑Fri May 27, 2022 1:32 am at Fri May 27, 2022 1:32 am
>
> 
Yes. The example file you provided contains mesh and texture files. .

How did you do that? What program do you use to decrypt them?
## Post #6
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-05-26T18:17:15+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

I also have more samples here. [https://www.mediafire.com/file/tugg17cz ... s.zip/file](https://www.mediafire.com/file/tugg17czc0od809/Pokemon+Home+Unity+Files.zip/file)
## Post #7
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-05-27T14:25:03+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

For the sake of completeness here is the structure for the *.abap files which are *.aba containers.

```
 {
    uint Magic; // "ppir"
    int RootHeadOffset;
    int NameHeadOffset;
    int DataHeadOffset;
        
    BundleInfo Bundles[DataCount];
    
    int RootBufferSize => NameHeadOffset - RootHeadOffset;
    int NameBufferSize => DataHeadOffset - NameHeadOffset;
    int DataCount => RootBufferSize >> 4;
 }
 
 struct BundleInfo
 {
    int NameOffset; // relative to header.NameHeadOffset
    int NameSize;
    int DataOffset; // relative to header.DataHeadOffset
    int DataSize;
 }

```


I've updated the above [gist](https://gist.github.com/barncastle/30e4261dbc956b1eb2404480f2112b4e) with code for this too.
## Post #8
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-05-27T15:16:47+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

> Reply from barncastle ↑Fri May 27, 2022 10:25 pm at Fri May 27, 2022 10:25 pm
>
> 
For the sake of completeness here is the structure for the *.abap files which are *.aba containers.
Code: Select all struct FileHeader
 {
    uint Magic; // "ppir"
    int RootHeadOffset;
    int NameHeadOffset;
    int DataHeadOffset;
        
    BundleInfo Bundles[DataCount];
    
    int RootBufferSize => NameHeadOffset - RootHeadOffset;
    int NameBufferSize => DataHeadOffset - NameHeadOffset;
    int DataCount => RootBufferSize >> 4;
 }
 
 struct BundleInfo
 {
    int NameOffset; // relative to header.NameHeadOffset
    int NameSize;
    int DataOffset; // relative to header.DataHeadOffset
    int DataSize;
 }


I've updated the above gist with code for this too.
Nice. Thanks. This would work.
## Post #9
- Username: DahniMae
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 19, 2023 4:18 am
- Post datetime: 2023-05-30T15:53:32+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

sorry to bump a really old thread
it looks like Home version 3.0.0 changed something for the new assetbundles?
so this script doesn't work for the newer scvi mons anymore

is it possible this can one day get updated for the new versions of the files? I can give an example if needed
## Post #10
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2023-10-01T06:06:50+00:00
- Post Title: Need help extracting Unity Encrypted Assets from Pokemon HOME (*aba)

Has the decryptor been updated?
