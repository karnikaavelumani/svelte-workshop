# Web basics with Svelte

Beginner Svelte workshop for FullyHacks 2023!

## Background

### What is this workshop about?

This workshop is about web development. Web development is the process of creating websites and web applications. Web development is a broad term that encompasses many different technologies and skills. This workshop will focus on the fundamentals of web development, specifically the fundamentals of Svelte.

### What is web development? (What is a website?)

A website is a collection of files that are served to a web browser. The web browser is a program that interprets the files and displays the website to the user. The web browser is the most common way to view websites, so it is important to know the compatibility of the technologies you are using with the web browser that your users are using.

> NOTE: It is also important to learn how to read and understand documentation, such as the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element). MDN has [a standard format for tables that illustrate compatibility of shared technologies across all browsers](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Page_structures/Compatibility_tables), such as DOM, HTML, CSS, JavaScript, SVG, etc.

#### What languages are understood by the browser?

The browser understands HTML, CSS, and JavaScript. HTML is used to structure the content of a website. CSS is used to style the content of a website. JavaScript is used to add interactivity to a website.

> NOTE: The browser also understands SVG and WebAssembly, but these are not covered in this workshop.

#### Why are frameworks/libraries so prevalent in web development?

Frameworks and libraries are used to reduce the amount of code that needs to be written. This is done by providing a set of pre-written code that can be used to solve common problems. This allows developers to focus on the unique aspects of their project instead of having to write the same code over and over again.

### What is Svelte?

Svelte is a powerful tool that compiles Svelte code into optimized HTML, CSS, and JavaScript, making it easy for developers to write efficient code. The Svelte compiler is a powerful tool that allows developers to write code that is easy to read and write, but is also optimized for the browser.

> NOTE: SvelteKit is a full-stack solution for Svelte (comparable to Next.js, Nuxt.js, and Remix), but this workshop will focus on using the Svelte compiler to learn HTML fundamentals and Svelte syntax.

#### Svelte vs React

Svelte is a compiler for building web interfaces, while React is a library. Svelte compiles components into optimized JavaScript code, resulting in smaller bundle sizes, faster load times, and efficient DOM updates, making it a more optimal choice for performance-oriented web applications. However, React has a larger ecosystem of libraries and community support.

### Workshop steps

#### Open a Svelte development environment

Either set up your Svelte development environment locally with SvelteKit (recommended: VSCode) or the official online Svelte REPL.

##### Set up VSCode

- Open a new SvelteKit project (`npm create svelte@latest my-app`) in VSCode in high-contrast mode.
- (Optional) Move files from `/my-app/` to the root of your repository.
- Run `npm run dev` to start the development server.
- Open the preview in your browser.

##### Set up Svelte REPL

- Open a new Svelte REPL (<https://svelte.dev/repl/>).
- Sign in to the Svelte REPL to save your work. Remember to save often! SAVE SAVE SAVE!

#### HTML introduction

> Svelte is a superset of HTML.

Svelte is a superset of HTML, which means that valid HTML code can also be used in Svelte, including HTML tags and their corresponding semantics.

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
<!-- Hello world! -->
```

#### Common HTML tags and semantics

HTML contains rich semantic information that conveys intended meaning to both the browser and readers of your code.

For example, the `h1` tag is used to indicate the most important heading on a page. The `h2` tag is used to indicate the second most important heading on a page. And so on until the `h6` tag.

```html
<h1>Hello world!</h1>
<h2>Hello world!</h2>
<h3>Hello world!</h3>
<h4>Hello world!</h4>
<h5>Hello world!</h5>
<h6>Hello world!</h6>
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
<ul>
  <li>Hello world!</li>
  <li>Hello world!</li>
  <li>Hello world!</li>
</ul>
```

Add an _ordered list_ to your HTML document using the `ol` tag.

```html
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

[HTML tables](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics) are a common way to display information of all shapes and sizes in a structured way.

```html
<table>
  <tr>
    <td>Row 1, Column 1</td>
    <td>Row 1, Column 2</td>
  </tr>
  <tr>
    <td>Row 2, Column 1</td>
    <td>Row 2, Column 2</td>
  </tr>
</table>
```

Collect user input in HTML using the [`input` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input).

```html
<input type="text" />
```

Customize your input element with more attributes.

> NOTE: There are several [HTML5 input types](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types).

```html
<input
  type="text"
  value="Hello world!"
  placeholder="Enter your name"
  maxlength="64"
  pattern="[a-zA-Z0-9]+"
  required
/>
```

Group your inputs in an HTML form. Add a form to your HTML document using the [`form` element](https://developer.mozilla.org/en-US/docs/Learn/Forms).

> NOTE: Presenter opens <https://formdata.deno.dev/> in a new tab to demonstrate how forms are used to store user input.

```html
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
<form action="https://formdata.deno.dev/" method="POST">
  <!-- Your form content -->
</form>
```

> NOTE: For a more comprehensive introduction to conventional HTML document structure, see <https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure>.

#### Svelte superpowers

We emphasize the "super" when we say "Svelte is a **super**set of HTML" because Svelte adds a few new features to HTML that make it even more powerful.

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

##### Reactivity statements

Svelte allows you to write code that reacts to changes in your application. For example, you may want to change the title of your document depending on the state of your application. The reactive statement is denoted by the `$:` prefix and is run whenever the variables it depends on change. In this case, the `isHappy` variable is used in the reactive statement, so the statement is run whenever the `isHappy` variable changes. Code outside of the reactive statement is run once when the component is first rendered.

```svelte
<script>
  let isHappy = false;

  function toggleHappiness() {
    isHappy = !isHappy;
  }

  let count = 0;

  $: {
    if (isHappy) {
      count++;
    }
  }
</script>

<button on:click={toggleHappiness}>
  {#if isHappy}
    😊
  {:else}
    😞
  {/if}
</button>

{count}
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

Import your Svelte component into another Svelte file.

```svelte
<script>
  import Form from "./Form.svelte";
</script>

<Form />
```

<details>
<summary>(Optional) Define your own element attributes.</summary>

In Svelte, component properties are defined using the `export` keyword.

> EXERCISE: For example, you may want to define a `name` attribute for your form component.

```svelte
<!-- ./Form.svelte -->

<script>
  export let name;
</script>
```

Component properties are used in the same way as HTML element attributes.

```svelte
<script>
  import Form from "./Form.svelte";
</script>

<Form name="My Form" />
```

</details>

##### Svelte stores

Svelte stores are reactive JavaScript variables that can be written to and read from any frontend file in your application.

> EXERCISE: Make a JavaScript file ending with `.js` and use the `writable` function to create a new Svelte store. Doing so allows you to access the store in any frontend file in your application.

```js
import { writable } from "svelte/store";

export const count = writable(0);
```

Access Svelte stores by importing them from the file where they are defined.

```svelte
<script>
  // Assuming your store is exported as `count` from `stores.js`
  import { count } from "./stores";
</script>
```

##### Honorable mentions

Svelte and SvelteKit have a lot of features that we didn't have time to cover. Here are some honorable mentions:

- [Svelte actions](https://svelte.dev/docs#template-syntax-element-directives-use-action)
- [Svelte slots](https://svelte.dev/docs#template-syntax-slot)
- [Svelte transitions](https://svelte.dev/docs#run-time-svelte-transition)
- [SvelteKit documentation](https://kit.svelte.dev/docs)

## Final thoughts

We hope you had a great time learning the basics of web development with Svelte in this workshop!

## Self learning references

- [Introduction to HTML by MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)
- [Svelte tutorial](https://svelte.dev/tutorial/basics)
- [Svelte documentation](https://svelte.dev/docs)

---

Presented at [**FullyHacks**](https://fullyhacks.acmcsuf.com/) (April 8th, 2023) with `<3` by [_ACM at CSUF_](https://acmcsuf.com/) President [**@KarnikaaVelumani**](https://karni.codes/) and Vice President [**@EthanThatOneKid**](https://etok.codes/)

Self link: <https://acmcsuf.com/basics>
