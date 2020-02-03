# Check if node has body and add a class

## Preprocess page

```php
  $node = \Drupal::routeMatch()->getParameter('node');
  if ($node instanceof \Drupal\node\NodeInterface) {
    // Get the body value from the node object.
    if (!empty($node->get('body')->value)) {
      $vars["node_has_body"] = 'has-body';
    }
  }
```

