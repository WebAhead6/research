# Advanced css

How can we use advanced CSS features to create complex custom components?

1 ) What are "combinator" selectors? Can you provide examples where they're useful?


### Universal selector 
Selects all elements. Optionally, it may be restricted to a specific namespace or to all namespaces.
#### Exapmle
https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors
### Type selector
Selects all elements that have the given node name.
#### Example
https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors
### Class selector
Selects all elements that have the given class attribute.
Syntax: .classname
Example: 
https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors
### ID selector
Selects an element based on the value of its id
#### Example
https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors
### attribute
 There should be only one element with a given ID in a document.

#### Example
https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors

### Attribute selector
Selects all elements that have the given attribute.

#### Example

### Grouping selectors
Selector list
The , is a grouping method, it selects all the matching nodes.
Syntax: `A, B`
Example: `div, span` will match both <span> and <div> elements.

## Combinators

### Descendant combinator
The (space) combinator selects nodes that are descendants of the first element.
Syntax: A B

### Child combinator
The > combinator selects nodes that are direct children of the first element.
Syntax: A > B

### General sibling combinator
The ~ combinator selects siblings. This means that the second element follows the first (though not necessarily immediately), and both share the same parent.
Syntax: A ~ B

### Adjacent sibling combinator
The + combinator selects adjacent siblings. This means that the second element directly follows the first, and both share the same parent.
Syntax: A + B

### Column combinator 
The || combinator selects nodes which belong to a column.
Syntax: A || B
Example: col || td will match all <td> elements that belong to the scope of the <col>.












<hr>
2) What are pseudo-elements? Can you provide examples where they're useful?



starts with the basics
# What are Pseudo-Elements?

> A CSS pseudo-element is used to style specified parts of an element.
For example, it can be used to:[color=#907bf7]
> > * Style the first letter, or line, of an element
> > * Insert content before, or after, the content of an element [color=red]

> Syntax
The syntax of pseudo-elements:

```javascript=+
selector::pseudo-element {
  property: value;
}
```
:arrow_down: 
another example:
### The ::first-line Pseudo-element
The ::first-line pseudo-element is used to add a special style to the first line of a text.

The following example formats the first line of the text in all <p> elements:
```javascript=
Example

p::first-line {
  color: #ff0000;
  font-variant: small-caps;
}
```

:::info
**Notice the double colon notation - ::first-line versus :first-line**

The double colon replaced the single-colon notation for pseudo-elements in CSS3. 
:::


>the Pseudo css comes down to two sections 
>> Pseudo elements [color=red]

> and

>> Psuedo Classes [color=blue]


All CSS Pseudo Elements
	Example	Example description

		


| Selector |Example | Description |
| ------ | ----------- |----------- |
| ::after	   | p::after |Insert something after the content of each <p> element |
| ::before	   | p::before |Insert something before the content of each <p> element|
| ::first-letter| p::first-letter |Selects the first letter of each <p> element |
|::first-line	|p::first-line	|Selects the first line of each <p> element|
|::selection	|p::selection	|Selects the portion of an element that is selected by a user|

lets see a live example!

```javascript=
<!DOCTYPE html>
<html>
<head>
<style>
h1::after {
  content: url(smiley.gif);
}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>The ::before pseudo-element inserts content before the content of an element.</p>

<h1>This is a heading</h1>
<p><b>Note:</b> IE8 supports the content property only if a !DOCTYPE is specified.</p>

</body>
</html>

```
>using the psuedo elemnt of ::after we will get =>
![](https://i.imgur.com/KFgsdtD.png)

:::info
:pushpin: For full list of Psuedo elements and Classes : https://www.w3schools.com/css/css_pseudo_elements.asp
:::

## now that we've grasped what is Psuedo-elements lets take a look at how amazing these can be!


It’s pretty amazing what you can do with the pseudo elements ==::before== and ==::after==. For every element on the page, **you get two more free ones that you can do just about anything another HTML element could do**. They unlock a whole lot of interesting design possibilities without negatively affecting the semantics of your markup.

>basically we can think of this as two layers: heres a clear demonstration of this
![](https://css-tricks.com/wp-content/uploads/2011/06/multiplecanvases.jpg)


another example is maybe 
### **Show URL’s of links in printed web pages**
without changing our markup structure 
![](https://css-tricks.com/wp-content/uploads/2011/06/printpreview.png)

> this is done with
```javascript=
@media print {
  a[href]:after {
    content: " (" attr(href) ") ";
  }
}
```
<br>

a really common use is with
### Apply typographic flourishes
![](https://css-tricks.com/wp-content/uploads/2011/06/typographicflourishheader.jpg)

heres how!
```javascript=
h2 {
  text-align: center;     
}
h2:before, h2:after {
  font-family: "Some cool font with glyphs", serif;
  content: "\00d7";  /* Some fancy character */
  color: #c83f3f;
}
h2:before {
  margin-right: 10px;
}
h2:after {
  margin-left: 10px;
}
```
this is enough for today, make sure you try these amazing features soon!
::: info
:pushpin: for the full more complex examples of this make sure to visit :
https://css-tricks.com/pseudo-element-roundup/ 
:::
<hr>



3)How might you create custom-styled checkboxes using both of the above?



![](https://i.imgur.com/EvRsSRZ.jpg)
![](https://i.imgur.com/qfMtcdK.png)
![](https://i.imgur.com/Pu8cGre.png)
![](https://i.imgur.com/VvUSFNF.jpg)
![](https://i.imgur.com/dmFdIon.png)
