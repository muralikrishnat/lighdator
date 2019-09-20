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
```
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
```

JS code for validating on submission of the form

```
window.onload = function() {
    lighdator.bindValidation();
};

var submitForm = function(elemSelector) {
    var errors = lighdator.validateForm(document.querySelector(elemSelector));
};
```