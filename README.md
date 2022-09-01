[1. Introduction](#1Introduction)
[2. Tools](#2Tools)
[3. Changing_Sleeves](#3Changing_Sleeves)
[4. Changing_Animations](#4Chaning_Animations)

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

# 3.Changing_Sleeves
STEPS:
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

# 4.Changing_Animations
Apps needed:
-Everything from [2. Tools](#2Tools)
-Python script(<a href="https://github.com/MattOstgard/spine_sequence/blob/master/spine_sequence.py">SCRIPT</a>)
-Python
-Spine(You can find a cracked version online)
Steps:
1. Find the CardId animation(check the  <a href="https://docs.google.com/spreadsheets/d/1IXpwCaabi47Ly8dAf4aJtFdYwi29yGkCJ4bvMhnsvc8/edit#gid=1574353405">Spreadsheet</a>).
2. Load the LocalData files in AssetStudio(check Changing_Sleeves steps).
3. Search by CardID in AssetStudio.
4. You will need to find and copy 6 files: 2xPCardId, 2xPCardId.atlas, 2xPCardIdJS where CardId is the animation ID from the spreedsheat.
5. You will need a new animation. One simple way is to find a GIF and convert it to PNG(multiple files).
Note: The PNG's file names must be in order ex:xxx00.png, xxx01.png, xxx02.png. The python script will not work if the files are not ordered.
6. Optional: make the PNG's transparent
7. Put the pyhton script in the same folders as the PNG's
8. Run the command "python spine_sequence.py --output XXXX.json --images *.png --framerate 22".
9. Open the generated .json file in Spine.
10. Click on the "Email" icon.
11. Click on Setup.
12. Keep the animation between 45-50 frames.
13. Click Export.
14. Select Json ->Pack Settings.
15. Change Max width:8192, Max height:8192, check Power of two, Scale 1.0.
16. Export in a different folder(.atlas, .json, .png).
Note: The export must be only one .png file. If not reduce the Scale value.
17.  Open the .json file.
18.  Change the value of "images"(from skeleton object) to "./images/" and the value of "audio" to "".
Note: You can also replace the values of width(replace all) and height(replace all) but I recommend to see the animation in game first. 
19.  Open the .atlas file.
20.  Change the SECOUND line to "PCardId.png" where CardId is the AnimationId(from spreedsheat).
21.  Add the .txt extension to .atlas and .json file(ex: XXXX.json.txt and XXXX.atlas.txt).
22.  Open UABEA.
23.  Open the original files(from step 4) one by one.
24.  Click on Plugins->Edit Texture/Import.txt(check steps 18->23 from Changing_Sleeves).
25.  Replace the original files(check step 27 from Changing_Sleeves).
26.  DONE.

