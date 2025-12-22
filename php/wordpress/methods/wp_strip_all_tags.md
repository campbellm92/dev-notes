# wp_strip_all_tags

Strip all HTML and PHP tags from a string.

Useful if you want to avoid unwanted styles:

```html
<p class="md:w-1/3 line-clamp-3 overflow-hidden">
  <?php echo wp_strip_all_tags(get_the_excerpt()); ?>
</p>
```

This will force the element to take the specified parent styles as opposed to whatever default WP sets.
