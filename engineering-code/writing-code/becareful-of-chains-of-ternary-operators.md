# Be careful of chains of ternary operators

A chain of ternary operators make it hard to judge what is happening.

Do not do this:

```text
$size = $button === 'submit' ? 'big : 'small';
$text = $button === 'submit'
  ? $l10n->getBigText()
  : $l10n->getSmallText();
$action = $button === 'submit'
  ? '/submit'
  : '/reset'
```

Do this:

```text
if ($button === 'submit') {
  $size = 'big';
  $text = $l10n->getBigText();
  $action = '/submit';
} else {
  $size = 'small';
  $text = $l10n->getSmallText();
  $action = '/reset';
}
```

## 

