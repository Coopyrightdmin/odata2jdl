# OData to JDL converter

This node module converts an existing OData metadata to JHipster Definition Language format.

## Install

Run `npm install --save odata2jdl`

## Usage

### Converting existing XML string

Use the `parse` and `convert` methods if you have the metadata as XML.

#### JavaScript

```js
const { parse, convert } = require('odata2jdl');

// Get the OData metadata as a string.
const xml = '';

const options = {
  host: 'services.odata.org',
  path: '/V4/Northwind/Northwind.svc'
};

parse(xml)
  .then(entitySets => convert(entitySets, options))
  .then(jdl => console.log(JSON.stringify(jdl, null, 2)))
  .catch(error => console.error(error))
```

#### TypeScript
```TypeScript
import { parse, convert, Options } from 'odata2jdl';

const options: Options = {
  host: 'services.odata.org',
  path: '/V4/Northwind/Northwind.svc'
};

// Get the OData metadata as a string.
const xml = '';

parse(xml)
  .then(entitySets => convert(entitySets, options))
  .then(jdl => console.log(JSON.stringify(jdl, null, 2)))
  .catch(error => console.error(error))
```
