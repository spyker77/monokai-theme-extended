## INITIAL ANSWER
This is designed for perfectionists who want to reproduce the visual experience from Sublime Text in Visual Studio Code, but are not satisfied with current marketplace solutions. Comparing to default theme, this version solves the problem with highlighting of methods and some additional inconsistencies.

How to apply:
1) In you Visual Studio Code go to "Code" => "Preferences" => "Color Theme" and pick Monokai;
2) On Mac go to the following path "/Applications/Visual Studio Code.app/Contents/Resources/app/extensions/theme-monokai/themes/" and replace default file "monokai-color-theme.json" with this version;
3) Reload your Visual Studio Code.

If necessary, change the font size and weight at "Code" => "Preferences" => "Settings" and write "font" in the search field.

Important!
This was adapted to Python language. If you have any wishes, drop me a line and let's see if I can improve it even further.


## UPDATE (April 2021)
It turns out that the previous solution is not sustainable. Therefore at the moment a better one could be, after choosing Monokai as described in point 1 above:
1) Open `settings.json` file ([how-to](https://code.visualstudio.com/docs/getstarted/tips-and-tricks#_tune-your-settings));
2) There will probably already be a bunch of settings in there, so all you need to do is just add the following customisations at the end and before the closing brace (don't forget a trailing comma after the last setting you continue):
```json
"editor.tokenColorCustomizations": {
        "[Monokai]": {
            "textMateRules": [
                {
                    "name": "Decorator definition decorator",
                    "scope": "punctuation.definition.decorator.python",
                    "settings": {
                        "foreground": "#F92672"
                    }
                },
                {
                    "name": "Meta function-call",
                    "scope": "meta.function-call.generic.python",
                    "settings": {
                        "foreground": "#66D9EF"
                    }
                },
                {
                    "name": "Storage type function async",
                    "scope": "storage.type.function.async.python",
                    "settings": {
                        "foreground": "#F92672",
                    }
                },
                {
                    "name": "Punctuation separator period",
                    "scope": "punctuation.separator.period.python",
                    "settings": {
                        "foreground": "#F8F8F2",
                    }
                },
                {
                    "name": "Entity name function decorator",
                    "scope": "entity.name.function.decorator.python",
                    "settings": {
                        "foreground": "#66D9EF",
                    }
                },
                {
                    "name": "Entity name type class",
                    "scope": "entity.name.type.class.python",
                    "settings": {
                        "fontStyle": ""
                    }
                },
                {
                    "name": "Entity other inherited-class",
                    "scope": "entity.other.inherited-class.python",
                    "settings": {
                        "fontStyle": "italic"
                    }
                },
                {
                    "name": "Support type python",
                    "scope": "support.type.python",
                    "settings": {
                        "fontStyle": ""
                    }
                },
                {
                    "name": "String quoted docstring multi python",
                    "scope": "string.quoted.docstring.multi.python",
                    "settings": {
                        "foreground": "#88846F",
                    }
                },
                {
                    "name": "Keyword control flow python",
                    "scope": "keyword.control.flow.python",
                    "settings": {
                        "foreground": "#88846F",
                    }
                }
            ]
        }
    }
```
3) Happy coding 🎉
