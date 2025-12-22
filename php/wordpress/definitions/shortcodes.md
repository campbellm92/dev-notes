# Shortcodes

A small piece of code that performs a specific function, like displaying content. Acts as a shortcut, allowing users to add functionality to a webpage without writing code.

examples:

```php
[gallery ids="1,2,3"]
[video src="movie.mp4"]
[contact-form id="123"]
```

Functions that do NOT run shortcodes:
get_the_content()

get_the_excerpt()

wp_trim_words()

Functions that DO run shortcodes:

the_content()

apply_filters('the_content', ...)
