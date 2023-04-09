# Web basics with Svelte

Beginner Svelte workshop for FullyHacks 2023!

## Background

### What is this workshop about?

This workshop is about web development. Web development is the process of creating websites and web applications. Web development is a broad term that encompasses many different technologies and skills. This workshop will focus on the fundamentals of web development, specifically the fundamentals of Svelte.

### What is web development? (What is a website?)

A website is a collection of files that are served to a web browser. The web browser is a program that interprets the files and displays the website to the user. The web browser is the most common way to view websites, but websites can also be viewed in other ways, such as in a web application.

#### What languages are understood by the browser?

The browser understands HTML, CSS, and JavaScript. HTML is used to structure the content of a website. CSS is used to style the content of a website. JavaScript is used to add interactivity to a website.

> NOTE: The browser also understands SVG and WebAssembly, but these are not covered in this workshop.

#### Why are frameworks/libraries so prevalent in web development?

Frameworks and libraries are used to reduce the amount of code that needs to be written. This is done by providing a set of pre-written code that can be used to solve common problems. This allows developers to focus on the unique aspects of their project instead of having to write the same code over and over again.

### What is Svelte?

Svelte is a compiler that compiles Svelte code into optimized HTML, CSS, and JavaScript. The Svelte compiler is a powerful tool that allows developers to write code that is easy to read and write, but is also optimized for the browser.

> NOTE: SvelteKit is a full-stack solution for Svelte (comparable to Next.js, Nuxt.js, and Remix), but this workshop will focus on using the Svelte compiler to learn HTML fundamentals and Svelte syntax.

#### Svelte vs React

Svelte is a compiler for building web interfaces, while React is a library. Svelte compiles components into optimized JavaScript code, resulting in smaller bundle sizes, faster load times, and efficient DOM updates, making it a more optimal choice for performance-oriented web applications. However, React has a larger ecosystem of libraries and community support.

### Workshop steps

#### Open a Svelte development environment

##### Set up VSCode

- Open a new SvelteKit project (`npm create svelte@latest my-app`) in VSCode in high-contrast mode.
- Run `npm run dev` to start the development server.
- Open the preview in your browser.

##### Set up Svelte REPL

- Open a new Svelte REPL (https://svelte.dev/repl/).
- Sign in to the Svelte REPL to save your work. Remember to save often! SAVE SAVE SAVE!

#### HTML introduction

> Svelte is a superset of HTML.

All valid HTML is valid Svelte, including plain text.

```html
Hello world!
```

#### The HTML tag

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

#### Common HTML tags and semantics

HTML is a format that contains rich semantic information. Semantic HTML is HTML that is used to convey intended meaning to the browser (and to readers of your code).

For example, the `h1` tag is used to indicate the most important heading on a page. The `h2` tag is used to indicate the second most important heading on a page. And so on until the `h6` tag.

```html
<h1>Hello world!</h1>
```

Add a paragraph to your HTML document using the `p` tag.

Line breaks are added to your HTML document using the `br` tag.

> NOTE: `p` tags cannot be nested inside of other `p` tags (i.e. a `p` tag cannot be the child of another `p` tag). It is generally not immediately clear why some elements are invalid to nest inside of other elements, but it is important to follow the rules of HTML by referencing the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) when in doubt.

> NOTE: A comment is used in the example below as a placeholder for the irrelevant HTML code.

```html
<h1>Hello world!</h1>

<!-- <p> and <br> spam -->

<p>Hello world!</p>
```

Some elements are responsible for behaviors that you'd expect from a web page, such as links and forms.

Add a link to your HTML document using the `a` tag.

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

Add an image to your HTML document using the `img` tag using the `src` attribute to set the image source and the `alt` attribute to set the image's alternative text.

> NOTE: The `alt` attribute is used to provide a textual description of the image. This is useful for users who are unable to view the image, such as users who are visually impaired. Generally, carefully choosing the proper semantic HTML tag and attributes will be the difference between a good user experience and a great user experience.

```html
<!-- Previous content -->

<img
  src="https://fullyhacks.acmcsuf.com/fullyhacks_logo.png"
  alt="FullyHacks logo"
/>
```

#### CSS introduction

Svelte looks for CSS in the `style` tag in your Svelte file.

```html
<style>
  /* CSS goes here */
</style>
```

##### Selectors

CSS selectors are used to select the HTML elements that you want to style.

For example, the `h1` selector is used to select all `h1` elements.

```html
<style>
  h1 {
    color: red;
  }
</style>
```

Share CSS styles between multiple HTML elements by using a comma-separated list of selectors.

```html
<style>
  h1,
  p {
    color: rebeccapurple;
  }
</style>
```

##### Properties

CSS properties are used to style HTML elements.

For example, the `color` property is used to set the color of the text. You are encouraged to reference the [named CSS colors](https://developer.mozilla.org/en-US/docs/Web/CSS/named-color#standard_colors).

There are many CSS properties that can be used to style HTML elements. For a full list of CSS properties, refer to the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference).

```html
<style>
  h1 {
    text-align: center;
  }
</style>
```

#### More HTML tags

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

> NOTE: Anchor tags are commonly used in `li` elements to make tables of contents.

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

> NOTE: Presenter opens <https://formdata.deno.dev/> in a new tab to demonstrate how forms are used to store user input.

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

Similarly to anchor tags, forms can be submitted to a web address. Instead of the `href` attribute, the `action` attribute is used to specify the web address. The `method` attribute is used to specify the HTTP method.

```html
<!-- Previous content -->

<form action="https://formdata.deno.dev/" method="POST">
  <!-- Your form content -->
</form>
```

> NOTE: For a more comprehensive introduction to conventional HTML document structure, see <https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure>.

#### Svelte superpowers

We emphasize the "super" when we say "Svelte is a **superset** of HTML" because Svelte adds a few new features to HTML that make it even more powerful.

##### Conditionals

You may want to display different content depending on the state of your application. For example, you may want to display a loading indicator while data is being fetched from a web API.

```svelte
<script>
  let isHappy = false;

  function toggleHappiness() {
    isHappy = !isHappy;
  }
</script>

<button on:click={toggleHappiness}>
  {#if isHappy}
    😊
  {:else}
    😞
  {/if}
</button>
```

##### Reactive statements

Svelte allows you to write code that reacts to changes in your application. For example, you may want to change the title of your document depending on the state of your application. The reactive statement is denoted by the `$:` prefix and is run whenever the variables it depends on change. In this case, the `isHappy` variable is used in the reactive statement, so the statement is run whenever the `isHappy` variable changes.

```svelte
<script>
  let isHappy = false;

  function toggleHappiness() {
    isHappy = !isHappy;
  }

  $: if (isHappy) {
    document.title = "😊";
  } else {
    document.title = "😞";
  }
</script>

<button on:click={toggleHappiness}>
  {#if isHappy}
    😊
  {:else}
    😞
  {/if}
</button>
```

##### Repeating code

It is common to repeat code in HTML documents. For example, you may want to display a list of items. Instead of writing out each item individually, you can use a loop to repeat the code for each item.

```svelte
<script>
  const items = ["🎉", "🎈", "🎊"];
</script>

<ul>
  {#each items as item}
    <li>{item}</li>
  {/each}
</ul>
```

More information about loops can be found in the [`{#each ...}` template syntax documentation](https://svelte.dev/docs#template-syntax-each).

##### Svelte components

Svelte components are reusable pieces of code that can be used to build complex user interfaces.

> EXERCISE: Make a new Svelte file ending with `.svelte` and grab any valid Svelte code. For example, abstract your HTML form into a Svelte component.

##### Svelte stores

Svelte stores are reactive JavaScript variables that can be written to and read from any frontend file in your application.

> EXERCISE: Make a JavaScript file ending with `.js` and use the `writable` function to create a new Svelte store.

```js
import { writable } from "svelte/store";

export const count = writable(0);
```

##### Honorable mentions

- [Svelte actions](https://svelte.dev/docs#template-syntax-element-directives-use-action)
- [Svelte slots](https://svelte.dev/docs#template-syntax-slot)
- [Svelte transitions](https://svelte.dev/docs#run-time-svelte-transition)
- [SvelteKit documentation](https://kit.svelte.dev/docs)

## References

- https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure
- https://kit.svelte.dev/docs

---

Written with <3 for [**FullyHacks**](https://fullyhacks.acmcsuf.com/)
