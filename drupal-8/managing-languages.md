# Some useful Drupal 8 language snippets.

```php
// Define variables for the language direction.
$lang = \Drupal::languageManager()->getCurrentLanguage(\Drupal\Core\Language\LanguageInterface::TYPE_CONTENT);
if ($lang->getDirection() === "ltr") {
  $variables['lang_direction'] = 'ltr';
}
else {
  $variables['lang_direction'] = 'rtl';
}

```

Define variables for the language direction.
