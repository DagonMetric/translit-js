# Transliterate Service for JavaScript Applications

[![GitHub Actions Status](https://github.com/DagonMetric/translit-js/workflows/Main%20Workflow/badge.svg)](https://github.com/DagonMetric/translit-js/actions)
[![npm version](https://badge.fury.io/js/%40dagonmetric%2Ftranslit-js.svg)](https://www.npmjs.com/package/@dagonmetric/translit-js)
[![Gitter](https://badges.gitter.im/DagonMetric/general.svg)](https://gitter.im/DagonMetric/general?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)


General purpose transliterate service for JavaScript applications which can be used in swapping letters such as α → a, ၎ → ၎င်း.

## Features

* Can transliterate/convert any script or Unicode letters by using from a simplest rule definition (just with `from` and `to` rules) to more powerful rule definition (with `tplVar`, `tplSeq`, `when`, `postRules`, etc.)
* Can transliterate input phase by phase
* Can define template variables with `tplVar` to reduce JSON size and to avoid repetition
* Can define template loop sequences with `tplSeq` for sequential rules checking and replacement
* Quick test input string checking with `quickTests` and `minLength` options for better performance
* Can check converted left portion string with `hasLeft` boolean option and `left` regular expression option
* Can check right part after matched input string with `right` regular expression option
* Conditional rules processing with `when` and `skip` options
* Can define post-rules with `postRules` for step-by-step conversions
* Can use `postRulesDef` and `postRulesRef`  to reduce JSON size and to avoid repetition in defining `postRules`
* Conversion trace information can be included in output result for debugging purpose

## Getting Started

### Installation

npm

```bash
npm install @dagonmetric/translit-js
```

or yarn

```bash
yarn add  @dagonmetric/translit-js
```

### Usage (app.component.ts)

```typescript
import { TranslitRuleItem, translit } from '@dagonmetric/translit-js';

const zg2uniRules: TranslitRuleItem[] = [
  {
    from: '\u103B([\u1000-\u1021])',
    to: '$1\u103C'
  },
  {
    from: '\u1039',
    to: '\u103A'
  }
];

const result = translit('ျမန္မာစာ', zg2uniRules);

// output: မြန်မာစာ
console.log('output: ', result.outputText);
```

## Transliterate Rules

* [zawgyi-unicode-translit-rules](https://github.com/myanmartools/zawgyi-unicode-translit-rules) - Zawgyi Unicode convert/transliterate rules in JSON and JavaScript formats

## Live Application

* [Zawgyi Unicode Converter](https://zawgyi-unicode-converter.myanmartools.org) - Progress Web Application designed to convert Myanmar font encodings between Zawgyi-One and Standard Myanmar Unicode


## For Other Frameworks

* [ng-translit](https://github.com/DagonMetric/ng-translit) -  Transliterate service for Angular 

## Build & Test Tools

We use [lib-tools](https://github.com/lib-tools/lib-tools) for bundling, testing and packaging our library projects.

[![Lib Tools](https://repository-images.githubusercontent.com/273890506/28038a00-dcea-11ea-8b4a-7d655158ccf2)](https://github.com/lib-tools/lib-tools)

## Feedback and Contributing

Check out the [Contributing](https://github.com/DagonMetric/translit-js/blob/master/CONTRIBUTING.md) page.

## License

This repository is licensed with the [MIT](https://github.com/DagonMetric/translit-js/blob/master/LICENSE) license.
