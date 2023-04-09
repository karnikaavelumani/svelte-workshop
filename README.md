# Web fundamentals workshop (with Svelte!)

Beginner Svelte workshop for FullyHacks 2023!

TODO: Remark about https://formdata.deno.dev/.

## Outline

### Background

- What is this workshop about?
- What is web development? (What is a website?)
  - What languages are understood by the browser?
  - Why are frameworks/libraries used?
- What is Svelte?
  - Svelte vs React
- Workshop steps

<!-- TODO: Convert background outline into background. -->

### Workshop steps

#### Open a Svelte development environment

##### VSCode steps

- Open a new SvelteKit project in VSCode in high-contrast mode.
- Run `npm run dev` to start the development server.
- Open the preview in your browser.

##### Svelte REPL steps

- Open a new Svelte REPL (https://svelte.dev/repl/).
- Sign in to the Svelte REPL to save your work.

#### HTML introduction

> Svelte is a superset of HTML.

All valid HTML is valid Svelte, including plain text.

```html
Hello world!
```

Svelte adds _syntax sugar_ to

##### The HTML tag

In addition to plain text, HTML tags are used to add structure to a web page.

For example, add a heading to your HTML document using the `h1` tag.

```html
<h1>Hello world!</h1>
```

Ignore lines of code by using the HTML comment tag. In most code editors, the keyboard shortcut is <kbd>Ctrl</kbd> + <kbd>/</kbd>.

```html
<!-- <h1>Hello world!</h1> -->

<!-- Hello world! -->
```

###### Common HTML tags and semantics

HTML is a format that contains rich semantic information. Semantic HTML is HTML that is used to convey intended meaning to the browser (and to readers of your code).

For example, the `h1` tag is used to indicate the most important heading on a page. The `h2` tag is used to indicate the second most important heading on a page. And so on until the `h6` tag.

```html
<h1>Hello world!</h1>
```

Add a paragraph to your HTML document using the `p` tag.

Line breaks are added to your HTML document using the `br` tag.

> Note: `p` tags cannot be nested inside of other `p` tags (i.e. a `p` tag cannot be the child of another `p` tag). It is generally not immediately clear why some elements are invalid to nest inside of other elements, but it is important to follow the rules of HTML by referencing the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) when in doubt.

```html
<h1>Hello world!</h1>

<p>Hello world!</p>
```

Some elements are responsible for behaviors that you'd expect from a web page, such as links and forms.

Add a link to your HTML document using the `a` tag.

A comment is used in the example below as a placeholder for the irrelevant HTML code.

```html
<h1>Hello world!</h1>

<!-- <p> and <br> spam -->

<a>The best programmers</a>
```

Test out your anchor tag by clicking on it, but it doesn't work just yet. How come?

The developer is required to set specific _attributes_ that provide the data needed by the browser to behave as desired.

At least two attributes are required for this kind of anchor tag.

1. Set the ID of the target element via the `id` attribute. In our case, we will go with `title`.
2. Set the `href` attribute to the desired hash. The desired hash is the ID of the target element prefixed with a `#`. In our case, it's `#title`.

```html
<h1 id="title">Hello world!</h1>

<!-- <p> and <br> spam -->

<a href="#title">The best programmers</a>
```

Test out your anchor tag by clicking on it, but now it should link to desired HTML element on the page.

Hyperlink to anywhere on the Internet by setting the `href` to your desired web address.

```html
<h1 id="title">Hello world!</h1>

<!-- <p> and <br> spam -->

<a href="https://acmcsuf.com/">The best programmers</a>
```

<!-- TODO: CSS introduction -->

###### More HTML tags

Lists are a common way to display information in a structured way.

Add an _unordered list_ to your HTML document using the `ul` tag.

This showcases the parent-child relationship between HTML elements. Notice how the `ul` element is the parent of the `li` elements, making the `li` elements children of the `ul` element.

```html
<!-- Previous content -->

<ul>
  <li>Hello world!</li>
  <li>Hello world!</li>
  <li>Hello world!</li>
</ul>
```

Add an _ordered list_ to your HTML document using the `ol` tag.

```html
<!-- Previous content -->

<ul>
  <li>Hello world!</li>
  <li>Hello world!</li>
  <li>Hello world!</li>
</ul>

<ol>
  <li>Hello world!</li>
  <li>Hello world!</li>
  <li>Hello world!</li>
</ol>
```

HTML even supports _nested lists_ which can be in any combination of `ul` and `ol` tags.

```html
<!-- Previous content -->

<ul>
  <li>
    Hello world!
    <ol>
      <li>Hello world!</li>
      <li>Hello world!</li>
      <li>Hello world!</li>
    </ol>
  </li>
  <li>Hello world!</li>
  <li>Hello world!</li>
</ul>
```

> Note: Anchor tags are commonly used in `li` elements to make tables of contents.

HTML even supports [_tables_](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics) of all shapes and sizes.

```html
<!-- Previous content -->

<table>
  <thead>
    <tr>
      <th>Column 1</th>
      <th>Column 2</th>
      <th>Column 3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Row 1, Column 1</td>
      <td>Row 1, Column 2</td>
      <td>Row 1, Column 3</td>
    </tr>
    <tr>
      <td>Row 2, Column 1</td>
      <td>Row 2, Column 2</td>
      <td>Row 2, Column 3</td>
    </tr>
    <tr>
      <td>Row 3, Column 1</td>
      <td>Row 3, Column 2</td>
      <td>Row 3, Column 3</td>
    </tr>
  </tbody>
</table>
```

HTML forms are a common way to collect user input.

Add a form to your HTML document using the `form` tag.

```html
<!-- Previous content -->

<form>
  <label for="name">Name</label>
  <input type="text" id="name" name="name" />

  <label for="favorite_number">Favorite Number</label>
  <input type="number" id="favorite_number" name="favorite_number" />

  <label for="telephone">Telephone</label>
  <input type="tel" id="telephone" name="telephone" />

  <label for="message">Message</label>
  <textarea id="message" name="message"></textarea>

  <label for="favorite_color">Favorite Color</label>
  <select id="favorite_color" name="favorite_color">
    <option value="red">Red</option>
    <option value="orange">Orange</option>
    <option value="yellow">Yellow</option>
    <option value="green">Green</option>
    <option value="blue">Blue</option>
    <option value="indigo">Indigo</option>
    <option value="violet">Violet</option>
  </select>

  <label for="range">Range</label>
  <input type="range" id="range" name="range" min="0" max="100" />

  <input type="submit" value="Submit" />
</form>
```

> Note: For a more comprehensive introduction to conventional HTML
> document structure, see
> <https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure>.

#### Svelte superpowers

We emphasize the "super" when we say "Svelte is a **super**set of HTML" because Svelte adds a few new features to HTML that make it even more powerful.

##### Reactive variables

#####

<!-- TODO: Finish the workshop instructions. -->
<!-- See: https://docs.google.com/presentation/d/1j6c6BZIb-0TCCQosohfreKOx8gXAubCppsJ4fJelSzY/edit#slide=id.g162a3bacc13_0_63 -->
<!-- See: https://docs.google.com/presentation/d/1aL7-3iEPinHcYkvjaNu-0zrAxy7EP86xN7U1jvEqfaI/edit#slide=id.g22bc14e53fc_0_21 -->

<!-- ## References

- https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure -->
