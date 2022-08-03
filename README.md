[1. Introduction](#1Introduction)
[2. Tools](#2Tools)
[3. Changing Sleeves](#3Changing Sleeves)

# 1.Introduction
In Yu-gi-oh Master Duel all your cards/sleeves/terrain/summon animation can be overridden on your local machine.
Because the changes only happens locally and you don't get an advantage by changing the resources I don't see why Konami would care. 

# 2.Tools
1. PC Steam version of Master Duel.
2. AssetStudio.net6 - this requires .Net framework v6.x.x.
3. UABEA.
4. Image Editor(GIMP is OK).
5. <a href="https://docs.google.com/spreadsheets/d/1IXpwCaabi47Ly8dAf4aJtFdYwi29yGkCJ4bvMhnsvc8/edit#gid=1574353405">Spreadsheet</a> with every card artwork, sleeve/protector, wallpaper.

## NOTE
I added AssetStudio.net6 and UABEA to this repository. You can also find them on github.

# 3.Changing Sleeves
1. Select the artwork you want to use as sleeve.
2. Open it in an image editor.
3. Change the dimension to 480/700 pixels.
4. Go into the installation folder(right click on the game in steam->Manage->Browse Local Files).
5. Go to Local Data.
6. If you have multiple accounts you will see multiple folders in here(Sort by "Data Modified", this way it's easier to know which account is which).
7. Copy the location of ".../LocalData/{account}/000".
8. Open AssetStudio.exe.
9. Go to File->Load Folder.
10. Paste ".../LocalData/{account}/000" and wait(~5min).
11. Go to Filer Type->Texture2D.
12. Click on Asset List.
13. In the Input Box add the ID of the sleeve that you want to modify(look for it in the Spreadsheet).
14. Look for the 2 files that start with "ProtectorIcon".
15. Right click on the 2 files ->Show orignal file.
16. Copy the files somewhere else.
17. Open UABEA.
18. Go to File->Open select one of the copies.
19. Select Info.
20. In the new Window select the one with type "Texture2D".
21. Click plugins->Edit Texture->Load.
22. Pick the new artwork you created.
23. Save in ALL the windows.
24. You can't save with the same name because it's still open in UABEA.
25. Do the same for the second copy(from 14).
26. Don't forget to backup the original and change the name of the edited one(from 23 and 24).
27. Copy the edited files to the insalation folder(you can find the correct folder by looking at the first 2 characters in the file name).
28. DONE.