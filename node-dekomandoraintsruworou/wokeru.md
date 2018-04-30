# 引数を受け取る

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
#! /usr/bin/env node
const args = process.argv.slice(2); // process.argv に引数
console.log("arg", args[0]);
```
{% endcode-tabs-item %}
{% endcode-tabs %}

