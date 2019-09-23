# lighdator
lighdator is simple and light weight field validator.


# Installation

Install via npm, which is useful for node based frameworks
```
npm i lighdator
```

Use via script tag in browser

```
<script src="https://unpkg.com/lighdator@latest/index.js"></script>
```


# Usage

**Demo**: https://jsfiddle.net/muralit/j8dnwbyk/

HTML structure for the form field to follow
```html
<div class="form-container">
    <div class="form-field">
        <label for="firstName"> First Name </label>
        <input type="text" id="firstName" 
			data-validate-alpha="true"
			data-validate-required="true"
			data-validate-minlength="2" 
			data-validate-maxlength="10" 
			data-validate-regex="^[a-zA-Z]+$"
			data-validate-reactive="true" 
			data-validate-alpha="true" />
        <span class="error-message required">This field is required</span>
        <span class="error-message alpha">This field is aplha validation</span>
        <span class="error-message regex">This field is regex validation</span>
        <span class="error-message minlength">This field is min length validation</span>
        <span class="error-message maxlength">This field is max length validation</span>
    </div>
    <div>
      <button type="button" onclick="submitForm('.form-container')">
        Submit
      </button>
    </div>
</div>
```

JS code for validating on submission of the form

```javascript
window.onload = function() {
    lighdator.bindValidation();
};

var submitForm = function(elemSelector) {
    var errors = lighdator.validateForm(document.querySelector(elemSelector));
};
```

CSS for error messages

```css
.form-field .error-message {
    display: none;
    color: red;
}

.form-field.required .required,
.form-field.alpha .alpha,
.form-field.alphanumeric .alphanumeric,
.form-field.regex .regex,
.form-field.minlength .minlength,
.form-field.maxlength .maxlength,
.form-field.email .email {
    display: inline;
}
```


# Allowed Rules

**"data-validate-required"**

check field is empty or not, appends "invalid" and "required" to form-field if the value of the field is empty


**"data-validate-minlength"**

Appends "minlength" if the length of field's value is lessthan provided value


**"data-validate-maxlength"**

Appends "maxlength" css classname if the length of the field's value is greater than provided value.


**"data-validate-regex"**

Appends "regex" if the field value doesn't match with the field value.


**"data-validate-email"**

Appends "email" if the field value doesn't match with email format.



**"data-validate-alpha"**

Appends "aplha" if the field value contains other than aplhabets


**"data-validate-alphanumeric"**

Appends "alphanumeric" if the field value contains other than aplhabets and numbers
