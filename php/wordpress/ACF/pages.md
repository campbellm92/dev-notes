# Using ACF with pages

## Creating

1. Create a page
2. Create a field group with the same name as the page
3. Create fields:
   - if it's a normal page with sections, give the field groups the titles of the sections
   - for HTML, use WYSIWYG as the field type
4. Do: Show this field group if > is equal to > Page > and > Page > is equal to > Page Name
5. Add desired text in the page section of WP

## Rendering

Good workflow for layouts:

1. Create whatever sort of layout you want. Example:

```php
<?php
/**
 * Expects:
 * $args['sections'] = [
 *   [
 *     'title' => '',
 *     'content' => '',
 *     'align' => 'left' | 'right'
 *   ]
 * ];
 */

// Extract sections from $args
$sections = $args['sections'] ?? [];

if (empty($sections))
    return;
?>

<main class="min-h-screen w-full pt-40">
    <div class="mx-auto w-full px-10">

        <?php foreach ($sections as $section): ?>

            <section class="grid grid-cols-12 gap-6 mb-18">
                <div class="
                        col-span-12
                        <?= $section['align'] === 'right'
                            ? 'md:col-span-9 md:col-start-6 md:text-right'
                            : 'md:col-span-7'
                            ?>
                    ">
                    <h1 class="pb-5">
                        <?= esc_html($section['title']); ?>
                    </h1>

                    <div class="<?= $section['align'] === 'right' ? 'md:ml-auto' : '' ?>">
                        <?= wp_kses_post($section['content']); ?>
                    </div>
                </div>
            </section>

        <?php endforeach; ?>

    </div>
</main>
```

2. Consume it in the top level page file:

```php

<?php
if (!defined('ABSPATH'))
    exit;

get_template_part('parts/header');


$sections = [
    [
        'title' => 'Donazione',
        'content' => get_field('donazione'),
        'align' => 'left',
    ],
    [
        'title' => '5x1000',
        'content' => get_field('five_x_onethousand'),
        'align' => 'right',
    ],
];

get_template_part(
    'template-parts/layouts/static-page-sections',
    null,
    ['sections' => $sections]
);

get_template_part('parts/footer');
```
