# User view mode theme hook

```php
/**
 * Implements hook_theme_suggestions_HOOK_alter().
 */
function dev_patterns_theme_suggestions_user_alter(&$suggestions, $vars) {
  $suggestions[] = 'user__' . $vars['elements']['#view_mode'];
}
```

 

