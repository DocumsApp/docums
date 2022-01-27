# Release Notes

---

## Upgrading

To upgrade Docums to the latest version, use pip:

    pip install -U docums

You can determine your currently installed version using `docums --version`:

    $ docums --version
    docums, version 1.0.0.0 from /path/to/docums (Python 3.6)

## Version 1.2.3 (2021-10-12)

* Built-in themes now also support these languages:
  * Simplified Chinese
  * Japanese
  * Brazilian Portuguese
  * Spanish
  * Vietnamese

* Third-party plugins will take precedence over built-in plugins with the same
  name

* Bugfix: Fix ability to load translations for some languages:
  core support and search plugin support with fallbacks

* Bugfix (regression in 1.2): Prevent directory traversal in the dev server

* Bugfix (regression in 1.2): Prevent webserver warnings from being treated as
  a build failure in strict mode

* Bugfix: Correctly print colorful messages in the terminal on Windows

* Bugfix: Python version 3.10 was displayed incorrectly in `--version`

* Bugfix (regression in 1.2): Fix serving files/paths with Unicode characters

* Bugfix (regression in 1.2): Revert livereload file watching to use polling
  observer

  This had to be done to reasonably support usages that span virtual
  filesystems such as non-native Docker and network mounts.

  This goes back to the polling approach, very similar to that was always used
  prior, meaning most of the same downsides with latency and CPU usage.

* Revert from 1.2: Remove the requirement of a `site_url` config and the
  restriction on `use_directory_urls`

* Bugfix (regression in 1.2): Don't require trailing slash in the URL when
  serving a directory index in `docums serve` server

  Instead of showing a 404 error, detect if it's a directory and redirect to a
  path with a trailing slash added, like before.

* Bugfix: Fix `gh_deploy` with config-file in the current directory

* Bugfix: Fix reversed breadcrumbs in "readthedocs" theme

* Allow "docums.yaml" as the file name when '--config' is not passed

* Stop treating ";" as a special character in URLs: urlparse -> urlsplit

* Improve build performance for sites with many pages (partly already done in
  1.2)

* Bugfix (regression in 1.2): Ensure 'gh-deploy' always pushes.

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
