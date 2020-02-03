# Create View modes programtically

```php
/**
 * Implements hook_entity_info_alter().
 *
 * Set up view modes as an array.
 */
function dev_patterns_entity_info_alter(&$entity_info) {
  // Node display modes.
  $entity_info['node']['view modes'] += [
    'person_tile' => [
      'label' => t('Person Tile'),
      'custom settings' => FALSE,
    ],
    '3up_card' => [
      'label' => t('3-Up Card'),
      'custom settings' => FALSE,
    ],
    'hero' => [
      'label' => t('Hero'),
      'custom settings' => FALSE,
    ],
  ];
}
```

## Other view modes:

```php
  // Field Collection display modes.
  $entity_info['field_collection_item']['view modes'] += []

  // Taxonomy Term display modes.
  $entity_info['taxonomy_term']['view modes'] += [

  // File display modes.
  $entity_info['file']['view modes'] += []

  // Bean display modes.
  $entity_info['bean']['view modes'] += []

  // Paragraphs Item view modes.
  $entity_info['paragraphs_item']['view modes'] += []
```

