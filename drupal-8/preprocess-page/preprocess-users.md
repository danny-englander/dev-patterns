# Preprocess users

```php
/**
 * Implements hook_preprocess_HOOK() for page title templates.
 */
function dev_patterns_preprocess_page(&$variables) {
  // Set template vars for user related info
  $user = \Drupal\user\Entity\User::load(\Drupal::currentUser()->id());
  $variables['user_id'] = $user->get('uid')->value;
  $variables['name'] = $user->get('name')->value;
  $variables['email'] = $user->get('mail')->value;
}
```

 

