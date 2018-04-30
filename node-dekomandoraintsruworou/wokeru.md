---
description: コマンドラインから実行する際に渡した引数を使用する簡易的な方法について説明します。
---

# 引数を受け取る

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
#! /usr/bin/env node
const args = process.argv.slice(2); // process.argv に引数も含まれている
console.log("arg", args[0]); // args は配列なので、その最初の値を使用する
```
{% endcode-tabs-item %}
{% endcode-tabs %}

```bash
npx cli test-arg
```



