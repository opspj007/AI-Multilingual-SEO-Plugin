=== AI Multilingual SEO ===
Requires at least: 5.8
Requires PHP: 7.4
Stable tag: 1.0.0
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

AI-powered multilingual SEO for WordPress. Translate pages, posts, WooCommerce products, and SEO metadata with AI-assisted translation, human review, hreflang support, and language-specific XML sitemaps.

== Description ==

**AI Multilingual SEO** helps you create and manage multilingual WordPress websites with AI-assisted translations and SEO optimization.

Key capabilities include:

* AI-assisted content translation
* Human review and approval workflow
* Multilingual SEO metadata
* WooCommerce product translation
* Yoast SEO and Rank Math integration
* Automatic hreflang and x-default tags
* Language-specific XML sitemaps
* Translation management dashboard
* Multilingual language switcher
* Bulk translation support

== Setup ==

1. Go to **Settings > AI Multilingual SEO** and select the original language, target languages, and content types.
2. Enable **Products** if you are using WooCommerce.
3. Configure your AI provider and API key. For better security, define the key in `wp-config.php`:

```php
define( 'WPAML_API_KEY', 'your-api-key' );
```

4. Edit any post, page, or product and open the **Translations** panel.
5. Click **Translate with AI**, or use **Bulk Translate** for multiple items.
6. Review translations side-by-side from **Multilingual SEO > Translations**.
7. Edit the translation if required, then **Approve & Publish**.
8. Add the `[wpaml_switcher]` shortcode to a menu, widget, page, or template.

For a dropdown language selector, use:

```text
[wpaml_switcher style="dropdown"]
```

Submit the following sitemap to search engines:

```text
/wpaml-sitemap.xml
```

== How It Works ==

Each translation is stored as a normal WordPress post and linked to its original content.

Every translation can have its own:

* URL slug
* SEO title
* Meta description
* Focus keyword
* Language
* Published status

The plugin integrates natively with **Yoast SEO** and **Rank Math** when available. If neither plugin is installed, AI Multilingual SEO can generate the required title, description, Open Graph, and related SEO metadata.

For published translations, the plugin automatically generates:

* `hreflang` tags
* `x-default` hreflang
* Language-specific sitemap entries
* Alternate language URLs

Sitemaps include:

```text
/wpaml-sitemap.xml
/wpaml-sitemap-{lang}.xml
```

Language alternates are exposed using `xhtml:link` sitemap annotations.

== WooCommerce ==

AI Multilingual SEO supports WooCommerce product translations.

Translated products can mirror the original product's:

* Price
* Stock status
* Product information
* SEO metadata

The plugin currently keeps the original WooCommerce product as the cart item. Therefore, cart and checkout content continues to use the default product configuration.

== Known Limitations ==

Version 1.0 currently has the following limitations:

* Page builders such as Elementor and Divi are not supported.
* WooCommerce variable products are currently blocked with a clear compatibility message.
* Categories and tags are not translated.
* Menus and widgets are not translated.
* Image alt text is not automatically translated.
* Theme strings are not translated.
* URLs are not language-prefixed.
* Translations use translated URL slugs.
* Archives and WooCommerce shop pages display one language at a time using `?lang=xx`.
* Language selection can optionally be remembered using a cookie.

== Developer API ==

### Functions

```php
wpaml_switcher();
wpaml_get_translation_url( $post_id, $lang );
```

### Actions

```text
wpaml_translated
wpaml_translation_created
wpaml_translation_approved
```

Developers can use these hooks to extend translation workflows and integrate AI Multilingual SEO with custom WordPress functionality.

== Compatibility ==

* WordPress 5.8+
* PHP 7.4+
* WooCommerce
* Yoast SEO
* Rank Math
* Anthropic API
* OpenAI-compatible AI APIs

== License ==

AI Multilingual SEO is licensed under the **GPLv2 or later** license.
