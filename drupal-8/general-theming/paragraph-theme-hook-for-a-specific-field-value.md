# Paragraph theme hook for a specific field value

```php
/**
 * Implements hook_theme_suggestions_paragraph_alter().
 */
function dev_patterns_theme_suggestions_paragraph_alter(array &$suggestions, array $vars) {
  $paragraph= $vars['elements']['#paragraph'];
  
  // Create a theme hook if it's a single CTA.
  if ($paragraph->getType() === 'text_and_button') {
    if ($paragraph->hasField('field_cta') &&
      !$paragraph->get('field_cta')->isEmpty()) {
      
      // Define the value.
      $value = $paragraph->get('field_cta')->getString();
      if ($value === '1') {
        $suggestions[] = 'paragraph__' . $paragraph->bundle() . '__cta';
      }
    }
  }
}
```

 

