# Address field \#after\_build

It's tricky to get at address fields with a standard form alter. I discovered, you can create an after build function to dig into the nested address field arrays. First create the custom function

```php
/**
 * Implements hook_form_alter().
 */
function dev_patterns_form_alter(&$form, &$form_state, $form_id) {
  if ($form_id == 'user_register_form') {
    // Custom after build for address elements.
    $form['field_address']['widget'][0]['address']['#after_build'][] = '_dev_patterns_register_alter_attr';
  }
}
```

 Next, use the new custom function to alter address fields as you normally would. 

```php
/**
 * Implements custom function: _gd_quote_register_alter_attr.
 */
function _dev_patterns_register_alter_attr($element, $form_state) {
  // Alter various elements of the reg form address field.
  $element["address_line1"]["#title"] = t('Address');
  $element["address_line2"]["#title"] = t('Address line 2');
  return $element;
}
```

 

