# Count number in a multi-value field array



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
  // Create a count var for use in the twig field template.
  if ($field_name === 'field_color_tiles_ref') {
    $vars['count'] = count($vars['items']);
  }
}
```

 

