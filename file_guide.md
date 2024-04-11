# File Guide
This section defines the files of the game, as well as their function.

# Main Files
.gitignore - Like its name, you should ignore this file. It only serves to specify which files that the Git backup system shouldn't back up. \n
LICENSE - The GNU General Public License. Specifies freedom to copy, modify, and reproduce the original files.
README.md - Landgreen's minimal description of n-gon. README files contain necessary information about the project that the end user should know.
Favicon.ico - The icon that appears in the page's tab.
index.html - The HTML index. Defines the elements on the page as well as some properties. Ties the whole site together. 
style.css - Contains various style and metadata properties linked to index.html.
todo.txt - Landgreen's to-do list. Contains the content that will be included in future updates, as well as some exclusive lore.
# Main Files - img
This folder contains all of the images used to display with the tech. I'm not listing all of them here, there are like hundreds.
# Main FIles - js
bullet.js - Defines the physics for all bullets used in the game, such as nails or super balls. Don't edit this unless you're adding a new GUNtech.
engine.js - Source code for n-gon's custom game world engine. Defines the overarching physics rules for every object to follow, such as collisions.
index.js - The javascript index. Defines several utility methods used throughout most files, such as `shuffle.array().`
level.js - Responsible for defining every official and player-made level in the game, as well as preloading and displaying the rooms.
lore.js - Handles all lore logic in the game. Defines the `null` room lore conversations and the such.
mob.js - Defines the shape, abilities, and properties of every mob in the game. This file is frequently called on by level.js because it also contains the functions used to spawn mobs at a certain position.
player.js - Contains the properties, abilities, and logic for `m.` It is recommended not to change this file unless you know what you're doing and have it backed up.
powerup.js - Contains the logic for lasting effects as caused by tech, such as 
