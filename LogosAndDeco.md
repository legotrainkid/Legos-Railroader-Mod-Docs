# Lego's Logos and Decos 

# Setup

To start, download the example mod on the logos and decos mod page, and unzip it into an easy to use location. 

Next, open the info.json file in a text editor. This file is where you’ll set up basic details like your mod name, description, and version number.
Make sure to change all the marked values, or it will cause errors and conflicts. Next, zip up the main folder and drag and drop it onto Unity Mod Manager to install it 

![image](https://github.com/user-attachments/assets/edcce07f-1dd8-4f08-aa61-cbf201b78436)


In order to design your liveries, you need to setup railroader to allow access to the definition editor. First, open steam and navigate to railroader. 
Then, right click the game, and select properties from the menu. In the general tab, type /editor into the launch options at the bottom, 
and close the menu. Now when you launch railroader, there will be a new option on the main menu called editor.
![image](https://github.com/user-attachments/assets/52233a1a-f5d1-4317-9b39-4efd3883fef4)


We need to move the rolling stock we want to edit to our assetpacks folder in appdata. First, open the railroader files and navigate to \Railroader_Data\StreamingAssets\AssetPacks. 
Find the rolling stock you want to use, and copy their folders. Now, navigate to %appdata%\LocalLow\Giraffe Lab LLC\Railroader\AssetPacks, and paste the folders.
![image](https://github.com/user-attachments/assets/903a7998-f217-49e7-ab80-19760c615747)



# Livelries and Components

To start creating your livery, open the editor in railroader, and use the menu in the top left to select the rolling stock you wish to use.
![stuff](https://github.com/user-attachments/assets/bff0be4e-fecf-4357-943b-92cc5ebd9c2d)

![image](https://github.com/user-attachments/assets/89b9b1f3-2d2e-497b-b754-600a559818b0)


Next, select the add component dropdown and scroll to the bottom the find the newly added components, CustomImage, ColorPainter, ColorableImage, and  the Set and Custom Textboxes. Each component has a debug checkbox 
that shows you where the component is currently located. Use this to position the components on your rolling stock, but make sure to turn off the debug and hit save when you are done.
![image](https://github.com/user-attachments/assets/4ef07c11-c3fa-48a4-8b09-c0679efed781)


To add an image to your rolling stock, you need to first add the image to your mod. Make sure it’s a .png file with a transparent background, then put the file in the LegosLogosFolder in your mod. 
Make sure to zip and reinstall the mod for it to load in UMM. Then, when you boot the game, open up the log file and find the ID for your image. Then, copy and paste it into the texture
value on the custom image component. This is also the same process for the custom colorable texture component, you just need to make sure the image is white with a transparent background instead.
![image](https://github.com/user-attachments/assets/e927fc65-d90c-4682-a62e-6015b6e6eb2a)
![image](https://github.com/user-attachments/assets/28becb22-b18c-45b3-9d6b-5485499dd07a)

If the game cannot find the specified texture, the component will remain as the debug cube regardless of whether or not the debug option is checked

To use the color painter component, simply place it over where you would like to set the color using the debug option, and select where you would like it to use the secondary color or not.
![image](https://github.com/user-attachments/assets/91d0f5a4-2b6c-49b7-be3a-5b24b7dadef5)


Using the text boxes is also pretty easy, position them to same way as the other components, and if you are using the SetText component, fill in your text to whatever you would like.
![image](https://github.com/user-attachments/assets/277ec081-1f9c-466d-8d13-1d0b53e6cf94)

A note for all components. They work using a unity system called decal projecters, with will "project" onto whatever surfaces are in the bounding box. They project in the direction of the blue arrow, and I have noticed some weird shader atrifacts may happen if the texture is being projected the wrong way. It will also flip text and images if oriented wrong.
![image](https://github.com/user-attachments/assets/3eb508a6-2bc2-46e5-b2e8-90bb4298fd23)

## 1.1.0 Update

There are 2 new values added in this update, Priority and ColorLevel

Priority tells Unity what order to render the decals in. Lower numbers (below 0) will be rendered first, higher numbers will be rendered last. Lettering will always be priority 0. 
Decals with the same priority will be rendered in an upredictable order

ColorLevel is the new system for telling the ColorPainter and ColorableImage what color to use. There are now 6 total colors, the 2 base game colors, and 4 new ones. The new ones start at 0, and the last one is 3
The base game colors are -1 (Base) and -2 (Lettering).

## Using Component Groups (Added in Library of Stuff V-1.4.0)

To add a component group, simply change the Runtime Editing of Definnitions JSON to create one instead of cloning the locomotive:

Old:
```json
{
    "identifier": "ne-caboose02",
    "newIdentifier": "ne-caboose02-legos-custom",
    "name": "Early Steel Caboose (Lego's Custom Paint)",
    "description": "An early steel caboose with a custom paint scheme",
    "clone": true,
    "cloneDefault": true,
    "bulkAdds": [
```

New:
```json
{
    "identifier": "ne-caboose02",
    "clone": false,
    "MakeComponentGroup": true,
    "GroupName": "Lego's Custom",
    "GroupID": "lego-custom",
    "bulkAdds": [
```

# Packaging the Mod

Now that your livery is done, it’s time to package it up into a mod you can share. My Library of Stuff mod adds a way for definitions to be changed at runtime, 
so that you don’t have to worry about files being overwritten or showing people where to put the folder. All you have to do is make a UMM mod, and do some extra setup with the files. 
In the mod template project there is a example-clone.json file you can use as a template. First, change the identifier to be the identifier of the rolling stock you made a livery for. 
Next, create a new identifier for the new object. The easiest way is to make it the vanilla id-the name for your livery (eg, ld-sw1-legos-2tone) . Keep in mind you cannot use spaces in the identifier. 
Next, open up the definition for the rolling stock (in %appdata%\LocalLow\Giraffe Lab LLC\Railroader\AssetPacks) and scroll to the bottom to find all the components you just added for your livery. 
Copy and paste the components into the square brackets after bulkAdds, and make sure you get all the curly brackets for the components. You may want to double check your JSON afterwards, 
you can use a free website like JSONLINT, which will format it nicely for you as well. Once you save and zip up your mod, it is ready to share!
![image](https://github.com/user-attachments/assets/7e4e8296-dfad-441a-a6be-ef0fc4b93128)


# LIST OF COMPONENTS

## Custom Image

## Colorable Texture

## Color painter

## Set Text

## Custom Text
