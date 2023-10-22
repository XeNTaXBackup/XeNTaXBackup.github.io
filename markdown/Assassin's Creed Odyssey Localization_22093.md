## Post #1
- Username: GodVader
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 02, 2020 12:57 am
- Post datetime: 2020-05-01T17:36:05+00:00
- Post Title: Assassin's Creed Odyssey Localization

Hello everyone,
I'm a Turkish English Teacher and a gamer. I want to translate Assassin's Creed Odyssey into Turkish. I'm not a coder but I'm an advanced user. I didn't know where the localization files were but I found them by researching in this forum.

1. I have extracted DataPC.forge and reached 2348-LocalizationPackage_English.data using Ubisoft_Forge_Tool_By_Delutto



looks like 



2. I have exported 2348-LocalizationPackage_English.data and had 0-LocalizationPackage_English.Localization_Package using Ubisoft_DATA_Tool_By_Delutto





3. I extracted 0-LocalizationPackage_English.Localization_Package by draggin it onto aclocalizationpackagetool and had 0-LocalizationPackage_English.Localization_Package.txt and 0-LocalizationPackage_English.Localization_Package.txt.header files



4. I have translated only the main menu(I searched the Press any Key, Continue, etc. and changed them as "Bir tuşa basın", "Devam Et" etc.) in 0-LocalizationPackage_English.Localization_Package.txt just to see if it works.
5. And to import my 0-LocalizationPackage_English.Localization_Package.txt I dragged it onto aclocalizationpackagetool and the tool imported the modified txt and the header file. I had a new file in the same directory named 0-LocalizationPackage_English.Localization_Package.txt.out



6. I deleted .txt.out extension from 0-LocalizationPackage_English.Localization_Package.txt.out just changing its name and had a 0-LocalizationPackage_English.Localization_Package



7. I imported 0-LocalizationPackage_English.Localization_Package into 0-LocalizationPackage_English.Localization_Package.data where I extracted all the .data files from DataPC.forge then It gave me a 0-LocalizationPackage_English.Localization_Package.data.NEW file in the same directory. Again I deleted .NEW from that file changing it's name.





8. As the last step I imported all the files I had extracted from DataPC.forge before, including my modified 0-LocalizationPackage_English.Localization_Package.data using Ubisoft_Forge_Tool_By_Delutto



I did these yesterday. And I tried the game but it was English.  
Then I realized there is a DataPC.forge.NEW file in the game directory.



Then i backed up my original DataPC.forge file and  replaced the .NEW file then I tried again. But the game was again English.



These are my steps I tried to write them as detailed as I can, I realized that the DATA tool is not importing the modified files, it only copies the original file. Can you help me? Thank you.
