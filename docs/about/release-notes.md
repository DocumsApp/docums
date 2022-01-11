# Release Notes

---

## Upgrading

To upgrade Docums to the latest version, use pip:

    pip install -U docums

You can determine your currently installed version using `docums --version`:

    $ docums --version
    docums, version 1.0.0.0 from /path/to/docums (Python 3.6)

## Version 1.0.0.0

* Bugfix: Ignore absolute links in Markdown
* Bugfix: Warn on relative paths in navigation
* Bugfix: Handle empty `theme_config.yml` files correctly
* Bugfix: Provide absolute `base_url` to error templates
* Bugfix: Prevent page reload when [Enter] is pressed in search box
* Bugfix: Avoid calling `search` until all assets are ready
* Bugfix: Exclude `README.md` if `index.md` is present
* Bugfix: Fix `readthedocs` theme navigation bug with homepage
