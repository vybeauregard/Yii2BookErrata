[return to README](README.md)

The first chunk of this chapter deals in the theory of how the Layout engine works.

####Page 92
Tests appear to work as advertised so far in Chapter 4.
Spelling `$this->assertGreaterThen();` should be corrected to `$this->assertGreaterThan();`

####Page 95
Holy smokes! It passed the test!

####Page 99
- `actionYaml()` will be added to `ServicesController.php`
- `use app\utilities\YamlResponseFormatter;` needs to be added to the use statements at the beginning of `ServicesController.php` in order for the YAML Formatter to be properly invoked.

####Page 107
- The overview for publishing asset bundles did not include steps for adapting the existing project for them. Replacing the two asset registration calls with `app\assets\ApplicationUiAssetBundle::register($this);` produces the following error:

  >The file or directory to be published does not exist: ~/Projects/crmapp/assets/ui

- Publising asset bundles outside of the `@webroot` folder is against official Yii recommendations: http://www.yiiframework.com/doc-2.0/guide-structure-assets.html#asset-locations

####Page 109
- In `assets/SnowAssetsBundle.php`, set the `$depends` property to an [empty array](http://stackoverflow.com/a/27154646):

  ```php
    class SnowAssetsBundle extends AssetBundle
    {
      public $sourcePath = '@app/assets/snow';
      public $css = ['snow.css'];
      public $depends = [
          //'apps\assets\ApplicationUiAssetBundle',
      ];
    }
  ```

####Page 110
- There are two `homepage.php` files. Make sure you update `themes/snowy/views/site/homepage.php` with the code at the top of this page.

[return to README](README.md)
