# Release Notes

---

## Upgrading

To upgrade Docums to the latest version, use pip:

    pip install -U docums

You can determine your currently installed version using `docums --version`:

    $ docums --version
    docums, version 1.0.0.0 from /path/to/docums (Python 3.6)

## Version 1.1.0

* Bugfix: Normalize IP addresses and change unsupported address error to a
  warning
* Bugfix: Allow compressed sitemap to be deterministic by supporting the
  `SOURCE_DATE_EPOCH` environment variable
* Bugfix: Use `README.md` as `index.html` even if `use_directory_urls` is false
* Bugfix: Ignore links which start with a backslash
* Bugfix: Pass `builder` to the `on_serve` event so that it can be passed to
  `server.watch` by plugins
* Bugfix: Use `lunr[languages]==0.5.8` to avoid `nltk` incompatibilities
* Bugfix: Ensure wheel is Python 3 only
* Bugfix: Clean up `dev_addr` validation and disallow `0.0.0.0`
* Add support for `min_search_length` parameter for search plugin
* Bugfix: `readthedocs` theme `code` colors

## Version 1.0.0.0

* Bugfix: Ignore absolute links in Markdown
* Bugfix: Warn on relative paths in navigation
* Bugfix: Handle empty `theme_config.yml` files correctly
* Bugfix: Provide absolute `base_url` to error templates
* Bugfix: Prevent page reload when [Enter] is pressed in search box
* Bugfix: Avoid calling `search` until all assets are ready
* Bugfix: Exclude `README.md` if `index.md` is present
* Bugfix: Fix `readthedocs` theme navigation bug with homepage
