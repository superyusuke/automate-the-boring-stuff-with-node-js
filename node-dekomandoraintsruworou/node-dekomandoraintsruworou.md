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

#### 公開する

```bash
npm version minor # マイナーチェンジを行なったので
npm publish # 変更を公開
```

### npm package を使う

```bash
npm update @superyusuke/node-learn # 更新を取り込む
```

#### Local にインストールしたパッケージ使う方法2つ

#### npx を使う

```bash
npx cli
```

#### npm script に記述して使う

{% code-tabs %}
{% code-tabs-item title="package.json" %}
```javascript
{
    "scripts": {
        "cli": "cli"
    }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

```bash
npm run cli
```

