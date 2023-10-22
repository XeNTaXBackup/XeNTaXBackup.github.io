## Post #1
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2011-03-23T10:43:32+00:00
- Post Title: Zeit² Resources.dll

Hello guys!

I'm trying translate this game for my language, but I don't know how edit this resources.dll. In the root folder, there languages folder (es, de, fr, it (where is the english folder?)) and inside there file Zeit2.resources.dll.

I tried the Hacker Resources and Resource Tuner, but not show the texts.

Please, help us with this!

Thanks for all!
[Zeit².rar](https://xentaxbackup.github.io/file/4095_Zeit².rar)
## Post #2
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2011-03-23T14:33:11+00:00
- Post Title: Zeit² Resources.dll

> Reply from bhrun
>
> Hello guys!

I'm trying translate this game for my language, but I don't know how edit this resources.dll. In the root folder, there languages folder (es, de, fr, it (where is the english folder?)) and inside there file Zeit2.resources.dll.

I tried the Hacker Resources and Resource Tuner, but not show the texts.

Please, help us with this!

Thanks for all!
It's a .NET dll. Search for a .NET resource editor (if any). PE Explorer, Resource Hacker, etc. wont do the job.
## Post #3
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2011-03-28T11:09:09+00:00
- Post Title: Zeit² Resources.dll

Thanks for your help XpoZed, but don't work with .NET resource editor, PE Explorer, Resource Hacker and OLLYDBG.

Anyone else can help?
## Post #4
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2011-04-06T20:27:11+00:00
- Post Title: Zeit² Resources.dll

One more topic dead...
Anybody can help?
## Post #5
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2011-04-07T08:03:32+00:00
- Post Title: Zeit² Resources.dll

As much as i see, Zeit2.resources.dll contains only strings. So, you can use Reflector to extract all the strings, translate them to your language, and then recompile new Zeit2.resources.dll with your patched resource.
## Post #6
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2011-04-07T13:46:50+00:00
- Post Title: Zeit² Resources.dll

Thanks man.

I'm searching for way to edit Zeit2.Localisation.Zeit2Strings.es.resources exported from Reflector.

If your know how edit, please, tell me   

Thank you!

Edit: At that thought, I need resgen.exe program that is included in Visual Studio. The syntax is this:The following command reads a binary resources file myResources.resources and writes an XML-based output file named myResources.resx.
```

```


Keep trying...
## Post #7
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2011-04-07T15:01:29+00:00
- Post Title: Zeit² Resources.dll

Yep, that's the way.
Then you edit the resx file with notepad and recompile a new DLL using edited resource.
## Post #8
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2011-04-07T19:54:39+00:00
- Post Title: Zeit² Resources.dll

I am not able to build, see the image below:
[http://img232.imageshack.us/i/imagemfij.jpg/](http://img232.imageshack.us/i/imagemfij.jpg/)

Not recognize the command ... to compile, I am using the syntax:

```
"C:\WINDOWS\Microsoft.NET\Framework\v4.0.20506\vbc.exe"/ target: library Zeit2.resources.vbproj
```


Am I doing something wrong?
## Post #9
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2011-04-07T20:05:20+00:00
- Post Title: Zeit² Resources.dll

> Reply from bhrun
>
> I am not able to build, see the image below:
http://img232.imageshack.us/i/imagemfij.jpg/

Not recognize the command ... to compile, I am using the syntax:
Code: Select all"C:\WINDOWS\Microsoft.NET\Framework\v4.0.20506\vbc.exe"/ target: library Zeit2.resources.vbproj

Am I doing something wrong?
Yes. You are trying to compile the resource file. You must create new project and add this resource file to it. Then compile the project to DLL.
## Post #10
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2011-04-08T01:16:32+00:00
- Post Title: Zeit² Resources.dll

I managed to compile the resources but the game automatically picks up the English language that I discovered what is inside the .exe of the game. I tried the same process to extract and compile, but there are mistakes in doing so in the .exe.
Is there a way to make the game run in another language?
Thanks again.
## Post #11
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2011-04-08T12:02:30+00:00
- Post Title: Zeit² Resources.dll

Dunno, i have to research that. Unfortunately i don't have any .NET compiler right now.
## Post #12
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2011-11-30T22:31:41+00:00
- Post Title: Zeit² Resources.dll

I had few free hours so i write an article about Zeit2.
You can check it out here : [http://nullsecurity.org/article/11](http://nullsecurity.org/article/11)
