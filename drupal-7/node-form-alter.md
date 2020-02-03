# Node form alter

```php
/**
 * Implements hook_form_alter().
 *
 */
function dev_patterns_form_node_form_alter(&$form, &$form_state) {

  // Switch for the node type bundle.
  switch ($form['#bundle']) {
    // Expert node type.
    case 'expert':
    // Do stuff.
      break;
      
    // Blog node type.
    case 'blog':
    // Do stuff.
      break;
   }
  }
```

