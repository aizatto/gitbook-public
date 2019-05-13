# DraftJS

## Decorators

Make sure to apply decorators before the content

```typescript
const [editorState, setEditorState] = useState(() =>
  EditorState.createWithContent(
    props.defaultContent,
    decorators
  )
);
  
return (
  <Editor
    editorState={editorState}
  />
);
```

## draft-js-plugins

[https://github.com/draft-js-plugins/draft-js-plugins](https://github.com/draft-js-plugins/draft-js-plugins)

#### draft-js-side-toolbar-plugin

Cons:

* You can't optionally change one of style of theme.
  * You have to change them all.
  * You can reuse the css if you go into the package and find the class names.

## Code Reference

Main Site

* [EditorState](https://draftjs.org/docs/api-reference-editor-state)

### GitHub

* [getDefaultKeyBinding](https://github.com/facebook/draft-js/blob/585af35c3a8c31fefb64bc884d4001faa96544d3/src/component/utils/getDefaultKeyBinding.js#L61)
* [KeyBindingUtil](https://github.com/facebook/draft-js/blob/585af35c3a8c31fefb64bc884d4001faa96544d3/src/component/utils/KeyBindingUtil.js#L18)
* [RichTextEditorUtil.handleKeyCommand](https://github.com/facebook/draft-js/blob/585af35c3a8c31fefb64bc884d4001faa96544d3/src/model/modifier/RichTextEditorUtil.js#L54)

