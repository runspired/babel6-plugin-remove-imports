# Strip Filtered Imports

This plugin enables you to strip individual import declarations or specifiers
when stripping code paths from a build.

For instance, you may use `babel-plugin-filter-imports` to remove some modules from
a production build. This plugin will additionally filter a list of import declarations
or specifiers that you wish to remove in conjunction with the above plugin.

## API

```js
"use strict";
// ...
const FilterImports = require('babel-plugin-filter-imports');
const StripFilteredImports = require('babel6-plugin-remove-imports');

const filteredImports = {
  'a-module-name': [
    'an-export',
    'another-export'
  ],
  'another-module-name': '*',
  'yet-another/module': true
};

// ...

new Babel('<some-path>', {
  plugins: [ 
    [FilterImports, filteredImports],
    [StripFilteredImports, filteredImports],
  ]
});
```
