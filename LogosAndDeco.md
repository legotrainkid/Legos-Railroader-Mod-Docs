# Lego's Logos and Decos 

# Setup

To start, download the template mod, and unzip it into an easy to use location. 

Next, open the info.json file in a text editor. This file is where you’ll set up basic details like your mod name, description, and version number.
Make sure to change all the marked values, or it will cause errors and conflicts. Next, zip up the main folder and drag and drop it onto Unity Mod Manager to install it

In order to design your liveries, you need to setup railroader to allow access to the definition editor. First, open steam and navigate to railroader. 
Then, right click the game, and select properties from the menu. In the general tab, type /editor into the launch options at the bottom, 
and close the menu. Now when you launch railroader, there will be a new option on the main menu called editor.

We need to move the rolling stock we want to edit to our assetpacks folder in appdata. First, open the railroader files and navigate to \Railroader_Data\StreamingAssets\AssetPacks. 
Find the rolling stock you want to use, and copy their folders. Now, navigate to %appdata%\LocalLow\Giraffe Lab LLC\Railroader\AssetPacks, and paste the folders.

# Livelries and Components

To start creating your livery, open the editor in railroader, and use the menu in the top left to select the rolling stock you wish to use. Next, select the add component 
dropdown and scroll to the button the find the newly added components, CustomImage, ColorPainter, ColorableTexture, and  the Set and Custom Textboxes. Each component has a debug checkbox 
that shows you where the component is currently located. Use this to position the components on your rolling stock, but make sure to turn off the debug and hit save when you are done.

To add an image to your rolling stock, you need to first add the image to your mod. Make sure it’s a .png file with a transparent background, then put the file in the LegosLogosFolder in your mod. 
Make sure to zip and reinstall the mod for it to load in UMM. Then, when you boot the game, open up the log file and find the ID for your image. Then, copy and paste it into the texture
value on the custom image component. This is also the same process for the custom colorable texture component, you just need to make sure the image is white with a transparent background instead.

To use the color painter component, simply place it over where you would like to set the color using the debug option, and select where you would like it to use the secondary color or not.

Using the text boxes is the also pretty easy, position them to same way as the other components, and if you are using the SetText component, fill in your text to whatever you would like.

# Packaging the Mod

Now that your livery is done, it’s time to package it up into a mod you can share. My Library of Stuff mod adds a way for definitions to be changed at runtime, 
so that you don’t have to worry about files being overwritten or showing people where to put the folder. All you have to do is make a UMM mod, and do some extra setup with the files. 
In the mod template project there is a sample.json file you can use as a template. First, change the identifier to be the identifier of the rolling stock you made a livery for. 
Next, create a new identifier for the new object. The easiest way is to make it the vanilla id-the name for your livery. Keep in mind you cannot use spaces in the identifier. 
Next, open up the definition for the rolling stock (in %appdata%\LocalLow\Giraffe Lab LLC\Railroader\AssetPacks) and scroll to the bottom to find all the components you just added. 
Copy and paste the components into the square brackets after bulkAdds, and make sure you get all the curly brackets for the components. You may want to double check your JSON afterwards, 
you can use a free website like JSONLINT, which will format it nicely for you as well. Once you save and zip up your mod, it is ready to share!

# LIST OF COMPONENTS

## Custom Image

## Colorable Texture

## Color painter

## Set Text

## Custom Text
