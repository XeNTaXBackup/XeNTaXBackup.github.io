## Post #1
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-22T12:07:07+00:00
- Post Title: batman bat

i try use for %%i In (*.wav) do "%CD%/ww2ogg.exe" %%i 
pause 

he say he can only one imput file at a time

and is works when i drag and drop file one by one 
someone know how make bat
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-12-22T16:55:09+00:00
- Post Title: batman bat

Try this (untested but modified from something I've seen work before):

```
:getfile
if "%~1"=="" goto end
ww2ogg.exe "%~1"
shift
goto getfile
:end
```

Put that in a .bat in the same directory as ww2ogg.exe, you should be able to drag and drop any number of files onto the .bat.

I think the problem in your script is just that you need quotes around %%i:

```
for %%i In (*.wav) do "%CD%/ww2ogg.exe" "%%i"
```

So that the command parser knows that %%i is just one argument (if there are spaces in the path it will be split up into multiple arguments without the quotes).
## Post #3
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-22T19:42:43+00:00
- Post Title: batman bat

tested and thanked ! nice it's make me happy
