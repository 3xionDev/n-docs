# How to create a map

One thing that most n-gon players want to try their hand at is map design. If you enable community maps, you will see that there are some very skilled creators in the community who have made some very impressive maps, as well as some not so good maps (yinyang).

This section will teach you how to create a very basic map and will teach you the core method behind designing an n-gon map.
____
### Prerequisites

You will need:

A desktop or laptop computer

Internet access

Website console access (specifically site console)

A text editor (Notepad and TextEdit are both fine)

Time

___
### Step 1

To start, create a local copy of n-gon. This can be done simply by downloading the source code from the Github repo. Go to the repo's home page, click "Code," and hit "Download Zip." Once it's done, extract the zip archive into your desktop, which will allow for easy access to all of the files.

### Step 2

Once you've finished step 1, open the extracted archive and enter the folder titled "js." Locate "level.js" and open it using a text editor of your choice. Find the code snippet that says `template() {`, which should be around line 2101. Replace "template" with the desired level name.

Find the line `level[simulation.isTraining ? "walk" : "initial"]()`, around line 73. Replace `"initial"` with `"your level name"`. This will force the game to boot into your level instead of the starting room.

### Step 3

Save and exit "level.js" and exit the "js" folder. Locate "index.html" and open it with your browser. Depending on your operating system, you may have to do extra steps for this. For the sake of time, I won't be explaining how to do this since it varies by operating system, so, if you need help, look up "how to run html files on (your OS)."

Opening the HTML file will boot your local copy of n-gon. Start the game. You'll notice that you're not in the spawn room but in a white void with a platform. This is what the template level looks like.

Open the javascript console. You can do this by pressing `ctrl+shift+i`, which will open the inspect element. From there, navigate to the JS console by pressing on the "console" tab in the top bar of the inspect window.

Once you've opened the console, type in `lore.unlockTesting()` and hit enter. This will unlock testing mode, which is a special admin menu normally unlocked by defeating finalBoss and entering the `null` room. To test whether this unlocked it, close the console and press "t." The testing menu should open.

### Step 4

While staying in the game, open the console again. Type in `simulation.enableConstructMode()`. This will turn on Construct Mode, which is n-gon's built in level editor.

### Step 5

Close the console and open testing mode. You should see a white box in the bottom right. This is where your level code will be outputted.

You are now editing the level. To place static ground (the dark grey blocks), click and drag the left mouse button. To create a dynamic (light grey) block, click and drag with the right mouse button. To place a spawn point for a random mob, click on the desired position with the center mouse button.

Notice that your mouse shows the level coordinate that it's currently at as two x-y values hovering over the cursor. These coordinates are used to position everything in the level. They are also used to reposition the level spawn and exit. To reposition the spawn, find the desired position with your cursor, record the coordinates, find the line `level.setPosToSpawn(0, -50);` in the function that defines your level and change 0 to the first (x) value of the coordinates you recorded and change -50 to the second (y) value that you recorded. Reload the page and re-enable construct mode. The spawn will be in the position you selected.

To change the exit position, it's a relatively similar process. Record the desired coordinates, find the line `level.exit.x = 1500;` in your level function, and replace the value with your desired x value. Just below that line, there's another line called `level.exit.y = -1875`. Same drill, replace the value with your desired y value. Upon reloading and re-enabling construct mode, the exit will be in the desired position.

If you want to place a boss spawner, record the coordinates, and find the line `spawn.mapRect(-100, 0, 1000, 100);` in your level function. Add a new line under this and write `spawn.randomBoss(x, y)`, replacing `x, y` with your desired x and y values.

From this point on, you're free to design your own level. Let your creativity run free! Keep in mind that every object placed (including walls) are calculated by the game every frame, which means that excessive objects *will* lag the level. This also counts for mobs. Make a unique level that's balanced and not laggy. Once your level is done, continue on to the next step.

### Step 6

Once your level is finished, it's time to playtest and export the level.

First, we need to copy the level code. While in testing mode, press `ctrl+a`, which will highlight your level code in the white box mentioned earlier. Copy it using `ctrl+c` and go back to your level function. Under `level.customTopLayer = () => { };`, paste your level code. Be sure the indentation is aligned with the rest of the function. Volia, your level is saved.

Next, we need to playtest. Reload the game window, but do not enable testing mode or construct mode. Instead, play the level like it is intended to play. Fix any bugs by re-copying and re-pasting your fixed code over the bugged code. Once all bugs have been resolved, your level is ready to play!

To submit the level as a community map, copy the entire level function and open an issue on the n-gon github page. Paste your code in the description area and title it "New community map: (your map name)," post it, and you're good!

Since landgreen is also a teacher, it will likely take him multiple days to weeks to respond to your submission. Do *not* bug him, and only submit the level once. 

I look forward to seeing your levels!
