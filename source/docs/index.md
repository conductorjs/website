## Getting Started with Conductor

To get started with Conductor.js, [download a copy of the library from
GitHub][gh-download].

[gh-download]: https://github.com/tildeio/conductor.js/blob/master/dist/conductor-0.2.0.js.html

The first thing to note is that this file is valid JavaScript _and_
HTML, which is why it has the extension `.js.html`. This might seem
unusual, but is what allows Conductor.js to work in both Internet
Explorer and modern browsers.

<span class="warning">Warning</span> Conductor.js is undergoing rapid
development and the API is subject to change. Your feedback is very
important. If you run into trouble, please [file an issue on
GitHub][gh-issues].

[gh-issues]: https://github.com/tildeio/conductor.js/issues

This documentation is also open source. [The website source code is
available at github.com/conductorjs/website][gh-website].

[gh-website]: https://github.com/conductorjs/website

## Installing the Library

After you've downloaded Conductor.js, include the hybrid JavaScript/HTML
file in your HTML page like this:

```html
<script src="/dist/conductor-0.2.0.js.html"></script>
```

## Setting Up Conductor

To add a Conductor cards to your application, first create a new
instance of `Conductor`:

```js
var conductor = new Conductor();
```

<span class="note">Note</span> Because Conductor needs to provide a copy
of the Conductor library to the cards you create, it assumes that it
can find a copy at the absolute URL `/dist/conductor-02.0.js.html`.  If
your copy of Conductor is at a different URL, specify that URL using the
`conductorURL` option:

```js
var conductor = new Conductor({
  conductorURL: '/js/libs/conductor.js.html'
});
```

## Creating a Card

Once you have created the Conductor instance, load a card by
passing the URL to the card's JavaScript to the `load` method:

```js
var card = conductor.load("/cards/test_card.js");
```

Once you have created the card object, tell it to render itself into the
DOM by calling the `appendTo` method with the `DOMElement` into which it
should render:

```js
card.appendTo(document.getElementById('card'));
```

