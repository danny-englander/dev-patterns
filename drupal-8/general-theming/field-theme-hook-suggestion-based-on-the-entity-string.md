# Field theme hook suggestion based on the entity string

```php
/**
 * Implements hook_theme_suggestions_HOOK_alter().
 * Used to add a generic field twig template without any
 * wrapping divs to have more
 * control over styles.
 *
 * @see: https://www.previousnext.com.au/blog/bare-templates-removing-unnecessary-markup-twig-files
 */
function dev_patterns_theme_suggestions_field_alter(&$hooks, $vars) {
  // Get the element names passed on when a page is rendered.
  $name = $vars['element']['#field_name'];

  // Define the field element.
  $element = $vars['element'];

  // Build the string layout for the fields,
  // these fields will use the no-markup twig template.
  // <entity type>:<bundle name>:<view mode>:<field name>.
  $bare_hooks = [
    'block_content:picture_button:rectangular:field_button_link',
    'block_content:picture_button:rectangular:field_picture_button_image',
    'block_content:callout:full:body',
    'media:event_cta_image:tile:thumbnail',
    'paragraph:links_downloads:default:field_links_downloads',
    'paragraph:slider:default:field_slides',
    'paragraph:slider:slide:field_slides',
  ];

  // Build the actual var structure from second parameter.
  $hook = implode(':', [
    $vars['element']['#entity_type'],
    $vars['element']['#bundle'],
    $vars['element']['#view_mode'],
    $vars['element']['#field_name'],
  ]);

  // Check if the strings match and assign the bare template.
  if (in_array($hook, $bare_hooks, TRUE)) {
    $hooks[] = 'field__no_markup';
  }
}
```

 

