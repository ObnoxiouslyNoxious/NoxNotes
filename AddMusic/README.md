# Using RDR Menu Theme Music in GTA Menu Theme

## 2 Options:

Option A - Follow Step 1 and replace your GMT_Config.lua with the one provided in this Repository (download it and drop it in to the below path, overwriting the existing GMT_Config.lua).

Option B - Follow Steps 1-4 to manually edit your GMT_Config.lua.

## Notes:

Back up your edited file. Copy the edited `GMT_Config.lua` and keep it outside the Workshop folder (for example in Documents or on your Desktop). After a GTA Menu Theme update, Steam replaces the Workshop files and you'll need to drop the backed-up file (or the pre-edited one provided in this Repository) back in to overwrite the replaced file from Steam.  
  
**WARNING:** There are only 2 available font slots for either Mod to use. Using this Method will load the RDR Menu Fonts. This is unfortunately a limitation of Lua load order. We need GTA Menu Theme to load first to display the images, but RDR Menu loading last means its font file files overwrite the GTA Menu font files.

## Steps:

1. **Find the file** (Ensure the game is closed before editing. Adjust the Steam path if yours differs):

   ```text
   C:\Program Files (x86)\Steam\steamapps\workshop\content\108600\3836840382\mods\GTAMenuTheme\42\media\lua\shared\GMT_Config.lua
   ```

2. Edit the file:

   Track count, change `11` to `27`:

   ```lua
   GMT_Config.MAIN_MENU_MUSIC_AVAILABLE_TRACKS = 27
   ```

   In `MAIN_MENU_MUSIC_TRACK_SOUNDS`, add:

   ```lua
    [12] = "RMT_Ambient_Brandywine",
    [13] = "RMT_Ambient_CalumetRavine",
    [14] = "RMT_Ambient_ChollaSprings",
    [15] = "RMT_Ambient_Colter",
    [16] = "RMT_Ambient_GreatPlains",
    [17] = "RMT_Ambient_Grizzlies",
    [18] = "RMT_Ambient_Guarma",
    [19] = "RMT_Ambient_Heartlands",
    [20] = "RMT_Ambient_LarnedSod",
    [21] = "RMT_Ambient_Lemoyne",
    [22] = "RMT_Ambient_Mexico",
    [23] = "RMT_Ambient_RattlesnakeHollow",
    [24] = "RMT_Ambient_Roanoke",
    [25] = "RMT_Ambient_ScarlettMeadows",
    [26] = "RMT_Ambient_TallTrees",
    [27] = "RMT_Ambient_Wapiti",
   ```

   In `MAIN_MENU_MUSIC_TRACK_NAMES`, add:

   ```lua
    [12] = "RDR - Brandywine",
    [13] = "RDR - Calumet Ravine",
    [14] = "RDR - Cholla Springs",
    [15] = "RDR - Colter",
    [16] = "RDR - Great Plains",
    [17] = "RDR - Grizzlies",
    [18] = "RDR - Guarma",
    [19] = "RDR - Heartlands",
    [20] = "RDR - Larned Sod",
    [21] = "RDR - Lemoyne",
    [22] = "RDR - Mexico",
    [23] = "RDR - Rattlesnake Hollow",
    [24] = "RDR - Roanoke",
    [25] = "RDR - Scarlett Meadows",
    [26] = "RDR - Tall Trees",
    [27] = "RDR - Wapiti",
   ```

   In `MAIN_MENU_MUSIC_TRACK_LENGTHS_MS`, add:

   ```lua
       [12] = 240064, [13] = 170731, [14] = 256064, [15] = 276987,
       [16] = 241954, [17] = 275968, [18] = 229850, [19] = 177295,
       [20] = 177295, [21] = 246921, [22] = 284544, [23] = 228987,
       [24] = 199744, [25] = 182064, [26] = 234731, [27] = 242249,
   ```

   Every line must end with a comma. A missing comma prevents the entire GTA Menu Theme from loading. Save the file.

3. Start Zomboid, enable both Mods and set the load order: GTA Menu Theme before RDR Menu Theme

4. Open the Menu Theme Settings, then the Audio tab. The RDR tracks should be in the Music Track list.
