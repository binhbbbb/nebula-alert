[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/arsnebula/nebula-alert)

[![Build Status](https://saucelabs.com/browser-matrix/arsnebula.svg)](https://saucelabs.com/beta/builds/f816dbafc9e2415baed45032acc091dd)

# \<nebula-alert\>

A web component to display an alert dialog.

* Responsive design adapts to screen size
* Covers the entire screen with a backdrop and centered container
* Supports optional title, icon, text and buttons
* Supports `a11y` for accessability
* Easily styled with style attributes or with CSS variables and mixins

> Warning: This element utilizes features of [ECMAScript 2015](http://www.ecma-international.org/ecma-262/6.0/) which may not be supported by all browsers. To ensure support by all browsers, consider using the [Core-js Polyfill](https://github.com/zloirock/core-js).

## Installation

```sh
$ bower install arsnebula/nebula-alert
```

## Usage

Import the package element:

```html
<link rel="import" href="/bower_components/nebula-loader/nebula-alert.html"> 
```

Add and configure the element declaratively:

```html
<nebula-alert
  title="Alert"
  icon="icons:warning"
  text="You have been warned."
  buttons='["OK"]'
  on-closed="_onClosed"
  result="{{alertResult">
</nebula-alert>
```

You can also easily create and display the element programatically using the `show` method. The element is appended and removed from the `document.body` automatically.

```js
// create the element
var alert = Polymer.Base.create('nebula-alert', {
  title: 'Alert',
  icon: 'warning',
  text: 'You have been warned',
  buttons: ['OK']
})

// show the element - automatically appended to document.body
alert.show().then(function(result) {
  console.log('The alert has been closed', result)
})
```

*For more information on element properties and methods see the element API documentation.*

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Change Log

See [CHANGELOG](/CHANGELOG.md)

## License

See [LICENSE](/LICENSE.md)