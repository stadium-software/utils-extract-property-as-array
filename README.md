# Extract Property As Array <!-- omit in toc -->

This module allows you to extract a property from a List of objects. Usde it when you have a List of objects, but you only want one of the properties. 

Original
```javascript
[{name: "myname", value: 1}, {name: "anothername", value: 2}]
```

Result
```javascript
[1, 2]
```

~[](images/View.gif)

# Version
Initial 1.0

# Setup

## Global Script
1. Create a Global Script called "ExtractPropertyAsArray"
2. Add the input parameters below to the Global Script
   1. ListOfObjects
   2. PropertyToExtract
3. Add the output parameter below to the Global Script
   1. Result
4. Drag a *JavaScript* action into the script
5. Add the Javascript below into the JavaScript code property
```javascript
/* Stadium Script v1.0 https://github.com/stadium-software/utils-extract-property-as-array */
let arrayOfObjects = ~.Parameters.Input.ListOfObjects;
let propertyToExtract = ~.Parameters.Input.PropertyToExtract;
return arrayOfObjects.map((a) => a[propertyToExtract]);
```
6. Drag a *SetValue* action under the Javascript action
   1. Target: ~.Parameters.Output.Result
   2. Source: ~.JavaScript

## Event Handler or Script
1. Drag the "ExtractPropertyAsArray" into an event handler or script
2. Provide the inputs
   1. ListOfObjects: A List of objects (e.g. text, value pairs, for example)
   2. PropertyToExtract: The name of the property to extract into a separate List (e.g. value)
3. The script returns the extracted property as a simple list

## Working with Stadium Repos
Stadium Repos are not static. They change as additional features are added and bugs are fixed. Using the right method to work with Stadium Repos allows for upgrading them in a controlled manner. How to use and update application repos is described here 

[Working with Stadium Repos](https://github.com/stadium-software/samples-upgrading)