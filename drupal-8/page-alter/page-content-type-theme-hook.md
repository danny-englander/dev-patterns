# Page content type theme hook

```php
  /**
 * Implements hook_theme_suggestions_page_alter().
 */
function dev_patterns_theme_suggestions_page_alter(array &$suggestions, array $vars) {
  // Add content type suggestions.
  if ($node = \Drupal::request()->attributes->get('node')) {
    array_splice($suggestions, 1, 0, 'page__node__' . $node->getType());
  }
}
```

 

