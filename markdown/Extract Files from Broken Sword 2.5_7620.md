## Post #1
- Username: elitetum
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 03, 2011 4:28 pm
- Post datetime: 2011-11-03T09:22:06+00:00
- Post Title: Extract Files from Broken Sword 2.5

Hi everyone,

since I have problems extracting files from the official games Broken Sword 1 and 2, I tried doing this on the fan game Broken Sword 2.5 ( [http://www.brokensword25.com/](http://www.brokensword25.com/) ).

They seem to have packed all files into on big file "data.b25c". Taking a look at it, it looks like there is some kind of diretory-tree written in it. Furthermore there is a file "packages.lua" (the programmers used the lua-scripting language) with following content:

> local PackageDefinitions =
>
> {
>
> 	{ 'data.b25c', '/', 'pack' },
>
> }
>
> 
>
> --------------------------------------------------------------------------------
>
> 
>
> for i, PackageDefinition in ipairs(PackageDefinitions) do
>
> 	if PackageDefinition[3] == 'dir' then
>
> 		Package.LoadDirectoryAsPackage(PackageDefinition[1], PackageDefinition[2])
>
> 	elseif PackageDefinition[3] == 'pack' then
>
> 		Package.LoadPackage(PackageDefinition[1], PackageDefinition[2])
>
> 	end
>
> end

Not sure if this helps, but taking a look at the lua-manual, "LoadPackage" seems to be a self-defined function. So maybe not as helpful as I thought at first.
Still maybe someone has allready done this or can give me hints on how to proceed?

Any help is appreciated a lot! Thanks!
