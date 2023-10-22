## Post #1
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2017-09-27T23:37:52+00:00
- Post Title: Noesis script help

Hi everyone,

I would like to know how to read two files in Noesis, because I want to read the header and the model without needing to merge them.
My script is working well with merged files, but it will be better reading them separeted. It will help me in my texture script, because I also need to merge the header and raw texture.

Also, if I could do it, I could improve the script to read the main file I call every other file.

Thanks in advance.
## Post #2
- Username: DGIorio
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-09-28T00:26:32+00:00
- Post Title: Noesis script help

example

```
		if( rapi.checkFileExists( rapi.getDirForFilePath( rapi.getLastCheckedName() ) + baseName + ".txd" ) ):
			texData = rapi.loadIntoByteArray( rapi.getDirForFilePath( rapi.getLastCheckedName() ) + baseName + ".txd" )
			txdLoadRGBA(texData, self.texList)
```
## Post #3
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2017-09-28T04:31:12+00:00
- Post Title: Noesis script help

> Reply from chrrox
>
> example
Code: Select all		baseName = rapi.getExtensionlessName(rapi.getLocalFileName(rapi.getLastCheckedName()))
		if( rapi.checkFileExists( rapi.getDirForFilePath( rapi.getLastCheckedName() ) + baseName + ".txd" ) ):
			texData = rapi.loadIntoByteArray( rapi.getDirForFilePath( rapi.getLastCheckedName() ) + baseName + ".txd" )
			txdLoadRGBA(texData, self.texList)

Thanks chrrox, it worked very well
