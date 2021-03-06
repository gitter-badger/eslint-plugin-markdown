# eslint-plugin-markdown

An [ESLint](http://eslint.org/) plugin to lint JavaScript in Markdown.

Supported extensions are `.markdown`, `.mdown`, `.mkdn`, and `.md`.

## Usage

Install the plugin:

```sh
npm install --save-dev eslint-plugin-markdown
```

Add it to your `.eslintrc`:

```json
{
    "plugins": [
        "markdown"
    ]
}
```

It will lint `js`, `javascript`, `jsx`, or `node` [fenced code blocks](https://help.github.com/articles/github-flavored-markdown/#fenced-code-blocks) in your Markdown documents:

    ```js
    // This gets linted
    var answer = 6 * 7;
    console.log(answer);
    ```

    ```JavaScript
    // This also gets linted

    /* eslint quotes: [2, "double"] */

    function hello() {
        console.log("Hello, world!");
    }
    hello();
    ```

    ```jsx
    // This gets linted too
    var div = <div className="jsx"></div>;
    ```

    ```node
    // And this
    console.log(process.version);
    ```

Blocks that don't specify either `js`, `javascript`, `jsx`, or `node` syntax are ignored:

    ```
    This is plain text and doesn't get linted.
    ```

    ```python
    print("This doesn't get linted either.")
    ```

## Contributing

```sh
$ git clone https://github.com/eslint/eslint-plugin-markdown.git
$ cd eslint-plugin-markdown
$ npm link
$ npm link eslint-plugin-markdown
$ npm test
```

This project follows the [ESLint contribution guidelines](http://eslint.org/docs/developer-guide/contributing.html).
