# Alter page title based on route

```php
/**
 * Implements hook_preprocess_HOOK() for the page title template.
 */
function MYTHEME_preprocess_page_title(&$vars) {
  // Define the route.
  $route = \Drupal::routeMatch()->getRouteName();
    // Set the page title for user register.
  if ($route === 'user.register') {
    $vars['title'] = t('A New Page Title Indeed');
  }
}
```
