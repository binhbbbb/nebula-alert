[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/arsnebula/nebula-alert)
[![Gitter chat](https://badges.gitter.im/org.png)](https://gitter.im/arsnebula/webcomponents)

[![Build Status](https://saucelabs.com/browser-matrix/arsnebula.svg)](https://saucelabs.com/beta/builds/1ac6d7661c754f6f9abd8f40512aa53f)

# \<nebula-alert\>

A web component to display an alert dialog.

* Responsive design adapts to screen size
* A full-screen overlay with backdrop and centered dialog
* Supports optional title, icon, text and buttons
* Easily styled with style attributes or with CSS variables and mixins
* Supports [WAI-ARIA](https://www.w3.org/TR/wai-aria-practices-1.1/#alert) for **a11y**

> Warning: This element requires browser support for [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). To ensure support by all browsers, use a promise polyfill such as [PolymerLabs Promise Polyfill](https://github.com/PolymerLabs/promise-polyfill).

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
  icon: 'icons:warning',
  text: 'You have been warned',
  buttons: ['OK']
})

// update any styles
alert.updateStyles({
  '--nebula-alert-dialog-color': 'white',
  '--nebula-alert-dialog-background-color': 'black',
  '--nebula-alert-dialog-border-color': 'silver',
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