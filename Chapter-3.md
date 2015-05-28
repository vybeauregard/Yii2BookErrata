[return to README](README.md)

From the author:
```
Inside the code bundle that comes with this book, you will find the
acceptance test definitions for the CRUD UI we have been building
in this chapter. This was not included in the text for brevity. 
```
At this point, it is very tempting to bypass all of the tests. If you can fill the forms out manually to verify everything is working as you'd expect, I would call it good.

The code bundle includes a Vagrant file for spinning up a virtual machine with _allegedly_ everything necessary to run the server and execute the included tests. While I was able to bring the server up and verify for myself that everything is configured properly, the test suite (which includes several technologies I am new to) would not execute. Because these technologies are not central to how Yii functions, skipping the included tests seems like the best way to progress.

[jump to Page 76](Chapter-3.md#page-76)

#### Page 74

- ~~Before running the next Codeception test, download the code bundle from https://www.packtpub.com/books/content/support~~

  > ~~Type `yii2` into the `Search...` field in the middle of the page and select `Web Application Development with Yii 2 and PHP`.
  > On the next screen, fill out the form and you will receive a download link in your email.~~

- ~~Open the zip file and copy the following files into their respective folders in your `crmapp`:~~
  - ~~`1885OS_Code/crmapp/tests/acceptance/_steps/CRMGuestSteps.php`~~
  - ~~`1885OS_Code/crmapp/tests/acceptance/_steps/CRMServicesManagementSteps.php`~~
  - ~~`1885OS_Code/crmapp/tests/acceptance/EditServiceCept.php`~~
  - ~~`1885OS_Code/crmapp/tests/acceptance/DeleteServiceCept.php`~~

> ~~The test imported from the code bundle has made a ton of assumptions about our project, many of which are incorrect. To compensate for this, the files I have copied from a `basic` Yii install include:~~
- ~~`models/User.php`~~
- ~~`models/ContactForm.php`~~
- ~~`models/EntryForm.php`~~
- ~~`models/LoginForm.php`~~
- ~~`views/site/*.php`~~
- ~~I have updated `controllers/SiteController.php` with the contents of the `basic` `SiteController`, but left `actionIndex()` unmodified.~~
- ~~`config/web.php` should be updated with a `user` component:~~
```php
'user' => [
            'identityClass' => 'app\models\User',
            'enableAutoLogin' => true,
        ],
```
- ~~The test has switched from using PHPBrowser to WebDriver. To make that work, add PhantomJS to `composer.json` as detailed here: https://samsonasik.wordpress.com/2014/12/18/using-php-phantomjs-with-codeception/~~

#### Page 76
As you're entering data manually, note that the field order in your app is reversed from the order in the book. Form validation will still warn you if you attempt to submit the form with invalid data.

[return to README](README.md)
