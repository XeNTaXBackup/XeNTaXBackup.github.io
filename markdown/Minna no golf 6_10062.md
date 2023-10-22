## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-01-20T12:53:59+00:00
- Post Title: Minna no golf 6

Looked at the game last year and thought it was encrypted. Characters are kinda cute but not too many of them. Anyone got the eboot decrypted?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-20T14:45:38+00:00
- Post Title: Minna no golf 6

The game is not encrypted I got the characters converted but there is one section i was not sure of for the dlc model from gravity rush.

this is what i had in the folder as notes.

> Bone Count long
>
> 0x1C header
>
> texture count long
>
> loop tex count {
>
> tex name size long
>
> tex name
>
> 8 bytes null
>
> }
>
> file name count long
>
> loop file name {
>
> file name size long
>
> file name
>
> 0x20 data
>
> }
>
> material count long
>
> loop materials {
>
> material name size long
>
> material name
>
> 0xA8 material def
>
> }
>
> mesh with extra header count long
>
> mesh loop start { = same as material count
>
> if is in range of header count { read 0x44 null }
>
> 0x44 Data before face count - contains mesh info and material id.
>
> read mesh info based on header flags.
>
> }
>
> bone data
>
> 2 nulls long
>
> loop bone {
>
> bone name length
>
> bone name
>
> 3 4x4 matrix
>
> 0x14 other bone info
>
> }
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-01-20T16:22:05+00:00
- Post Title: Minna no golf 6

lol, guess I must have been drunk when looking at the files then .
