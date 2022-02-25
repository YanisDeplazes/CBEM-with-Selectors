# BEM #
The Block, Element, Modifier (BEM) methodology is a popular naming convention for classes in HTML and CSS. 
### 1. Container ###
Some blocks and elements needs a parent container for styling, which is used outside of the block. It feels slightly wrong to call it something like .block__container and have it placed outside the .block block itself.
### 2. Class everything ###
BEM dictates that you should add classes to each element in a component. 

# CBEM with Selectors - Enhanced BEM Methodology #
**CBEM with Selectors - Enhanced BEM Methodology** is not officialy created by the BEM author and is just a methodology that I'm using additionaly to BEM in order to make using CSS a bit easier.
CBEM with Selectors is an extension to the BEM Methodligy to avoid the main problems you get while using BEM. CBEM is using **Container**, **Block**, **Element** and **Modifier** as it's main structure. Container alows to add a Container around a block with a specific naming convention. 
## Reusable and Specific HTML Elements ##
To save code we have to ask ourselves for each element if the code has to be reusable and specific. To apply this correctly, you need to fully understand the design and prototype before implementing a website, otherwise there could be complications.
### Reusable ####
Reusable HTML Elements which can occure more than once within a site. 
### Specific ###
Speficic HTML Elements which is dentified with it's `class` or `id`.

## Selectors ##
In CSS, selectors are patterns used to select the element(s) you want to style. 
### Child Elements ###
Using the `>` to identify child elements with their parents. 
### multiple classes ###
Using the `class1.class2` to identify modifier depending on their parents class. 

[All Selectors](https://www.w3schools.com/cssref/css_selectors.asp)

# Container #
In order to use a container above a block or element we use a dash `-` r to make it clear that it relates to your block. This is used to name a parent HTML element of a Block or Element. Used to name Wrapper, Container, etc of a block.
## HTML ##
```
<div class="block-container">
   <div class="block-wrapper">
      <div class="block">
      </div>
   </div>
</div>
```
## CSS ##
```
.block-container{

}
.block-wrapper{

}
```
# Block #
Standalone entity that is meaningful on its own. 

## HTML ##
```
<nav>
</nav>
<nav class="navigation">
</nav>
<nav id="navigation">
</nav>
```
## CSS ##

### Reusable Block ###
Selects all `<nav>` blocks.
```
nav {
  
}
```
### Specific Block ###
Select the block with the ID `navigation`.
```
#navigation {
  
}
```
### Reusable & Specific Block ###
Select all blocks with the class `navigation`.
```
.navigation {
  
}
```
# Elements #
A part of a block that has no standalone meaning and is semantically tied to its block. Depending on whether you want to use it in relation to its parent, you can use the selector to create a relationship within the CSS.

## HTML ## 
```
<div class="block">
   <span></span>
   <div class="block__element"></div> 
   <div class="block__element"></div>
</div>
```
##  CSS ##
###  Reusable Element with Selector ###
Selects all `<span>` elements where the parent is a `.block` element.
```
.block > span{
   
}
```
### Reusable & Specific Element with Selector ###
Select all elements with the class `block__element` where the parent is a `.block` element.
```
.block > .block__element{
   
}
```
### Reusable & Specific Element ###
Select all elements with the class `block__element`.
```
.block__element{

}
```
# Modifier #
A flag on a block or element. Use it to change the appearance or behavior. Depending on whether you want to use it in relation to its parent, you can use the selector to create a relationship within the CSS. In the BEM method, you normally name the block inside the modifiers classname, but to save lines of code, we only use the modifier name, and if it refers to its parent, we use the specific reusable modifier selector.

## HTML ##
```
<div class="block">
   <div class="block__element modifier"></div>
   <div class="block__element modifier"></div>
</div>
```
## CSS ##
### Reusable & Specific Modifier with Selector ###
Selects all modifiers with both `block__element` and `modifier` set within its class attribute.
```
.block__element.modifier{

}
```
### Reusable & Specific Modifier ### 
Select all modifiers with the class `modifier`.
```
.modifier {

}
```
