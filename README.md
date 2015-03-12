# Laravel Form Helper

**Form helpers for Laravel 5+**

## Contents

1. <a href="#introduction">Introduction</a>
2. <a href="#installation">Installation</a>
3. <a href="#quick-start">Quick start</a>
4. <a href="#helpers">Helpers</a>
5. <a href="#helpers">Helpers</a>
6. <a href="#themes">Themes</a>
7. <a href="#support">Support</a>
8. <a href="#license">License</a>

## <a id="introduction"></a>Introduction

*Laravel Form* provides a series of helpers for form creation on Blade templates.

Compatible with Laravel 5+.

## <a id="installation"></a>Installation

At `composer.json` of your Laravel installation, add the following require line:

``` json
{
    "require": {
        "intentor/laravel-form": "~1.0"
    }
}
```

Run `composer update` to add the package to your Laravel app.

At `config/app.php`, add the Service Provider and the Facade:

```php
    'providers' => [
		'Intentor\LaravelForm\ServiceProvider',
    ]

	//...

    'aliases' => [
        ''Form' => 'Intentor\LaravelForm\Facade'
    ]
```

## <a id="quick-start"></a> Quick start

To create a form, use the `Form` facade to open and close it:

```php
{!! Form::open(action('LoginController@store')) !!}
					
{!! Form::close() !!}
```

Any controls you want to create must be placed between the opening and closing of the form:

```php
{!! Form::open(action('LoginController@store')) !!}
	
{!! Form::text('name', 'Name') !!}
						
{!! Form::buttons('Send', 'Reset') !!}
			
{!! Form::close() !!}
```

## <a id="helpers"></a> Helpers

### Form::open

Opens a form. See <a href="#themes">Themes</a> for more details on form themes.

```php
{!! Form::open($url, $method = 'POST', $theme = null, $includeCsrfToken = true, $attributes = []) !!}
```

**Parameters**

* string `$url` Action URL.
* string `$method` Form method.
* bool `$theme` Controls theme. It's a subfolder on the partials.form folder.
* bool `$includeCsrfToken` Indicates whether the CSRF token should be included.
* array `$attributes` Form attributes.

### Form::model

Opens a form for a model. See <a href="#themes">Themes</a> for more details on form themes.

```php
{!! Form::model($model, $url, $method = 'POST', $theme = null, $includeCsrfToken = true, $attributes = []) !!}
```

**Parameters**

* object `$model` Model object.
* string `$url` Action URL.
* string `$method` Form method.
* bool `$theme` Controls theme. It's a subfolder on the partials.form folder.
* bool `$includeCsrfToken` Indicates whether the CSRF token should be included.
* array `$attributes` Form attributes.

### Form::close

Closes a from.

```php
{!! Form::close() !!}
```

**Parameters**

None.

### Form::label

Creates a label.

```php
{!! Form::label($text, $field = null, $attributes = []) !!}
```

**Parameters**
 
* string `$text` Label text.
* string `$field` Related field name.
* array `$attributes` Element attributes.

### Form::readonly

Creates a readonly control.

```php
{!! Form::readonly($label, $text, $attributes = []) !!}
```

**Parameters**
 
* string `$label` Label text.
* string `$text` Field text.
* array `$attributes` Element attributes.


### Form::hidden

Creates a hidden field.

```php
{!! Form::hidden($name, $value = null, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$value` Field value.
* array `$attributes` Element attributes.

### Form::text

Creates a text field.

```php
{!! Form::text($name, $label = null, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* array `$attributes` Element attributes.

### Form::textarea

Creates a textarea field.

```php
{!! Form::textarea($name, $label = null, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* array `$attributes` Element attributes.

### Form::email

Creates an e-mail field.

```php
{!! Form::email($name, $label = null, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* array `$attributes` Element attributes.

### Form::url

Creates an URL field.

```php
{!! Form::url($name, $label = null, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* array `$attributes` Element attributes.

### Form::number

Creates an URL field.

```php
{!! Form::number($name, $label = null, $min = 0, $max = 9999, $step = 1, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* int `$min` Minimum number.
* int `$max` Maximum number.
* int `$step` Combined with the min value, defines the acceptable numbers in the range.
* array `$attributes` Element attributes.

### Form::password

Creates a password field.

```php
{!! Form::password($name, $label = null, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* array `$attributes` Element attributes.

### Form::checkbox

Creates a checkbox field.

```php
{!! Form::checkbox($name, $label = null, $value = 1, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* string `$value` Field value.
* array `$attributes` Element attributes.

### Form::radio

Creates a radio field.

```php
{!! Form::radio($name, $label = null, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* array `$attributes` Element attributes.

### Form::checkboxGroup

Creates a checkbox group.

```php
{!! Form::checkboxGroup($name, $label = null, $list = [], $selected = [], $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* array `$list` Item's list. Should be on format [ 'value' => '', 'text' => '' ].
* array `$selected` Selected values.
* array `$attributes` Element attributes.

### Form::radioGroup

Creates a radio group.

```php
{!! Form::radioGroup($name, $label = null, $list = [], $selected = null, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* array `$list` Item's list. Should be on format [ 'value' => '', 'text' => '' ].
* string `$selected` Selected value.
* array `$attributes` Element attributes.

### Form::dropdown

Creates a dropdown field.

```php
{!! Form::dropdown($name, $label = null, $list = [], $empty = null, $selected = null, $attributes = []) !!}
```

**Parameters**
 
* string `$name` Field name.
* string `$label` Field label.
* array `$list` Item's list. Should be on format [ 'value' => 'text', 'text' => '' ].
* string `$empty` Empty value text. If no text is provided, there will not be an empty option.
* string `$selected` Selected value.
* array `$attributes` Element attributes.

### Form::submit

Creates a submit button.

```php
{!! Form::submit($label) !!}
```

**Parameters**
 
* string `$label` Control label.

### Form::reset

Creates a reset button.

```php
{!! Form::reset($label) !!}
```

**Parameters**

None

### Form::buttons

Creates form buttons (submit and reset).

```php
{!! Form::buttons($submitLabel, $resetLabel = null) !!}
```

**Parameters**

* string `$submitLabel` Submit button label.
* string `$resetLabel` Reset button label. If no label is given, the button is not created.

## <a id="themes"></a>Themes

Themes are a way to customize the look of forms using partial views.

There are three different themes available:

1. **default**: a simple form theme without any third party dependencies.
2. **horizontal**: default [Bootstrap horizontal](http://getbootstrap.com/css/#forms-horizontal) form (Requires [Bootstrap 3](http://getbootstrap.com/)).
3. **vertical**: default [Bootstrap vertical](http://getbootstrap.com/css/#forms-example) form (Requires [Bootstrap 3](http://getbootstrap.com/)).

All themes are subfolders at `src/resources/views/partials/form` folder.

**Note**: currently, to create a custom form theme, you have to place the theme at `src/resources/views/partials/form` folder. 

## <a id="support"></a>Support

Found a bug? Please create an issue on the [GitHub project page](https://github.com/intentor/laravel-form/issues) or send a pull request if have a fix or extension.

You can also send me a message at support@intentor.com.br to discuss more obscure matters about the component.

## <a id="license"></a>License

Licensed under the [The MIT License (MIT)](http://opensource.org/licenses/MIT). Please read LICENSE for more information.