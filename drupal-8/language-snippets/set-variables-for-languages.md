# Set twig variables for languages



```php
/**
 * Implements hook_preprocess_HOOK() for page title templates.
 */
function dev_patterns_preprocess_page(&$variables) {
  // Set variables for languages.
  $language_name = \Drupal::languageManager()->getCurrentLanguage()->getName();
  $language_id = \Drupal::languageManager()->getCurrentLanguage()->getId();
  $variables['language_name'] = $language_name;
  $variables['language_id'] = $language_id;
 }
```

 

