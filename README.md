# PLEASE DOWNLOAD THE LATEST RELEASE

<p align="center"><img width="400" alt="Logo" src="https://cdn.slations.co.uk/images/Slations-Logo.svg"></p>

<br>

# Directus PHP SDK

The Slations unofficial PHP SDK for Directus 9


# Documentation

## Installation (DONE)

To install the Directus PHP SDK is super simple and easy. First download the latest release from the releases section of Github and extract the files. Then copy the following files into your project and your ready to get started.
```
Desired Folder
|- Directus.php
```

## Usage (DONE)

```
<?php 

include 'Directus.php'; // Include the SDK Class

$directus = new Directus(); // Create a new Directus SDK instance

// Setup the config for the Directus SDK
$directus->config([
  "base_url" => "https://url.to.your.directus.install.io/",
  "auth_storage" => "$_SESSION" // This can be set to $_SESSION or if you want to store it as a cookie you can also use $_COOKIE
]);

```


## Global

### Getting the API URL (DONE)

```
$directus->base_url;
```


## Items

### Create Single Item (DONE)
```
$directus->create_items('articles', array(
  "status" => "draft",
  "title" => "example",
  "slug" => "example"
));
```

### Read All (DONE)
```
$directus->get_items('articles');
```

### Read By Query (TODO: Not yet completed)
```
$directus->get_items('articles', array(
  search => "",
  filter => array(
    "date_published" => array(
      "_gte" => "$NOW"
    )
  )
));
```

### Read By Primary Key(s)
```
// Single (DONE)
$directus->get_items('articles', 15);

// Multiple (TODO: Not yet completed)
$directus->get_items('articles', array(15, 42));
```

### Update an Item
```
$directus->update_items('articles', array("title" => "example_new"), ID/'UUID');
```

### Delete an Item
```
$directus->delete_items('articles', ID/'UUID');
```

### Delete multiple Items
```
$directus->delete_items('articles', array('UUID', 'UUID2', ID, ID2));
```


## Auth

### Login (DONE)

```
$directus->auth_user('demo@slations.co.uk', 'Pa33w0rd');
```

### Refresh (TODO: Not yet completed)

By default the SDK will call a new

### Logout (DONE)

```
$directus->auth_logout();
```

### Request a Password Reset (DONE)
The second value is optional if you want to sent a custom return URL for the reset email.
```
$directus->auth_password_request('demo@slations.co.uk', 'https://example.com/comfirm');
```

### Reset a Password (DONE)
Note: the token passed in the first parameter is sent in an email to the user when using `auth_password_request`
```
$directus->auth_password_reset('the.id.passed.from.the.email', 'The1rN3wPa33W0rd');
```

## Users

### Invite a New User (TODO: Not yet completed)


### Accept a User Invite (TODO: Not yet completed)


### Enable Two-Factor Authentication (TODO: Not yet completed)


### Disable Two-Factor Authentication (TODO: Not yet completed)


### Get the Current User (TODO: Not yet completed)


### Update the Current Users (TODO: Not yet completed)
