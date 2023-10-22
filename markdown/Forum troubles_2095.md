## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-15T20:24:17+00:00
- Post Title: Forum troubles

> Reply from DenizOezmen
>
> 
Hello all,

am I the only one experiencing some strange behaviour in the forums?
For example, each time I try and post a message, an error of the following type will appear:

Code:
General Error

Could not insert new word

DEBUG MODE

SQL Error : 1016 Can't open file: 'phpbb_search_wordlist.MYI' (errno: 145)

INSERT IGNORE INTO phpbb_search_wordlist (word_text, word_common) VALUES ('1kb', 0), ('analyze', 0), ('archive', 0), ('attached', 0), ('called', 0), ('complete', 0), ('correct', 0), ('cut', 0), ('determine', 0), ('extract', 0), ('file', 0), ('files', 0), ('guarantee', 0), ('however', 0), ('i', 0), ('itl', 0), ('least', 0), ('logically', 0), ('might', 0), ('names', 0), ('posted', 0), ('program', 0), ('sample', 0), ('simply', 0), ('since', 0), ('single', 0), ('snakedef', 0), ('test', 0), ('themselves', 0), ('think', 0), ('thinking', 0), ('type', 0), ('used', 0), ('whatever', 0), ('work', 0), ('works', 0)

Line : 234
File : functions_search.php


The message has sometimes successfully been posted at this point, though. Adding attachments to posts is inherently luck-based.

Additionally, using the subforum links on the main forum page sometimes leads to raw PHP code being displayed on screen. Manually adding a "&sid=<something>"-parameter to the URL called solves this issue ...

Anyway, just wanted to mention this.

This is what Deniz wrote, does anyone else have similar problems, then PM Captain or me.
