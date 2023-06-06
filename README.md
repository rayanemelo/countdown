
![countdown](https://github.com/rayanemelo/countdown/assets/80798717/c83010bf-f065-4a84-97e8-26e098409a6d)

# Countdown Shelf

The Countdown Shelf app is responsible for providing render a countdown timer together with a shelf.

## Configuration
1. Install the app running `vtex install corebiz.countdown-shelf@0.x` in the workspace that you’ll develop it, when it’s ready for deploy, you can install it in production workspace.
2. Add the store vendor `corebiz.countdown-shelf@0.x` as a peerDependency within the manifest
3. Add `count-down-shelf` block to your block files, in the place you want to show the shelf.

Now, you can import any of the exported components and hooks from the app. Here's an example of a component that render's the name of the product whose data is stored in the nearest `ProductContext`:

    "count-down-shelf": {
        "props": {
            "countDownTitle": "### Novidades",
            "countDownSubtitle": "Ofertas especiais",
            "countDownDate": "31/12/2021",
            "countDownHour": "23:59",
            "countDownFormat": "days",
            "countDownImage": "/arquivos/teste_img_countdown.png",
            "includeShelf": true,
            "isActive": true,
            "backgroundColor": "#2680EB",
            "textColor": "#ffffff", 
            "cta": {
              "text": "Saiba mais",
              "url": "#"
            }
        },
        "children": [
            "list-context.product-list#home-shelf-novidades"
        ]
    },

:warning: *if you want a shelf within the component, make sure to pass the list-context.product-list as a children*

| Prop name           | Type      | Description                                                                                 |
| ------------------- | --------- | ------------------------------------------------------------------------------------------- |
| `countDownTitle`     | `String`  | Define the countdown title    |
| `countDownSubtitle`     | `String` |  Define the countdown subtitle                                          |
| `countDownDate`        | `String` |  Define the end date of the counter             |
| `countDownHour`  | `String` |  Define the countdown title                                                                |
| `countDownFormat`       | `countDownFormatEnum` | Define the countdown format. Default: `days`                                                       |
| `countDownImage`       | `String` | Source of the image displayed in the counter  
| `includeShelf`       | `Boolean` |  If the counter needs to render a shelf 
| `isActive`       | `Boolean` | If the component will render `true` 
| `backgroundColor`       | `String` |Hexadecimal of the background
| `textColor`       | `String` | Hexadecimal of the main font
| `cta`       | `CTAObject` | Unique class name to be appended to block classes. Default: '' 
| `utm`| `string` | Parameter to load a specific shelf countdown when the UTM_SOURCE correspond in url

Here are the possible values of `countDownFormatEnum`

| Enum name | Enum value | Description |
| --------- | ---- | ----------- |
| days | 'days' | The component will render in the format of: days/hours/minutes/seconds |
| hours | 'hours' | The component will render in the format of: hours/minutes/seconds |

Here are the possible values of `CTAObject`

| Property name  | Description |
| --------- | ----------- |
| text |  Text displayed in the call to action button |
| url |  Link `href` displayed in the call to action button. |

