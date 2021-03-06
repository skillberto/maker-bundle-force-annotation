# Sylius and Symfony patch to force annotation in MakerBundle

## Resolve following issues

- [https://github.com/Sylius/Sylius/issues/10809](https://github.com/Sylius/Sylius/issues/10809)

## Install

**Enable composer patching**

First step, your composer could be install patch, so you need the following package `cweagans/composer-patches`.

```bash
composer require cweagans/composer-patches
```

**Apply patch**

In your `composer.json`:

```js
{
    // {...} composer.json content
    "extra": {
        "patches": {
            "symfony/maker-bundle": {
                "Provide flag to force annotation in make entity command": "https://raw.githubusercontent.com/vklux/maker-bundle-force-annotation/master/maker-force-annotation-flag.patch"
            }
        }
    }
}
```

Now, run `composer update`.

**Use**

Add flag `--force-annotation` in make:entity `command`.