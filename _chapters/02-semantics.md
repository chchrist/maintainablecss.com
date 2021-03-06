---
layout: chapter
title: Semantics
section: Background
permalink: /chapters/semantics/
description: Why naming something based on what it is, instead of how it looks or behaves is a cornerstone of writing well architected and maintainable CSS code.
---

Summary: Name something based on what it *is*, not how it *looks* or *behaves*.

## The longer explanation

Semantic HTML isn't just about the elements we use. It's quite obvious that we should use `<a>` for links, `<table>` for tabular data and `<p>` for paragraphs etc.

What's not quite so obvious is the values we give to class names (and IDs). These attributes allow us to enhance a web page with style (and behaviour) using CSS (and Javascript).

> &ldquo;There are only two hard things in Computer Science: cache invalidation and naming things.&rdquo;
<br>&mdash; <cite>Phil Karlton</cite>

It's important to get naming right. Humans are not so good at understanding abbreviated, non-semantic abstractions.

## Good and bad class names

Can you spot the difference between semantic and non-semantic class names?

	<!-- non semantic -->
	<div class="red pull-left">
	<div class="grid row">
	<div class="col-xs-4">

	<!-- semantic -->
	<div class="basket">
	<div class="product">
	<div class="searchResults">

Non semantic classes don't tell you *what* the HTML represents. At best, they give you an idea of what the elements look like (at certain screen sizes), but that's all.

Semantic classes have a much clearer meaning. They don't tell you what they look like, but that's okay. That's what CSS is for. Semantic class names mean something to HTML, CSS, Javascript and automation test scripts.

There are many reasons why semantic class names are advantageous:

## 1. Because their intention is clear

The intention of a semantic class name is clear, whether you're viewing the HTML or the CSS. Understanding the intention of an element when it has a sprinkling of visual classes is far less clear. At most you'll have a vague understanding of the stylistic intentions.

## 2. Because it's easier to build responsive sites

Styles often change based on viewport size. For example, you might float elements on big screens but not on small screens. If you have, for example, a class called `clearfix` but it doesn't clear on small screens, your code is misleading.

If you use semantic class names, then you can style them differently based on media queries making it easier to maintain.

## 3. Because they are easier to find

Non semantic classes such as `.red` and `.pull-left` will be scattered all over the code. This means a search will yield many results, making it hard to find a particular portion of HTML.

On the other hand, searching for a semantic class will find the HTML in question. And if you're inspecting an element, finding the related CSS will be far easier.

## 4. Because they reduce the risk of regression

When you edit a class that describes *style*, the change will propogate to every single element with that class. Knowing CSS as you do, do you feel comfortable that you didn't cause unexpected problems elsewhere?

Semantic class names are unique, so when editing one, you'll feel confident that your change only applies to the module in question, making maintenance easier.

## 5. Because you want to be confident in making changes

When you don't feel confident changing code, you either cause problems or you avoid it altogether. The latter means that you'll end up with redundancy which itself causes maintenance issues.

## 6. Because they provide hooks for automated tests too

Automated functional tests work by searching for and interacting with elements. This may include:

1. clicking a link;
2. finding a text box;
3. typing in text;
4. submitting a form; and then
5. verifying some criteria.

Visual class names don't allow you to target specific elements because they're applied to multiple. What I've seen people do in this case is apply an extra semantic class name just so the tests can work.

## 7. Because they provide hooks for Javascript too

Semantic class names are useful for Javascript too. We can't use visual class names as a reliable way to target elements for enhancement.

## 8. Because they don't need maintaining

If you name something based on what it is, you won't have to update the HTML again. A heading is always a heading, no matter what it *looks* like. The styling might change but this only requires a CSS update. This is known as Loose Coupling which improves maintainability.

## 9. Because they are easier to debug

If you use visual class names, when inspecting an element there will be several applicable CSS selectors. This means you have to wade through many more lines of code. With semantic class names there will be just one.

## 10. Because the standards recommend it

On using the class attribute, HTML5 specs say in 3.2.5.7:

> "[...] authors are encouraged to use values that describe the nature of the content, rather than values that describe the desired presentation of the content."

## 11. Because they encourage lean HTML

This is a small benefit but when an element has only one class, the HTML will be smaller. And whilst the CSS might get a little bigger, it's cacheable.

<!--## Because visual class names might declare the same property!

It's likely that several different utility classes could refer to the same property meaning order matters and performance degrades.

Think of an example of this.
-->

## Final thoughts on semantics

Semantic class names are a corner stone of *MaintainableCSS*. Without this, everything else makes little sense. So name something based on what it is and everything else follows.
