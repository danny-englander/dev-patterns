# Twig user variables

```jsx
{{ user.AccountName }}
{{ user.DisplayName }}
{{ user.Email }}
{{ user.LastAccessedTime }}
{{ user.TimeZone }}
{{ user.PreferredLangcode }}
{{ user.id }}

{% for item in user.Roles %}
  {{ item }}
{% endfor %}

{% if user.Anonymous == true %}
  {{ "You're an anonymous user"|t }}
{% else %}
  {{ "You're an authenticated user"|t }}
{% endif %}

{% if logged_in == true %}
  {{ "yes, I am logged in"|t }}
{% endif %}
```

See [https://api.drupal.org/api/drupal/core%21lib%21Drupal%21Core%21Session%21AccountInterface.php/interface/AccountInterface/8.8.x](https://api.drupal.org/api/drupal/core%21lib%21Drupal%21Core%21Session%21AccountInterface.php/interface/AccountInterface/8.8.x) for more info on these. 

