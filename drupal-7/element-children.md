# Element Children

## Element Children is a great way to dig into arrays with multiple keys

This might appear under a pre-process node

```php
/**
 * Override or insert vars into the node template.
 */
function nrdc_preprocess_node(&$vars) {
  // Define the node.
  $node = $vars['node'];
  $nodetype = $node->type;

  // Retrive terms on node and loop through each term
  // using a $key in place of the array number.
  // so that it does not get reset with every pass.
  // The array might look something like this in Xdebug
  // $vars['field_issue_term']['0']['taxonomy_term']
  // $vars['field_issue_term']['1']['taxonomy_term']
  // etc...
  // Set the linked_terms variable to false before the loop.
  $vars['linked_terms'] = FALSE;
  // Loop using a key value via element_children.
  foreach (element_children($vars['field_issue_term']) as $key) {
    // Get the term name.
    $term_name = $vars['field_issue_term'][$key]['taxonomy_term']->name;
    // Get the term TID.
    $term_tid = $vars['field_issue_term'][$key]['taxonomy_term']->tid;
    // Convert the term path into an alias.
    $term_url = drupal_lookup_path('alias', 'taxonomy/term/' . $term_tid);
  }
}
```

