# Node form alter

```php
/**
 * Implements hook_form_alter().
 *s
 */
function dev_patterns_form_node_form_alter(&$form, &$form_state) {
  // Define the global user.
  global $user;
  // Define the module path.
  $module_path = drupal_get_path('module', 'dev_patterns');


  switch ($form['#bundle']) {
    // Expert node.
    case 'expert':
    // Do stuff.
      break;

    case 'blog':
    // Do stuff.
      break;

  }

```
