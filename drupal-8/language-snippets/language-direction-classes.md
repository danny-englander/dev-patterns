# Language direction classes

Set HTML classes for language

```php
/**
 * Implements hook_preprocess_html().
 */
function dev_patterns_preprocess_html (&$vars) {
  // We add a class to the html element instead of loading a file
  // specific for rtl languages to keep scss components in a more
  // semantic fashion.  All RTL styles will be included in their
  // corresponding component file
  if ($vars['html_attributes']['dir'] == 'rtl') {
    $vars['html_attributes']->addClass('rtl-lang');
  }
  if ($vars['html_attributes']['dir'] == 'ltr') {
    $vars['html_attributes']->addClass('ltr-lang');
  }

  $lang = \Drupal::languageManager()->getCurrentLanguage(\Drupal\Core\Language\LanguageInterface::TYPE_CONTENT);
  $vars['html_attributes']->addClass('lang-' . $lang->getId());
}
```

 

