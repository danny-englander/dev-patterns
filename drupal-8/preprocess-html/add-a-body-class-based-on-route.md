# Add a body class based on route

```php
/**
 * Implements hook_preprocess_html().
 */
function dev_patterns_preprocess_html(array &$vars) {
  // Define the route.
  $route = \Drupal::routeMatch()->getRouteName();
  // Define an array of pages that are quotes / orders menu pages.
  $quote_menu_paths = [
    'dev_patterns.signup_form',
    'view.user_stats.page',
    'view.commerce_user_orders.order_page',
  ];

  // If the route matches, add the class to the pages above.
  // We then use this class for theming.
  if (in_array($route, $quote_menu_paths)) {
    $vars['attributes']['class'][] = 'commerce-user-page';
  }
}
```

 

