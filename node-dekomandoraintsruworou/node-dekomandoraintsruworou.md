# node でコマンドラインツールを作ろう

package.json に　"bin" :  { "command-name" : "to-path" } を追加することでシェルコマンドとして実行したときに、どのファイルを実行するかを指定する。ここでは "cli" という名前で実行すると、index.js が実行されるように指定した。

{% code-tabs %}
{% code-tabs-item title="package.json" %}
```javascript
{
    "bin": {
        "cli": "index.js"
    },
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

冒頭に \#!/usr/bin/env node をつけることで node で実行されるよう shell に伝える。

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
#! /usr/bin/env node
console.log("cli ok!!");
```
{% endcode-tabs-item %}
{% endcode-tabs %}

