sweet-alert2-rails
==================

[![Build Status](https://travis-ci.org/nicolasblanco/sweet-alert2-rails.svg?branch=master)](https://travis-ci.org/nicolasblanco/sweet-alert2-rails)

This library easily integrates the SweetAlert 2 library into a Rails application.

It replaces the boring standard JavaScript alert boxes with nice looking and animated ones.

<img src="https://github.com/nicolasblanco/sweet-alert2-rails/blob/master/doc/sweet_alert.png?raw=true" width="800" alt="before" />

Using the same Rails markup :

```Ruby
  = link_to 'Delete', item, method: :delete, data: { confirm: 'Are you sure you want to delete this item?' }
```

It is heavily based on the work from Moises Viloria with SweetAlert. Some cleaning and refactoring were made to make it compatible with SweetAlert 2.

It replaces the browser confirm dialog when using `data: { confirm: 'message' }` with the link_to helper with a nice looking sweet alert.

## Requirements

Rails >= 4.2, tested with Rails 5

## Usage

Add the SweetAlert2 and sweet-alert2-rails to your Gemfile:

```ruby
gem 'rails-assets-sweetalert2', '~> 5.1.1', source: 'https://rails-assets.org'
gem 'sweet-alert2-rails'
```

Add the following to application.js:

```javascript
//= require sweetalert2
//= require sweet-alert2-rails
```

Note : if you're using Rails >= 5.1, you need to inject before this plugin `jquery` and `jquery-ujs` because they are not dependencies anymore. Read https://github.com/rails/jquery-rails#installation for more information.


Add the following to application.css:

```css
/*
 *= require sweetalert2
 */
```

Try it:

```Ruby
  = link_to "Delete", user, method: :delete, data: { confirm: 'Are you sure?' }
```

### Custom options

You may pass options in `data:`
```Ruby
 data: {
  confirm: 'Are you ready?',
  'confirm-button-text': 'Im ready',
  'cancel-button-text': 'No way',
  'confirm-button-color': '#66CD00',
  'sweet-alert-type': 'info',
  text: 'This is a subtitle',
  'image-url': '/pic.png'
}
```

Default options that will be used application wide so it is not necessary to set the option on each link. Put this object inside your app to override default options with the `sweetAlertConfirmConfig` object.

```Javascript
window.sweetAlertConfirmConfig = {
  title: 'Are you sure?',
  type: 'warning',
  showCancelButton: true,
  confirmButtonColor: '#DD6B55',
  confirmButtonText: 'Ok'
};
```

## Contribute

Fork the repo & make a pull request with your fix or feature. Thanks :).
