# coverage-diff

## What it does

* Accepts base-summary.json and head-summary.json
* Diffs the two jsons and outputs info about
  * Percentage of changed coverage (in changed/added files)
  * Formatted as markdown table
* Fail if coverage decreases on a file (check on percentage) for any of the lines/func/statements/branches. Can
   be configured to only check some criteria.
* Written in Typescript

## Usage

```js
const fs = require('fs');
const coverageDiff = require('coverage-diff');

const base = JSON.parse(fs.readFileSync('./base-summary.json'));
const head = JSON.parse(fs.readFileSync('./head-summary.json'));
const diff = coverageDiff.diff(base, head);

console.log(diff.diff);
console.log(diff.results);
console.log(diff.regression);
```

Out:

| File   | LinesΔ(%) | FunctionsΔ(%) | Ok  |
| ------ | --------- | ------------- | --- |
| file_1 | 80.2      | 80.2          | ✅  |
| file_2 | -2        | -2            | 🔴  |


API at https://flaviusone.github.io/coverage-diff/globals.html#diff

## Auto-generated docs 

https://flaviusone.github.io/coverage-diff/
