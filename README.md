# ARIA in HTML to Code Generator

This utility parses the [ARIA in HTML](https://www.w3.org/TR/html-aria/) specification and generates a Javascript Object representing the information in HTML Tage Name table in the specification.  The object created is available as a [JSON object](releases/ariaInHtmlInfo.json) or as a [Javascript include file](releases/ariaInHtmlInfo.js).  Note the generator code has some exception clauses due to the complexity of some of the table rows in the specification.  The exceptions need to be verified for any updates to the speficiation.

## Creating the JSON and JS files

These steps assume you have both `git` and `node.js` installed on your computer.

### Step 1: Checkout the Repository from Github

```git clone git@github.com:opena11y/aria-in-html-to-code.git```

### Step 2: Setup the `node` environment

```npm install```

### Step 3: Generating the JSON and JS files

```node src/generate-aria-in-html.js```

The following two files are created in the `releases` directory:

* [ariaInHtmlInfo.json](releases/ariaInHtmlInfo.json)
* [ariaInHtmlInfo.js](releases/ariaInHtmlInfo.js)

## Organization of the Javascript Object

The primary property in the Javascript Object is the `elementInfo` object.  The `elementInfo` object uses the tag name as the key representing each row in the ARIA in HTML Specfication.  The following table describes the possible properties of each key.

| Property        | Description  |
|-----------------|---|
| `tagName`       | tag name |
| `defaultRole`   | The default [ARIA role](https://www.w3.org/TR/wai-aria/#role_definitions) for the tag  |
| `noRoleAllowed` | True if no other ARIA roles are allowed on the tag, otherwise false  |
| `allowedRoles`  | An array of allowed roles for the tag  |
| `id`            | Unique identifier for the row in the ARIA in HTML table, based on tag name and attributes  |
| `attr1`         | Optional required attribute with an optional value |
| `attr2`         | Optional required attribute with an optional value |



