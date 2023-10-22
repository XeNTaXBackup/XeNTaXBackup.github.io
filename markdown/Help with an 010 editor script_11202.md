## Post #1
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2014-02-11T19:45:02+00:00
- Post Title: Help with an 010 editor script

Hey all, I couldn't find any forums dedicated to 010 Editor, but I figured this would be the next best, if not the best, place to look anyway. What I'm trying to do is strip out XMA files from a Marvel Ultimate Alliance ZSS/ZSM sound container. I know I can simply look at the RIFF header, size, etc and strip them out that way, but the filenames as well as offsets and size are stored elsewhere in the file.

What I'm interested in doing is the AUTO FIND section I've added to the commented header here. I need to find a .xma extension, then move back until I get 4 00 bytes. I can't just roll back an arbitrary number since I'm not sure how long the filename will be. Then I just need to be able to move the cursor back and forth to grab my offsets and whatnot.

What you see here is a transition from the old way (the first six steps) to the new way (the seven steps under AUTO FIND). I haven't actually written the entire code (because admittedly I don't recall how to find bytes, nor how to move the cursor). Thus my plea for help here.

```
//--- 010 Editor v2.1.3 Script File
//
// File:
// Author: Teancum
// ZSS ripper
// 1) start with RIFF (4 bytes), record location of 'R'
// 2) next four bytes, file size (chunk_size)
// 3) add 8 bytes to chunk_size to cover header
// 4) return to this 'R' location
// 5) select from 'R' to chunk_size
// 6) export

// AUTO-FIND
// 1) Find first '.xma'
// 2) Go backward, find first 4-byte 00 set (filenames may be short or long, so we need to find the first set to ensure we're past the beginning of the name)
// 3) Go back 16 bytes
// 4) Record next 4 bytes as offset
// 5) Record next 4 bytes after that as size
// 6) Go forward 12 bytes
// 7) Record next 20 bytes as file name


//--------------------------------------

char filename[];
const char file_ext[]=".xma
uint chunk_offset;
const char find_xma[4]={'.','x','m','a'} //find XMA file name
const char chunk_type[4]={'R','I','F','F'}; // "RIFF"
char chunk_name[];
uint chunk_begin;
int i;
int filenum;

filename=InputOpenFileName(
    "Open ZSM/ZSS ile", 
    "All files (*.zsm/zss)|*.zss",
    "*.zsm" );
FileOpen(filename);
filenum = GetFileNum();

TFindResults find_chunk=FindAll(
//Find all XMA files
    find_xma, 
    true, 
    true, 
    false, 
    0.0, 
    1, 
    0, 
    0 );

for(i = 0; i < find_chunk.count; i++ )
//Start at first RIFF chunk, iterate through until done
  {
    chunk_begin=find_chunk.start[i]; //.xma
    chunk_offset=ReadInt(chunk_begin+4); //4 over from RIFF, read int
    //chunk_name=ReadString(chunk_begin+16);
    //Printf("%s\n", chunk_name+file_ext); 

    SetSelection( chunk_begin, chunk_offset+8); //Start at RIFF, end at chunk_offset+8 (to account for header)
    CopyToClipboard(); //copy data
    FileNew(); //Start a new file
    PasteFromClipboard(); //paste into file
    FileSave(chunk_name+file_ext); //Save here (can I get the actual names, or prompt to save?)
    FileClose();
    FileSelect( filenum );
  };







```
