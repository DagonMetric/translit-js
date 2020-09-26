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

npm packages are available on:

* [@dagonmetric/translit-js - npm registry](https://www.npmjs.com/package/@dagonmetric/translit-js)
* [@dagonmetric/translit-js - github package registry](https://github.com/DagonMetric/translit-js/packages)
