# Loop index

Cycle odd even row classes

```jsx
{% for item in items %}
  <div class="{{ cycle(['row-odd', 'row-even'], loop.index0) }}">
  <section{{ item_attributes.addClass(item_classes) }}>
      {{ item.content }}
  </section>
  </div>
{% endfor %}
```

 

