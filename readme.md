# instagram-clone-with-sass

A clone from instagram styles using Sass

## Theory

# What is SASS? What does SASS stand for?

  It is a preprocessor of CSS that lets you to use things like variables, nested rules, inline imports and more.

# What is a CSS pre-processor?

  CSS preprocessors are scripting languages that extend the default capabilities of CSS. They enable us to use logic in our CSS code, such as variables, nesting, inheritance, mixins, functions, and mathematical operations.

# Why use SASS?

  - It gives you more functionalities.
  - It gives you variables.
  - It uses nested syntax.
  - It includes functions (mixins).
  - It is well documented.
  - You can use loops

# SASS disadvantages?

  - I thas some learning curve.
  - Code is compiled.

# What is a SASS Variable?

  Sass Variables are a way to store information that you want to reuse later. There is also variables in simple CSS using var(--example)

# Explain the SASS variables property with an example.

```
$base: #b458c;
$border: #FAFAFA;

.div {
  border: 1px solid $border;
}
```

# What is a mixin?

A mixin’s name can be any Sass identifier, and it can contain any statement other than top-level statements. They can be used to encapsulate styles that can be dropped into a single style rule; they can contain style rules of their own that can be nested in other rules or included at the top level of the stylesheet; or they can just serve to modify variables.

```
@mixin main-component {​​margin: 0;padding: 0;list-style: none;}​​
```

# What is SCSS? Give an example
  The SCSS syntax uses the file extension .scss. With a few small exceptions, it’s a superset of CSS, which means essentially all valid CSS is valid SCSS as well. Because of its similarity to CSS, it’s the easiest syntax to get used to and the most popular.
```
div {
  color:#000;
  .a{
      text-decoration: none;
  }
}
```


# What is the difference between .scss and .sass
  .sass doesn't allow you to use css syntax.

# In which cases would we use SCSS? And in which cases would we use SASS?

  - SASS is used when we need a original syntax, code syntax is not required for SCSS.
  - SASS follows strict indentation, SCSS has no strict indentation.
  - SASS has a loose syntax with white space and no semicolons, the SCSS resembles more to CSS style and use of semicolons and braces are mandatory.
  - SASS file extension is .sass and SCSS file extension is .scss.
  - SASS has more developer community and support than SCSS.

# Explain how traditional CSS and Preprocessed CSS workflows are different.

  The traditional CSS are getting by the html, match the coincidences and aply the styles. The preprocessed CSS, in develop before you upload your app to the server, you need to compile the scss or sass to a css file that the browser understand it.

# Can we create functions with SASS? If it is true, give an example.

  Functions allow you to define complex operations on SassScript values that you can re-use throughout your stylesheet. They make it easy to abstract out common formulas and behaviors in a readable way.

```
body
  @function pow($base, $exponent) {​​
  $result: 1;
  @for $_ from 1 through $exponent {​​
    $result: $result * $base;
  }​​
  @return $result;
}​​

.sidebar {​​
  float: left;
  margin-left: pow(4, 3) * 1px;
}​​
```

# What is nesting? Is it useful? Give an example of nesting

  When writing HTML you've probably noticed that it has a clear nested and visual hierarchy. CSS, on the other hand, doesn't.
  Sass will let you nest your CSS selectors in a way that follows the same visual hierarchy of your HTML.

```
nav {​​
  ul {​​
    margin: 0;
    padding: 0;
    list-style: none;
  }​​

  li {​​ display: inline-block; }​​

  a {​​
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }​​
}​​
```

# Why use @import?
  Sass extends CSS's @import rule with the ability to import Sass and CSS stylesheets, providing access to mixins, functions, and variables and combining multiple stylesheets' CSS together. Unlike plain CSS imports, which require the browser to make multiple HTTP requests as it renders your page, Sass imports are handled entirely during compilation.

# How can we import other CSS/SASS files in SASS? Give an example

```
@import 'foundation/code', 'foundation/lists';
```

# Explain the concept of inheritance in SASS.

  Using @extend lets you share a set of CSS properties from one selector to another. It helps keep your Sass very DRY. In our example we're going to create a simple series of messaging for errors, warnings and successes using another feature which goes hand in hand with extend, placeholder classes. A placeholder class is a special type of class that only prints when it is extended, and can help keep your compiled CSS neat and clean.

# Why use @extend? Give an example

  You can extend most simple CSS selectors in addition to placeholder classes in Sass, but using placeholders is the easiest way to make sure you aren't extending a class that's nested elsewhere in your styles, which can result in unintended selectors in your CSS.

```
/* This CSS will print because %message-shared is extended. */
%message-shared {​​
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}​​

// This CSS won't print because %equal-heights is never extended.
%equal-heights {​​
  display: flex;
  flex-wrap: wrap;
}​​

.message {​​
  @extend %message-shared;
}​​

.success {​​
  @extend %message-shared;
  border-color: green;
}​​

.error {​​
  @extend %message-shared;
  border-color: red;
}​​

.warning {​​
  @extend %message-shared;
  border-color: yellow;
}​​
```