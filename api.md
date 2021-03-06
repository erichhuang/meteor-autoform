## aldeed:autoform Public API ##

Easily create forms with automatic insert and update, and automatic reactive validation.

_API documentation automatically generated by [docmeteor](https://github.com/raix/docmeteor)._

-

### <a name="AutoForm.addHooks"></a>*autoform*.addHooks(formIds, hooks)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __addHooks__ is defined in `AutoForm`*

__Arguments__

* __formIds__ *{[String[]](#String[])|String|null}*  

 Form `id` or array of form IDs to which these hooks apply. Specify `null` to add hooks that will run for every form.

* __hooks__ *{Object}*  

 Hooks to add, where supported names are "before", "after", "formToDoc", "docToForm", "onSubmit", "onSuccess", and "onError".


__Returns__  *{undefined}*


Defines hooks to be used by one or more forms. Extends hooks lists if called multiple times for the same
form.

> ```AutoForm.addHooks = function autoFormAddHooks(formIds, hooks, replace) { ...``` [autoform-api.js:19](autoform-api.js#L19)


-

### <a name="AutoForm.hooks"></a>*autoform*.hooks(hooks)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __hooks__ is defined in `AutoForm`*

__Arguments__

* __hooks__ *{Object}*  

__Returns__  *{undefined}*


Defines hooks by form id. Extends hooks lists if called multiple times for the same
form.

> ```AutoForm.hooks = function autoFormHooks(hooks, replace) { ...``` [autoform-api.js:57](autoform-api.js#L57)


-

### <a name="AutoForm.resetForm"></a>*autoform*.resetForm(formId, [template])&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __resetForm__ is defined in `AutoForm`*

__Arguments__

* __formId__ *{String}*  
* __template__ *{[TemplateInstance](#TemplateInstance)}*  (Optional)

 Looked up if not provided. Pass in for efficiency.


__Returns__  *{undefined}*


Resets an autoform, including resetting validation errors. The same as clicking the reset button for an autoform.

> ```AutoForm.resetForm = function autoFormResetForm(formId, template) { ...``` [autoform-api.js:72](autoform-api.js#L72)


-

### <a name="AutoForm.setDefaultTemplate"></a>*autoform*.setDefaultTemplate(template)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __setDefaultTemplate__ is defined in `AutoForm`*

__Arguments__

* __template__ *{String}*  


> ```AutoForm.setDefaultTemplate = function autoFormSetDefaultTemplate(template) { ...``` [autoform-api.js:84](autoform-api.js#L84)


-

### <a name="AutoForm.getDefaultTemplate"></a>*autoform*.getDefaultTemplate()&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __getDefaultTemplate__ is defined in `AutoForm`*


Reactive.

> ```AutoForm.getDefaultTemplate = function autoFormGetDefaultTemplate() { ...``` [autoform-api.js:95](autoform-api.js#L95)


-

### <a name="AutoForm.setDefaultTemplateForType"></a>*autoform*.setDefaultTemplateForType(type, template)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __setDefaultTemplateForType__ is defined in `AutoForm`*

__Arguments__

* __type__ *{String}*  
* __template__ *{String}*  


> ```AutoForm.setDefaultTemplateForType = function autoFormSetDefaultTemplateForType(type, template) { ...``` [autoform-api.js:106](autoform-api.js#L106)


-

### <a name="AutoForm.getDefaultTemplateForType"></a>*autoform*.getDefaultTemplateForType(type)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __getDefaultTemplateForType__ is defined in `AutoForm`*

__Arguments__

* __type__ *{String}*  

__Returns__  *{String}*
Template name


Reactive.

> ```AutoForm.getDefaultTemplateForType = function autoFormGetDefaultTemplateForType(type) { ...``` [autoform-api.js:125](autoform-api.js#L125)


-

### <a name="AutoForm.getFormValues"></a>*autoform*.getFormValues(formId)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __getFormValues__ is defined in `AutoForm`*

__Arguments__

* __formId__ *{String}*  

 The `id` attribute of the `autoForm` you want current values for.


__Returns__  *{Object}*


Returns an object representing the current values of all schema-based fields in the form.
The returned object contains two properties, "insertDoc" and "updateDoc", which represent
the field values as a normal object and as a MongoDB modifier, respectively.

> ```AutoForm.getFormValues = function autoFormGetFormValues(formId) { ...``` [autoform-api.js:143](autoform-api.js#L143)


-

### <a name="AutoForm.getFieldValue"></a>*autoform*.getFieldValue(formId, fieldName)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __getFieldValue__ is defined in `AutoForm`*

__Arguments__

* __formId__ *{String}*  

 The `id` attribute of the `autoForm` you want current values for.

* __fieldName__ *{String}*  

 The name of the field for which you want the current value.


__Returns__  *{Any}*


Returns the value of the field (the value that would be used if the form were submitted right now).
This is a reactive method that will rerun whenever the current value of the requested field changes.

> ```AutoForm.getFieldValue = function autoFormGetFieldValue(formId, fieldName) { ...``` [autoform-api.js:165](autoform-api.js#L165)


-

### <a name="AutoForm.getInputValue"></a>*autoform*.getInputValue(element, [ss])&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __getInputValue__ is defined in `AutoForm`*

__Arguments__

* __element__ *{[DOMElement](#DOMElement)}*  

 The input DOM element, generated by an autoform input control, which must have a `data-schema-key` attribute set to the correct schema key name.

* __ss__ *{[SimpleSchema](#SimpleSchema)}*  (Optional)

 Provide the SimpleSchema instance if you already have it.


__Returns__  *{Any}*


Returns the value of the field (the value that would be used if the form were submitted right now).
Unlike `AutoForm.getFieldValue`, this function is not reactive.

> ```AutoForm.getInputValue = function autoFormGetInputValue(element, ss) { ...``` [autoform-api.js:182](autoform-api.js#L182)


-

### <a name="AutoForm.addInputType"></a>*autoform*.addInputType(name, definition)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __addInputType__ is defined in `AutoForm`*

__Arguments__

* __name__ *{String}*  

 The type string that this definition is for.

* __definition__ *{Object}*  

 Defines how the input type should be rendered.

    * __componentName__ *{String}*  

    The component name. A template with the name <componentName>_bootstrap3, and potentially others, must be defined.


__Returns__  *{undefined}*


Use this method to add custom input components.

> ```AutoForm.addInputType = function afAddInputType(name, definition) { ...``` [autoform-api.js:259](autoform-api.js#L259)


-

### <a name="AutoForm.validateField"></a>*autoform*.validateField(formId, fieldName, [skipEmpty])&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __validateField__ is defined in `AutoForm`*

__Arguments__

* __formId__ *{String}*  

 The `id` attribute of the `autoForm` you want to validate.

* __fieldName__ *{String}*  

 The name of the field within the `autoForm` you want to validate.

* __skipEmpty__ *{Boolean}*  (Optional, Default = false)

 Set to `true` to skip validation if the field has no value. Useful for preventing `required` errors in form fields that the user has not yet filled out.


__Returns__  *{Boolean}*
Is it valid?


In addition to returning a boolean that indicates whether the field is currently valid,
this method causes the reactive validation messages to appear.

> ```AutoForm.validateField = function autoFormValidateField(formId, fieldName, skipEmpty) { ...``` [autoform-api.js:276](autoform-api.js#L276)


-

### <a name="AutoForm.validateForm"></a>*autoform*.validateForm(formId)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __validateForm__ is defined in `AutoForm`*

__Arguments__

* __formId__ *{String}*  

 The `id` attribute of the `autoForm` you want to validate.


__Returns__  *{Boolean}*
Is it valid?


In addition to returning a boolean that indicates whether the form is currently valid,
this method causes the reactive validation messages to appear.

> ```AutoForm.validateForm = function autoFormValidateForm(formId) { ...``` [autoform-api.js:294](autoform-api.js#L294)


-

### <a name="AutoForm.getValidationContext"></a>*autoform*.getValidationContext(formId)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __getValidationContext__ is defined in `AutoForm`*

__Arguments__

* __formId__ *{String}*  

 The `id` attribute of the `autoForm` for which you want the validation context


__Returns__  *{SimpleSchemaValidationContext}*
The SimpleSchema validation context object.


Use this method to get the validation context, which can be used to check
the current invalid fields, manually invalidate fields, etc.

> ```AutoForm.getValidationContext = function autoFormGetValidationContext(formId) { ...``` [autoform-api.js:310](autoform-api.js#L310)


-

### <a name="AutoForm.find"></a>*autoform*.find()&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __find__ is defined in `AutoForm`*

__Returns__  *{Object}*
The data context for the closest autoform.


Call this method from a UI helper to get the data context for the closest autoform. Always returns the context or throws an error.

> ```AutoForm.find = function autoFormFind(type) { ...``` [autoform-api.js:325](autoform-api.js#L325)


-

### <a name="AutoForm.findAttribute"></a>*autoform*.findAttribute(attrName)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __findAttribute__ is defined in `AutoForm`*

__Arguments__

* __attrName__ *{String}*  

 Attribute name


__Returns__  *{Any|undefined}*
Searches for the given attribute, looking up the parent context tree until the closest autoform is reached.


Call this method from a UI helper. Might return undefined.

> ```AutoForm.findAttribute = function autoFormFindAttribute(attrName) { ...``` [autoform-api.js:344](autoform-api.js#L344)


-

### <a name="AutoForm.findAttributesWithPrefix"></a>*autoform*.findAttributesWithPrefix(prefix)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __findAttributesWithPrefix__ is defined in `AutoForm`*

__Arguments__

* __prefix__ *{String}*  

 Attribute prefix


__Returns__  *{Object}*
An object containing all of the found attributes and their values, with the prefix removed from the keys.


Call this method from a UI helper. Searches for attributes that start with the given prefix, looking up the parent context tree until the closest autoform is reached.

> ```AutoForm.findAttributesWithPrefix = function autoFormFindAttributesWithPrefix(prefix) { ...``` [autoform-api.js:369](autoform-api.js#L369)


-

### <a name="AutoForm.debug"></a>*autoform*.debug()&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __debug__ is defined in `AutoForm`*


Call this method in client code while developing to turn on extra logging.

> ```AutoForm.debug = function autoFormDebug() { ...``` [autoform-api.js:401](autoform-api.js#L401)


-

### <a name="AutoForm.arrayTracker"></a>*autoform*.arrayTracker {any}&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This property __arrayTracker__ is defined in `AutoForm`*


> ```AutoForm.arrayTracker = arrayTracker;``` [autoform-api.js:415](autoform-api.js#L415)


-

### <a name="AutoForm.getInputType"></a>*autoform*.getInputType(atts)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __getInputType__ is defined in `AutoForm`*

__Arguments__

* __atts__ *{Object}*  

 The attributes provided to afFieldInput.


__Returns__  *{String}*
The input type. Most are the same as the `type` attributes for HTML input elements, but some are special strings that autoform interprets.


Call this method from a UI helper to get the type string for the input control.

> ```AutoForm.getInputType = getInputType;``` [autoform-api.js:425](autoform-api.js#L425)


-

### <a name="AutoForm.getSchemaForField"></a>*autoform*.getSchemaForField(name, [autoform])&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __getSchemaForField__ is defined in `AutoForm`*

__Arguments__

* __name__ *{String}*  

 The field name attribute / schema key.

* __autoform__ *{Object}*  (Optional)

 The autoform context. Optionally pass this if you've already retrieved it using AutoForm.find as a performance enhancement.


__Returns__  *{Object}*


Call this method from a UI helper to get the field definitions based on the schema used by the closest containing autoForm.
Always throws an error or returns the schema object.

> ```AutoForm.getSchemaForField = function autoFormGetSchemaForField(name, autoform) { ...``` [autoform-api.js:437](autoform-api.js#L437)


-

### <a name="AutoForm.invalidateFormContext"></a>*autoform*.invalidateFormContext(formId)&nbsp;&nbsp;<sub><i>Client</i></sub> ###

*This method __invalidateFormContext__ is defined in `AutoForm`*

__Arguments__

* __formId__ *{String}*  

 The form ID.


__Returns__  *{undefined}*


Call this to force invalidate the form context, such as when you're changing the `doc`
and it does not react by itself.

> ```AutoForm.invalidateFormContext = function autoFormInvalidateFormContext(formId) { ...``` [autoform-api.js:457](autoform-api.js#L457)


