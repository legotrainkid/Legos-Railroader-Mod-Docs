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

