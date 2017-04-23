# \<nebula-alert\>

`<nebula-alert>` is a web component to display an alert dialog.
  
## Usage

The following demonstrates the element with some common properties and events.

```html
<nebula-alert
  icon="icons:warning"
  title="Alert"
  text="You have been warned"
  buttons='["OK"]'
  value="{{alertValue}}>
</nebula-alert>
```

You can also create and show the element programatically. The `show` method will ensure the element is appended and removed from the `document.body` automatically. The method returns a promise that is resolved once the element closing animation is complete.

```js
// create the element
var alert = Polymer.Base.create('nebula-alert', {
  title: 'Alert',
  icon: 'warning',
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

The `result` property wil return the index of the button clicked to close the dialog, or `undefined` if the dialog was cancelled by pressing the `ESC` key or clicking the backdrop. To disable cancel, set the `allowCancel` property to `false`.

## Style

The most common way to style the alert element is to set color properties for the various sub-elements. To make this easy, a collection of CSS variables are provided to easily theme the element.

Custom property | Description | Default
:--- | :--- | :---
`--nebula-alert-backdrop-color` | The background color of the host element. | transparent
`--nebula-alert-dialog-background-color` | The color of the dialog background. | transparent
`--nebula-alert-dialog-border-color` | The color of the dialog border. | transparent
`--nebula-alert-dialog-color` | The base color for all dialog sub-elements. | white
`--nebula-alert-title-color` | The color of the title. | currentColor
`--nebula-alert-text-color` | The color of the text. | | currentColor
`--nebula-alert-icon-color` | The color of the icon. | | currentColor
`--nebula-alert-button-color` | The color of the buttons. | currentColor

For more granular control, the following mixins can be used to fully control the styling of each sub-element.

Custom property | Description
:--- | :---
`--nebula-alert` | Mixin applied to the alert base element.
`--nebula-alert-dialog` | Mixin applied to the alert dialog container.
`--nebula-alert-title` | Mixin applied to the title element.
`--nebula-alert-text` | Mixin applied to the text element.
`--nebula-alert-icon` | Mixin applied to the icon element.
`--nebula-alert-button` | Mixin applied to alert button elements.
