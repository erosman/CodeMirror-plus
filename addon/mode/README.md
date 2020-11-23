# How to Use

## keyword.js
Apply style to any keywords in any CodeMirror instance, with or without an active `mode`

- Install the file in `/addon/mode/` or any preferred directory
- Add the `keyword: {word: style}` option to the editor instance e.g.
 
    ```js
    const editor = CodeMirror(document.body, {
      lineNumbers: true,
      mode:  "javascript",
      keyword: {
        "word1": "style1",
        "word2": "style1",
        "word3": "style1",
        "word4": "style2"
      }
    });
    ```
- **Note**: If a word is a sub-string of another, the longer word should be listed first, otherwise the shorter word will match first and prevent matching of the the longer word e.g.

    ```js
    keyword: {
        "nevertheless": "style1",
        "never": "style1"
      }
    ```

- Add the corresponding CSS in existing `.css` or a new one. The style name will appear as `.cm-NAME` e.g.

    ```css
    .cm-style1 {
      color: maroon;
    }
    .cm-style2 {
      color: #00f;
    }
    ```

    In case other CSS that overrides the added CSS, use `!important` e.g.
    
    ```css
    .cm-style1 {
      color: maroon !important;
    }
    .cm-style2 {
      color: #00f !important;
    }
    ```

- Add the necessary `<script>` & `<link rel="stylesheet">` to the HTML document
