# Frontend Mentor - Recipe page solution

This is my solution to the [Recipe page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/recipe-page-KiTsR8QQKm).

## Table of contents

- [Overview](#overview)
  - [Screenshots](#screenshots)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learnt](#what-i-learnt)

## Overview

### Screenshots

Mobile:

![](/assets/images/mobile-screenshot.jpeg)

Desktop:

![](/assets/images/desktop-screenshot.jpeg)

### Links

- [Solution URL](https://www.frontendmentor.io/solutions/recipe-page-Rxfn1w9v9i)
- [Live site URL](https://recipe-page-dionysialemonaki.vercel.app/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

### What I learnt

I found that the main purpose of this challenge was to get the HTML semantics right and ensure the page was accessible. I also found that I spent a lot of time thinking through the page structure and class naming to avoid repetition for sections that share styles.

For the preparation, ingredients, instructions and nutrition sections I used the `section` element, and to improve accessibility, I gave it an accessible name and exposed its implicit `role="region"`. I did this by labelling the `section` with `aria-labelledby` and associating it with the respective `h2` heading. This allows screen reader users to jump directly to the different sections.

```html
<section aria-labelledby="preparation">
  <h2 id="preparation">Preparation time</h2>
  ....
</section>

<section aria-labelledby="ingredients">
  <h2 id="ingredients">Ingredients</h2>
  ....
</section>

<section aria-labelledby="instructions">
  <h2 id="instructions">Instructions</h2>
  ....
</section>

<section aria-labelledby="nutrition">
  <h2 id="nutrition">Nutrition</h2>
  ....
</section>
```

I also learnt about table syntax and the proper use of the `table`, `tr`,`th` and `td` elements.

`table` holds all the table content, `tbody` (not strictly required in the markup as browsers insert it automatically, but including it improves readability) wraps the main part of the table content, `tr` creates a table row, `th` creates a single table header cell and `td` creates a single table cell.

I also learnt how the `scope` attribute on `th` elements improves accessibility, as it associates each table header with all the data in that column or row.

```html
<table>
  <tbody>
    <tr>
      <th scope="row">Calories</th>
      <td>277kcal</td>
    </tr>
  </tbody>
</table>
```

Lastly, I learnt about the `::marker` pseudo-element, which I used to style the bullets and numbers in the unordered and ordered lists respectively, as well as more complex pseudo-classes such as `:not()`, `:first-child` and `:last-child`.

```css
/* add a border-bottom under every row except the last one */
tr:not(:last-child) {
  border-bottom: var(--border);
}

/* remove padding-top and padding-bottom from the cells in the first and last rows respectively */
tr:first-child th,
tr:first-child td {
  padding-block-start: 0;
}

tr:last-child th,
tr:last-child td {
  padding-block-end: 0;
}
```
