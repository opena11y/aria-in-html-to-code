# ARIA in HTML to Code Generator Version 1.0 Beta

This utility parses the [ARIA in HTML](https://www.w3.org/TR/html-aria/) specification and generates a Javascript Object representing the information in HTML Tage Name table in the specification.  The object created is available as a [JSON object](releases/ariaInHtmlInfo.json) or as a [Javascript include file](releases/ariaInHtmlInfo.js).  Note the generator code has some exception clauses due to the complexity of some of the table rows in the specification.  The exceptions need to be verified for any updates to the speficiation.

## Creating the JSON and JS files

These steps assume you have both `git` and `node.js` installed on your computer.

### Step 1: Checkout the Repository from Github

```git clone git@github.com:opena11y/aria-in-html-to-code.git```

### Step 2: Setup the `node` environment

```npm install```

### Step 3: Generating the JSON and JS files

```node run build```

The following two files are created in the `releases` directory:

* [gen-aria-in-html-info.json](releases/gen-aria-in-html-info.json)
* [gen-aria-in-html-info.js](releases/gen-aria-in-html-info.js)

## Organization of the Javascript Object

The primary property in the Javascript Object is the `elementInfo` object.  The `elementInfo` object uses the tag name as the key representing each row in the ARIA in HTML Specfication.  The following table describes the possible properties of each key.

| Property        | Description  |
|-----------------|---|
| `tagName`       | tag name |
| `defaultRole`   | The default [ARIA role](https://www.w3.org/TR/wai-aria/#role_definitions) for the tag  |
| `noRoleAllowed` | True if no other ARIA roles are allowed on the tag, otherwise false  |
| `allowedRoles`  | An array of allowed ARIA roles for the tag  |
| `id`            | Unique identifier for the row in the HTML Tag Name table, based on tag name and any required attributes  |
| `attr1`         | Optional required attribute with an optional value |
| `attr2`         | Optional required attribute with an optional value |


## History

* 1.1 Updates generated files to ARIA in HTML version 29 June 2023
