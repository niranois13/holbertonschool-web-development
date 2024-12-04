CSS, advanced

![css_logo](https://i.imgur.com/S6ETT92.png)

This repo contains all files needed to fulfill Holberton's project: CSS, avanced.
The purpose of this project is to recreate the design of a web page from a figma.
Doing so, I have learned CSS principles and basics.

This project uses the HTML structure made in the HTML, advanced project.

Learning objectives:

What is CSS : Cascading Style Sheets, CSS, is a stylesheet language. It is used to describe how a web page will be presented and rendered.

How to add style to an element: To style a HTML element, in your CSS file, you need to refer to a specific selector of said HTML element you want to design and then give it the ruleset you want to apply.
For example, to make the text of all paragraph blocks red : 
`p {
    color: red;
}`

What is a class: A class is a type of selector. It allows to apply a specific ruleset to all element having the same class selector. You can have multiple instance of a class, that allows reusability of a ruleset.

For example, let's consider this HTML block:

```
<h1 class="red_text">Title</h1>
<h2>Sub title</h2>
<p class="red_text">Some text</p>
```

with this CSS ruleset:

```
.red_text {
    color: red;
}
```

The h1 and p will be written in red, not the h2.

What is a selector: A selector allows to select specific HTML elements.

There are many CSS selectors, here are the main ones:
- Element selector to select a HTML element: `p` will select all `<p>`.
- Class selector to select all HTML elements having the specified class attribute: `.red` will select all element having the attribute `class="red"`.
- ID selector to select a HTML element having this specified ID attribute. Each ID should be unique: `#modal_button` will select the element having the attribute `id="modal_button"`.
- Attribute selector to select all HTML elements shring the same attribute: `a[href]` will select all elements `a` having a `href`attribute.
- Pseudo-class selectors to select a specified element in a specified state. `a:hover` selects all links on `hover` state.

How to compute CSS Specificity Value: In CSS, specificity defines the priority of style appliance. It s used to debug and write CSS effectively. It is declared as a set of numbers noted (A, B, C, D), where:
- A represents an inline style applied to an element (`<p style="color: red;">`). Its value is 1 if an inline style exists, 0 otherwise.
- B is the number of ID selectors in a CSS ruleset.
- C is the number of class, pseudo-class and attributes selectors in a CSS ruleset.
- D is the number of elements and pseudo-elements selectors in a CSS ruleset. 
To compute the specificity value, we have to count the number of each. We just have to compare each specificity values to understand which CSS ruleset will apply first to an element. A takes precedence over everything else, (therefore, inline styles apply above anything else). In case two rulesets have the same specificity, the latter will aplly to the selected element. the rule `!important` overrides everything.

What are Box properties in CSS:
In CSS, every elements are define in a Box Model, a rectangle with those specificities:
- Content: the inside of this box, where text, images and other content are displayed.
- Padding: the space between the content and its border. Increasing padding adds inner spacing.
- Border: the boundarie between the content (or padding if any) and the margin.
- Margin: space around the border, creating space between elements.
A lot of properties exist in CSS to control this Box Model. By knowing and understanding them, you can have a total control on the layout of a web page.

How does the browser load a webpage: 
I will start this explanation at the rendering step, after the DNS resolution and HTTP requests (amongst other steps). I will ommit JavaScript role here.
When receiving the response of the HTTP request the browser will start building the web page:
- The browser will parse the HTML sequentially and build the DOM (Document Object Model), a tree representation of the HTML.
- The browser will parse the CSS sequentially (inline styles and external stylesheet) and build the CSSOM (CSS Object Model), a tree representation of the CSS.
- The browser will combine the DOM and the CSSOM in the Render Tree, a visual representation of the web page.
- Reflow: The browser will calculate and position the layout baed on the Render Tree informations.
- The browser then converts the Render Tree in pixels and applies the layout.
- In parrallel to all this, the browser downloads all images, videos and non critical ressources.