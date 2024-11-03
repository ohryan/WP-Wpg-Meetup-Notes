# WordPress 6.7 Preview

**Release Date:** November 12

## Font Library - Fluid Typography

{{demo}}

## Query Loop Block Refinements

{{demo}}

## Block Bindings

{{demo}}

## Under the hood

### New template registration API
- `wp_register_block_template()` replaces complicated registration process
- Previous code required three filters: `pre_get_block_template`, `pre_get_block_file_template` and `get_block_templates`
- Reference: [Guttenberg Pull Request](https://github.com/WordPress/gutenberg/pull/61577)

Example Snippet
```php
add_action(
	'init',
	function () {
		wp_register_block_template(
			'gutenberg//plugin-template',
			array(
				'title'       => 'Plugin Template',
				'description' => 'A template registered by a plugin.',
				'content'     => '<!-- wp:template-part {"slug":"header","tagName":"header"} /--><!-- wp:group {"tagName":"main","layout":{"inherit":true}} --><main class="wp-block-group"><!-- wp:paragraph --><p>This is a plugin-registered template.</p><!-- /wp:paragraph --></main><!-- /wp:group -->',
			)
		);
		add_action(
			'category_template_hierarchy',
			function () {
				return array( 'plugin-template' );
			}
		);
	}
);
```

### Preview Options API


### Etc
- HEIC Support ([Make Post](https://make.wordpress.org/core/2024/08/15/automatic-conversion-of-heic-images-to-jpeg-in-wordpress-6-7/))
- One minor PHP 8.1 compat fix ([PR](https://github.com/WordPress/wordpress-develop/pull/7039))

## Resources

### Blog Post
- [Make "Development Cycle"](https://make.wordpress.org/core/6-7/)
- [WP Beginner](https://www.wpbeginner.com/news/whats-coming-in-wordpress-6-7-features-and-screenshots/)

### Tools

- [LocalWP](https://localwp.com/)

### Plugins
- [Code Snippets](https://wordpress.org/plugins/code-snippets/)
- [Gutenberg](https://wordpress.org/plugins/gutenberg/)
