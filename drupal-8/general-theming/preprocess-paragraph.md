# Preprocess Paragraph

```php
/**
 * Implements hook_preprocess_paragraph().
 */
function dev-patterns_preprocess_paragraph(&$vars) {
  $paragraph= $vars['elements']['#paragraph'];

  // Theme text and button as a CTA.
  if ($paragraph->getType() === 'text_and_button') {
    // Add a contained width class.
    if ($paragraph->hasField('field_cta') &&
      !$paragraph->get('field_cta')->isEmpty()) {
      // Define the value.
      $value = $paragraph->get('field_cta')->getString();
      if ($value === '1') {
        $vars['attributes']['class'][] = 'is-cta';
      }
    }
  }
```

 

