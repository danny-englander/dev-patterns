# Check if a node has body content and create a variable

You can query the node object in a preprocess page function and then set a Twig page template variable

```php
/**
 * Implements hook_preprocess_html().
 */
function dev_patterns_preprocess_page(array &$vars) {
  $node = \Drupal::routeMatch()->getParameter('node');
  if ($node instanceof \Drupal\node\NodeInterface) {
    // Get the body value from the node object.
    if (!empty($node->get('body')->value)) {
      $vars["page_has_body"] = 'page-has-body';
    }
  }
}
```

