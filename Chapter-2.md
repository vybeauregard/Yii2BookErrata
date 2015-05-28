[return to README](README.md)
## Chapter 2

#### Page 30
- The author jumped over to the command line to install Faker. Continue entering these methods into `tests/acceptance/_steps/CRMOperatorSteps.php`

#### Page 32
- `CRMUsersSteps.php`: `fillInPhoneFieldWithDataFrom()` must fill the field identified as `phone_number`, not `PhoneRecord[number]` in order for the test to yield success.

    ```php
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
```php
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

    ```php
    date.timezone = "America/New_York"
    ```
[return to README](README.md)
