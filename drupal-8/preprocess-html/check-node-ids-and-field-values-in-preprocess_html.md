# Check node ids and field values in preprocess\_html

```php
/**
 * Implements hook_preprocess_html().
 */
function dev_patterns_preprocess_html(array &$vars) {
  // Define the node.
  $node = \Drupal::routeMatch()->getParameter('node');
  // Check for a node.
  if ($node instanceof \Drupal\node\NodeInterface) {
    // Define the nid.
    $nid = $node->id();
    // If it's id 2 or 3 (Drupal defined 403 and 404 pages.)
    if (($nid === '2') || ($nid === '3')) {
      $vars['attributes']['class'][] = 'is-utility';
    }

    // Add a contained width class.
    if ($node->hasField('field_contained_width') &&
      !$node->get('field_contained_width')->isEmpty()) {
      // Define the value.
      $value = $node->get('field_contained_width')->getString();
      if ($value === '1') {
        $vars['attributes']['class'][] = 'has-contained-width';
      }
    }

    // Add the page class if present.
    if ($node->hasField('field_page_class') &&
      !$node->get('field_page_class')->isEmpty()) {
      // Define the value.
      $value = $node->get('field_page_class')->getString();
      $vars['attributes']['class'][] = 'page-' . $node->field_page_class->value;
    }
  }
}
```

 

