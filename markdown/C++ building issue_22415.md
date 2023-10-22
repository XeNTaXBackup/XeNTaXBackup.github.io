## Post #1
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-07-16T21:16:30+00:00
- Post Title: C++ building issue

Hi,

i am very new to C++ so please dont judge me 

I have been trying to build a project from source code i found and seem to have an issue,
i have added all Lib and Include directories to appropriate location and when i build as a win32 project i have no issue and file is successfully created.
when i try to build the exact same project under x64, i get an error msg that *.h " No such file or directory" for all files that previously worked.
how can i fix this?

i am building from 3dsmax SDK and these files seem to be relevant for both x32 and x64 as far as i can tell

Thanks in advance
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-16T21:40:59+00:00
- Post Title: C++ building issue

If you're using Visual Studio, then you probably have to change configuration in project settings for your new build
like adding new include directories or library directories 
[https://imgur.com/a/y9HrYaH](https://imgur.com/a/y9HrYaH)
[https://imgur.com/a/FLQ5PG2](https://imgur.com/a/FLQ5PG2)

But remember to choose Configuration and platform in the settings window first 
[https://imgur.com/a/6fzTXiy](https://imgur.com/a/6fzTXiy)
## Post #3
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-07-16T22:06:11+00:00
- Post Title: C++ building issue

> If you're using Visual Studio, then you probably have to change configuration in project settings for your new build
>
> like adding new include directories or library directories
>
> https://imgur.com/a/y9HrYaH
>
> https://imgur.com/a/FLQ5PG2
>
> 
>
> But remember to choose Configuration and platform in the settings window first
>
> https://imgur.com/a/6fzTXiy

Thanks for the fast reply 

I am using a 2013 3ds max SDK and the only files in the x64 folder of the SDK are .lib which i have included in my project (i also left the x32 version)
but all the .h and .cpp files are under the x86 the i assume the are relevant for both

I changed my platform and configuration unfortunately that didn't work

any more tricks i could try?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-16T22:25:53+00:00
- Post Title: C++ building issue

Can you attach a screenshots of your additional include directories and additional library directories (in both configurations)?
And also some listing or screenshots of source folder structure?
## Post #5
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-07-16T23:23:59+00:00
- Post Title: C++ building issue

ill PM you all the pictures
## Post #6
- Username: jayn23
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-17T21:05:32+00:00
- Post Title: C++ building issue

Ok, I have answered by PM.
## Post #7
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-07-18T18:10:53+00:00
- Post Title: C++ building issue

Ill just update that one of the many solutions suggested by ikskoks worked for me so thanks a lot.
i ended up using absolute paths for my include files.
