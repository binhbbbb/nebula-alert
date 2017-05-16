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

The `result` property wil return the index of the button clicked to close the dialog, or `undefined` if the dialog was cancelled by pressing the `ESC` key or clicking the backdrop. To disable cancel, set the `allowCancel` property to `false`.

## Style

The most common way to style the alert element is to set color or font properties for the various sub-elements. To make this easy, a collection of CSS variables are provided to easily theme the element.

Custom property | Description | Default
:--- | :--- | :---
`--nebula-alert-color` | The base color for all dialog sub-elements. | white
`--nebula-alert-backdrop-color` | The background color of the host element. | transparent
`--nebula-alert-background-color` | The color of the dialog background. | transparent
`--nebula-alert-border-color` | The color of the dialog border. | transparent
`--nebula-alert-title-color` | The color of the title. | currentColor
`--nebula-alert-title-font` | The font of the title. | 1.2rem bold
`--nebula-alert-text-color` | The color of the text. | currentColor
`--nebula-alert-text-font` | The font of the text. | | inherit
`--nebula-alert-icon-color` | The color of the icon. | currentColor
`--nebula-alert-icon-size` | The size of the icon. | 32px
`--nebula-alert-button-color` | The color of the buttons. | currentColor
