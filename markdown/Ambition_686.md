## Post #1
- Username: sigget
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-02T16:19:22+00:00
- Post Title: Ambition

Hi, ive written a few tools and utilities for a game file format, and i think a common standard gui tool for such formats is a great idea, however i wasnt all that pleased with multiex, it seems a little too simplistic. The format ive worked with is basically a FAT-style file system contained in a file. As such it has a few extra features and limitations to other game archives. For example, it has support for folders but cant grow beyond a certain size. 

What id like to see is a tool that can adjust itself to the format being used, supporting features of all formats but not requiring any format to support them all. When creating portable software and in general stuff that is one-solution-to-work-for-all-kinds you often get a least-common-denominator effect, that is, you wind up only supporting the really basic stuff that all instances support. For example, if an archive supports directories then there should be a tree-view visible else not, if it supports compression there should be a percentage column shown, and so on. 

I think a good goal of such a tool would be that it should be able to view and work with, without limitations, all compressed archives, such as ZIP,RAR,TAR,ARJ etc, and all iso/image/ghost -files, such as bin/cue, iso and so on. If it can do this, then it can probably handle all possible file formats we'll see developed by game companies.

I searched your site for an SDK on how to develop custom format handlers, but couldnt find one, are you really developing all this on your own? in that case im impressed. I liked the online downloading of format handlers, but it doesnt make it easy for other developers to help on writing plugins. And it also doesnt allow the tool to recognize formats by itself, id love to see a message such as: "In order to read this format i need to download the <whatever> plugin, click OK to proceed or Cancel to abort.". 

Perhaps this is where you're taking OpenMex, in that case id love to write plugins for it. If not, then at least ive given you my few cents.

In summary, 
Plugins should be able to add menus and views in the gui, and be able to control what columns are shown in the file list. 
An SDK so that other developers can join in
A standard Plugin API
Automatic recognition of formats
Extensibility

As ive already said, ive havent taken that close a look at multiex, if im misstaken about any details then i apologize.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-03T07:58:33+00:00
- Post Title: Ambition

Hi, and thanks for raising some points, some of which are definitely worth taking a look at. 

> Reply from sigget
>
> Hi, ive written a few tools and utilities for a game file format, and i think a common standard gui tool for such formats is a great idea, however i wasnt all that pleased with multiex, it seems a little too simplistic. The format ive worked with is basically a FAT-style file system contained in a file. As such it has a few extra features and limitations to other game archives. For example, it has support for folders but cant grow beyond a certain size.

Yes, MultiEx is presented in a very simplistic manner to the public. Frankly, the public doesn't care about zillions of options. It just wants to be able to open the game resource archive (GRA) they are interested in and extract the contents. This is a tried and tested formula, and done after discussion with users and programmers. 

A FAT-style approach seems feasible enough for some GRA-formats (GRAFs), but would still be very limited in features and universally application to the multitude of formats around. 

> Reply from sigget
>
> What id like to see is a tool that can adjust itself to the format being used, supporting features of all formats but not requiring any format to support them all. For example, if an archive supports directories then there should be a tree-view visible else not, if it supports compression there should be a percentage column shown, and so on. 

You are talking basically aestethics here. MultiEx doesn't show a tree-like view, indeed. It shows exactly the entry as found in a GRA. Of course, you are right, and this might be picked up by the Commander (remember, MultiEx is the processor of GRAs, that runs on script files, and coughs up a list-of-contents for the Commander to use and show to the user). I have thought about this before, making the Commander show a Windows Explorer-like tree-view, but have labeled it "non-priority". 

> Reply from sigget
>
> When creating portable software and in general stuff that is one-solution-to-work-for-all-kinds you often get a least-common-denominator effect, that is, you wind up only supporting the really basic stuff that all instances support.

MultiEx.dll runs on script files to access and interpret GRAs. This script (at least the MultiEx3 script - the latest) enables MultiEx to correctly process a lot of formats, as you might have seen form the Supported Games list. However, this script is not the ultimate answer to your common-denominator effect. I and others have often thought of different approaches to address this problem, and I still do, but whatever the approach it must be from an engine that can universally be used on encountered new formats. The reason I use the script is because I can support most new GRAs in a matter of minutes after I have figured out the format. I simply need to write the appropriate script and MultiEx and Commander will do the rest. Any new approach would have to offer me the same speed and flexibility. 

> Reply from sigget
>
> I think a good goal of such a tool would be that it should be able to view and work with, without limitations, all compressed archives, such as ZIP,RAR,TAR,ARJ etc, and all iso/image/ghost -files, such as bin/cue, iso and so on. If it can do this, then it can probably handle all possible file formats we'll see developed by game companies. 

I have no ambition of redoing the amount of work that went into creating WinRAR, WinACE, WinZIP, 7z etc. The idea (when you can process these you can process 'em all) is not true. You can't imagine the number of different GRAFs I have seen. 

> Reply from sigget
>
> I searched your site for an SDK on how to develop custom format handlers, but couldnt find one, are you really developing all this on your own? in that case im impressed. I liked the online downloading of format handlers, but it doesnt make it easy for other developers to help on writing plugins. And it also doesnt allow the tool to recognize formats by itself, id love to see a message such as: "In order to read this format i need to download the <whatever> plugin, click OK to proceed or Cancel to abort.".

1. I tried to get fellow programmers to join in the project, and even started a open source project at Sourceforge. I released all source code. To no effect. I have long since the start of this MultiEx project (1997!) tried to encourage people to write their own format scripts, because THAT is why I created it in the first place and what I envisaged. To no effect. Most people, rightly so, do not care about these kind of things, they just want to use the tool. 
2. Yes, I have personally figured out every single supported GRAF that is in there, using a Hex editor to open the GRA and then applying common logic to the bits and bytes visible. 
3. As I said, there are no other developers joining the project at Sourceforge ot anywhere else. I have offered people to just email me a new script they created and it would be tested and uploaded to the XeNTaX MultiEx server. 
4. GRA recognition is a tricky thing, to say the least. Especially since half of them don't use ID-tags anywhere. I have thought long and hard on this one, along with others, because I would really like the program to be able to figure out new formats that are not even supported. That would be cool. But impossible. Recognition of all known formats is then second best, but still near impossible. You end up with a process that will recognize a lot of archives, but still not all, which is irritating. Still, simply recognition is already since long on my "to-do" list, but again, without priority. Why not let the user choose which format to apply to the GRA it wants to open? Yes, why not. Let's select the game from a top-down menu and choose "open". 

> Reply from sigget
>
> Perhaps this is where you're taking OpenMex, in that case id love to write plugins for it. If not, then at least ive given you my few cents.

Captain Corny (Arjan Dikhoff) cancelled the OpenMex project due to the enormous amount of work that would go into it before it would reach the same functionality as MultiEx Commander (and subsequently could really start to go beyond it). 
We both enthusiastically thoughy it was the way forward, but it turned out not very lucrative in terms of gratification and work vs joy. 
Unless you can and want to spent a huge amount of free time on it, it's a pain to code. And there's more to life. So I picked up work on MultiEx Commander yet again. 

Plugins are possible though, the ActiveX-DLL approach is working (see the Painkiller thread in Game Requests), and I will add an option for the DLL to tell the Commander which columns to use in the presentation to the user. The DLL-approach let't me go beyond the script of MultiEx/Importation method of the Commander, because I can do that all from the DLL. And anyone who can write these DLL's can do the same, as long as they obey the function names that the Commander expects to find in the DLLs. This technique I will explain on the forum in more detail, hopefully with the new release. 

> Reply from sigget
>
> As ive already said, ive havent taken that close a look at multiex, if im misstaken about any details then i apologize.

Well, it would help if you would take a better look at what MultiEx offers, before calling it simplistic. Try recreating it.   
Also, take a look at the info in the tool Mex3Scriptor, it opens up a book on the scripting.
## Post #3
- Username: sigget
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-03T17:13:32+00:00
- Post Title: Ambition

The script approach is really cool and time saving of course. But for more complicated formats custom coding is of course necessary, for example plugins in form of DLLs. I think that if you published a SDK or something for just this bit then its more probable that people join in. Downloading the whole source code and going through it to understand how to extend it is just too big a hassle. A standard API is what people wants.

About the FAT-style format i mentioned, i didnt mean this as some kind of universial internal representation. Instead i was describing the GRAF ive worked with. 
[http://www.geocities.com/sigget2003/vfsspec_v02.html](http://www.geocities.com/sigget2003/vfsspec_v02.html)
Its a rather complicated format and i tried writing a GUI for it, but decided it was too much work. I did however write a Total Commander plugin for it, it works, but i find their plugin API very crappy.

Perhaps something along the lines of 
CAPS_FOLDERVIEW
CAPS_CUSTOMCOLUMNS
and in the Plugin
DWORD GetCapsBits();
int OnFolderSelectionChanged(...);

And some way of creating new archives from scratch, for example the ufo vfs format has a fixed size that need to be decided when creating the archive.

Well, its just a wishlist from my part.

I know just how frustrating it is posting source and trying to get other people to join in with no results.

Recognition is tricky, and impossible for some formats, but it doesnt require id's. Formats can be identified by the ranges of values in headers and such. But it doesnt go well with the download on demand thingie. Hmm, then again, people probably know what game they're playing.
