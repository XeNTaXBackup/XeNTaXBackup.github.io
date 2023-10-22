## Post #1
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-09-22T15:46:15+00:00
- Post Title: encryption method analysis

i have a question... is there a way to determine encryption method if i have 2 files with same content but 1 of them is encrypted and the other isnt??
## Post #2
- Username: mnrhacker
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 21, 2021 3:42 pm
- Post datetime: 2021-12-23T15:37:34+00:00
- Post Title: encryption method analysis

If it's properly encrypted with something like AES256 then no, comparison of the plaind and encrypted file will yield no useful information. The encrypted data is essentially like random noise without a decryption key. However if it is a weaker or rather simple encryption then a "known-plaintext analysis" might give enough clues to break the encryption.
