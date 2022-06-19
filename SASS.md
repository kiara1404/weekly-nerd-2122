### Introduction
A couple of speakers during the Weekly Nerd mentioned working with SASS. During my studies I've heard it quite some time but I still don't really have a clue what it is exactly. So I thought this would be a perfect subject for my third article.

### What's SASS?
Sass stands for Syntactically Awesome Stylesheet. It's a CSS preprocessor that gives your CSS superpowers. 
Writing CSS nowadays can be tedious at times, many times you'll find that you're repeating yourself often.

Basically, CSS is missing some features that would help turn it into an easier to use method.Sass comes to the rescue in this situation. It helps you stick to the DRY method. Sass adds variables, nesting, partials, mixins and Extends and Operators. Some things that programming languages tend to have. I will explain these further in the article.

Sass provides a compiler that allows us to write stylesheets in to different syntaxes:
* Indented syntax. This is the older syntax and gets rid of the curly braces and semi colons. It has a `.sass` file extention.

```css
nav
  ul
    margin: 0
    padding: 0
    list-style: none

  li
    display: inline-block

  a
    display: block
    text-decoration: none

```

* SCSS syntax. This is the newer and more popular syntax. It looks alot like the CSS3 syntax. You can actually write regular CSS with some extra functionalities. It has a `.scss` file extention. It's often termed as _Sassy CSS_
```css
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }
  li {
    display: inline-block;
  }

  a {
    display: block;
    text-decoration: none;
  }
}
```

### How does it work?

#### Variables
Sass allows you to define variables. This allows you to use the variable multiple times and changing the colour would be a lot faster.
```css
$heading_primary: #efefef;

h1{
    color: $heading_primary;
}
```
#### Nesting
In CSS you can't nest and often you are repeating code. In Sass you can nest:
```css
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }
}
```
#### Partials
Partials are files that have an underscore in the beginning of the filename. For example: `_test.scss`. This means that this file should not be compiled into CSS. These files will contain snippets of CSS that can be imported by other SCSS files. 
This allows you to work modular and keep things more organized and managable.

#### Mixins
Another  issue with CSS is that you'll often use a similar group of styles. Mixins allow you to encapsulate a group of styles, and apply those styles anywhere in your code using the @include keyword.

```css
@mixin transform($property) {
  -webkit-transform: $property;
  -ms-transform: $property;
  transform: $property;
}
.box { @include transform(rotate(30deg)); }
```

Instead of typing `rotate(30deg)` three times, you can create something that feels like a function.

#### Extends
Extend allows you to take the style from one element into another. The @extend diretive works like mixins in that you're able to share snippets of code across your stylesheet. It's useful for sharing sets of related properties that get repeated.

```css
.btn--primary {
  background-color: #333;
  border-radius: 5px;
  text-transform: uppercase;
}
.btn--callout {
  @extend .btn;
}
.btn--info {
  @extend .btn;
}
```
#### Operators
Sass adds mathematical operators, such as +,-,* etc.

```css
@use "sass:math";

@function pxToRem($pxValue) {
  @return math.div($pxValue, 16px) * 1rem;
}

div {
  width: pxToRem(480px); // gives 30rem
}
```


## Conclusion
There are a lot of new aspects to learn about Sass but if you have a basic understanding about programming, it wouldn't be too difficult. I think there are quite some benefits such as mixins, extend and partials to keep your code a lot cleaner.  I think I would like to try it out in future projects!

## Sources
* https://www.geeksforgeeks.org/what-is-the-difference-between-css-and-scss/
* https://sass-lang.com/guide
* https://medium.com/swlh/learn-the-scss-sass-basics-in-5-minutes-73002653b443
* https://www.freecodecamp.org/news/the-beginners-guide-to-sass/