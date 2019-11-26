[<img width="200" alt="get in touch with Consensys Diligence" src="https://user-images.githubusercontent.com/2865694/56826101-91dcf380-685b-11e9-937c-af49c2510aa0.png">](https://diligence.consensys.net)<br/>
<sup>
[[  🌐  ](https://diligence.consensys.net)  [  📩  ](mailto:diligence@consensys.net)  [  🔥  ](https://consensys.github.io/diligence/)]
</sup><br/><br/>


# Inline Bookmarks   

<img width="350" alt="inline_bookmarks_icon" src="https://user-images.githubusercontent.com/2865694/69679883-91366500-10a9-11ea-8e36-ba3e799127b3.png">

Code navigation for inline bookmarks made easy.

Other extensions only allow you to specify bookmarks within your IDE. With Inline Bookmarks you can specify trigger words within your documents that are automatically turned into VSCode Bookmarks. They will show up with a customizable gutter icon next to the code lines and trigger words will be highlighted as well. An **Inline Bookmarks` View in the Explorer Pane helps you keep track of all your bookmarks. Navigating to the bookmark is as easy as clicking on an item in the view.

It's really useful to keep track of development notes and todos as well as log analysis, auditing and review purposes. Since bookmarks are mainly stored in your documents you can easily share your notes with others.

## Tour

<img width="350" alt="inline_bookmarks_icon" src="https://user-images.githubusercontent.com/2865694/69009240-d5ac5d00-0953-11ea-811e-f7fded9c6ecb.png">

![vscode-inline-bookmarks-2](https://user-images.githubusercontent.com/2865694/69681775-67803c80-10af-11ea-8e99-c79caf7781a5.gif)


#### Customizable Inline Bookmarks

* the following bookmark styles are provided by default: red, green, blue, purple

    <img width="350" alt="inline_bookmarks_icon" src="https://user-images.githubusercontent.com/2865694/69679883-91366500-10a9-11ea-8e36-ba3e799127b3.png">

**Note:** Additional custom styles can be added in the extension settings. See [Expert](#expert) options.

* the following default trigger words/tags are configured by default:
  * `@todo` - (blue) General ToDo remark.
  * `@note` - (blue) General remark.
  * `@remind` - (blue) General remark.
  * `@follow-up` - (blue) General remark.
  * `@audit` - (red) General bookmark for potential issues.
  * `@audit-info` - (blue) General bookmark for information to be noted for later use.
  * `@audit-ok` - (green) Add a note that a specific line is not an issue even though it might look like.
  * `@audit-issue` - (purple) Reference a code location an issue was filed for.

**Note:** Words can be fully customized in: `code → preferences → Extensions: Inline Bookmarks`.

<img width="350" alt="inline_bookmarks_icon" src="https://user-images.githubusercontent.com/2865694/69680065-1457bb00-10aa-11ea-853b-c36fdfc68b96.png">

## Expert

* go to the extension settings: `code → preferences → Extensions: Inline Bookmarks`
* Exceptions
  * configure file-extensions to be exempt from decoration
  * configure temporary overrides for trigger words to be exempt from decoration (matches begin of word)
* Custom Styles
  * be aware that existing styles can be overridden
  * The `gutterIconPath` is not customizable right now. You can only use the images provided with the extension right now: `images/bookmark-{red,green,blue,purple}.svg`. See example below.
* Custom word mappings
  * You can assign multiple regex trigger words to a decoration style. See example below.

**Example style definition:** (all vscode style properties are allowed)

```json
"inline-bookmarks.expert.custom.styles": {
    "default": {
        "gutterIconPath": "images/bookmark-blue.svg",
        "overviewRulerColor": "rgba(21, 126, 251, 0.7)",
        "light": {
            "fontWeight": "bold"
        },
        "dark": {
            "color": "Chocolate"
        }
    },
    "red": {
        "gutterIconPath": "images/bookmark-red.svg",
        "light": {
            "fontWeight": "bold"
        },
        "dark": {
            "color": "Chocolate"
        }
    },
    "blue": {
        "gutterIconPath": "images/bookmark-blue.svg",
        "light": {
            "fontWeight": "bold"
        },
        "dark": {
            "color": "Chocolate"
        }
    },
    "green": {
        "gutterIconPath": "images/bookmark-green.svg",
        "light": {
            "fontWeight": "bold"
        },
        "dark": {
            "color": "Chocolate"
        }
    },
    "purple": {
        "gutterIconPath": "images/bookmark-purple.svg",
        "light": {
            "fontWeight": "bold"
        },
        "dark": {
            "color": "Chocolate"
        }
    }
}
```

**Example word mapping:** (all vscode style properties are allowed)

```json
"inline-bookmarks.expert.custom.words.mapping": {
    "blue": ["@audit\\-info[ \\t\\n]"],
    "purple": ["@audit\\-issue[ \t\\n]"],
    "green": ["@audit\\-ok[ \\t\\n]"],
    "red": ["@audit[ \\t\\n]"]
}
```

* Note: gutter icons are hardcoded atm.

#### Bookmarks View

* click on a bookmark to jump to its location
* click refresh to re-scan loaded files for changes
 
## Release Notes

see [CHANGELOG](./CHANGELOG.md)

## 0.0.7
- new: configuration options
  - disable decorations
  - blacklist files-extensions that should not be decorated
  - blacklist words that should be temporarily ignored from decoration
  - hard-code default styles but allow to override them in the configuration
  - expose trigger words for default styles and allow to customize them
  - allow users to configure new styles and map trigger words to them
- fix: bokmarks view: did not auto-refresh on load
- fix: pattern for audit-issue
- fix: clear empty bookmarks

-----------------------------------------------------------------------------------------------------------
