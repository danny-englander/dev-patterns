# Page title theme hook

```php
/**
 * Implements hook_theme_suggestions_page_title_alter().
 */
function dvele_theme_suggestions_page_title_alter(&$suggestions, $vars) {
  $route_name = \Drupal::routeMatch()->getRouteName();
  $suggestions[] = 'page_title__' . str_ireplace('.', '__', $route_name);
}
```

 

