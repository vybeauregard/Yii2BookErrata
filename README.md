# Yii2BookErrata
An attempt to log and provide workarounds for omissions, assumptions, and other less-than-clear instructions in "Web Application Development with Yii2 and PHP"

## Chapter 1

No code is written in the chapter, as it covers configuring your dev environment.

## Chapter 2

This chapter is critical, as it is the basis for the rest of the exercises in the book. 

#### Page 30
- The author jumped over to the command line to install Faker. Continue entering these methods into `tests/acceptance/_steps/CRMOperatorSteps.php`

#### Page 40
- `getRecordsAccordingToQuery()` is referred to as `findRecordsByQuery()` throughout the rest of this exercise. Change it here to avoid errors.

#### Page 43
- Make sure you save `db.php` under `config/`.

#### Page 46
- Yii expects the date format as `yyyy-M-d`. http://stackoverflow.com/a/26098149

>http://userguide.icu-project.org/formatparse/datetime#TOC-Date-Time-Format-Syntax

#### Page 52
- Don't mess with RewriteRules right now. Just make sure any urls past this point include `http://localhost:8000/index.php/` any place the book references `http://yourdomain/`.

#### Page 53
- The form in the book is definitely not what comes up here. Refer to http://blogyii.com/blog/class-customerrecord-not-found to resolve the multitude of errors produced.
- Also, bower has moved the jQuery path! *From the command line:* `crmapp/vendor $ ln -s bower-asset/ bower`

#### Page 54
- "shorthand" means include the code snippet as a method of the `CustomersController` class.

#### Page 56
- `wrapIntoDataProvider()` should be added to the `CustomersController` class, as it is called by its `findRecordsByQuery()` method.
- see also: http://blogyii.com/blog/unknown-method-and-wrong-redirect

#### Page 58
- `actionQuery()` should be added to `CustomersController`
- The "custom handcrafted form" is the full content of `views/customers/query.php`

#### Page 59
- If `date.timezone` has not been set in `/var/php.ini`, add it. `date.timezone = "America/New_York"`

>I haven't been able to get codeception to successfully run the tests created for this project. It is failing to find  the `PhoneRecord[number]` field when entering customer info into the form.
>
>Suggestions are welcome.
