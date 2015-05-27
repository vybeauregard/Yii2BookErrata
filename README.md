# Yii2BookErrata
An attempt to log and provide workarounds for omissions, assumptions, and other less-than-clear instructions in "Web Application Development with Yii2 and PHP"

## Chapter 1

No code is written in the chapter, as it covers configuring your dev environment.

## Chapter 2

This chapter is critical, as it is the basis for the rest of the exercises in the book. 

#### Page 30
- The author jumped over to the command line to install Faker. Continue entering these methods into `tests/acceptance/_steps/CRMOperatorSteps.php`

#### Page 32
- `CRMUsersSteps.php`: `fillInPhoneFieldWithDataFrom()` must fill the field identified as `phone_number`, not `PhoneRecord[number]` in order for the test to yield success.

```
    function fillInPhoneFieldWithDataFrom($customer_data)
    {
        $I = $this;
        $I->fillField(
            'phone_number',
            $customer_data['PhoneRecord[number]']
        );
    }
```

#### Page 40
- `getRecordsAccordingToQuery()` is referred to as `findRecordsByQuery()` throughout the rest of this exercise. Change it here to avoid errors.

#### Page 41
- Add the following construct method to `Phone.php`:
```
    public function __construct($number)
    {
        $this->number = $number;
    }
```

#### Page 43
- Make sure you save `db.php` under `config/`.

#### Page 46
- Yii expects the date format as `yyyy-M-d`. http://stackoverflow.com/a/26098149

>http://userguide.icu-project.org/formatparse/datetime#TOC-Date-Time-Format-Syntax

#### Page 52
- Don't mess with RewriteRules right now. If you're using the server built into your local php installation, your URLs should resolve properly without them.

#### Page 53
- The form in the book is definitely not what comes up here. Refer to http://blogyii.com/blog/class-customerrecord-not-found to resolve the multitude of errors produced.
- Also, bower has moved the jQuery path! Follow the instructions at http://blogyii.com/blog/installing-yii2-with-composer to correct that and add all other packages this project will need.

#### Page 54
- "shorthand" means include the code snippet as a method of the `CustomersController` class.

#### Page 56
- `wrapIntoDataProvider()` should be added to the `CustomersController` class, as it is called by its `findRecordsByQuery()` method.
- see also: http://blogyii.com/blog/unknown-method-and-wrong-redirect

#### Page 58
- `actionQuery()` should be added to `CustomersController`
- The "custom handcrafted form" is the full content of `views/customers/query.php`

#### Page 59
- If `date.timezone` has not been set in `/var/php.ini`, add it:

```
date.timezone = "America/New_York"
```

## Chapter 3

We are continuing to build upon the CRM app we started on in Chapter 2. Most of the issues resolved in that stage of development should carry through to this chapter.

#### Page 74
- Before running the next Codeception test, download the code bundle from https://www.packtpub.com/books/content/support

> Type `yii2` into the `Search...` field in the middle of the page and select `Web Application Development with Yii 2 and PHP`.
> On the next screen, fill out the form and you will receive a download link in your email.

- Open the zip file and copy the following files into their respective folders in your `crmapp`:
  - `1885OS_Code/crmapp/tests/acceptance/_steps/CRMGuestSteps.php`
  - `1885OS_Code/crmapp/tests/acceptance/_steps/CRMServicesManagementSteps.php`
  - `1885OS_Code/crmapp/tests/acceptance/EditServiceCept.php`
  - `1885OS_Code/crmapp/tests/acceptance/DeleteServiceCept.php`

> The test imported from the code bundle has made a ton of assumptions about or project, many of which are incorrect. To compensate for this, the files I have copied from a `basic` Yii install include:
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
