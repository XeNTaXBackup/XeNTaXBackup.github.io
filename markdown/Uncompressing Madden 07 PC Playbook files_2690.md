## Post #1
- Username: calhoupe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 06, 2007 2:46 am
- Post datetime: 2007-07-05T20:07:23+00:00
- Post Title: Uncompressing Madden 07 PC Playbook files

From looking through the forum I know that uncompressing a Madden DAT file would be very difficult or impossible because EA uses its own custom compression method with its Madden games.  However, I think I have a way that might work in discovering Madden's compression method. 

The default playbooks are contained in the gamedata.dat file in compressed form.  However, one can create a custom playbook in the game that is saved in uncompressed form.  From all of my research I am 100% sure that the uncompressed custom playbooks and the compressed default playbooks will look nearly the same uncompressed.  

The custom playbooks are set up in a database format.  Each custom playbook has 19 Tables with x number of fields per table and x number of records per field.  Even looking with a hex editor this is quickly recognizable.  The file lists the 19 tables first and then shows the field names for the first table and then lists the data that would be entered into those fields.  This process is then repeated for the next 18 tables.  After a default playbook is uncompressed it will also have 19 tables and the same number of fields per table as the custom playbooks.  The only thing that would vary would be the number of records per field.  In general, there will be more records per field in a default playbook than in a custom playbook.

If we know how the compressed playbooks should look when they are uncompressed can that help us figure out the method of compression?

I have attached a compressed playbook file that I extracted from the gamedata.dat file, an uncompressed custom playbook file, and here's a link to a program called Tdbviewer that can read the database format the custom playbook uses.  [http://www.artemkh.com/nhlmisc.html](http://www.artemkh.com/nhlmisc.html)

If anyone can make significant headway on this issue I will donate $ to this website.  Actually, I will probably donate $ to this website anyway since it's a pretty cool website.  In any case, I would appreciate any help anyone has to offer.  Thanks,
calhoupe
[Madden Playbooks.rar](https://xentaxbackup.github.io/file/1252_Madden Playbooks.rar)
