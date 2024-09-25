# Lego's Library of Stuff

A libray mod that has a lot of useful tools and functions for modding. 

# Adding Custom Components

To add a component, use the static method LibraryOfStuff.AddNewComponent(Type baseClass, string typeIdentifier, Type type, IComponentBuilder builder)   

baseClass - typeof(Component)  
typeIdentifier - Whatever you want to call your component, should match the one in your components JSON  
type - typeof(YourComponent)  
builder - A class that inherits the IComponentBuilder interface  

## Example

Component

![image](https://github.com/user-attachments/assets/d74d4ba0-c046-4244-90f8-a7fbc142cb3e)  

Component Builder  

![image](https://github.com/user-attachments/assets/51668cd0-bd6c-4db9-89fb-f38b0c1e2566)


# Utilizing the Runtime Editing of Definitions (RED)

RED allows you to edit the definition files of rolling stock at runtime without actually changing the JSON files themselves. That means that game updtes won't override your files, and multiple mods can make changes without fighting each other.

To start, create a folder to use as your project folder. Create an info.json file in it, and paste in this JSON code  
```
{
  "Id": "CHANGE THIS",
  "DisplayName": "CHANGE THIS",
  "Author": "CHANGE THIS",
  "Version": "1.0.0",
}
```

Then, create a folder called `LegosLibraryOfStuff`, and inside of that folder create another one called `Definitions`.  

Now, inside the `Definitions` folder, create as many JSON files as you need (Each JSON file can only edit one definition). The JSON code will look like this  
```
{
    "identifier": "DEFINITION TO EDIT",
    "newIdentifier": "NEW DEFINITION'S ID (ONLY USED IF CLONING)",
    "clone": true,
    "name": "DISPLAY NAME FOR THE ROLLING STOCK, LEAVE EMPTY TO KEEP THE CURRENT NAME (UNLESS CLONING)",
    "description": "NEW DESCRIPTION, KEEP EMPTY TO USE CURRENT ONE (UNLESS CLONING)",
    "price": -1,
    "removes": [
        {
            "kind": "COMPONENT KIND",
            "name": "COMPONENT NAME"
        },
        {
            "kind": "COMPONENT KIND",
            "name": "COMPONENT NAME"
        }
    ],
    "adds": [
        {
            "replace": true,
            "component": {
                PASTE YOUR COMPONENT JSON HERE
        },
        {
            "replace": true,
            "component": {
                PASTE YOUR COMPONENT JSON HERE
        }
    ]
}
```

## identifier

The object identifier to edit. If it doesn't exist, nothing will happen (Literally)

## newIdentifier

The new identifier for the object to use, required if cloning, will be ignored otherwise

## clone

Whether or not the edits should take place on the current definition, or it should be copied and the edits made there

## name

The display name for the rolling stock. Leave empty to keep the current one (If you aren't cloning it, otherwise you need a name)

## description

The description for the rolling stock. Leave empty to keep the current one (If you aren't cloning it, otherwise you need a description)

## price

The new price for the rolling stock. -1 keeps the same price, 0 means it is not puchasable.

## removes

The components to remove from the definition. Only removes them if kind and name match.

## adds

The components to add to the definition. If replace is true it will remove any components that have the same name and kind as the added component


