# Region alter

```php
/**
 * Implements hook_theme_suggestions_region_alter().
 */
function dev_patterns_theme_suggestions_region_alter(&$suggestions, $vars, $hook) {
  // Define a var for the #region.
  $region = $vars['elements']['#region'];
  // Global reset for all regions.
  $suggestions[] = 'region' . '__' . 'all';

  // Check for any of the three footer regions and create a theme hook.
  if ($region === 'footer' || $region === 'footer_left' || $region === 'footer_right') {
    $suggestions[] = 'region' . '__' . 'footer_all';
  }

  // Check for any of the three header regions and create a theme hook.
  if ($region === 'header_nav' || $region === 'header_utility' || $region === 'header_off_canvas') {
    $suggestions[] = 'region' . '__' . 'header_all';
  }
}
```

 

