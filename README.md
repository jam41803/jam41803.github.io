# QRScout

A QR Code-based scouting system for FRC

Forked from Team 2713

## config.json

The config.json file is what configures the form fields for QRScout, the page title, the title at the top of your screen, and the line delimiter used in the QRCode.

The config.json can be edited to change most parts of QRScout, and change the line delimiter character used by the QRCode.

The basic structure of the config.json file is as follows:

Root:
$schema: A refrence to the schema used by the config.json file. This shouldn't be changed from the default "../schema.json".
title: The title of the page. This is what appears in the tab bar.
page_title: The title that appears at the top of the QRScout page.
delimiter: The line delimiter used by the QR code
sections: An array of sections/columns that hold and organize form inputs

Induvidual sections:
name: The name of the section/column
preserveDataOnReset: If the data in this section is preserved when the Reset Form button is pressed.
fields: An array of fields, which describe form inputs.

Induvidual fields:
title: The name of this field
type: One of "text", "number", "boolean", "range", "select", "counter", "image" or "timer". Describes the type of input this is.
required: a boolean indicating if this must be filled out before the QRCode is generated. If any field with this set to true is not filled out, QRScout will not generate a QRCode when the commit button is pressed.
code: camelCase string with a unique name indicaing what this field is.
disabled: Boolean indicating if this field is disabled. If it is, things cannot be inputted into it. This and the requied value are mutually exclusive if you want people to be able to submit this form.
preserveDataOnReset: If the data in this field is preserved when the Reset Form button is pressed.
choices: An object containng numbered keys mapping to values that this can hold. For example:

```json
"choices": {
    "1": "First option",
    "2": "Second option"
}
```

defaultValue: The default value of this field.
