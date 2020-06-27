# Adding Taunts to GMod

The sound files should be stored under ```/garrysmod/sound/husklesph/<player_folder>```, where **\<player_folder>** is the folder for the player the taunt belongs to.

The lua files should be stored under ```/garrysmod/lua/husklesph/taunts/<player>.lua```, where **\<player>** is the player's name.

## addTaunt Function Structure

* **name** is the name of your sound, this is basically the "frendly" name that shows under the category
* **sound1.wav** is the path to your sound file (don't include sound/)
* **team** is the team it should belong to (props or hunters); may be a list of teams
* **gender** is the gender of the voice (male, female or both)
* **category** is the categories the taunt should belong to (all categories should be camelCase and not contain spaces)
* **durationOverride** is the length the taunt goes for (you must specify this for mp3)
* **allowedModels** is a table of player model names or paths which should have access to the taunt. If nil (or not specified), all may access the taunt.

```lua
addTaunt(
    "name",
    {
        "husklesph/sound1.wav",
        "husklesph/sound2.wav"
    },
    "team",
    "gender",
    {
        "category1",
        "category2"
    },
    durationOverride,
    allowedModels
)
```

Each addTaunt adds one entry to the list which when clicked will randomly play one of the sound files

## Examples

* This shows adding the sound "Farts" under the category "farts" for both genders.

```lua
addTaunt(
    "Farts",
    {
        "husklesph/fart1.mp3",
        "husklesph/fart2.mp3"
    },
    "props",
    "both",
    { "farts" },
    5
)
    -- NOTE the 5 specifying the length, this is required for mp3s
```

* This shows adding the sound "Get the hell out" under the category "talk" for only male characters.

```lua
addTaunt(
    "Get the hell out",
    {
        "vo/npc/male01/gethellout.wav"
    },
    "props",
    "male",
    { "talk" }
)
```

* This shows adding the sound "Zombie Growl" under the category "zombie" and "growls" for both genders.

```lua
addTaunt(
    "Zombie Growl",
    {
        "npc/zombie/zombie_alert1.wav",
        "npc/zombie/zombie_alert2.wav",
        "npc/zombie/zombie_alert3.wav"
    },
    "props",
    "both",
    {
        "zombie",
        "growls"
    }
)
```

* This shows adding the sound "Radio" under the tab or category "music" with the lenght of 39 seconds.

```lua
addTaunt(
    "Radio",
    { "music/radio1.mp3" },
    "props",
    nil,
    {"music"},
    39
)
```

* Here is a full example of what a file should look like:

```lua
local menu_tab = {"My Menu Tab"}
local path = "husklesph/player_folder/"

-- Arrays

local arrayWithABunchOfFiles = {
    path .. "ABunchOfSoundFiles_1.ogg",
    path .. "ABunchOfSoundFiles_2.ogg",
    path .. "ABunchOfSoundFiles_3.ogg",
    path .. "ABunchOfSoundFiles_4.ogg",
    path .. "ABunchOfSoundFiles_5.ogg",
    path .. "ABunchOfSoundFiles_6.ogg",
    path .. "ABunchOfSoundFiles_7.ogg",
    path .. "ABunchOfSoundFiles_8.ogg",
    path .. "ABunchOfSoundFiles_9.ogg",
    path .. "ABunchOfSoundFiles_10.ogg",
    path .. "ABunchOfSoundFiles_11.ogg",
    path .. "ABunchOfSoundFiles_12.ogg",
    path .. "ABunchOfSoundFiles_13.ogg",
    path .. "ABunchOfSoundFiles_14.ogg",
    path .. "ABunchOfSoundFiles_15.ogg",
    path .. "ABunchOfSoundFiles_16.ogg",
    path .. "ABunchOfSoundFiles_17.ogg"
}

-- Add Taunt Functions

addTaunt("A lot of sounds", arrayWithABunchOfFiles , "props", "both", menu_tab )
addTaunt("Only one file", { path .. "mySingleFileSound.ogg"}, "props", "both", menu_tab)
```

Keeping arrays sperate like the one above helps to keep the "addTaunt" section nice and clean, it also helps sort by alphabetical order. The order in which the "addTaunt" occures in this file is how it will how in the taunt menu.
