# Yii2BookErrata
An attempt to log and provide workarounds for omissions, assumptions, and other less-than-clear instructions in "Web Application Development with Yii2 and PHP"

## Chapter 1

No code is written in the chapter, as it covers configuring your dev environment.

## Chapter 2

#### Page 30
- Continue entering these methods into `tests/acceptance/_steps/CMUserSteps.php`

#### Page 40
- `getRecordsAccordingToQuery()` is referred to as `findRecordsByQuery()` throughout the rest of this exercise. Change it here to avoid errors.

#### Page 53
- The form in the book is definitely not what comes up here. Refer to http://blogyii.com/blog/class-customerrecord-not-found to resolve the multitude of errors produced.
- Also, bower has moved the jQuery path!
`crmapp/vendor $ ln -s bower-asset/ bower`

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
