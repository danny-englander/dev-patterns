# Replace field name



```php

/**
 * Prepares variables for field templates.
 *
 * Default template: field.html.twig.
 *
 * @param array $vars
 *   An associative array containing:
 *   - element: A render element representing the field.
 *   - attributes: A string containing the attributes for the wrapping div.
 *   - title_attributes: A string containing the attributes for the title.
 */
function dev_patterns_preprocess_field(&$vars, $hook) {
  // Define vars for use as classes.
  $field_name = $vars["element"]["#field_name"];
  $name = str_replace('field', 'item_row_', $field_name);
  $vars["name"] = $name;
}
```

 

