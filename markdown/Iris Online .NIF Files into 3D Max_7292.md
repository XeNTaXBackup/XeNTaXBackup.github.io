## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-04T11:59:02+00:00
- Post Title: Iris Online .NIF Files into 3D Max

Hello guys well today I trying work with Iris Online files are stored in .NIF, nifskope and GameBryo work fine loading files but I install 3D Max Plugin for load there and get this error? I trying in Max 9 and 2009 and get same error, can anyone help me please? anyway I GameBryo don't have option to Export it is really bad and Nifskope I export to OBJ but nothing happened when try import -.- so what I do wrong?






[Error.jpg](https://xentaxbackup.github.io/file/4686_Error.jpg)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-04T13:22:41+00:00
- Post Title: Iris Online .NIF Files into 3D Max

I believe it is because they discontinued development on their max plugin and therefore any bugs...that's it.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-04T13:49:44+00:00
- Post Title: Iris Online .NIF Files into 3D Max

> Reply from finale00
>
> I believe it is because they discontinued development on their max plugin and therefore any bugs...that's it.umm and what about Nifskope? when export OBJ and try import into 3D MAX or Blender nothing imported, nulled object
## Post #4
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-09-05T06:13:48+00:00
- Post Title: Iris Online .NIF Files into 3D Max

Iris have NIF 20.6.0.0 version which currently not fully supported by NifTools (NifSkope, Max plugin, Blender script).
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-05T15:07:11+00:00
- Post Title: Iris Online .NIF Files into 3D Max

> Reply from Nazaroff
>
> Iris have NIF 20.6.0.0 version which currently not fully supported by NifTools (NifSkope, Max plugin, Blender script).yes I cheked it yesterday, its not possible update it?
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-05T15:26:29+00:00
- Post Title: Iris Online .NIF Files into 3D Max

well the weird thing is that Szkaradek123 made an blender importer for I think it was Catherine witch has this model format. So there might be some trick to use but I don't know how
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-06T12:16:36+00:00
- Post Title: Iris Online .NIF Files into 3D Max

yes you right my friend, this is what I get.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-06T14:03:54+00:00
- Post Title: Iris Online .NIF Files into 3D Max

> Reply from CriticalError
>
> Nazaroff wrote:Iris have NIF 20.6.0.0 version which currently not fully supported by NifTools (NifSkope, Max plugin, Blender script).yes I cheked it yesterday, its not possible update it?

You just have to update the nif XML file to register the new data structures.
Though the format is massive and confusing to me   

I've been wanting to write a plugin to get the basic geometry out cause it looks challenging but never got anywhere.
## Post #9
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-06T14:08:40+00:00
- Post Title: Iris Online .NIF Files into 3D Max

> Reply from finale00
>
> CriticalError wrote:Nazaroff wrote:Iris have NIF 20.6.0.0 version which currently not fully supported by NifTools (NifSkope, Max plugin, Blender script).yes I cheked it yesterday, its not possible update it?

You just have to update the nif XML file to register the new data structures.
Though the format is massive and confusing to me   

I've been wanting to write a plugin to get the basic geometry out cause it looks challenging but never got anywhere.ok thanks a lot for quick reply finale, this really helpful you soon make a script for max better
