# data-twig-suggestion preprocess

Alter an input by creating a twig theme hook

```php
/**
 * Implements hook_form_alter().
 */
function dev_patterns_form_alter(&$form, FormStateInterface $form_state, $form_id) {
  if ($form["#id"] === "views-exposed-form-news-page-1") {
    $form['actions']['submit']['#attributes']['data-twig-suggestion'] = 'search_news';
  }
}
```

 Then create the theme hook

```php
/**
 * Implements hook_theme_suggestions_input_alter().
 */
function moscone_theme_suggestions_input_alter(&$suggestions, array $vars) {
  // Define the element.
  $element = $vars['element'];
  // Check for specifc hooks.
  if ((isset($element['#attributes']['data-twig-suggestion']) && ($element['#attributes']['data-twig-suggestion'] === 'search_news'))) {
    // Create a theme hook if there is a data-twig-suggestion for search_news
    $suggestions[] = 'input__search_news';
  }
}
```

 

