# How to Use

- keyword.1.0.js version 1.0 can be used for strings only
- keyword.js version 1.1 can be used for strings and Regular Expressions ([#2](https://github.com/erosman/CodeMirror-plus/issues/2))

## keyword.js
Apply style to any keywords in any CodeMirror instance, with or without an active `mode`

- Install the file in `/addon/mode/` or any preferred directory
- Add the `keyword: {word: style}` option to the editor instance
- Strings & Regular Expressions are converted with `new RegExp()` and special characters must be escaped
- Strings & Regular Expressions are case-sensitive
 
    ```js
    const editor = CodeMirror(document.body, {
      lineNumbers: true,
      mode:  "javascript",
      keyword: {
        "word1": "style1",
        "word2": "style1",
        "word3": "style1",
        "example\.com": "style2",
        "abc\\d+": "style2"
      }
    });
    ```
- **Note**: If a word is a sub-string of another, the longer word should be listed first, otherwise the shorter word will match first and prevent matching of the the longer word e.g.

    ```js
    keyword: {
        "nevertheless": "style1",
        "never": "style2"
      }
    ```

- Add the corresponding CSS in existing `.css` or a new one. The style name will appear as `.cm-NAME` e.g.
    
    ```css
    .cm-style1 {
      color: maroon !important;
    }
    .cm-style2 {
      color: #00f !important;
    }
    ```

- Add the necessary `<script>` & `<link rel="stylesheet">` to the HTML document
