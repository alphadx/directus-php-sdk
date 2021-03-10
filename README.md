# THIS IS NOT A PRODUCTION VERSION

This is still in heavy development and is not a working project, we are working as hard as we can to get this finished.


<p align="center"><img width="400" alt="Logo" src="https://cdn.slations.co.uk/images/Slations-Logo.svg"></p>

<br>

# Directus PHP SDK

The Slations unofficial PHP SDK for Directus 9


# Documentation

## Installation

To install the Directus PHP SDK is super simple and easy. First download the latest release from the releases section of Github and extract the files. Then copy the following files into your project and your ready to get started.
```
Desired Folder
|- Directus.php
```

## Usage

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

### Getting the API URL

```
$directus->base_url;
```


## Auth

### Login

```
$directus->auth_user('demo@slations.co.uk', 'Pa33w0rd');
```

### Refresh

By default the SDK will call a new

### Logout

```
$directus->auth_logout();
```

### Request a Password Reset
The second value is optional if you want to sent a custom return URL for the reset email.
```
$directus->auth_password_request('demo@slations.co.uk', 'https://example.com/comfirm');
```

### Reset a Password
Note: the token passed in the first parameter is sent in an email to the user when using `auth_password_request`
```
$directus->auth_password_reset('the.id.passed.from.the.email', 'The1rN3wPa33W0rd');
```

## Users

### Invite a New User


### Accept a User Invite


### Enable Two-Factor Authentication


### Disable Two-Factor Authentication


### Get the Current User


### Update the Current Users
