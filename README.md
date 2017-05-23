[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/arsnebula/nebula-alert)
[![Polymer Version](https://img.shields.io/badge/polymer-v2-blue.svg)](https://www.polymer-project.org)
[![Sauce Labs Build Status](https://img.shields.io/badge/saucelabs-passing-red.svg)](https://saucelabs.com/beta/builds/49cf66af5a334fb9aad3ba70c659c2bd)
[![Gitter Chat](https://badges.gitter.im/org.png)](https://gitter.im/arsnebula/webcomponents)
[![Become a Patreon](https://img.shields.io/badge/patreon-support_us-orange.svg)](https://www.patreon.com/arsnebula)

# \<nebula-alert\>

A customizable alert dialog.

* A full-screen overlay with backdrop and centered dialog
* Supports optional title, icon, text and buttons
* Supports [WAI-ARIA](https://www.w3.org/TR/wai-aria-practices-1.1/#alert) for **a11y**

## Installation

```sh
$ bower install -S arsnebula/nebula-alert
```

## Getting Started

Import the package.

```html
<link rel="import" href="/bower_components/nebula-loader/nebula-alert.html"> 
```

Add the element.

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
const alert = document.createElement('nebula-alert')

// update any styles
alert.updateStyles({
  '--nebula-alert-color': 'white',
  '--nebula-alert-background-color': 'black',
  '--nebula-alert-border-color': 'silver',
})

// show the element - automatically appended to document.body
alert.show({
  title: 'Alert',
  icon: 'icons:warning',
  text: 'You have been warned',
  buttons: ['OK']
}).then(function(result) {
  console.log('The alert has been closed', result)
})
```

*For more information, see the API documentation.*

## Contributing

We welcome and appreciate feedback from the community. Here are a few ways that you can show your appreciation for this package:

* Give us a **Star on GitHub** from either [webcomponents.org](https://www.webcomponents.org/element/arsnebula/nebula-element-mixin) or directly on [GitHub](https://github.com/arsnebula/nebula-element-mixin).

* Submit a feature request, or a defect report on the [Issues List](https://www.webcomponents.org/element/arsnebula/nebula-element-mixin/issues).

* Become a [Patreon](https://www.patreon.com/arsnebula). It takes a lot of time and effort to develop, document, test and support the elements in our [Nebula Essentials](https://www.webcomponents.org/collection/arsnebula/nebula-essentials) collection. Your financial contribution will help ensure that our entire collection continues to grow and improve.

If you are a developer, and are interested in making a code contribution, consider opening an issue first to describe the change, and discuss with the core repository maintainers. Once you are ready, prepare a pull request:

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Change Log

See [CHANGELOG](/CHANGELOG.md)

## License

See [LICENSE](/LICENSE.md)