# Twig loops

This example is in a custom paragraphs template

```jsx
<nav class="orbit-bullets">
  {# Loop through for the bullets. #}
  {% for key, item in content.field_slides if key|first != '#' %}
    <button {% if loop.first %}class="is-active" {% endif %}data-slide="{{ key }}">
      <span class="show-for-sr">{{ trans }}Slide {{ key + 1 }} details.{{ endtrans }}</span>
    </button>
  {% endfor %}
</nav>
```

 Get multi field values within a loop in a paragraphs template

```jsx
{% for key, item in content.field_picture_buttons if key|first != '#' %}
  <div class="layout__region layout__region--three-col">
    <div class="picture-button">
      <div class="picture-button__wrap">

        <a class="picture-button__link" href="{{ item.field_button_link.0["#url"] }}">
          <div class="picture-button__media">
            {{ item.field_picture_button_image | field_value }}
          </div>

          <div class="picture-button__title">
            <h3 class="h4">
              {{ item.field_button_link.0["#title"] }}
            </h3>
          </div>
        </a>

      </div>
    </div>
  </div>
{% endfor %}
```

 

