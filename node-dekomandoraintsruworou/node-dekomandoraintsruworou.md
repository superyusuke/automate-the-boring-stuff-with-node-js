# node でコマンドラインツールを作ろう

冒頭に \#!/usr/bin/env node をつけることで node で実行されるようにする

package.json に　"bin" :  { "command-name" : "to-path" } を追加することでシェルコマンドとして実行したときに、どのファイルを実行するかを指定する

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

