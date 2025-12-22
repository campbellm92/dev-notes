# wp_kses_post

Returns safe, expected HTML

Does not:

- run shortcodes
- format
- apply block rendering
- auto-add tags
- do anything with WordPress filters

wp_kses_post is best practise for non-complex previews (e.g. when there's just text, rendering excerpts)
