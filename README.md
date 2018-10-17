# Pardot-API
PHP package to interact with the Pardot API

[![Latest Stable Version](https://poser.pugx.org/cyber-duck/pardot-api/v/stable)](https://packagist.org/packages/cyber-duck/pardot-api)
[![Latest Unstable Version](https://poser.pugx.org/cyber-duck/pardot-api/v/unstable)](https://packagist.org/packages/cyber-duck/pardot-api)
[![Total Downloads](https://poser.pugx.org/cyber-duck/pardot-api/downloads)](https://packagist.org/packages/cyber-duck/pardot-api)
[![License](https://poser.pugx.org/cyber-duck/pardot-api/license)](https://packagist.org/packages/cyber-duck/pardot-api)

Author: [Andrew Mc Cormack](https://github.com/Andrew-Mc-Cormack)

## Pardot API PHP Library

A library to integrate with the Pardot API through PHP objects

This library simplifies the process of authentication and querying the Pardot API and provides access to all of the v4 API features.

### Setup

To initalise the Pardot API object pass your user email, password, and user key credentials.

```php
use CyberDuck\Pardot\PardotApi;

$pardot = new PardotApi(
    'EMAIL',
    'PASSWORD',
    'USER_KEY'
);
```

## Method Objects

Methods can be called on the PardotApi instance which correspond to the object types in Pardot. 
When calling a method a specific Object instance is returned granting access to the object methods.
Response are either arrays of or single PHP stdClass objects.
The full list of objects available are as follows:

### Account methods

```php
$pardot->account()->read(); // retrieves current account information
```

### Campaign methods

```php
$pardot->campaigns()->query([...]); // queries and returns a filtered campaign list
$pardot->campaigns()->create([...]); // creates a campaign with array data
$pardot->campaigns()->read(1); // queries a campaign by ID
$pardot->campaigns()->update(1, [...]); // updates a campaign by ID with array data 
```

### Custom Fields methods

```php
$pardot->customFields()->query([...]); // queries and returns a filtered custom field list
$pardot->customFields()->create([...]); // creates a custom field with array data
$pardot->customFields()->read(1); // queries a custom field by ID
$pardot->customFields()->update(1, [...]); // updates a custom field by ID with array data 
$pardot->customFields()->delete(1); // deletes a custom field by ID
```

### Custom Redirects methods

### Dynamic Content methods

### Email Clicks methods

### Email methods

### Email Templates methods

### Forms methods

### Lifecycle Histories methods

### Lifecycle Stages methods

### List Memberships methods

### Lists methods

### Opportunities methods

### Prospect Accounts methods

### Prospects methods

### Tag Objects methods

### Tags methods

### Users methods

### Visitor Activities methods

### Visitors methods

### Visits methods

## Debugging

Error messages can be enabled by turning debugging on. Requests to the Pardot API will fail silently by default so as to prevent
fatal application errors. Extra response checking should be conducted when implementing this library as most methods will return
null when there is an issue with the API query.

```php
$pardot->setDebug(true);
```

## Output Type

You can change the output type to full, simple, mobile, or bulk. Defaults to full.

```php
$pardot->setOuput('full');
```

