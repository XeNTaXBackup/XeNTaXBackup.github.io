## Post #1
- Username: ShadyTheFirst
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 09, 2017 3:35 am
- Post datetime: 2017-10-22T03:14:24+00:00
- Post Title: Changing Noesis' file associations

I've been trying to learn Noesis python scripting for a couple days now, and I think I've managed to write a decent, partially working script. However, I can't test it because upon loading it, Noesis thinks it's a Naruto Shippuden: Ultimate Ninja Storm 2 file, which it's not. Here's an image showing what I mean:



I'd like to know if there's a way to force Noesis to attempt to load a model using the specified script, as opposed to choosing the one it's been told to load for this kind of file, Thanks.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-22T04:45:39+00:00
- Post Title: Changing Noesis' file associations

you can temporarily move the conflicting script out of the python folder or give your new script a unique type check.
## Post #3
- Username: ShadyTheFirst
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 09, 2017 3:35 am
- Post datetime: 2017-10-22T15:15:35+00:00
- Post Title: Changing Noesis' file associations

I would do that, but I've searched all through the files and can't find this script that's causing it. I never installed such a script, so maybe it was built into Noesis?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-10-22T22:40:03+00:00
- Post Title: Changing Noesis' file associations

just re download noesis and move your script to the new folder.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-23T00:20:07+00:00
- Post Title: Changing Noesis' file associations

> Reply from ShadyTheFirst
>
> I never installed such a script, so maybe it was built into Noesis?
it seems so, it is mentioned in native noesis.dll
## Post #6
- Username: ShadyTheFirst
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 09, 2017 3:35 am
- Post datetime: 2017-10-23T15:32:06+00:00
- Post Title: Changing Noesis' file associations

> Reply from AceWell
>
> it seems so, it is mentioned in native noesis.dll

If that's the case, is there a way to remove it or disable it?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-23T21:23:53+00:00
- Post Title: Changing Noesis' file associations

in theory you can hex edit out anything you want, just need to know what you're looking at, otherwise you
need to add a unique type check to your script or even change the extension of your samples temporarily.  
thats all i got man, good luck!
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-10-24T21:55:28+00:00
- Post Title: Changing Noesis' file associations

there is a python function to overwrite built in plugins. noesis.disableFormatByDescription("Hokuto Musou Model") as an example
also just rename the extension to something else and test your plugin with that.
