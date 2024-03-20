# Fluttering Frost Forms

A lightweight JavaScript library for creating and managing forms with ease.

## Installation

Install `fluttering-frost-forms` using npm:

```bash
npm install fluttering-frost-forms
```

## Usage

First, import `FlutteringFrostForms` into your project:

```javascript
import FlutteringFrostForms from 'fluttering-frost-forms';
```

Define a schema for your form:

```javascript
const formSchema = {
username: {
defaultValue: '',
validator: (value) => value.length > 0 && value.length < 20
},
birthday: {
defaultValue: '',
validator: (value) => moment(value, 'YYYY-MM-DD').isValid()
}
};
```

Initialize your form with the schema:

```javascript
const myForm = new FlutteringFrostForms(formSchema);
myForm.initializeForm();
```

Validate and submit the form:

```javascript
try {
myForm.validateField('username', 'johnDoe');
myForm.validateField('birthday', '1990-01-01');
myForm.submitForm();
} catch (error) {
console.error(error.message);
}
```

## License

This project is licensed under the MIT License.
