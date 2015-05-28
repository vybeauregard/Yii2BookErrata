[return to README](README.md)
#### Page 74
- Before running the next Codeception test, download the code bundle from https://www.packtpub.com/books/content/support

> Type `yii2` into the `Search...` field in the middle of the page and select `Web Application Development with Yii 2 and PHP`.
> On the next screen, fill out the form and you will receive a download link in your email.

- Open the zip file and copy the following files into their respective folders in your `crmapp`:
  - `1885OS_Code/crmapp/tests/acceptance/_steps/CRMGuestSteps.php`
  - `1885OS_Code/crmapp/tests/acceptance/_steps/CRMServicesManagementSteps.php`
  - `1885OS_Code/crmapp/tests/acceptance/EditServiceCept.php`
  - `1885OS_Code/crmapp/tests/acceptance/DeleteServiceCept.php`

> The test imported from the code bundle has made a ton of assumptions about our project, many of which are incorrect. To compensate for this, the files I have copied from a `basic` Yii install include:
- `models/User.php`
- `models/ContactForm.php`
- `models/EntryForm.php`
- `models/LoginForm.php`
- `views/site/*.php`
- I have updated `controllers/SiteController.php` with the contents of the `basic` `SiteController`, but left `actionIndex()` unmodified.
- `config/web.php` should be updated with a `user` component:
```
'user' => [
            'identityClass' => 'app\models\User',
            'enableAutoLogin' => true,
        ],
```
- The test has switched from using PHPBrowser to WebDriver. To make that work, add PhantomJS to `composer.json` as detailed here: https://samsonasik.wordpress.com/2014/12/18/using-php-phantomjs-with-codeception/

[return to README](README.md)
